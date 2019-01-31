+++
author = "Camunda BPM Team"
categories = ["Execution"]
tags = ["Release Note"]
date = "2019-02-01T12:00:00+01:00"
title = "Camunda 7.11.0-alpha1 Released"
+++

**Camunda BPM 7.11.0-alpha1** is here and the highlights are:

* Fine-grained Permissions for Batches and Job Retries
* MariaDB/MySQL: Job Due Dates after 2038
* JBoss/Wildfly: Expressions in Camunda Subsystem
* Java/REST API: Deleting Historic Variables
* [X Bug Fixes](https://app.camunda.com/jira/issues/?jql=issuetype%20%3D%20%22Bug%20Report%22%20AND%20fixVersion%20%3D%207.11.0-alpha1)

You can [Download Camunda for free](https://camunda.com/download/) (click on Preview Release) or [Run it with Docker](https://hub.docker.com/r/camunda/camunda-bpm-platform/).


If you are interested, you can see the complete [release notes](https://app.camunda.com/jira/secure/ReleaseNote.jspa?projectId=10230&version=15346).

If you want to dig in deeper, you can find the source code on [GitHub](https://github.com/camunda/camunda-bpm-platform/releases/tag/7.11.0-alpha1).

<!--more-->

## Fine-grained Permissions for Batches and Job Retries

Within this alpha, we introduce the first portion of more fine-grained permissions. It contains create batch permission for each type of batch operation. Also, job retry permission for process definitions and process instances. Here is a use case when these permissions will be a handful: An user is allowed to perform set retries batch operation and they are not supposed to delete process instance by batch. In such case, the user can be granted "Create Batch Set Job Retries" permission and they will be able to perform only this tipe of batch operations. For a complete list of the available permission, please visit our [User guide](https://docs.camunda.org/manual/latest/user-guide/process-engine/authorization-service/#additional-batch-permissions). Stay tuned for further permission additions for process instance and process definition in the next alpha releases. 

## MariaDB/MySQL: Job Due Dates after 2038

Idea (Thorben): Could link to this in the introduction: https://en.wikipedia.org/wiki/Year_2038_problem

## JBoss/Wildfly: Expressions in Camunda Subsystem

Starting with this alpha, it is possible to reference system properties using Ant-style expressions (i.e., `${PROPERTY_KEY}`) in the camunda subsystem in the server configuration of JBoss AS 7 and all WildFly versions (`standalone.xml` or `domain.xml`). 

All elements and attributes except for the `name` attribute on the elements `process-engine` and `job-acquisition` support expressions. 

Here is an example:

```xml
<!-- ... -->
<plugin>
  <class>org.camunda.bpm.engine.impl.plugin.AdministratorAuthorizationPlugin</class>
  <properties>
    <property name="administratorUserName">${camunda.administratorUserName}</property>
  </properties>
</plugin>
<!-- ... -->
```

Read more on expressions in the documentation for [JBoss](https://docs.jboss.org/author/display/AS71/Expressions) and [WildFly](http://docs.wildfly.org/15/Extending_WildFly.html#expressions).

## Java/REST API: Deleting Historic Variables

<!--no-more-->

## What's Next?

This is the first alpha release on the road to **Camunda BPM 7.11** (due May 30, 2018). Stay tuned for more features around permissions, job execution and testing support. For details see our [roadmap](https://camunda.com/learn/community/#roadmap).

## Your Feedback Matters!

With every release we constantly strive to improve Camunda BPM. To make this possible, we are reliant on your feedback. Feel free to share your ideas and suggestions with us.

You can contact us by writing a post in the [forum](https://forum.camunda.org/).
