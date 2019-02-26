+++
author = "Camunda BPM Team"
categories = ["Execution"]
tags = ["Release Note"]
date = "2019-03-01T08:00:00+01:00"
title = "Camunda BPM 7.11.0-alpha2 Released"
+++

**Camunda BPM 7.11.0-alpha2** is here and the highlights are:

* Fine-grained Permissions for Tasks and Process Instances
* Recalculate Timer Due Dates
* Java/REST API: Case Insensitive Semantics for Task Variables
* Cockpit: Delete Variable History
* [XXX Bug Fixes](https://app.camunda.com/jira/issues/?jql=issuetype%20%3D%20%22Bug%20Report%22%20AND%20fixVersion%20%3D%207.11.0-alpha2)

You can [Download Camunda for free](https://camunda.com/download/) (click on Preview Release) or [Run it with Docker](https://hub.docker.com/r/camunda/camunda-bpm-platform/).


If you are interested, you can see the complete [release notes](https://app.camunda.com/jira/secure/ReleaseNote.jspa?projectId=10230&version=15374).

If you want to dig in deeper, you can find the source code on [GitHub](https://github.com/camunda/camunda-bpm-platform/releases/tag/7.11.0-alpha2).

<!--more-->

## Fine-grained Permissions for Tasks and Process Instances



## Recalculate Timer Due Dates



## Java/REST API: Case Insensitive Semantics for Task Variables

From this release on, queries for tasks with process-, task- and or case instance variables support case-insensitive semantics.

There are three new operators to help you use this feature with the REST API: eqci, neqci and likeci (corresponding to eq, neq and like) 

Here are some examples.

GET `/task?taskVariables=varName_eqci_varValue`

GET `/task?processVariables=varName_neqci_varValue`

GET `/task?caseInstanceVariables=varName_likeci_varValue`


A POST request could look like this:

POST `/task`

Request Body:

```json
{"taskVariables":
    [{"name": "varName",
    "value": "varValue",
    "operator": "eqci"},
    {"name": "anotherVarName",
    "value": "anotherVarValue",
    "operator": "likeci"},
   {"name": "thirdVarName",
    "value": "thirdVarValue",
    "operator": "neqci"}]
}
```

For more information please check the documentation [here](https://docs.camunda.org/manual/latest/reference/rest/task/post-query/) and [here](https://docs.camunda.org/manual/latest/reference/rest/task/get-query/).

The new semantics are also supported in the Java API. They can be used for `TaskQuery` and `TaskFilter`. Creating a case-insensitive `TaskQuery` with Java is as simple as:

```java
taskQuery.taskVariableValueEqualsCaseInsensitive(variableName, variableValue)
taskQuery.processVariableValueNotEqualsCaseInsensitive(variableName, variableValue)
taskQuery.caseInstanceVariableValueLikeCaseInsensitive(variableName, variableValue)
```

You can find more information on the new TaskQuery features [here](https://docs.camunda.org/javadoc/camunda-bpm-platform/7.11/org/camunda/bpm/engine/task/TaskQuery.html).


## Cockpit: Delete Variable History



<!--no-more-->

## What's Next?

This is the first alpha release on the road to **Camunda BPM 7.11** (due May 30, 2018). Stay tuned for more features around permissions, job execution and testing support. For details see our [roadmap](https://camunda.com/learn/community/#roadmap).

## Your Feedback Matters!

With every release, we strive to improve Camunda BPM. To make this possible, we are reliant on your feedback. Feel free to share your ideas and suggestions with us.

You can contact us by writing a post in the [forum](https://forum.camunda.org/).
