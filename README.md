# Understanding Mirror Bugs in Multiple-Language Projects

---

## Project summary

As software is widely used in daily life, software bugs can introduce catastrophic consequences. To understand the characteristics of bugs, researchers have conducted various empirical studies. These studies analyze many interesting research topics, including their buggy locations, symptoms, causes, and repair patterns.

Many applications have versions in different languages. Although their languages are different, they can implement identical functionalities. If a version has a bug, the other versions can have corresponding bugs. In this paper, we call them cross-language mirror bugs, or mirror bugs for short. Mirror bugs are important since many applications release versions in different languages. Still, all the prior studies analyze bugs in the same language, and only a few studies analyze bugs in similar code snippets. To the best of our knowledge, no study explores cross-language mirror bugs. Many research questions are still open. For example, are there any cross-language mirror bugs in real projects? Are bug fixes in a language useful to detect and repair bugs in other languages?

To answer the above questions, we conduct the first empirical study to explore cross-language mirror bugs. In this study, we manually analyze 638 bugs that are collected from four projects, and all the projects' release versions in both Java and C\#. Our study presents answers to three interesting research questions. For example, we confirm that the bug fixes from a version are useful to repair mirror bugs in other versions. According to our results, there is a timely need for a tool that assists in detecting cross-language mirror bugs. Indeed, we find that some programmers already manually identify and fix mirror bugs, even without any tool support.

---
## Dataset

We collect 638 bug reports from 4 project pairs. For details, see [all_bugs.txt](https://anonymous.4open.science/r/cross-language-DD47/all_bugs.txt) and [open_bug_reports.csv](https://anonymous.4open.science/r/cross-language-DD47/open_bug_reports.csv) for the whole set; [two_sided_bugs.md](https://anonymous.4open.science/r/cross-language-DD47/two_sided_bugs.md) for fixed two-sided bugs.

---

## Our found new cross-language mirror bugs

We successfully learned new bugs from known ones in cross-language implementations as discussed in section 6 in our paper. We reproduced and reported 9 new cross-language bugs, the details are listed in the table below.

| original_bug_report | original_patch | our_bug_report | our_patch | our_patch_status |
| ------- | --------- | ----------- | ------- |  ------- |
| [LUCENE-8755](https://issues.apache.org/jira/browse/LUCENE-8755) | [LUCENE-commit\#26628b2](https://github.com/apache/lucene/commit/26628b2717a73235db56fde94f7f5b64cbc5b8b2) | [LUCENENET#644](https://github.com/apache/lucenenet/issues/644)            |    [LUCENENET-PR\#644](https://github.com/apache/lucenenet/pull/738/files)     | PR rejected |
| [LUCENE-10059](https://issues.apache.org/jira/browse/LUCENE-10059)  | [LUCENE-PR\#254](https://github.com/apache/lucene/pull/254/files)     | [LUCENENET#775](https://github.com/apache/lucenenet/issues/775)    | [LUCENENET-PR\#777](https://github.com/apache/lucenenet/pull/777/files)        |  PR accepted|
| [LUCENE-10008](https://issues.apache.org/jira/browse/LUCENE-10008)  | [LUCENE-PR\#188](https://github.com/apache/lucene/pull/188/files)          | [LUCENENET#780](https://github.com/apache/lucenenet/issues/780)            | [LUCENENET-PR\#781](https://github.com/apache/lucenenet/pull/781/files)      | PR accepted |
| [LUCENE-9940](https://issues.apache.org/jira/browse/LUCENE-9940)    | [LUCENE-PR\#110](https://github.com/apache/lucene/pull/110/files)     | [LUCENENET#779](https://github.com/apache/lucenenet/issues/779)       | [LUCENENET-PR\#783](https://github.com/apache/lucenenet/pull/783/files)        | Open |
| [HHH-14413](https://hibernate.atlassian.net/browse/HHH-14413)       | [HHH-PR\#3699](https://github.com/hibernate/hibernate-orm/pull/3699/files)    |  [NH\#3198](https://github.com/nhibernate/nhibernate-core/issues/3198)           | [NH-PR\#3199](https://github.com/nhibernate/nhibernate-core/pull/3199/files)        | PR accepted |
| [NH\#1419](https://github.com/nhibernate/nhibernate-core/issues/1419)      | [NH-PR\#1420](https://github.com/nhibernate/nhibernate-core/pull/1420/files)     | [HHH-15848](https://hibernate.atlassian.net/browse/HHH-15848)         |  [HHH-PR\#5737](https://github.com/hibernate/hibernate-orm/pull/5737/files)      | Open |
| [NTS\#589](https://github.com/NetTopologySuite/NetTopologySuite/issues/589)      | [NTS-commit\#e94157a](https://github.com/NetTopologySuite/NetTopologySuite/commit/e94157ac19e97fbbdf0808f18bac8ea899288516)          |  [JTS\#939](https://github.com/locationtech/jts/issues/939)       | [JTS-PR\#941](https://github.com/locationtech/jts/pull/941/files)       | Open |
| [NTS\#567](https://github.com/NetTopologySuite/NetTopologySuite/issues/567)      | [NTS-commit\#a9becc0](https://github.com/NetTopologySuite/NetTopologySuite/commit/a9becc07dcad66fc9405d1869364ac8e6ce8650d)          |  [JTS\#919](https://github.com/locationtech/jts/issues/919)           | [JTS-PR\#922](https://github.com/locationtech/jts/pull/922/files)        | PR accepted  |
| [LUCENE-10441](https://issues.apache.org/jira/browse/LUCENE-10441) | https://github.com/apache/lucene/pull/12392/files | [LUCENENET#1003](https://github.com/apache/lucenenet/issues/1003) | [LUCENENET-PR#1003](https://github.com/apache/lucenenet/issues/1003) | PR accepted |
| [LUCENE-8614](https://issues.apache.org/jira/browse/LUCENE-8614) | https://github.com/apache/lucene/pull/12392/files | [LUCENENET#1003](https://github.com/apache/lucenenet/issues/1003) | [LUCENENET-PR#1003](https://github.com/apache/lucenenet/issues/1003) | PR accepted |
