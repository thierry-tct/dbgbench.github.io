## Summary
How do professional software engineers debug computer programs? In an experiment with 27 real bugs that existed in several widely used programs, we invited 12 professional software engineers, who together spent one month on localizing, explaining, and fixing these bugs. This did not only allow us to study the various tools and strategies used to debug the same set of errors. We could also determine exactly which statements a developer would localize as faults, how a developer would diagnose and explain an error, and how a developer would fix an error – all of which software engineering researchers seek to automate. Until now, it has been difficult to evaluate the effectiveness and utility of automated debugging techniques without a user study. We publish the collected data, called DBGBENCH, to facilitate the effective evaluation of automated fault localization, diagnosis, and repair techniques w.r.t. the judgement of human experts.

<p style="position:fixed; left: 50%; top: 200px; transform: translate(-545px, 0%); width: 200px; padding: 0px">
<a href="#setup">Downloads</a><br/>
<a href="#find">DBGBench (find)</a><br/>
<a href="#grep">DBGBench (grep)</a><br/>
<a href="#use">Use DBGBench</a><br/>
<a href="#cite">Cite DBGBench</a><br/>
<a href="abstract.pdf"><img src="abstract.png" alt="DBGBench Abstract" style="width: 200px;"/></a></p>

<p align="center"><img src="mainobjective.png" alt="Main Objectives" width="100%" /></p>
<br/>

## FAQ
* <a href="#use">How can I evaluate my **automated fault localization** technique?</a>
* <a href="#use">How can I evaluate my **automated bug diagnosis** technique?</a>
* <a href="#use">How can I evaluate my **automated repair** technique?</a>
* <a href="#setup">Where do I get **more test cases** for DBGBench?</a>
* <a href="#use">What **distinguishes** DBGBench from other error benchmarks?</a>
* <a href="#cite">How do I **cite** DBGBench?</a>

## DBGBench
In the following we provide the complete list of errors and their average debugging time, difficulty, and patch correctness, with human-generated explanations of the runtime actions leading to the error, and examples of correct and incorrect fixes, sorted according to average debugging time. For each error, we also provide the commit introducing the error, the simplified and original bug report, the fault locations, and the submitted and original patches.

### <a name="setup"></a>Setup and Infrastructure
* Download the <a href="benchmark.pdf" target="_blank">benchmark summary</a> containing the complete list of errors, their average debugging time, difficulty, and patch correctness, human-generated explanations of the runtime actions leading to the error, and examples of correct and incorrect fixes, sorted according to average debugging time.
* Download the <a href="https://docs.google.com/spreadsheets/d/12dYERCbuVCX6Ks4QgAF-XEEsLIxD9zsm2XAHE1bhyK0/edit?usp=sharing" target="_blank">complete data</a> containing for each debugging session (error, participant) the following data:
  * BUG ID & Participant ID
  * Provided Fault Locations, Bug diagnosis/Explanations & Patches
  * Patch Plausibility, Correctness and Category
  * Reasons for (In)correctness
  * Simplified Bug Report
* Download the <a href="questionnaire.pdf" target="_blank">example questionnaire</a>.
* Download the <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/docker" target="_blank">Docker virtual infrastructure</a>.
* Download the <a href="https://drive.google.com/open?id=0Bx6dkN27OssKVWJYZGdXcWdWQ0U" target="_blank">tutorial material</a>, including slides, videos, and readme files.
* Download <a href="https://github.com/thierry-tct/Tests_CPA_ICSE" target="_blank">more test cases</a> for DBGBench.<br/>(Credits to <a href="https://sites.google.com/site/mikepapadakis/ICSE17.pdf?attredirects=0&d=1" target="_blank">Titcheu Chekam Thierry, Mike Papadakis, Yves Le Traon, and Mark Harman</a>)!
* Read out [full paper](notlinked) (**@ESEC/FSE'17**) to find out more about DBGBENCH.
* Read our extended <a href="abstract.pdf" target="_blank">abstract</a> or <a href="poster.pdf" target="_blank">poster</a> (**@ICSE'17**) to find out more about DBGBENCH.


### <a name="find"></a>GNU Findutils
GNU [findutils](https://www.gnu.org/software/findutils/) offers basic file searching utilities to search the systems directories of GNU and Unix-based computers. 

| Descriptive Statistics &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Benchmark Details  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
| -- | -- |
| **<a href="benchmark.pdf" target="_blank">[find.24e2271e]</a>**<br/>*Error Type*: Functional Bug<br/>*Avg. Debugging Time*: 13.8 min<br/>*Explanation*: Slightly difficult<br/>*Patching*: Slightly difficult<br/>*Patch Correctness*: 75% | *Regression*: <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=f0759ab8db9cab16699fba45fa6117ef06620194" target="_blank">Developer</a><br/>*Bug Report*: <a href="find.24e2271e.report.txt" target="_blank">Simple</a>, [Original](http://savannah.gnu.org/bugs/?18222)<br/>*Fault Locations*: <a href="find.24e2271e.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="find.24e2271e.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/find.24e2271e/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=24e2271ec05c9b5a5517a76d3756af417a637e95" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[find.dbcb10e9]</a>**<br/>*Error Type*: Crash<br/>*Avg. Debugging Time*: 22.9 min<br/>*Explanation*: Slightly difficult<br/>*Patching*: Slightly difficult<br/>*Patch Correctness*: 81%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=daf7f100ed3cc056b6cfad04435f8ae879587f67" target="_blank">Developer</a><br/>*Bug Report*: <a href="find.dbcb10e9.report.txt" target="_blank">Simple</a>, [Original](http://savannah.gnu.org/bugs/?20139)<br/>*Fault Locations*: <a href="find.dbcb10e9.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="find.dbcb10e9.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/find.dbcb10e9/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=dbcb10e9f939a649a7ba99a1fec39eb01e40fde2" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[find.07b941b1]</a>**<br/>*Error Type*: Crash<br/>*Avg. Debugging Time*: 23.7 min<br/>*Explanation*: Slightly difficult<br/>*Patching*: Slightly difficult<br/>*Patch Correctness*: 80% | *Regression*: <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=84aef0ea1170af8910613c39e98e05505c7c03d0" target="_blank">Developer</a><br/>*Bug Report*: <a href="find.07b941b1.report.txt" target="_blank">Simple</a>, [Original](http://savannah.gnu.org/bugs/?17490)<br/>*Fault Locations*: <a href="find.07b941b1.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="find.07b941b1.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/find.07b941b1/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=07b941b1e71a2212b8fd2d3a32662aa5dbfdfa8b" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[find.c8491c11]</a>**<br/>*Error Type*: Crash<br/>*Avg. Debugging Time*: 31.4 min<br/>*Explanation*: Slightly difficult<br/>*Patching*: Slightly difficult<br/>*Patch Correctness*: 54%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=864b25ed9c1f9f87c036196cb70a7cc21357207b" target="_blank">Developer</a><br/>*Bug Report*: <a href="find.c8491c11.report.txt" target="_blank">Simple</a>, [Original](http://savannah.gnu.org/bugs/?24169)<br/>*Fault Locations*: <a href="find.c8491c11.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="find.c8491c11.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/find.c8491c11/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=c8491c11d581598348f034dc55e51e12ee46159a" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[find.6e4cecb6]</a>**<br/>*Error Type*: Functional Bug<br/>*Avg. Debugging Time*: 38.2 min<br/>*Explanation*: Moderately difficult<br/>*Patching*: Not at all difficult<br/>*Patch Correctness*: 89%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=856533490292139199302c67dc5c22a5debbc7fa" target="_blank">Developer</a><br/>*Bug Report*: <a href="find.6e4cecb6.report.txt" target="_blank">Simple</a>, [Original](http://savannah.gnu.org/bugs/?12181)<br/>*Fault Locations*: <a href="find.6e4cecb6.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="find.6e4cecb6.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/find.6e4cecb6/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=6e4cecb65be5b8978492f11f6e71dfd4ed061726" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[find.091557f6]</a>**<br/>*Error Type*: Crash<br/>*Avg. Debugging Time*: 44.8 min<br/>*Explanation*: Slightly difficult<br/>*Patching*: Slightly difficult<br/>*Patch Correctness*: 54%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=b46b0d89384207be73e32468a064393a43b82514" target="_blank">Developer</a><br/>*Bug Report*: <a href="find.091557f6.report.txt" target="_blank">Simple</a>, [Original](http://savannah.gnu.org/bugs/?19613)<br/>*Fault Locations*: <a href="find.091557f6.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="find.091557f6.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/find.091557f6/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=091557f6185bf667af98f407824f7101f07b712d" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[find.24bf33c0]</a>**<br/>*Error Type*: Crash<br/>*Avg. Debugging Time*: 45.1 min<br/>*Explanation*: Moderately difficult<br/>*Patching*: Slightly difficult<br/>*Patch Correctness*: 50%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=b46b0d89384207be73e32468a064393a43b82514" target="_blank">Developer</a><br/>*Bug Report*: <a href="find.24bf33c0.report.txt" target="_blank">Simple</a>, [Original](http://savannah.gnu.org/bugs/?19605)<br/>*Fault Locations*: <a href="find.24bf33c0.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="find.24bf33c0.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/find.24bf33c0/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=24bf33c0e608253fa4bfc428377a297ba4ab2b43" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[find.183115d0]</a>**<br/>*Error Type*: Resource Leak<br/>*Avg. Debugging Time*: 49.2 min<br/>*Explanation*: Slightly difficult<br/>*Patching*: Slightly difficult<br/>*Patch Correctness*: 83%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=e66802375963941b3b54a0e038d18eccde449e14" target="_blank">Developer</a><br/>*Bug Report*: <a href="find.183115d0.report.txt" target="_blank">Simple</a>, [Original](http://savannah.gnu.org/bugs/?34976)<br/>*Fault Locations*: <a href="find.183115d0.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="find.183115d0.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/find.183115d0/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=183115d0484816336f9c4d2a3198b5eae2ad4b92" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[find.93623752]</a>**<br/>*Error Type*: Functional Bug<br/>*Avg. Debugging Time*: 50.8 min<br/>*Explanation*: Moderately difficult<br/>*Patching*: Slightly difficult<br/>*Patch Correctness*: 92%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=e8bd5a2c245f583f7d1b7b33f01b71ac1a678e98" target="_blank">Developer</a><br/>*Bug Report*: <a href="find.93623752.report.txt" target="_blank">Simple</a>, [Original](http://savannah.gnu.org/bugs/?28824)<br/>*Fault Locations*: <a href="find.93623752.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="find.93623752.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/find.93623752/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=93623752ecd97a2d136ca5467ae918895f88a096" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[find.66c536bb]</a>**<br/>*Error Type*: Functional Bug<br/>*Avg. Debugging Time*: 55.5 min<br/>*Explanation*: Moderately difficult<br/>*Patching*: Slightly difficult<br/>*Patch Correctness*: 92%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=e8bd5a2c245f583f7d1b7b33f01b71ac1a678e98" target="_blank">Developer</a><br/>*Bug Report*: <a href="find.66c536bb.report.txt" target="_blank">Simple</a>, [Original](http://savannah.gnu.org/bugs/?20005)<br/>*Fault Locations*: <a href="find.66c536bb.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="find.66c536bb.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/find.66c536bb/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=66c536bbb7cdb1673fb6f389b18c77165392cdc7" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[find.b445af98]</a>**<br/>*Error Type*: Functional Bug<br/>*Avg. Debugging Time*: 56.5 min<br/>*Explanation*: Moderately difficult<br/>*Patching*: Slightly difficult<br/>*Patch Correctness*: 50%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=f4d8c73d0bc493c07da291e2587192113270d319" target="_blank">Developer</a><br/>*Bug Report*: <a href="find.b445af98.report.txt" target="_blank">Simple</a>, [Original](http://savannah.gnu.org/bugs/?25359)<br/>*Fault Locations*: <a href="find.b445af98.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="find.b445af98.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/find.b445af98/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=b445af98c22cd2d13673e2699a77ab728a7073b0" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[find.ff248a20]</a>**<br/>*Error Type*: Infinite Loop<br/>*Avg. Debugging Time*: 57.7 min<br/>*Explanation*: Moderately difficult<br/>*Patching*: Moderately difficult<br/>*Patch Correctness*: 40%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=2d428f84bd80ecf768446f6d9e717bcc5dc719db" target="_blank">Developer</a><br/>*Bug Report*: <a href="find.ff248a20.report.txt" target="_blank">Simple</a>, [Original](http://savannah.gnu.org/bugs/?13381)<br/>*Fault Locations*: <a href="find.ff248a20.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="find.ff248a20.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/find.ff248a20/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=ff248a20f57753f772abb2b5db25aa151a442ffe" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[find.e6680237]</a>**<br/>*Error Type*: Functional Bug<br/>*Avg. Debugging Time*: 76.4 min<br/>*Explanation*: Moderately difficult<br/>*Patching*: Moderately difficult<br/>*Patch Correctness*: 27%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=7dc70069a3095a42eadb22b24cb9260c243aff8f" target="_blank">Developer</a><br/>*Bug Report*: <a href="find.e6680237.report.txt" target="_blank">Simple</a>, [Original](http://savannah.gnu.org/bugs/?29949)<br/>*Fault Locations*: <a href="find.e6680237.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="find.e6680237.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/find.e6680237/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=e66802375963941b3b54a0e038d18eccde449e14" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[find.e1d0a991]</a>**<br/>*Error Type*: Functional Bug<br/>*Avg. Debugging Time*: 88.2 min<br/>*Explanation*: Very difficult<br/>*Patching*: Very difficult<br/>*Patch Correctness*: 17%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=f0759ab8db9cab16699fba45fa6117ef06620194" target="_blank">Developer</a><br/>*Bug Report*: <a href="find.e1d0a991.report.txt" target="_blank">Simple</a>, [Original](http://savannah.gnu.org/bugs/?27563)<br/>*Fault Locations*: <a href="find.e1d0a991.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="find.e1d0a991.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/find.e1d0a991/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/findutils.git/commit/?id=e1d0a991e96ee164d74579efc027b09336e50c79" target="_blank">Developer</a><br/>*Tests*: Researcher |

### <a name="grep"></a> GNU Grep
GNU [grep](https://www.gnu.org/software/grep/manual/grep.html) is a command-line utility for searching plain-text data sets for lines that match a regular expression.

| Descriptive Statistics &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Benchmark Details  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
| -- | -- |
**<a href="benchmark.pdf" target="_blank">[grep.55cf7b6a]</a>**<br/>*Error Type*: Functional Bug<br/>*Avg. Debugging Time*: 21.1 min<br/>*Explanation*: Slightly difficult<br/>*Patching*: Not at all difficult<br/>*Patch Correctness*: 91%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=75bc6fb14dea81ade7d761448610c2280d17d1d6" target="_blank">Developer</a><br/>*Bug Report*: <a href="grep.55cf7b6a.report.txt" target="_blank">Simple</a>, [Original](http://bugs.debian.org/cgi-bin/bugreport.cgi?bug=669084)<br/>*Fault Locations*: <a href="grep.55cf7b6a.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="grep.55cf7b6a.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/grep.55cf7b6a/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=55cf7b6a1905320c36702a476b09ebb29a2934d3" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[grep.54d55bba]</a>**<br/>*Error Type*: Crash<br/>*Avg. Debugging Time*: 26.7 min<br/>*Explanation*: Slightly difficult<br/>*Patching*: Slightly difficult<br/>*Patch Correctness*: 69%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=401d81946e98f70ed135f57522f58eeeff54cdb2" target="_blank">Developer</a><br/>*Bug Report*: <a href="grep.54d55bba.report.txt" target="_blank">Simple</a>, [Original](http://lists.gnu.org/archive/html/bug-grep/2010-03/msg00477.html)<br/>*Fault Locations*: <a href="grep.54d55bba.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="grep.54d55bba.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/grep.54d55bba/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=54d55bba41f2ff31682fe6523ef6f49b37a0e20f" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[grep.9c45c193]</a>**<br/>*Error Type*: Functional Bug<br/>*Avg. Debugging Time*: 37.7 min<br/>*Explanation*: Moderately difficult<br/>*Patching*: Slightly difficult<br/>*Patch Correctness*: 83%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=c4e8205b988dd2a95a00e188d32f4d6ec1d3f7e7" target="_blank">Developer</a><br/>*Bug Report*: <a href="grep.9c45c193.report.txt" target="_blank">Simple</a>, [Original](http://savannah.gnu.org/bugs/?29876)<br/>*Fault Locations*: <a href="grep.9c45c193.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="grep.9c45c193.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/grep.9c45c193/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=9c45c193825d1f59e1d341e556ecf4adeb7a03a2" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[grep.5fa8c7c9]</a>**<br/>*Error Type*: Infinite Loop<br/>*Avg. Debugging Time*: 38.8 min<br/>*Explanation*: Moderately difficult<br/>Patching: Slightly difficult<br/>*Patch Correctness*: 50%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=6d952beebdac1d8f31ba20abb12a756a9877e50d" target="_blank">Developer</a><br/>*Bug Report*: <a href="grep.5fa8c7c9.report.txt" target="_blank">Simple</a>, [Original](http://lists.gnu.org/archive/html/bug-grep/2010-03/msg00586.html)<br/>*Fault Locations*: <a href="grep.5fa8c7c9.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="grep.5fa8c7c9.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/grep.5fa8c7c9/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=5fa8c7c9775577fda035b741cb1db5f9fe7c5d74" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[grep.db9d6340]</a>**<br/>*Error Type*: Infinite Loop<br/>*Avg. Debugging Time*: 40.6 min<br/>*Explanation*: Slightly difficult<br/>*Patching*: Slightly difficult<br/>*Patch Correctness*: 45%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=deccad69bd9b4689af9fd950c48049cdc1284a81" target="_blank">Developer</a><br/>*Bug Report*: <a href="grep.db9d6340.report.txt" target="_blank">Simple</a>, [Original](http://lists.gnu.org/archive/html/bug-grep/2010-03/msg00579.html)<br/>*Fault Locations*: <a href="grep.db9d6340.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="grep.db9d6340.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/grep.db9d6340/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=db9d6340b42a7774fae526f6a90eea3ce834e2d0" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[grep.2be0c659]</a>**<br/>*Error Type*: Functional Bug<br/>*Avg. Debugging Time*: 47.2 min<br/>*Explanation*: Moderately difficult<br/>*Patching*: Moderately difficult<br/>*Patch Correctness*: 13%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=70e236167c3973fc428d2b5b297218fde9b68e73" target="_blank">Developer</a><br/>*Bug Report*: <a href="grep.2be0c659.report.txt" target="_blank">Simple</a>, [Original](http://lists.gnu.org/archive/html/bug-grep/2012-06/msg00001.html)<br/>*Fault Locations*: <a href="grep.2be0c659.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="grep.2be0c659.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/grep.2be0c659/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=2be0c6591ea5d56ee7fbc364228f24b85f569a5c" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[grep.8f08d8e2]</a>**<br/>*Error Type*: Functional Bug<br/>*Avg. Debugging Time*: 48.4 min<br/>*Explanation*: Moderately difficult<br/>*Patching*: Moderately difficult<br/>*Patch Correctness*: 75%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=8a025cf81cdf5c3e809c3ecf0656419a2d596796" target="_blank">Developer</a><br/>*Bug Report*: <a href="grep.8f08d8e2.report.txt" target="_blank">Simple</a>, [Original](http://lists.gnu.org/archive/html/bug-grep/2010-03/msg00443.html)<br/>*Fault Locations*: <a href="grep.8f08d8e2.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="grep.8f08d8e2.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/grep.8f08d8e2/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=8f08d8e282bf3d4917e94135e67ba17d738313ce" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[grep.58195fab]</a>**<br/>*Error Type*: Functional Bug<br/>*Avg. Debugging Time*: 50.5 min<br/>*Explanation*: Moderately difficult<br/>*Patching*: Slightly difficult<br/>*Patch Correctness*: 82%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=bf3bd92c950d3182d5f2e90ada6cd75de424b7a3" target="_blank">Developer</a><br/>*Bug Report*: <a href="grep.58195fab.report.txt" target="_blank">Simple</a>, [Original](http://lists.gnu.org/archive/html/bug-grep/2012-04/msg00056.html)<br/>*Fault Locations*: <a href="grep.58195fab.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="grep.58195fab.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/grep.58195fab/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=58195fabc7559541b3736400e08e901011acd61f" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[grep.c1cb19fe]</a>**<br/>*Error Type*: Functional Bug<br/>*Avg. Debugging Time*: 58.4 min<br/>*Explanation*: Very difficult<br/>*Patching*: Slightly difficult<br/>*Patch Correctness*: 71%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=0d38a8bba16bdc4aa8d657becd5526575a3f8ca8" target="_blank">Developer</a><br/>*Bug Report*: <a href="grep.c1cb19fe.report.txt" target="_blank">Simple</a>, [Original](http://lists.gnu.org/archive/html/bug-grep/2010-03/msg00449.html)<br/>*Fault Locations*: <a href="grep.c1cb19fe.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="grep.c1cb19fe.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/grep.c1cb19fe/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=c1cb19fe67f4c83f9232087ae03c178905d62b0d" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[grep.7aa698d3]</a>**<br/>*Error Type*: Functional Bug<br/>*Avg. Debugging Time*: 59.9 min<br/>*Explanation*: Moderately difficult<br/>*Patching*: Moderately difficult<br/>*Patch Correctness*: 13%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=70e236167c3973fc428d2b5b297218fde9b68e73" target="_blank">Developer</a><br/>*Bug Report*: <a href="grep.7aa698d3.report.txt" target="_blank">Simple</a>, [Original](http://lists.gnu.org/archive/html/bug-grep/2012-06/msg00001.html)<br/>*Fault Locations*: <a href="grep.7aa698d3.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="grep.7aa698d3.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/grep.7aa698d3/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=7aa698d36b5b2eeb8e90e7a327eb7ebe46d59e87" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[grep.3220317a]</a>**<br/>*Error Type*: Crash<br/>*Avg. Debugging Time*: 63.7 min<br/>*Explanation*: Moderately difficult<br/>*Patching*: Moderately difficult<br/>*Patch Correctness*: 20%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=8f9106c419d18759f767da351b3b6913f022c8f8" target="_blank">Developer</a><br/>*Bug Report*: <a href="grep.3220317a.report.txt" target="_blank">Simple</a>, [Original](http://lists.gnu.org/archive/html/bug-grep/2010-03/msg00395.html)<br/>*Fault Locations*: <a href="grep.3220317a.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="grep.3220317a.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/grep.3220317a/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=3220317a428d63a4303ffee0fb45becf835cf1fd" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[grep.3c3bdace]</a>**<br/>*Error Type*: Crash<br/>*Avg. Debugging Time*: 64.8 min<br/>*Explanation*: Very difficult<br/>*Patching*: Moderately difficult<br/>*Patch Correctness*: 70%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=6245829135f68fd77e5ba590650abbe6c350bf42" target="_blank">Developer</a><br/>*Bug Report*: <a href="grep.3c3bdace.report.txt" target="_blank">Simple</a>, [Original](http://savannah.gnu.org/bugs/?33547)<br/>*Fault Locations*: <a href="grep.3c3bdace.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="grep.3c3bdace.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/grep.3c3bdace/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=3c3bdace487c2c961ab3126d9a573af29c449c8b" target="_blank">Developer</a><br/>*Tests*: Researcher |
| **<a href="benchmark.pdf" target="_blank">[grep.c96b0f2c]</a>**<br/>*Error Type*: Functional Bug<br/>*Avg. Debugging Time*: 67.6 min<br/>*Explanation*: Very difficult<br/>*Patching*: Moderately difficult<br/>*Patch Correctness*: 50%| *Regression*: <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=c32c042126a633d1bda23317410667cdd3a527f5" target="_blank">Developer</a><br/>*Bug Report*: <a href="grep.c96b0f2c.report.txt" target="_blank">Simple</a>, [Original](http://lists.gnu.org/archive/html/bug-grep/2012-08/msg00012.html)<br/>*Fault Locations*: <a href="grep.c96b0f2c.faults.txt" target="_blank">Participants</a><br/>*Bug Diagnosis*: <a href="grep.c96b0f2c.diagnosis.txt" target="_blank">Participants</a><br/>*Patches*: <a href="https://github.com/dbgbench/dbgbench.github.io/tree/master/patches/grep.c96b0f2c/" target="_blank">Participants</a> <a href="http://git.savannah.gnu.org/cgit/grep.git/commit/?id=c96b0f2c8220f171f8fabd62aa1457ebff4d9277" target="_blank">Developer</a><br/>*Tests*: Researcher |

## <a name="use"></a>How to Use?

## <a name="cite"></a>How to Cite?
```
@inproceedings{dbgbench, 
  author = {B\"{o}hme, Marcel and Soremekun, Ezekiel Olamide and Chattopadhyay, Sudipta and Ugherughe, Emamurho and Zeller, Andreas}, 
  title = {Where is the Bug and How is it Fixed? An Experiment with Practitioners}, 
  booktitle = {Proceedings of the Joint meeting of the European Software Engineering Conference and the ACM SIGSOFT Symposium on the Foundations of Software Engineering (ESEC/FSE) 2017}, 
  series = {FSE 2017}, 
  pages = {1-11}, 
  year = {2017}
}
```


