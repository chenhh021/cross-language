# An Empirical Study on Bugs of Cross-language Implementations

---

## Project summary

As software is widely used in daily life, software bugs can introduce catastrophic consequences. To understand the characteristics of bugs and to motivate future work on bugs, researchers have conducted various empirical studies, and their studies show that many bugs appear in similar code fragments. Although this finding motivates many interesting research topics,  all the prior studies are limited to code fragments in a single language. In real development, most mobile applications have both iOS and Android implementations. Furthermore, researchers have detected many similar code fragments across languages. However, to the best of our knowledge, no prior study has been conducted to explore the characteristics of bugs in similar cross-language code fragments, and many related research questions are still open. For example, are there any bugs in similar cross-language code fragments? Are bug fixes useful to repair cross-language bugs?

To answer the above questions, we conduct the first empirical study to explore bugs in cross-language similar code fragments. In this study, we manually analyze 296 bugs that are collected from four projects, and all the projects have implementations in both Java and C\#. Our study presents answers to four interesting research questions. For example, we confirm that the bug fixes in an implementation are useful to repair bugs from implementations in other languages. Our findings and interpretations complement the prior empirical studies on bugs.

---
## Dataset

We collect 296 bug reports from 4 project pairs. For details, see all_bugs.txt, two_sided_bugs.txt and learnt_bugs.txt. all_bugs.txt is for all bugs; two_sided_bugs.txt is for two-sided bugs; learnt_bugs.txt is for new bugs learnt from known ones discussed in RQ4.