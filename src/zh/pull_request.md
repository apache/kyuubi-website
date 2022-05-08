---
title: 提交PR指南
menu:
  main:
    name: "提交PR指南"
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

## 审查 PR

Kyuubi 鼓励帮助审查其他开发人员的PR，这可以使得代码更加健壮。
审核指南可以查看 [Google’s Engineering Practices documentation](https://google.github.io/eng-practices/review/).

## 提交你的PR

### 在这之前

在开始之前，最好先搜索问题和PR请求的历史记录，因为该问题可能已经被讨论过了。

检查后，可以新建一个 issue 来描述想要做什么，关于 issue，我们有丰富的类型可以选择, 看 [这里](https://github.com/apache/incubator-kyuubi/issues/new/choose).

然后在PR中提交你的代码。如果你是新的贡献者，请按照本指南逐步了解设置开发环境和做出你的第一个贡献。

```shell
# 1. Fork GitHub 上的 Kyuubi 存储库
#    访问 'https://github.com/apache/incubator-kyuubi' 然后点击 'Fork' ，Fork到你的代码仓库
# 2. 使用下面的git命令克隆代码到本地
     git clone https://github.com/${你的Github用户名}/incubator-kyuubi.git
     cd incubator-kyuubi
# 3. 添加 git 远程仓库
     git remote add origin https://github.com/${你的Github用户名}/incubator-kyuubi.git
     git remote add apache https://github.com/apache/incubator-kyuubi.git
# 4. 设置你的github名字和邮箱
     git config user.name "${你的Github用户名}"
     git config user.email "${你的公开邮箱}"
# 5. 创建一个新分支
     git checkout -b ${分支名称}
# 6. 进行开发并提交更改
     git commit -am "${提交信息}"
# 7. 将你的分支推送到你的存储库
     git push origin ${分支名称}
# 8. 访问 'https://github.com/apache/incubator-kyuubi' 然后点击 'new pull request' 
```

为更好进行代码审查，强烈建议提供清晰的描述。
编写好的PR描述能够帮助审查者在审查代码时更好的了解代码的意图。

作为开发人员，我们的责任是解决问题或者实现新功能，并将开发工作清楚地传达给审查者。
开发人员可以通过详细的 PR 描述来体现代码的更改逻辑及目的。
它们也有利于追踪每次更改完成后要做的事情，例如测试、添加单元测试和更新 git 日志中的文档。
详见 [Pull Request Template](https://github.com/apache/incubator-kyuubi/blob/master/.github/PULL_REQUEST_TEMPLATE).

### 之后

等待其他开发人员审查可能需要一些时间。可以随意 @ 任何在类似领域工作过的 Committer。
一般来说，你可以通过 git 的历史提交记录找到合适的人来审查你的代码。

还有一件事，Kyuubi 利用 [Github Actions](https:github.comapacheincubator-kyuubiactions)
覆盖 Linux AMD64 上的单元测试和集成测试以及 Linux ARM64 上的 [TravisCI](https:app.travis-ci.comgithubapacheincubator-kyuubi)，
所以请确保你发起的PR的测试是绿色的。它将加快你PR的合入 :)。
