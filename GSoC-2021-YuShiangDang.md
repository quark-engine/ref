---
title: GSoC-2021-YuShiangDang
date: 2021-08-17 15:03:55
index_img:
tags:
---

# New Rule Generation Technique & Make Quark Everywhere Among Security Open Source Projects

## Summary

My name is YuShiang Dang. I am a third-year graduate student at [NKUST](https://eng.nkust.edu.tw), Taiwan. This summer, I participated in [Google Summer of Code](https://summerofcode.withgoogle.com/) project for [Honeynet Project](https://www.honeynet.org) to contribute to [Quark-Engine](https://github.com/quark-engine/quark-engine). Two main goals of my project are __1. To boost up rule generation for Quark__ and __2. Make Quark everywhere among open source projects.__

As for my project, I worked on multiple repositories, including [quark-rule-generate](https://github.com/quark-engine/quark-rule-generate), [Jadx](https://github.com/skylot/jadx), [MobSF](https://github.com/MobSF/Mobile-Security-Framework-MobSF) and [APKLab](https://github.com/APKLab/APKLab).

The following section is the summary of <span style="color:#FF3377">__7__</span> important works I've done and its impacts:

### __1\. First Goal - Implement a new rule generate technique for quark-rule-generate__

-- <span style="color:#FF3377">_Work:_</span> The new rule generate technique is implemented.  
-- <span style="color:#FF3377">_Impact:_</span> And is proved to be helpful finding important rules within a relatively short time.  
-- <span style="color:#FF3377">_Related PR:_</span> __[PR: #2](https://github.com/quark-engine/quark-rule-generate/pull/2)__  
-- <span style="color:#FF3377">_Details:_</span> [Go to details on this page](#1-Implement-a-new-rule-generate-technique-for-quark-rule-generate).  

### __2\. First Goal - Solve CPU idle problem for quark-rule-generate__

-- <span style="color:#FF3377">_Work:_</span> A solution is proposed and is implmented for the CPU idle problem.  
-- <span style="color:#FF3377">_Impact:_</span> The work has made huge improvement of the performace.  
-- <span style="color:#FF3377">_Related PR:_</span> __[PR: #3](https://github.com/quark-engine/quark-rule-generate/pull/3)__  
-- <span style="color:#FF3377">_Details:_</span> [Go to details on this page](#2-Solve-CPU-idle-problem-for-quark-rule-generate).  

### __3\. Second Goal - Improve the UX for using Quark in Jadx__

-- <span style="color:#FF3377">_Work #1:_</span> Implemented Error Dialog.  
-- <span style="color:#FF3377">_Work #2:_</span> Implemented Quark auto installation for Jadx.  
-- <span style="color:#FF3377">_Impact:_</span> Improve the user experience for using Quark in Jadx.  
-- <span style="color:#FF3377">_Related PRs:_</span> __[PR: #1203](https://github.com/skylot/jadx/pull/1203)__,  __[PR: #1202](https://github.com/skylot/jadx/pull/1202)__, __[PR: #1199](https://github.com/skylot/jadx/pull/1199)__  
-- <span style="color:#FF3377">_Details:_</span> [Go to details on this page](#3-Improve-the-UX-for-using-Quark-in-Jadx).  

### __4\. Second Goal - Provide more details of Quark’s summary report in Jadx__

-- <span style="color:#FF3377">_Work:_</span> We plan to provide more details so as to help users quickly locate malicious behaviors in the binary. However, during the GSoC, the founder of Jadx, [Skylot](https://github.com/skylot) unexpectedly helped us implement this feature.  
-- <span style="color:#FF3377">_Impact:_</span> With this added information, users can have an overview. Then they know where to start and can dive into the source codes.  
    -- <span style="color:#FF3377">_Related Commit:_</span> __[Commit: #b5720b](https://github.com/skylot/jadx/commit/b5720bd14e9e9673a60f9aa8e8b1390efef39288)__  
-- <span style="color:#FF3377">_Details:_</span> [Go to details on this page](#4-Provide-more-details-of-Quarks-summary-report-in-Jadx).  

### __5\. Second Goal - Integrate Quark to MobSF__

-- <span style="color:#FF3377">_Work:_</span> An implementation of integration to MobSF was done and was merged.  
-- <span style="color:#FF3377">_Impact:_</span> This can definitly help Quark to grow huge number of users since MobSF is a well-known project in mobile security.  
    -- <span style="color:#FF3377">_Related PR:_</span> __[PR: #135](https://github.com/APKLab/APKLab/pull/135)__  
-- <span style="color:#FF3377">_Details:_</span> [Go to details on this page](#5-Integrate-Quark-to-MobSF).  

### __6\. Second Goal - Implement behavior map of Quark to APKLab__

-- <span style="color:#FF3377">_Work:_</span> This feature is implemented and is submitted to APKLab. However, this PR is awaiting to be solved since we encountered some CI issues.  
-- <span style="color:#FF3377">_Impact:_</span> This feature allows APKLab users to have a deeper insight of function/method calls in the suspicious binary.  
-- <span style="color:#FF3377">_Related PR:_</span> __[PR: #135](https://github.com/APKLab/APKLab/pull/135)__  
-- <span style="color:#FF3377">_Details:_</span> [Go to details on this page](#6-Implement-behavior-map-of-Quark-to-APKLab).  

### __7\. Second Goal - Improve UI/UX of Quark integration in APKLab__

-- <span style="color:#FF3377">_Work:_</span> Three issues were opened for improving Quark UI/UX in APKLab, more discussion are going with the founder of APKLab, [Surendrajat](https://github.com/Surendrajat).  
-- <span style="color:#FF3377">_Impact:_</span> These issues help to improve the readability of Quark reports and performance of Quark in APKLab.  
-- <span style="color:#FF3377">_Related Issue:_</span> __[Issue: #142](https://github.com/APKLab/APKLab/issues/142)__, __[Issue: #141](https://github.com/APKLab/APKLab/issues/141)__, __[Issue: #140](https://github.com/APKLab/APKLab/issues/140)__  
-- <span style="color:#FF3377">_Details:_</span> [Go to details on this page](#7-Improve-UIUX-of-Quark-integration-in-APKLab).  

## Details

### 1. Implement a new rule generate technique for quark-rule-generate

<span style="color:#157040">___1.1. Drawbacks of the old technique___</span>

As described in [here](https://quark-engine.readthedocs.io/en/latest/addRules.html), we need two native APIs to construct one detection rule. The old technique simply finds all possible combinations of native APIs in the target apk. For example, if the target apk has N native APIs, then the old technique would generate N x N rules and verify all of them. This is time and disk volume consuming. And the worst of all, we found out that most of the rules are useless.

<span style="color:#157040">___1.2. The new technique___</span>

The main goal of the new technique is to find valuable detection rules within relatively short time. Hence, we first calculate the number of API call for each API. Then, we sort the numbers. Then we define P (primary) as the set of 20% least used APIs and S (secondary) as the set of 80% most used APIs. In other words, the total number of API (N) is the sum of P and S.

The reason why we choose 20% least used APIs as primary APIs is because we find API such as toSting() is being called everywhere. And toString() is not a helpful API for malware researchers. Why 20%? The answer is simple, we believe in 20-80 rule and we'd like to give it try.

So, despite of the N x N combination. We now have four sets to choose. See Table 1.1. for our inferences on rule value and computational cost of each set. Apparently, set (P x P) is our top priority for hunting high value detection rules.

![](https://i.imgur.com/j9CWeIq.png)

<center>Table 1.1. The comparison of four different sets</center><br/><br/>

<span style="color:#157040">___1.3. Experiment for the new technique:___</span>

To prove our inferences, we choose [Ahmyth RAT](https://github.com/AhMyth/AhMyth-Android-RAT) as our target APK.：

![](https://i.imgur.com/CELHY7r.png)

<center>Figure 1.1. The line chart for the ratio of the number of rules to search times</center><br/><br/>

According to the graph, the Y axis represents (the number of 100% rules / the number of API searches). In other words,Y is the average number of 100% rules per API search. On the other hand, X axis represents the percentage of P.

The result shows perfectly that set PP has the greatest performance among all percentages of P. Set SS, not surprisingly, has the worst performance. Set PS and Set SP have almost the same performances. Last but not least, the result proves that 20-80 rule can be applied perfectly in the rule generating technique.

One drawback in this experiment is that we only use one target APK. Our future goal is to prove that our findings are still applicable in other APKs.

<span style="color:#157040">___Related PR:___</span>

quark-rule-generate [PR#2](https://github.com/quark-engine/quark-rule-generate/pull/2): New rule generate technique

[Go back to summary](#1-First-Goal---Implement-a-new-rule-generate-technique-for-quark-rule-generate)

------

### 2. Solve CPU idle problem for quark-rule-generate

The multiprocess evenly distribute APIs to each process (one CPU core) for analysis. However, some processes are idle when they finish the analysis of distributed APIs. And this is a waste of the CPU resource. Therefore, for maximizing the usage of the CPU, I implemented a feature that continuously checks the CPU status and reallocates the APIs that are yet to be analyzed to all CPU cores when the idle CPU core is found.

<span style="color:#157040">___Related PR:___</span>

quark-rule-generate [PR#3](https://github.com/quark-engine/quark-rule-generate/pull/3): Fix the CPU idle problem

[Go back to summary](#2-First-Goal---Solve-CPU-idle-problem-for-quark-rule-generate)

------

### 3. Improve the UX for using Quark in Jadx

<span style="color:#157040">___3.1. Implemented Quark auto installation for Jadx___</span>

In previous integration, Jadx users need to install quark themselves before using the quark analysis module. Therefore, for better UX, I implemented the auto installation of quark in [PR#1199](https://github.com/skylot/jadx/pull/1199).

<span style="color:#157040">___3.2. Implemented Error Dialog___</span>

In the previuos integration of quark to Jadx, Error/Warning messages show only in the logger. In other words, users won't have a clue when until they check the log message. Therefore, I implemented a feature that pops up the Error or Warning dialog when Quark is not working properly. See Figure 3.1. and Figure 3.2. for the demo.

![](https://i.imgur.com/apIwqVr.png)

<center>Figure 3.1. Error dialog</center><br/><br/>

![](https://i.imgur.com/UfibQJ1.png)

<center>Figure 3.2. Warning dialog</center><br/><br/>

<span style="color:#157040">___3.3. Implement the progress bar___</span>

The time consumed for different analysis varies. And we think users can have better UX if they know the progress of the analysis. Therefore, I implemented a progress bar on the main window of Jadx to remind users the analysis progress. See Figure 3.3. for the demo.

![](https://i.imgur.com/9iKPVQ1.gif)

<center>Figure 3.3. Progress bar for Quark in Jadx</center><br/><br/>

<span style="color:#157040">___Related PRs___</span>

Jadx [PR#1203](https://github.com/skylot/jadx/pull/1203): Change Quark task to background task <br/>
Jadx [PR#1202](https://github.com/skylot/jadx/pull/1202): Add Error/Warning dialogs <br/>
Jadx [PR#1199](https://github.com/skylot/jadx/pull/1199): Improvements of Quark integration

[Go back to summary](#3-Second-Goal---Improve-the-UX-for-using-Quark-in-Jadx)

------

### 4. Provide more details of Quark’s summary report in Jadx

We plan to provide more details so as to help users quickly locate malicious behaviors in the binary. With this added information, users can have an overview. Then they know where to start and can dive into the source codes.

However, during the GSoC, the founder of Jadx, Skylot unexpetedly helped us implement this feature. We appreciate his kindly and unexpected help. :D

See Figure 4.1. and Figure 4.2. for the demo.

![](https://i.imgur.com/t9wcIrd.png)

<center>Figure 4.1. The binary overview</center><br/><br/>

![](https://i.imgur.com/jQwhvrK.gif)

<center>Figure 4.2. Jump to the source code </center><br/><br/>

<span style="color:#157040">___Related Commits___</span>

Jadx [commit b5720b:](https://github.com/skylot/jadx/commit/b5720bd14e9e9673a60f9aa8e8b1390efef39288) fix(gui): improve Quark tasks scheduling and report viewer

[Go back to summary](#4-Second-Goal---Provide-more-details-of-Quarks-summary-report-in-Jadx)

------

### 5. Integrate Quark to MobSF

<span style="color:#157040">___5.1. Add Quark Analysis Report___</span>

An implementation of quark integration to MobSF is done and is merged. See Figure 5.1. for the demo.

![](https://i.imgur.com/icBM873.png)

<center>Figure 5.1. Quark analysis report in MobSF</center><br/><br/>

<span style="color:#157040">___5.2. Dive into the Source Code___</span>

We also implemented a killer feature in MobSF. Users can jump to where the suspicious behavior happens when clicking on the activity shows in Figure 5.1. See Figure 5.2. for the demo.

![](https://i.imgur.com/L83yrws.gif)

<center>Figure 5.2. The demo for source code overview</center><br/><br/>

<span style="color:#157040">___Related PR:___</span>

MobSF [PR#1761](https://github.com/MobSF/Mobile-Security-Framework-MobSF/pull/1761): Add Quark Engine as one of the static analyzers

[Go back to summary](#5-Second-Goal---Integrate-Quark-to-MobSF)

------

### 6. Implement behavior map of Quark to APKLab

<span style="color:#157040">___6.1. Add behavior map to APKlab___</span>

Before we implemented this feature, we fix a permission issue for APKLab. See [PR#135](https://github.com/APKLab/APKLab/pull/135) for more information. The behavior map is implemented. See Figure 6.1. and Figure 6.2. With the behavior map, users can quickly understand the relationship between the suspicious behaviors quark detected. However, this PR is awaiting to be solved since we encountered some CI issues.

![](https://i.imgur.com/U8f48DL.gif)

<center>Figure 6.1. Behavior map in APKLab</center><br/><br/>

![](https://i.imgur.com/r9EwLun.png)

<center>Figure 6.2. Behavior map</center><br/><br/>

<span style="color:#157040">___Related PR:___</span>

APKLab [PR#135](https://github.com/APKLab/APKLab/pull/135): Quark integration improvement

[Go back to summary](#6-Second-Goal---Implement-behavior-map-of-Quark-to-APKLab)

------

### 7. Improve UI/UX of Quark integration in APKLab

<span style="color:#157040">___7.1. [UX] Time Consuming when analyzing large size APKs___</span>

In the previous integration of quark to APKLab, we've found out that it may take a long time when analyzing large size apks. There are several reasons we think might cause this problem. The problem could be the slow performance of Quark. Or the problem could be the slow performance when executing tools that works with Quark simultaneously.

As for the performance of Quark, our team has conducted a performance assessment and improvement proposal in another GSoC project. Therefore, in this project, we choose to make tools work with Quark to be executed asynchronously. So that users can use other features first and no time is wasted. See [issue#140](https://github.com/APKLab/APKLab/issues/140) for my discussion with APKLab.

<span style="color:#157040">___7.2. [UX]More options for the suspicious behavior traversal___</span>

This issue discusses that the Quark report only shows activities with 100% confidence, but we found out that most 80% confidence activities are also valuable.

Therefore, we add a checkbox to filter the percentage of confidence and provide a better UX for the suspicious traversal. See  [issue#141](https://github.com/APKLab/APKLab/issues/141) for my discussion with APKLab.

<span style="color:#157040">___7.3. [UI] Indention of the sub-item in Quark report___</span>

Lack of indention of the sub-item in the Quark report may cause misunderstanding for users. Therefore, we opened an issue to discuss with APKLab. See [issue#142](https://github.com/APKLab/APKLab/issues/142) for more information.

<span style="color:#157040">___Related Issues:___</span>

APKLab [Issue#140](https://github.com/APKLab/APKLab/issues/140) Quark analysis may take a long time <br/>
APKLab [Issue#141](https://github.com/APKLab/APKLab/issues/141) Quark report only shows 100% confidence activities <br/>
APKLab [Issue#142](https://github.com/APKLab/APKLab/issues/142) There are no indent spaces at the sub-item in the Quark report

[Go back to summary](#7-Second-Goal---Improve-UIUX-of-Quark-integration-in-APKLab)

## Acknowledgments

Thank Google, for providing such a great project.<br/>
Thank [Honeynet Project](https://www.honeynet.org) gives me the opportunity.<br/>
Thank my mentor, [KunYu Chen](https://github.com/18z), for all his sincere support and guidance.<br/>
Thank [Jadx](https://github.com/skylot/jadx), [MobSF](https://github.com/MobSF/Mobile-Security-Framework-MobSF), [APKLab](https://github.com/APKLab/APKLab) for helping me reach my goal.<br/>
Thank [TTC](https://www.ttc.org.tw/eng/) for providing me the working environment.<br/>
