---
title: Contributing
menu:
    main:
        name: "Contributing to Kyuubi"
        parent: "community"
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

Apache Kyuubi (Incubating) welcomes contribution from anyone. The contibution does not only about the code.
Subscribe and helping users on the mailing list, Come up with some features, Review other developers pull requests,
Improving documentation, Tell us your story are also welcome. This guide help you learn about the details of Kyuubi community.


# Mailing list

We discuss question or announce some important news through Kyuubi mailing list, such as the most popular
mailing [dev@kyuubi.apache.org](mailto:dev@kyuubi.apache.org). Subscribe mailing is a good start to join Kyuubi community.
See all Kyuubi supported [mailing list](https://kyuubi.apache.org/mailing_lists.html).


# Report bugs

For bug reports, this should ideally include a short reproduction of the problem and it can also accelerate problem solving
if you can provide the used Kyuubi version and environment information details. Kyuubi use github issues to track and maintain the bug list.
See our [Bug Report Template](https://github.com/apache/incubator-kyuubi/issues/new?assignees=&labels=kind%3Abug%2Cpriority%3Amajor&template=bug-report.yml&title=%5BBug%5D+).


# Request feature

As Kyuubi can be used in a wide variety of scenarios, the more and more features are merged into. Post your idea and describe your proposal to us.
See our [Feature Request Template](https://github.com/apache/incubator-kyuubi/issues/new?assignees=&labels=kind%3Afeature%2Cpriority%3Amajor&template=feature-request.yml&title=%5BFEATURE%5D+).


# Improve documentation

The documentation and code are maintained in the same project at Kyuubi, and the root directory of documentation is in `docs/`.
It would be great if you document some best practice with your use case. Including quick start, trouble shooting, deep optimization and so on.


# Share your story

If your team has used Kyuubi for some time, we are looking forward to listen to your story.
See [Who is using Apache Kyuubi (Incubating)](https://github.com/apache/incubator-kyuubi/discussions/925).

# Review pull requests

Kyuubi also encourage to help review pull requests of other developers which makes code more robust.
The review guide can see [Google’s Engineering Practices documentation](https://google.github.io/eng-practices/review/).


# Contributing code changes

## Before

Before proceeding, it's better to search the issues and pull requests history first. Likely, the problem or request has been discussed before.

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
# 4. Create a new branch
     git checkout -b ${Your_branch_name}
# 5. Do your develop and commit the changes
     git commit -am "${Your_commit_information}"
# 6. Push your branch to your repository
     git push origin ${Your_branch_name}
# 7. Go to 'https://github.com/apache/incubator-kyuubi' and click the 'new pull request' button
```

About the pull request, it is highly recommended providing a clear descriptions for a better code review process.
Writing good pull request descriptions is a great way to help reviewers know what to expect when reviewing code.
As developers, our responsibility is to fix issues or implement new features and clearly communicate the development work to reviewers.
A developer can convey proposed code changes and their purposes either through detailed PR descriptions.
They're also a great way to help track things that should be done for every change, such as testing, adding unit tests, and updating documentation in the git log.

Descriptions shall clearly answer:

Q1.
Q3.
Q3

## After

It may take some time to wait other developer to review. Feel free to ping any committer who has worked on the similar area.
In general, You can find out the right people to review your code through git commit history.

One more thing, Kyuubi leverage github action to cover unit test and integration test, so please make sure your pull request's
tests are green. It will Speed up the merging :).
