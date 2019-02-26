+++
author = "Camunda BPM Team"
categories = ["Execution"]
tags = ["Release Note"]
date = "2019-03-01T08:00:00+01:00"
title = "Camunda BPM 7.11.0-alpha2 Released"
+++

**Camunda BPM 7.11.0-alpha2** is here and the highlights are:

* Fine-grained Permissions for Tasks and Process Instances
* Java/REST API: Recalculate Timer Due Dates
* Java/REST API: Case Insensitive Semantics for Task Variables
* Cockpit: Delete Variable History
* [XXX Bug Fixes](https://app.camunda.com/jira/issues/?jql=issuetype%20%3D%20%22Bug%20Report%22%20AND%20fixVersion%20%3D%207.11.0-alpha2)

You can [Download Camunda for free](https://camunda.com/download/) (click on Preview Release) or [Run it with Docker](https://hub.docker.com/r/camunda/camunda-bpm-platform/).


If you are interested, you can see the complete [release notes](https://app.camunda.com/jira/secure/ReleaseNote.jspa?projectId=10230&version=15374).

If you want to dig in deeper, you can find the source code on [GitHub](https://github.com/camunda/camunda-bpm-platform/releases/tag/7.11.0-alpha2).

<!--more-->

## Fine-grained Permissions for Tasks and Process Instances



## Java/REST API: Recalculate Timer Due Dates
Everything changes and nothing stands still.
Thus, this alpha now allows recalculation of job due dates. 
This comes in handy if your due dates are based on variables and other context that might change over time. 

The recalculation can be based on the original creation date of the job or the current date.
The first option will be the default for REST API interaction if you do not specify otherwise.
You can find an example for both below:

```java
managementService.recalculateJobDuedate("aJobId", true);// based on original creation date of the job

managementService.recalculateJobDuedate("aJobId", false);// based on current date
```

The REST API examples would look as follows (both calls return status code `204 No content`):

POST `/job/aJobId/duedate/recalculate`

POST `/job/aJobId/duedate/recalculate?creationDateBased=false`

For more infomation please check the [REST documentation](https://docs.camunda.org/manual/latest/reference/rest/job/post-recalculate-job-duedate/).


## Java/REST API: Case Insensitive Semantics for Task Variables

From this release on, queries for tasks with process-, task- and or case instance variables support case-insensitive semantics.

There are three new operators to help you use this feature with the REST API: `eqic`, `neqic` and `likeic` (corresponding to `eq`, `neq` and `like`, with _ic_ standing for `ignore case`) Here are some examples:

GET `/task?taskVariables=varName_eqic_varValue`

GET `/task?processVariables=varName_neqic_varValue`

GET `/task?caseInstanceVariables=varName_likeic_varValue`


A POST request could look like this:

POST `/task`

Request Body:

```json
{"taskVariables":
    [{"name": "varName",
    "value": "varValue",
    "operator": "eqic"},
    {"name": "anotherVarName",
    "value": "anotherVarValue",
    "operator": "likeic"},
   {"name": "thirdVarName",
    "value": "thirdVarValue",
    "operator": "neqic"}]
}
```

For more information please check the documentation [here](https://docs.camunda.org/manual/latest/reference/rest/task/post-query/) and [here](https://docs.camunda.org/manual/latest/reference/rest/task/get-query/).

The new semantics are also supported in the Java API. They can be used for `TaskQuery` and `TaskFilter`. Creating a case-insensitive `TaskQuery` with Java is as simple as:

```java
taskQuery.taskVariableValueEqualsIgnoreCase(variableName, variableValue)
taskQuery.processVariableValueNotEqualsIgnoreCase(variableName, variableValue)
taskQuery.caseInstanceVariableValueLikeIgnoreCase(variableName, variableValue)
```

You can find more information on the new TaskQuery features [here](https://docs.camunda.org/javadoc/camunda-bpm-platform/7.11/org/camunda/bpm/engine/task/TaskQuery.html).


## Cockpit: Delete Variable History



<!--no-more-->

## What's Next?

This is the first alpha release on the road to **Camunda BPM 7.11** (due May 30, 2018). Stay tuned for more features around permissions, job execution and testing support. For details see our [roadmap](https://camunda.com/learn/community/#roadmap).

## Your Feedback Matters!

With every release, we strive to improve Camunda BPM. To make this possible, we are reliant on your feedback. Feel free to share your ideas and suggestions with us.

You can contact us by writing a post in the [forum](https://forum.camunda.org/).
