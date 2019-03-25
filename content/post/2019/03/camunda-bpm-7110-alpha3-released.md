+++
author = "Camunda BPM Team"
categories = ["Execution"]
tags = ["Release Note"]
date = "2019-03-29T08:00:00+01:00"
title = "Camunda BPM 7.11.0-alpha3 Released"
+++

**Camunda BPM 7.11.0-alpha3** is here and the highlights are:

* Fine-grained Permissions for Tasks, Process Instances, and Process Definitions
* Java/REST API: Recalculate Job Due Dates
* Java/REST API: Case Insensitive Semantics for Task Variables
* Delete Variable History in Cockpit Full (Enterprise)
* [XXX](https://app.camunda.com/jira/issues/?jql=issuetype%20%3D%20%22Bug%20Report%22%20AND%20fixVersion%20%3D%207.11.0-alpha3)

You can [Download Camunda for free](https://camunda.com/download/) (click on Preview Release) or [Run it with Docker](https://hub.docker.com/r/camunda/camunda-bpm-platform/).


If you are interested, you can see the complete [release notes](XXX).

If you want to dig in deeper, you can find the source code on [GitHub](https://github.com/camunda/camunda-bpm-platform/releases/tag/7.11.0-alpha3).

<!--more-->

## Official Support for Camunda BPM Assert

BPM Assert is now **an official part of Camunda BPM** with the release of version 3.0.0-alpha1.

We want to thank [Martin Schimak and the many other contributors](https://github.com/camunda/camunda-bpm-assert/graphs/contributors), who have made BPM Assert into what it is today.

The current release is mostly concentrated on including the project in the Camunda development lifecycle and resolving compatibility issues. You can read up on this in the separate [blog post](https://blog.camunda.com/post/2019/03/camunda-bpm-assert-300-alpha1-released/).

The highlights from this release:

* new Maven coordinates:
```xml
<dependency>
  <groupId>org.camunda.bpm.assert</groupId>
  <artifactId>camunda-bpm-assert</artifactId>
  <version>3.0.0-alpha1</version>
</dependency>
```

* no inheritance from [AssertJ](http://joel-costigliola.github.io/assertj/) Assertions anymore

* compatibility artifacts if you want to use BPM Assert with Java 1.7 or Spring Boot 2.0.x (see our [version compatibility overview](https://docs.camunda.org/manual/develop/user-guide/testing/#assertions-version-compatibility))

* official support for CMMN assertions

* assertions for external tasks, just write:
```java
complete(externalTask("review"), withVariables("approved", true));
```

The final release is scheduled for May 31, 2019. Stay tuned for the next releases!

## Java/REST API: Case Insensitive Semantics for Task Variables Names

## Java/REST API: Return Variables after task completion

## Password Policies for engine-managed users

## Cockpit: Audit Log Dashboard

## Cockpit: Recalculate Timer Due Dates
<!--no-more-->

## What's Next?

This is the third alpha release on the road to **Camunda BPM 7.11** (due May 31, 2019). Stay tuned for more features around permissions, job execution and testing support. For details see our [roadmap](https://camunda.com/learn/community/#roadmap).

## Your Feedback Matters!

With every release, we strive to improve Camunda BPM. To make this possible, we are reliant on your feedback. Feel free to share your ideas and suggestions with us.

You can contact us by writing a post in the [forum](https://forum.camunda.org/).
