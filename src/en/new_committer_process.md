---
title: Inviting New Committers
menu:
    main:
        name: "Inviting New Committers"
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

This is the Apache Kyuubi specific processes for adding new committers,
following the [Apache Project Management Committee](https://www.apache.org/dev/pmc.html)
and [New Committer Process](https://community.apache.org/newcommitter.html#new-committer-process) guidelines.

### New Committer Progress

To go through the whole process of inviting a new committer, you need to be a Kyuubi PMC member
and go step by step according to the following table.

| Steps            | Who                     | Where                                                      | Notes                                                                                                                                                                                                                                                            | Templates                                                  | Time to Wait |
|:-----------------|-------------------------|------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------|--------------|
| **DISCUSSION**   | PMC                     | private@kyuubi.apache.org                                  | If you recognize someone's contributions have met our [requirements](become_committer.html), please raise a discussion in the private@ w/ the Kyuubi PMC before the formal vote.  It may be nice to include some details about why you want to invite the person | [discussion](vote/templates/committer_discussion.html)     | 72 hours     |
| **VOTE**         | PMC                     | private@kyuubi.apache.org                                  | If there are no strong objections in the discussion, please raise new threads to vote the candidates one by one.                                                                                                                                                 | [vote](vote/templates/committer_vote.html)                 | 72 hours     |
| **RESULT**       | PMC                     | private@kyuubi.apache.org                                  | No matter whether the result is positive or negative, please raise a new thread to summarize. If the result is negative, dismiss the following steps.                                                                                                            | [result](vote/templates/committer_vote_close.html)         | 0            |
| **INVITATION**   | PMC                     | invitee's email</br>private@kyuubi.apache.org              | If the result is positive(achieved by **Consensus Approval**: at least 3 +1 votes and no vetoes), send a invitation to the new committer candidate.                                                                                                              | [invitation](vote/templates/committer_invitation.html)     | 0            |
| **REPLY**        | Invitee                 | the current mail thread                                    | If the invitee accepts, go to next step; otherwise, express the gratitude of Kyuubi community and stop here.                                                                                                                                                     |                                                            | 0            |
| **ACCEPT**       | PMC                     | the current mail thread                                    | Reply to the current thread w/ a warm welcome and more information for account creation.                                                                                                                                                                         | [accept](vote/templates/committer_accept.html)             | 0            |
| **ACCOUNT**      | Invitee / asf secretary | secretary@apache.org                                       | Follow the guidelines in the invitation email to make a account creation request.                                                                                                                                                                                |                                                            | a week       |
| **NOTIFICATION** | PMC                     | invitee's email</br>private@kyuubi.apache.org              | After the committer account is established(after received *[NOTICE] Account created:* from root@apache.org), DO NOT forget to notice the invitee.                                                                                                                | [completion](vote/templates/committer_completion.html)     | 0            |
| **NEWS**         | Invitee                 | [kyuubi-website](https://github.com/apache/kyuubi-website) | Make a pull request against the web repo to update the [news](project_history.html) and [current committers](become_committer.html) pages.                                                                                                                        |                                                            | 0            |
| **ANNOUNCEMENT** | PMC                     | dev@kyuubi.apache.org                                      | The last step to announce and celebrate the new committer.                                                                                                                                                                                                       | [announcement](vote/templates/committer_announcement.html) | 0            |

### Additional

A post to introduce yourself and how you become a committer is welcome to be submitted to our WeChat public account @apachekyuubi.
