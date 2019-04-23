+++
author = "Camunda BPM Team"
categories = ["Execution"]
tags = ["Release Note"]
date = "2019-04-22T18:00:00+01:00"
title = "Camunda BPM 7.11.0-alpha4 Released"
+++

**Camunda BPM 7.11.0-alpha4** is here and the highlights are:


* [XX Bug Fixes](https://app.camunda.com/jira/issues/?jql=issuetype%20%3D%20%22Bug%20Report%22%20AND%20fixVersion%20%3D%207.11.0-alpha4)

You can [Download Camunda for free](https://camunda.com/download/) (click on Preview Release) or [Run it with Docker](https://hub.docker.com/r/camunda/camunda-bpm-platform/).


If you are interested, you can see the complete [release notes](UPDATE LINK).

If you want to dig in deeper, you can find the source code on [GitHub](https://github.com/camunda/camunda-bpm-platform/releases/tag/7.11.0-alpha4).

<!--more-->

## Engine Wide History Time to Live


## More User Operation Log Entries


## Support for Password Policies
Most online users should know about the importance of choosing a secure password. However, each year the [list of most commonly used passwords](https://en.wikipedia.org/wiki/List_of_the_most_common_passwords) is dominated by passwords like `123456`, `password` and `qwerty`.

With this alpha release we introduce password policies that can be used to enforce certain security standards when choosing a password. Note that this applies only for users that are managed within the Camunda engine. LDAP user management is not affected.

To enable the default password policy set the `enablePasswordPolicy` setting in the engine configuration. The default policy enforces a minimum length (10 characters) and at least one lower case, upper case and special character as well as at least one digit.

It is also possible to deploy your own password policy. More information on that can be found in the [user guide](https://docs.camunda.org/manual/latest/user-guide/process-engine/password-policy/).

## Tasklist: Case-Insensetive Task Querys


<!--no-more-->

## What's Next?

This is the fourth and last alpha release on the road to **Camunda BPM 7.11** (due May 31, 2019). Please have a look at our [roadmap](https://camunda.com/learn/community/#roadmap) for whats still to come.

## Your Feedback Matters!

With every release, we strive to improve Camunda BPM. To make this possible, we are reliant on your feedback. Feel free to share your ideas and suggestions with us.

You can contact us by writing a post in the [forum](https://forum.camunda.org/).

