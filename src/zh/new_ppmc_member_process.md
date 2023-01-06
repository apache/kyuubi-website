---
title: 新晋 PPMC 流程
menu:
    main:
        name: "新晋 PPMC 流程"
        parent: "community"
        weight: 3 
---
<!---
  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this file except in compliance with the License.
  You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License. See accompanying LICENSE file.
-->

<img src="https://svn.apache.org/repos/asf/comdev/project-logos/originals/kyuubi-1.svg" alt="Kyuubi logo" width="30%" align="right" />

本指南基于 [new_ppmc](https://incubator.apache.org/guides/ppmc.html#voting_in_a_new_ppmc_member) 和 [apache newpmc](https://community.apache.org/newcommitter.html#new-committer-process).

## 新晋 PPMC 成员流程

### 在 `private@kyuubi.apache.org` 发起讨论

see **PPMC Member Discuss Template**

### 在 `private@kyuubi.apache.org` 中发起投票

see **PMC Member Vote Template**

### 关闭投票

see **Close Vote Template**

### 发送投票结果至 IPMC

see **Send message to IPMC Template**

### 如果通过，则邀请成为 PPMC 成员

see **PMC Member Invite Template**

### 如果接受，然后: 接受成为 PPMC 成员

see **PMC Member Accept Template**

### 通知 PPMC 成员完成

see **PMC Member Done Template**

### 宣布新的 PPMC 成员

see **PMC Member Announce Template**

## Template

Note that, there are three placeholder in template should be replaced before using

- NEW_PPMC_NAME
- NEW_PPMC_EMAIL
- NEW_PPMC_APACHE_NAME

### PPMC Member Vote Template

```text
To: private@kyuubi.apache.org
Subject: [VOTE] New PPMC member candidate: ${NEW_PPMC_NAME}
```
```text
Hi Kyuubi PPMC,

This is a formal vote about inviting ${NEW_PPMC_NAME} as our new PPMC member.

${Work list}[1]

[1] https://github.com/apache/incubator-kyuubi/commits?author=${NEW_PPMC_NAME}
```

Note that, Voting ends one week from today, i.e. [midnight UTC on YYYY-MM-DD](https://www.timeanddate.com/counters/customcounter.html?year=YYYY&month=MM&day=DD)
See voting [guidelines](https://community.apache.org/newcommitter.html)


### Close Vote Template

```text
To: private@kyuubi.apache.org
Subject: [RESULT] [VOTE] New PPMC member: ${NEW_PPMC_NAME}
```
```text
Hi Kyuubi PPMC,

The vote has now closed. The results are:

Binding Votes:

+1 [TOTAL BINDING +1 VOTES]
 0 [TOTAL BINDING +0/-0 VOTES]
-1 [TOTAL BINDING -1 VOTES]

The vote is ***successful/not successful***
```

### Send message to IPMC Template
```text
To: private@incubator.apache.org
Cc: private@kyuubi.apache.org
Subject: [VOTE][RESULT] ${NEW_PPMC_NAME} PPMC membership
```
```text
${NEW_PPMC_NAME} has been voted as a new member of the Kyuubi PPMC.
The vote thread is at https://lists.apache.org/...
```

### PPMC Member Invite Template

```text
To: ${NEW_PPMC_EMAIL}
Cc: private@kyuubi.apache.org
Subject: Invitation to become Kyuubi PPMC member: ${NEW_PPMC_NAME}
```
```text
Hello ${NEW_PPMC_NAME},

The Kyuubi Project Management Committee (PMC) 
hereby offers you committer privileges to the project
as well as membership in the PPMC.
These privileges are offered on the understanding that
you'll use them reasonably and with common sense.
We like to work on trust rather than unnecessary constraints. 

Being a PPMC member enables you to guide the direction of the project.

Being a PPMC member does not require you to 
participate any more than you already do. It does 
tend to make one even more committed.  You will 
probably find that you spend more time here.

Of course, you can decline and instead remain as a 
contributor, participating as you do now.

A. This personal invitation is a chance for you to 
accept or decline in private.  Either way, please 
let us know in reply to the private@kyuubi.apache.org
address only.

B. If you accept, the next step is to register an iCLA:
    1. Details of the iCLA and the forms are found 
    through this link: https://www.apache.org/licenses/#clas

    2. Instructions for its completion and return to 
    the Secretary of the ASF are found at
    https://www.apache.org/licenses/#submitting

    3. When you transmit the completed iCLA, request 
    to notify the Apache Kyuubi and choose a 
    unique Apache ID. Look to see if your preferred 
    ID is already taken at 
    https://people.apache.org/committer-index.html
    This will allow the Secretary to notify the PPMC 
    when your iCLA has been recorded.

When recording of your iCLA is noted, you will 
receive a follow-up message with the next steps for 
establishing you as a PPMC member.
```

### PPMC Member Accept Template

```text
To: ${NEW_PPMC_EMAIL}
Cc: private@kyuubi.apache.org
Subject: Re: invitation to become Kyuubi PPMC member
```
```text
Welcome. Here are the next steps in becoming a project PPMC. After that
we will make an announcement to the dev@kyuubi.apache.org list.

You need to send a Contributor License Agreement to the ASF.
Normally you would send an Individual CLA. If you also make
contributions done in work time or using work resources,
see the Corporate CLA. Ask us if you have any issues.
https://www.apache.org/licenses/#clas.

You need to choose a preferred ASF user name and alternatives.
In order to ensure it is available you can view a list of taken IDs at
https://people.apache.org/committer-index.html

Please notify us when you have submitted the CLA and by what means 
you did so. This will enable us to monitor its progress.

We will arrange for your Apache user account when the CLA has 
been recorded.

After that is done, please make followup replies to the dev@kyuubi.apache.org list.
We generally discuss everything there and keep the
private@kyuubi.apache.org list for occasional matters which must be private.

The developer section of the website describes roles within the ASF and provides other
resources:
  https://www.apache.org/foundation/how-it-works.html
  https://www.apache.org/dev/

The incubator also has some useful information for new PPMC
in incubating projects:
  https://incubator.apache.org/guides/committer.html
  https://incubator.apache.org/guides/ppmc.html

Just as before you became a PPMC member, participation in any ASF community
requires adherence to the ASF Code of Conduct:
  https://www.apache.org/foundation/policies/conduct.html

Yours,
The Apache Kyuubi PPMC
```

### PPMC Member Done Template

```text
To: private@kyuubi.apache.org, ${NEW_PPMC_EMAIL}
Subject: account request: ${NEW_PPMC_NAME}
```
```text
${NEW_PPMC_EMAIL}, as you know, the ASF Infrastructure has set up your
committer account with the username '${NEW_PPMC_APACHE_NAME}'.

Please follow the instructions to set up your SSH,
svn password, svn configuration, email forwarding, etc.
https://www.apache.org/dev/#committers

You have commit access to specific sections of the
ASF repository, as follows:

The general "committers" at:
  https://svn.apache.org/repos/private/committers

If you have any questions during this phase, then please
see the following resources:

Apache developer's pages: https://www.apache.org/dev/
Incubator committer guide: https://incubator.apache.org/guides/committer.html

Naturally, if you don't understand anything be sure to ask us on the dev@kyuubi.apache.org mailing list. 
Documentation is maintained by volunteers and hence can be out-of-date and incomplete - of course
you can now help fix that.

A PPMC member will announce your election to the dev list soon.
```

### PPMC Member Announce Template
```text
To: dev@kyuubi.apache.org
[ANNONCE] New PPMC member: ${NEW_PPMC_NAME}
```
```text
Hi Kyuubi Community,

The Podling Project Management Committee (PPMC) for Apache Kyuubi
has invited ${NEW_PPMC_NAME} to become our PPMC member and
we are pleased to announce that he has accepted.

### add specific details here ###

Please join me in congratulating ${NEW_PPMC_NAME}!

Being a committer enables easier contribution to the
project since there is no need to go via the patch
submission process. This should enable better productivity.
A PPMC member helps manage and guide the direction of the project.

Thanks,
On behalf of the Apache Kyuubi (Incubating) PPMC
```
