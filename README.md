# An Empirical Study on Bugs of Cross-language Implementations

---

## Project summary

As software is widely used in daily life, software bugs can introduce catastrophic consequences. To understand the characteristics of bugs and to motivate future work on bugs, researchers have conducted various empirical studies, and their studies show that many bugs appear in similar code fragments. Although this finding motivates many interesting research topics,  all the prior studies are limited to code fragments in a single language. In real development, most mobile applications have both iOS and Android implementations. Furthermore, researchers have detected many similar code fragments across languages. However, to the best of our knowledge, no prior study has been conducted to explore the characteristics of bugs in similar cross-language code fragments, and many related research questions are still open. For example, are there any bugs in similar cross-language code fragments? Are bug fixes useful to repair cross-language bugs?

To answer the above questions, we conduct the first empirical study to explore bugs in cross-language similar code fragments. In this study, we manually analyze 296 bugs that are collected from four projects, and all the projects have implementations in both Java and C\#. Our study presents answers to four interesting research questions. For example, we confirm that the bug fixes in an implementation are useful to repair bugs from implementations in other languages. Our findings and interpretations complement the prior empirical studies on bugs.

---
## Dataset

We collect 296 bug reports from 4 project pairs. For details, see [all_bugs.txt](https://github.com/chenhh021/cross-language/blob/main/all_bugs.txt) for the whole set; [two_sided_bugs.md](https://github.com/chenhh021/cross-language/blob/main/two_sided_bugs.md) for two-sided bugs.

---

## Our found new cross-language bugs

We successfully learnt new bugs from known ones in cross-language implementations as discussed in section 4.4 in our paper. We reproduced and reported 8 new cross-language bugs, the details are listed in the table below.

| original_bug_report | original_patch | our_bug_report | our_patch | our_patch_status |
| ------- | --------- | ----------- | ------- |  ------- |  
| [LUCENE-8755](https://issues.apache.org/jira/browse/LUCENE-8755) | [LUCENE-commit\#26628b2](https://github.com/apache/lucene/commit/26628b2717a73235db56fde94f7f5b64cbc5b8b2) | [LUCENENET#644](https://github.com/apache/lucenenet/issues/644)            |    [LUCENENET-PR\#644](https://github.com/apache/lucenenet/pull/738/files)     | PR rejected |  
| [LUCENE-10059](https://issues.apache.org/jira/browse/LUCENE-10059)  | [LUCENE-PR\#254](https://github.com/apache/lucene/pull/254/files)     | [LUCENENET#775](https://github.com/apache/lucenenet/issues/775)    | [LUCENENET-PR\#777](https://github.com/apache/lucenenet/pull/777/files)        |  Open|
| [LUCENE-10008](https://issues.apache.org/jira/browse/LUCENE-10008)  | [LUCENE-PR\#188](https://github.com/apache/lucene/pull/188/files)          | [LUCENENET#780](https://github.com/apache/lucenenet/issues/780)            | [LUCENENET-PR\#781](https://github.com/apache/lucenenet/pull/781/files)      | Open | 
| [LUCENE-9940](https://issues.apache.org/jira/browse/LUCENE-9940)    | [LUCENE-PR\#110](https://github.com/apache/lucene/pull/110/files)     | [LUCENENET#779](https://github.com/apache/lucenenet/issues/779)       | [LUCENENET-PR\#783](https://github.com/apache/lucenenet/pull/783/files)        | Open |  
| [HHH-14413](https://hibernate.atlassian.net/browse/HHH-14413)       | [HHH-PR\#3699](https://github.com/hibernate/hibernate-orm/pull/3699/files)    |  [NH\#3198](https://github.com/nhibernate/nhibernate-core/issues/3198)           | [NH-PR\#3199](https://github.com/nhibernate/nhibernate-core/pull/3199/files)        | PR accepted | 
| [NH\#1419](https://github.com/nhibernate/nhibernate-core/issues/1419)      | [NH-PR\#1420](https://github.com/nhibernate/nhibernate-core/pull/1420/files)     | [HHH-15848](https://hibernate.atlassian.net/browse/HHH-15848)         |  [HHH-PR\#5737](https://github.com/hibernate/hibernate-orm/pull/5737/files)      | Open | 
| [NTS\#589](https://github.com/NetTopologySuite/NetTopologySuite/issues/589)      | [NTS-commit\#e94157a](https://github.com/NetTopologySuite/NetTopologySuite/commit/e94157ac19e97fbbdf0808f18bac8ea899288516)          |  [JTS\#939](https://github.com/locationtech/jts/issues/939)       | [JTS-PR\#941](https://github.com/locationtech/jts/pull/941/files)       | Open |  
| [NTS\#567](https://github.com/NetTopologySuite/NetTopologySuite/issues/567)      | [NTS-commit\#a9becc0](https://github.com/NetTopologySuite/NetTopologySuite/commit/a9becc07dcad66fc9405d1869364ac8e6ce8650d)          |  [JTS\#919](https://github.com/locationtech/jts/issues/919)           | [JTS-PR\#922](https://github.com/locationtech/jts/pull/922/files)        | PR accepted  |
