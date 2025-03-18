## Two-sided bugs

We conducted an additional study to explore the challenges of automating the repair process with TBar (Section 6.2). We find that templates can repair 5 out of 9 mirror bugs after the Original Template (C\#)s are manually modified, but templates may be unsuitable to repair the remaining 4 mirror bugs due to only additional patch. The next parameter shows the modification of templates.

### 1. LUCENE-5716 & LUCENE NET\#559

- Original Template (C\#)


```diff
- if(var == CONTAINS)...;
if(var == DISJOINT)...;
+ if(var == CONTAINS)...;
- Relate(ctx.MakePoint((var1, var2))) == CONTAINS
+ CornerContainsNonGeo(var1, var2)
```

- Modified Template (Java)

```diff
- if(var == CONTAINS)...;
if(var == DISJOINT)...;
+ if(var == CONTAINS)...;
- relate(ctx.makePoint((var1, var2))) == CONTAINS
+ cornerContainsNonGeo(var1, var2)
```

### 2. LUCENE-6001 & LUCENE NET-598 

- Original Template (C\#)


```diff
- dims[1].disi.GetCost()
+ drillDownAdvancedCost
```

- Modified Template (Java)

```diff
- dims[1].disi.cost()
+ drillDownAdvancedCost
```

### 3. HHH-13456  & NH\#1244 

- Original Template (C\#)


```diff
- var1 = var2.Save(...);
+ if (var3 is ISession var2)
+   {var1 = var2.Save(...); }
+ else if (var3 is IStatelessSession var2)
+   {var1 = var2.Insert(...); }
+ else { throw new Exception(...); }
```

- Modified Template (Java)

```diff
- var1 = var2.save(...);
+ if (var3 isisntanceof Session)
+   {var1 = (Session)var3.save(...); }
+ else if (var3 isisntanceof StatelessSession)
+   {var1 = (StatelessSession)var3.insert(...); }
+ else { throw new Exception(...); }
```

### 4. HHH-15359  & NH-2011

- Original Template (C\#)


```diff
- ReplaceAssociations(...);
+ object[] var = ReplaceAssociations(...);
+ if (!var.IsAnyType)
+     var.SetPropertyValues(...);
```

- Modified Template (Java)

```diff
- replaceAssociations(...);
+ Object[] var = replaceAssociations(...);
+ if (!var isinstanceof AnyType)
+     var.setPropertyValues(...);
```

### 5. HHH-5210  & NH\#1730  

- Original Template (C\#)


```diff
- var = session.Timestamp;
+ var = session.Factory.Settings.CacheProvider.NextTimestamp();
```

- Modified Template (Java)

```diff
- var = session.getTimestamp();
+ var = session.getFactory().getSettings().getCacheProvider().nextTimestamp();
```

