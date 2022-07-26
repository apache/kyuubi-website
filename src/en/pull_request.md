---
title: Guide for Pull Requests
menu:
  main:
    name: "Pull Request"
    parent: "development"
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

## Review pull requests

Kyuubi encourage to help review pull requests of other developers which makes code more robust.
The review guide can see [Google’s Engineering Practices documentation](https://google.github.io/eng-practices/review/).

## Submit your pull requests

### Before

Before proceeding, it's better to search the issues and pull requests history first. Likely, the problem or request has been discussed.

After checking, you can create a new issue to describe what want to do, and about issues, we have rich types to
choose, see [here](https://github.com/apache/incubator-kyuubi/issues/new/choose).

Then submit your code within a pull request. If you are a new contributor, please follow this guide to get a gentle step-by-step
introductionto setting up the development environment and making your first contribution.

```shell
# 1. Fork the repository on GitHub
#    Go to 'https://github.com/apache/incubator-kyuubi' and click the 'Fork' button to your repository
# 2. Clone the repository locally using follow git cmd
     git clone https://github.com/${Github_user}/incubator-kyuubi.git
     cd incubator-kyuubi
# 3. Add git remmote repository
     git remote add origin https://github.com/${Github_user}/incubator-kyuubi.git
     git remote add apache https://github.com/apache/incubator-kyuubi.git
# 4. Set up your identifier
     git config user.name "${Your_github_name}"
     git config user.email "${Your_public_email}"
# 5. Create a new branch
     git checkout -b ${Your_branch_name}
# 6. Do your develop and commit the changes
     git commit -am "${Your_commit_information}"
# 7. Push your branch to your repository
     git push origin ${Your_branch_name}
# 8. Go to 'https://github.com/apache/incubator-kyuubi' and click the 'new pull request' button
```

It is highly recommended providing a clear descriptions for a better code review process.
Writing good pull request descriptions is a great way to help reviewers know what to expect when reviewing code.
As developers, our responsibility is to fix issues or implement new features and clearly communicate the development work to reviewers.
A developer can convey proposed code changes and their purposes either through detailed PR descriptions.
They're also a great way to help track things that should be done for every change, such as testing, adding unit tests, and updating documentation in the git log.
See [Pull Request Template](https://github.com/apache/incubator-kyuubi/blob/master/.github/PULL_REQUEST_TEMPLATE).

### After

It may take some time to wait other developer to review. Feel free to ping any committer who has worked on the similar area.
In general, you can find out the right people to review your code through git commit history.

One more thing, Kyuubi leverages [Github Actions](https://github.com/apache/incubator-kyuubi/actions) to cover unit 
test and integration test on Linux AMD64 and [TravisCI](https://app.travis-ci.com/github/apache/incubator-kyuubi) 
on Linux ARM64, so please make sure your pull request's tests are green. It will Speed up the merging :).
