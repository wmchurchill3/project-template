# Project Template for Cleaner Code

## Table of Contents
- [Overview](#overview)
- [Build & Run](#build-run)
- [References](#references)

<a name="overview"></a>
## OVERVIEW

This is a project template to be used as a parent pom for projects wishing to standardize on

* Formated Code
* Statically Analyzed Code
* Copy-Paste Detection
* Unit and Integration Tested Code
* Git-Sha tagged artifacts
* Reporting for Testing, Copy-Paste Detection, and Static Analysis

<a name="build-run"></a>
## BUILD & RUN

To build the artifact, running tests and static code analysis.  This is the **preferred** way to generate the artifact, as it runs all validations and generates HTML reports.

```
mvn verify
```  

To build the jar while running tests.
```
mvn package
```

### Static Code Analysis

The code anaylsis done is default PMD rules and default copy-paste detection.  The default PMD rules can be found in the <project dir>/target/pmd/rulesets/maven-pmd-plugin-default.xml file after running the verify goal.

To run only the static analysis pass-fail

```
mvn pmd:check
```

An xml file with error can be found in the target/pmd.xml file

An html report (target/site/pmd.html) can be generated using 

```
mvn pmd:pmd
```

### Copy-Paste Detection

Pass-fail copy-paste detection with generatation of target/cpd.xml 

```
mvn pmd:cpd-check
```

An html report (target/site/pmd.html) can be generated using 

```
mvn pmd:cpd
```

### Code Formatting

The code formatting is checked as part of the test-compile phase. It is pass-fail and will stop the build if violations are found.  These can be corrected using the apply goal.

```
mvn spotless:apply
```

One can check their code formatting explicitly using 

```
mvn spotelss:check
```

<a name="reference"></a>
## REFERENCE

* [PMD static code analysis](https://pmd.github.io/)
* [Spotless Code Formatting Plugin](https://github.com/diffplug/spotless/tree/main/plugin-maven)


