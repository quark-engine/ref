---
title: GSoC-2021-ShengFengLu
date: 2021-08-17 15:12:03
index_img:
tags:
---

# Replace the core library of Quark-Engine

## Summary

My name is Sheng-Feng Lu. I am a fourth-year CS undergraduate student at [NSYSU](https://www.nsysu.edu.tw/), Taiwan. This summer, I participated in a [Google Summer of Code](https://summerofcode.withgoogle.com/) project under the [Honeynet Project](https://www.honeynet.org/) and I contributed to [Quark-Engine](https://github.com/quark-engine/quark-engine), an Android malware storyteller. The two main goals of my project are __1\. To rewrite the core library of Quark with [Rizin](https://github.com/rizinorg/rizin)__ and __2\. Evaluate and improve the performance of Quark Engine__.  

The following section is the summary of <span style="color:#FF3377">__9__</span> important works I've done and their impacts. Also, works like [#3](#3-Implement-an-abstract-class-for-Quark-core-libraries), [#4](#4-Implement-Quarks-new-core-library-with-Rizin), [#5](#5-Implement-more-bytecode-instructions-in-Quarks-Dalvik-bytecode-loader), [#6](#6-Add-feature-Inheritance-class-check), and [#8](#8-Quark-Performance-Improvement) need to be highlighted since they reached huge milestones for Quark Engine.  

### __1\. Add new test cases and improve the existing ones for Quark-Engine__

-- <span style="color:#FF3377">_Work:_</span> __96__ test cases are added and __19__ test cases are improved.  
-- <span style="color:#FF3377">_Impact:_</span> Great tests can protect the correctness of the program so that the original function will not be error-prone when refactoring or modifying.  
-- <span style="color:#FF3377">_Related Issue:_</span> __[Issue #1](https://github.com/quark-engine/gsoc2021-ShengFengLu/issues/1)__  
-- <span style="color:#FF3377">_Related PRs:_</span> __[PR #189](https://github.com/quark-engine/quark-engine/pull/189)__, __[PR #182](https://github.com/quark-engine/quark-engine/pull/182)__  
-- <span style="color:#FF3377">_Details:_</span> [Go to details on this page](#1-Detail-Add-new-test-cases-and-improve-the-existing-ones-for-Quark-Engine).  

### __2\. Implement a more comprehensive call graph (Behavior Map)__

-- <span style="color:#FF3377">_Work #1:_</span> Behavior Map is implemented.  
-- <span style="color:#FF3377">_Work #2:_</span> Rule classification report is enhanced with information such as relationships between behaviors.  
-- <span style="color:#FF3377">_Impact:_</span> By reading the behavior map, users can have an overview of the relationships between suspicious behaviors in the targeted APK file.  
-- <span style="color:#FF3377">_Related Issue:_</span> __[Issue #191](https://github.com/quark-engine/quark-engine/issues/191)__  
-- <span style="color:#FF3377">_Related PR:_</span> __[PR #192](https://github.com/quark-engine/quark-engine/pull/192)__  
-- <span style="color:#FF3377">_Details:_</span> [Go to details on this page](#2-Detail-Implement-a-more-comprehensive-call-graph-Behavior-Map).  

### __3\. Implement an abstract class for Quark core libraries__

-- <span style="color:#FF3377">_Work:_</span> Implement an [abstract class](https://github.com/quark-engine/quark-engine/blob/master/quark/core/interface/baseapkinfo.py) for Quark core libraries such as [apkinfo.py](https://github.com/quark-engine/quark-engine/blob/master/quark/core/apkinfo.py) and [rzapkinfo.py](https://github.com/quark-engine/quark-engine/blob/master/quark/core/rzapkinfo.py).  
-- <span style="color:#FF3377">_Impact:_</span> This helps to define essential methods of the Quark core library and reduces a lot of repetitive work in developing new core libraries.  
-- <span style="color:#FF3377">_Related PRs:_</span> __[PR #194](https://github.com/quark-engine/quark-engine/pull/194)__, __[PR #197](https://github.com/quark-engine/quark-engine/pull/197)__, __[PR #203](https://github.com/quark-engine/quark-engine/pull/203)__  
-- <span style="color:#FF3377">_Details:_</span> [Go to details on this page](#3-Detail-Implement-an-abstract-class-for-Quark-core-libraries).  

### __4\. Implement Quark's new core library with Rizin__

-- <span style="color:#FF3377">_Work:_</span> Implement Quark's new core library ([rzapkinfo.py](https://github.com/quark-engine/quark-engine/blob/master/quark/core/rzapkinfo.py)) with Rizin.  
-- <span style="color:#FF3377">_Impact:_</span> [Androguard](https://github.com/androguard/androguard) is one of the libraries used by Quark to analyze APKs, and it is rarely maintained now. Therefore, we decided to replace Androguard with Rizin. Rizin is a more active binary analysis framework that can help Quark maintain stability.  
-- <span style="color:#FF3377">_Related Issue:_</span> __[Issue #1276](https://github.com/rizinorg/rizin/issues/1276)__  
-- <span style="color:#FF3377">_Related PRs:_</span> __[PR #1303](https://github.com/rizinorg/rizin/pull/1303), [PR #205](https://github.com/quark-engine/quark-engine/pull/205)__, __[PR #209](https://github.com/quark-engine/quark-engine/pull/209)__  
-- <span style="color:#FF3377">_Details:_</span> [Go to details on this page](#4-Detail-Implement-Quarks-new-core-library-with-Rizin).  

### __5\. Implement more bytecode instructions in Quark's Dalvik bytecode loader__

-- <span style="color:#FF3377">_Work:_</span> __227__ bytecode instructions are newly implemented! Only __19__ bytecode instructions were implemented before this project.  
-- <span style="color:#FF3377">_Impact:_</span> More behaviors are detected since we implemented almost all bytecode instructions.  
-- <span style="color:#FF3377">_Related Issue:_</span> __[Issue #131](https://github.com/quark-engine/quark-engine/issues/131)__  
-- <span style="color:#FF3377">_Related PR:_</span> __[PR #207](https://github.com/quark-engine/quark-engine/pull/207)__  
-- <span style="color:#FF3377">_Details:_</span> [Go to details on this page](#5-Detail-Implement-more-bytecode-instructions-in-Quarks-Dalvik-bytecode-loader).  

### __6\. Add feature: Inheritance class check__

-- <span style="color:#FF3377">_Work:_</span> We implement a feature that checks whether a class is inherited from another class.  
-- <span style="color:#FF3377">_Impact:_</span> With this feature, Quark can detect inheritance methods usage.  
-- <span style="color:#FF3377">_Related PR:_</span> __[PR #210](https://github.com/quark-engine/quark-engine/pull/210)__  
-- <span style="color:#FF3377">_Details:_</span> [Go to details on this page](#6-Detail-Add-feature-Inheritance-class-check).  

### __7\. Add feature: API parameters check__

-- <span style="color:#FF3377">_Work:_</span> We have implemented a feature that can support detecting the parameters of the Android API.  
-- <span style="color:#FF3377">_Impact:_</span> With this feature implemented, Quark can now figure out if resources like SMS, call logs, or any other sensitive information is targeted.  
-- <span style="color:#FF3377">_Related PR:_</span> __[PR #212](https://github.com/quark-engine/quark-engine/pull/212)__  
-- <span style="color:#FF3377">_Details:_</span> [Go to details on this page](#7-Detail-Add-feature-API-parameters-check).  

### __8\. Quark Performance Improvement__

-- <span style="color:#FF3377">_Work:_</span> Tools like [Flame Graph](https://www.brendangregg.com/flamegraphs.html), [Austin](https://github.com/P403n1x87/austin), [Yappi](https://github.com/sumerc/yappi), and [Guppy3](https://github.com/zhuyifei1999/guppy3) were used to evaluate to performance of Quark. Two performance bottlenecks were found.  
-- <span style="color:#FF3377">_Impact:_</span> With these two bottlenecks resolved, Rizin Core Library: CPU time saves up to __59.20%__ on average, memory usage saves up to __22.27%__ on average. Androguard Core Library: CPU time saved up to __23.95%__ on average.  
-- <span style="color:#FF3377">_Related PRs:_</span> __[PR #231](https://github.com/quark-engine/quark-engine/pull/231)__, __[PR #232](https://github.com/quark-engine/quark-engine/pull/232)__  
-- <span style="color:#FF3377">_Details:_</span> [Go to details on this page](#8-Detail-Quark-Performance-Improvement).  

### __9\. Implement parallelized analysis__

-- <span style="color:#FF3377">_Work:_</span> We implemented parallelized techniques for Quark analysis.  
-- <span style="color:#FF3377">_Impact:_</span> With this technique, the analysis performed on large APK is improved. The improvement is suitable to apply when users encounter speed issues on Quark.  
-- <span style="color:#FF3377">_Related PRs:_</span> __[PR #231](https://github.com/quark-engine/quark-engine/pull/231)__, __[PR #232](https://github.com/quark-engine/quark-engine/pull/232)__  
-- <span style="color:#FF3377">_Details:_</span> [Go to details on this page](#9-Detail-Implement-parallelized-analysis).  

---  

## Details

### 1\. [Detail] Add new test cases and improve the existing ones for Quark-Engine

To improve existing test cases and develop a new Rizin-based core library in a test-driven development. I added several test cases based on two guidelines __1. Boundary value analysis__ and __2. Equivalence class partitioning__ to improve efficiency and have more comprehensive test cases.

A total of __96__ test cases have been added and __19__ existing test cases have been improved. Quark's overall test coverage is now __79%__ (an increase of __10%__).

<span style="color:#157040">___Relative Issue:___</span>  

Gsoc2021-ShengFengLu [Issue #1](https://github.com/quark-engine/gsoc2021-ShengFengLu/issues/1): Enrich Quark tests  

<span style="color:#157040">___Relative PRs:___</span>  

Quark-Engine [PR #189](https://github.com/quark-engine/quark-engine/pull/189): Refactor/enrich the rest of Quark's tests  
Quark-Engine [PR #182](https://github.com/quark-engine/quark-engine/pull/182): Refactor/enrich the tests of the analysis part of modules  

[Go back to summary](#1-Add-new-test-cases-and-improve-the-existing-ones-for-Quark-Engine)  

---  

### 2\. [Detail] Implement a more comprehensive call graph (Behavior Map)

We are committed to providing users with more insightful information. Therefore, by developing a behavior map, users can have an overview of the relationship between suspicious behaviors of different functions in the target APK. Also, these relationships could be found in the rule classification report. Please see figure 2.1\. and figure 2.2\. for more details.

![](https://i.imgur.com/r9EwLun.png)  

<center>Figure 2.1. Behavior Map</center><br /><br />

![](https://i.imgur.com/rClsdbS.png)

<center>Figure 2.2. Rule classification report </center><br /><br />

<span style="color:#157040">___Relative Issue:___</span>  

Quark-Engine [Issue #191](https://github.com/quark-engine/quark-engine/issues/191): Show Parent Functions' Cross-References in Rule Classification  

<span style="color:#157040">___Relative PR:___</span>  

Quark-Engine [PR #192](https://github.com/quark-engine/quark-engine/pull/192): Show Parent Functions' Cross-References In Rule Classification  

[Go back to summary](#2-Implement-a-more-comprehensive-call-graph-Behavior-Map)  

---  

### 3\. [Detail] Implement an abstract class for Quark core libraries

To have the Rizin based core library co-exist with the Androguard based core library and to ensure the resilience of Quark, I implemented an abstract class for Quark core libraries. Figure 3.1\. is a glance at the source code of the abstract class. Please go [here](https://github.com/quark-engine/quark-engine/blob/master/quark/core/interface/baseapkinfo.py) for the complete source code. 

![](https://i.imgur.com/OpM0Fmc.png)  

<center>Figure 3.1. Source code of The abstract class</center><br /><br />

<span style="color:#157040">___Relative PRs:___</span>  

Quark-Engine [PR #194](https://github.com/quark-engine/quark-engine/pull/194): Add A Standard Interface for Accessing APK Information  
Quark-Engine [PR #197](https://github.com/quark-engine/quark-engine/pull/197): Clean Up the Direct Use of MethodAnalysis  
Quark-Engine [PR #203](https://github.com/quark-engine/quark-engine/pull/203): Make Apkinfo implement the standard APK interface  

[Go back to summary](#3-Implement-an-abstract-class-for-Quark-core-libraries)  

---  

### 4\. [Detail] Implement Quark’s new core library with Rizin

Currently, many features in Quark-Engine  rely on [Androguard](https://github.com/androguard/androguard) for analysis. However, Androguard remained inactive in the past two years. Therefore, to keep Quark's resilience, we choose [Rizin](https://github.com/rizinorg/rizin), a more active reverse engineering framework open source project, as Quark's new core library.

During development, two issues were encountered while implementing the Rizin core library. __1\. The result of Xref is incorrect in some cases__ __2\. It doesn't support multiple dex file analysis.__

We reported these two issues to the Rizin community. For the [Xref issue](https://github.com/rizinorg/rizin/issues/1276), the community proved that it is the bug of Rizin itself and they put this issue to be resolved. As for the multi-dex analysis issue, the community now has [this problem fixed](https://github.com/rizinorg/rizin/pull/1303).  

Here is a [video](https://i.imgur.com/Uc2dJPx.mp4) demonstrating a Quark analysis of the Rizin-based library.  

<span style="color:#157040">___Relative Issue:___</span>  

Rizin [Issue #1276](https://github.com/rizinorg/rizin/issues/1276): Missing method references in DEX  

<span style="color:#157040">___Relative PRs:___</span>  

Rizin [PR #1303](https://github.com/rizinorg/rizin/pull/1303): Load all dalvik files in an APK  
Quark-Engine [PR #205](https://github.com/quark-engine/quark-engine/pull/205): Add a Rizin-based core library  
Quark-Engine [PR #209](https://github.com/quark-engine/quark-engine/pull/209): Update travis.yml to set up Rizin  

[Go back to summary](#4-Implement-Quarks-new-core-library-with-Rizin)  

---  

### 5\. [Detail] Implement more bytecode instructions in Quark’s Dalvik bytecode loader

In the previous version of Quark, the Dalvik bytecode loader supported only two types of bytecodes. The lack of bytecodes may cause false positives in tainted analysis.

Therefore, one of my goals is to improve accuracy by adding the missing __227__ bytecodes to the loader. All added bytecodes are related to the data flow between the registers. Now the Dalvik bytecode loader supports bytecode types such as array/exception accessing, function calls, and arithmetic operations.

And surprisingly, this had improved the analysis accuracy. We use [14d9f1a92dd984d6040cc41ed06e273e.apk](https://github.com/quark-engine/apk-malware-samples/blob/master/14d9f1a92dd984d6040cc41ed06e273e.apk) to test this implementation. Experiment results show the confidence of detected behavior increased __20%__. See Figure 5.1\. and Figure 5.2\. for more details.  

![](https://i.imgur.com/OVSPS1A.png)

<center>Figure 5.1. 19 bytecode instructions implemented</center><br /><br />

![](https://i.imgur.com/PZUMOn1.png)

<center>Figure 5.2. 227 bytecode instructions implemented</center><br /><br />

<span style="color:#157040">___Relative Issue:___</span>  

Quark-Engine [Issue #131](https://github.com/quark-engine/quark-engine/issues/131): Improve Quark's tainted analysis accuracy in stage 5  

<span style="color:#157040">___Relative PR:___</span>  

Quark-Engine [PR #207](https://github.com/quark-engine/quark-engine/pull/207): Improve the tainted analysis of Quark  

[Go back to summary](#5-Implement-more-bytecode-instructions-in-Quarks-Dalvik-bytecode-loader)  

---  

### 6\. [Detail] Add feature: Inheritance class check

Class inheritance checking is not supported by the previous versions of Quark. However, it is quite essential when detecting Android API usage.

Therefore, I implemented a patch to deal with this problem. Three things were implemented in this [patch](https://github.com/quark-engine/quark-engine/pull/210):  

1\. Track the data type of each register in the bytecode loader.  
2\. Construct a class inheritance relation dictionary in [pyeval.py](https://github.com/quark-engine/quark-engine/blob/master/quark/evaluator/pyeval.py).  
3\. Add a lookup procedure to check the inheritance relationship to the loader.  

And surprisingly, this had improved the analysis accuracy. We use [14d9f1a92dd984d6040cc41ed06e273e.apk](https://github.com/quark-engine/apk-malware-samples/blob/master/14d9f1a92dd984d6040cc41ed06e273e.apk) to test this implementation. Experiment results show the confidence of detected behavior increased __20%__. See Figure 6.1\. and Figure 6.2\. for more details.  

![](https://i.imgur.com/zLvKhWR.png)

<center>Figure 6.1. No inheritance class check </center><br /><br />

![](https://i.imgur.com/jMOAImJ.png)  

<center>Figure 6.2. With inheritance class check</center><br /><br />

<span style="color:#157040">___Relative PR:___</span>  

Quark-Engine [PR #210](https://github.com/quark-engine/quark-engine/pull/210): Enhance the Simulation Accuracy of the Bytecode Loader  

[Go back to summary](#6-Add-feature-Inheritance-class-check)  

---  

### 7\. [Detail] Add feature: API parameters check

Many Android APIs represent different behaviors based on parameters. However, in the previous versions of Quark, it could not check Android API parameters, which always need manual checks when analyzing malware.

Therefore, by implementing this feature, Quark can now determine whether the malware gathers personal information such as SMS, call logs, or any other sensitive information.

This implementation lets users fill in keywords like targeted resources (SMS, Calllog) in the detection rule.

And surprisingly, this had improved the analysis accuracy. We use [14d9f1a92dd984d6040cc41ed06e273e.apk](https://github.com/quark-engine/apk-malware-samples/blob/master/14d9f1a92dd984d6040cc41ed06e273e.apk) to test this implementation. Experiment results show that the API parameters check with the new rule. See Figure 7.1\. and Figure 7.2\. for more details.  

![](https://i.imgur.com/a4kkmph.png)

<center>Figure 7.1. New detection rule</center><br /><br />

![](https://i.imgur.com/o7XgtTg.png)

<center>Figure 7.2. Summary report With API parameters check</center><br /><br />

<span style="color:#157040">___Relative PR:___</span>  

Quark-Engine [PR #212](https://github.com/quark-engine/quark-engine/pull/212): Add an Optional Parameter Filter For JSON Rules  

[Go back to summary](#7-Add-feature-API-parameters-check)  

---  

### 8\. [Detail] Quark Performance Improvement

According to user feedback, Quark encounters performance problems when analyzing large-size APKs. Therefore, we choose several performance evaluation tools such as Flame Graph, Austin, Yappi, and Guppy3 to find performance problems and solve them.

Our evaluation is quite simple, we take __CPU time__ and __memory usage__ as the indicators to evaluate the performance of Quark's __two core libraries__ (apkinfo.py, rzapkinfo.py). __3__ sample APKs were chosen based on different file sizes to conduct the evaluation.

<span style="color:#157040">___8.1\. Core Library based on Androguard___</span>  

__CPU time - Androguard based core library__  

In this section, we use 3 sample APKs sizes ranged from 1MB, 4MB, and 10MB to evaluate the CPU time of the Androguard based core library. All 3 APKs are from the database of the University of Luxembourg, [AndroZoo](https://androzoo.uni.lu/), and flagged as malware by [VirusTotal](https://www.virustotal.com/). We use Flame Graph to generate 3 figures below. All figures point to one problem, that is, ==find_method()== in [apkinfo.py](https://github.com/quark-engine/quark-engine/blob/master/quark/core/apkinfo.py) occupied most of the CPU times. See Figure 8.1., Figure 8.2\. and Figure 8.3\. for more details.  

![](https://i.imgur.com/Ju4v6nK.png)

<center>Figure 8.1. CPU Time: APK size 1 MB</center><br /><br />

![](https://i.imgur.com/NUhyFZG.png)

<center>Figure 8.2. CPU Time: APK size 5.3 MB</center><br /><br />

![](https://i.imgur.com/dWafXc0.png)

<center>Figure 8.3. CPU Time: APK size 10 MB</center><br /><br />

__Memory Usage - Androguard based core library__  

In this section, the same sample APKs were used to evaluate the memory usage of the Androguard based core library. We use Flame Graph to generate 3 figures below. All figures point to one problem: most of the memory was consumed when parsing APKs with Androguard. See Figure 8.4., Figure 8.5\. and Figure 8.6\. for more details. 

![](https://i.imgur.com/1mfQB5d.png)

<center>Figure 8.4. Memory Usage: APK size 1 MB</center><br /><br />

![](https://i.imgur.com/hDAycJC.png)

<center>Figure 8.5. Memory Usage: APK size 5.3 MB</center><br /><br />

![](https://i.imgur.com/Iq7Ldp9.png)

<center>Figure 8.6. Memory Usage: APK size 10 MB</center><br /><br />

<span style="color:#157040">___8.2\. Core Library based on Rizin___</span>  

__CPU time - Rizin based core library__  

In this section, the same sample APKs were used to evaluate the CPU time of the Rizin based core library. We use Flame Graph to generate 3 figures below. All figures point to one problem, that is, repeated calculation of unchanging results. And we found out that 3 methods have this problem. They're ==all_methods()==, ==permission()==, and ==class_hierarchy()== in [rzapkinfo.py](https://github.com/quark-engine/quark-engine/blob/master/quark/core/rzapkinfo.py). See Figure 8.7., Figure 8.8\. and Figure 8.9\. for more details.  

![](https://i.imgur.com/koZyNFX.png)

<center>Figure 8.7. CPU Time: APK size 1 MB</center><br /><br />

![](https://i.imgur.com/Ulpl8B6.png)

<center>Figure 8.8. CPU Time: APK size 5.3 MB</center><br /><br />

![](https://i.imgur.com/g6sHi9J.png)

<center>Figure 8.9. CPU Time: APK size 10 MB</center><br /><br />

__Memory Usage - Rizin based core library__  

In this section, the same 3 sample APKs were used to evaluate the memory usage of Rizin based core library. We use Flame Graph to generate 3 figures below. All figures point to one problem, that is, duplicate Rizin processes. And we found out that 1 method has this problem. It is ==permission()== in rzapkinfo.py. Note that ==permission()== is invisible in the last figures since massive objects are created in the third-party method, ==cmdj()==.

![](https://i.imgur.com/K2JPkvD.png)

<center>Figure 8.10. Memory Usage: APK size 1 MB</center><br /><br />

![](https://i.imgur.com/sdDH2zE.png)

<center>Figure 8.11. Memory Usage: APK size 5.3 MB</center><br /><br />

![](https://i.imgur.com/0HDcd6u.png)

<center>Figure 8.12. Memory Usage: APK size 10 MB</center><br /><br />

<span style="color:#157040">___8.3. Solutions to Problems found___</span>  

Androguard based core library  

- CPU Time: We implemented a [patch](https://github.com/quark-engine/quark-engine/pull/232) to [apkinfo.py](https://github.com/quark-engine/quark-engine/blob/master/quark/core/apkinfo.py) to fix this problem.  
- Memory Usage: The solution, for now, is the Rizin core library. We arrange to help Androguard solving it in the future.

Rizin based core library  

- CPU Time: We implemented a [patch](https://github.com/quark-engine/quark-engine/pull/231) to [rzapkinfo.py](https://github.com/quark-engine/quark-engine/blob/master/quark/core/rzapkinfo.py) to this problem.  
- Memory Usage: This problem is solved by the same [patch](https://github.com/quark-engine/quark-engine/pull/231) we submitted. 

<span style="color:#157040">___8.4. Performance Re-assessments___</span>  

__Androguard based core library__  
After implemented the [patch](https://github.com/quark-engine/quark-engine/pull/232), the CPU time saved up to __23.95%__ on average.  

| MD5                              | Size<br>(MB) | Before The Improvement<br/> (second) | After The Improvement<br>(second) | Percentage increase<br>(%) |
|:-------------------------------- | ------------:| ------------------------------------:| ---------------------------------:| --------------------------:|
| 9283c74dd8356c18bb6d94b88b8fdd9b | 1            | 2.00                                 | 1.58                              | 26%                        |
| 8e241d9a7a7cf8bf606b15a9f43af5fd | 5.3          | 3.47                                 | 2.91                              | 16.13%                     |
| 3edfc78ab53521942798ad551027d04f | 10           | 60.53                                | 42.53                             | 29.73%                     |

<center>Table 8.1. CPU Time on all APKs</center><br /><br />

__Rizin based core library__  
After implemented the [patch](https://github.com/quark-engine/quark-engine/pull/231), the CPU time saved up to __59.20%__ on average.  

| MD5                              | Size<br>(MB) | Before The Improvement<br/> (second) | After The Improvement<br>(second) | Percentage <br>(%) |
|:-------------------------------- | ------------:| ------------------------------------:| ---------------------------------:| ------------------:|
| 9283c74dd8356c18bb6d94b88b8fdd9b | 1            | 5.56                                 | 1.24                              | 77.70%             |
| 8e241d9a7a7cf8bf606b15a9f43af5fd | 5.3          | 21.47                                | 12.60                             | 41.31%             |
| 3edfc78ab53521942798ad551027d04f | 10           | 1118.00                              | 462.90                            | 58.60%             |

<center>Table 8.2. CPU Time on all APKs</center><br /><br />

After implemented the [patch](https://github.com/quark-engine/quark-engine/pull/231), the memory usage saved up to __22.27%__ on average.  

| MD5                              | Size (MB) | Before The Improvement  (MB) | After The Improvement (MB) | Percentage  (%) |
| -------------------------------- | ---------:| ----------------------------:| --------------------------:| ---------------:|
| 9283c74dd8356c18bb6d94b88b8fdd9b | 1         | 285.00                       | 211.76                     | 25.70%          |
| 8e241d9a7a7cf8bf606b15a9f43af5fd | 5.3       | 278.19                       | 235.63                     | 15.30%          |
| 3edfc78ab53521942798ad551027d04f | 10        | 1116.40                      | 828.11                     | 25.82%          |

<center>Table 8.3. Memory Usage on all APKs</center><br /><br />

<span style="color:#157040">___Relative PRs:___</span>  

Quark-Engine [PR #231](https://github.com/quark-engine/quark-engine/pull/231): Cache commonly used attributes in the Rizin core library  
Quark-Engine [PR #232](https://github.com/quark-engine/quark-engine/pull/232): Simplify the generator value check in the Androguard core library

[Go back to summary](#8-Quark-Performance-Improvement)  

### 9\. [Detail] Implement parallelized analysis

__Androguard based core library__  

The improvement is significant on large APKs. However, the cost of process initialization makes it not obvious when analyzing small ones. I conclude that the improvement is suitable to apply when users encounter speed issues on Quark. See Table 9.1\. for more details.  

| MD5                              | Size<br>(MB) | Before The Improvement<br/> (Second) | After The Improvement<br>(Second) | Percentage <br>(%) |
| -------------------------------- | ------------:| ------------------------------------:| ---------------------------------:| ------------------:|
| 9283c74dd8356c18bb6d94b88b8fdd9b | 1            | 2.90                                 | 2.04                              | 29.65%             |
| 8e241d9a7a7cf8bf606b15a9f43af5fd | 5.3          | 3.04                                 | 4.10                              | -34.87%            |
| 3edfc78ab53521942798ad551027d04f | 10           | 69.32                                | 42.30                             | 38.98%             |

<center>Table 9.1. Androguard analysis time on all apks</center><br /><br />

__Rizin based core library__  

The improvement is significant on large APKs. However, the cost of process initialization makes it not obvious when analyzing small ones. I conclude that the improvement is suitable to apply when users encounter speed issues on Quark. See Table 9.2\. for more details.  

| MD5                              | Size (MB) | Before The Improvement  (Second) | After The Improvement (Second) | Percentage  (%) |
| -------------------------------- | ---------:| --------------------------------:| ------------------------------:| ---------------:|
| 9283c74dd8356c18bb6d94b88b8fdd9b | 1         | 1.24                             | 1.70                           | -37.09%         |
| 8e241d9a7a7cf8bf606b15a9f43af5fd | 5.3       | 21.47                            | 12.60                          | 41.31%          |
| 3edfc78ab53521942798ad551027d04f | 10        | 462.90                           | 36.93                          | 92.02%          |

<center>Table 9.2. Rizin analysis time on all apks</center><br /><br />

<span style="color:#157040">___Relative PRs:___</span>  

Quark-Engine [PR #223](https://github.com/quark-engine/quark-engine/pull/223):  Parallelize the analysis

[Go back to summary](#9-Implement-parallelized-analysis)

---

## What's Next

1. Keep assisting the Rizin community with the [Xref issue](https://github.com/rizinorg/rizin/issues/1276) in APKs.
2. Address the Androguard memory problem we found and help Androguard to solve it.
3. Continuously improve the Rizin core library to make its performance better than the Androguard core library. 

## Thanks

Thank my mentors, [JunWei Song](https://github.com/krnick) and [KunYu Chen](https://github.com/18z), for their sincere support and guidance.  
Thank [Androguard](https://github.com/androguard/androguard) and [Rizin](https://github.com/rizinorg/rizin) for helping me reach my goal.  
Thank [TTC](https://www.ttc.org.tw/Eng/) for providing me the working environment.  
Thank [Honeynet Project](https://www.honeynet.org/) for this great opportunity.  
Thank Google for making all this happend!  
