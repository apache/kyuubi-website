---
title: Kyuubi 改进提案 (KPIP)
menu:
    main:
        name: "改进提案 (KPIP)"
        parent: "development"
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

KPIP 的目的是在整个开发过程中通知用户社区并让用户社区参与对 Kyuubi 代码库的重大改进，以增加用户需求。

KPIP 应该用于重大的面向用户或跨领域的更改，而不是小的增量改进。如有疑问，Committer 认为这个更改需要 KPIP，那它确实需要。

## 什么是 KPIP?

KPIP 类似于产品管理中常用的产品需求文档。

一个 KPIP:

- 是一张标有“KPIP”的票，提议对 Kyuubi 进行重大改进或改变
- 遵循下面定义的模板
- 包括关于提案的票证的讨论

## 谁?

任何**社区成员**都可以通过讨论一个 KPIP 是否可能满足他们的需求或者提出一个 KPIP 来提供帮助。

**Contributors**可以通过讨论 KPIP 在技术上是否可行来提供帮助。

**Committer**可以通过讨论 KPIP 是否符合项目的长期目标以及引导 KPIP 来提供帮助。

**KPIP 作者** 是任何创作 KPIP 并致力于在整个过程中推动变革的社区成员。 KPIP 的作者身份可以转让。

**KPIP Shepherd** 是 PMC 成员，致力于在整个过程中引导提议的变更。虽然 Shepherd 可以在开发过程中委托或与其他 Committer 合作，但 Shepherd 最终对 KPIP 的成功或失败负责。Shepherd 的职责包括但不限于：

- 成为提议变革的倡导者
- 帮助推进设计并在关键利益相关者之间达成共识
- 审查代码更改，确保更改符合项目标准
- 从用户那里获得反馈并迭代设计和实现
- 维护变更的质量，包括在发布之前验证变更是否满足 KPIP 的目标以及是否存在关键的错误

## KPIP 流程
### 提出一个 KPIP

任何人都可以使用下面的文档模板提出 KPIP。请仅在你愿意提供帮助的情况下提交 KPIP，至少要与讨论有关。

如果 KPIP 太小或者是增量的并且可以通过正常的 JIRA 流程完成的，则 committer 应该删除 KPIP 标签。

### KPIP 文档模板

A KPIP document is a short document with a few questions, inspired by the Heilmeier Catechism:

- Q1. What are you trying to do? Articulate your objectives using absolutely no jargon.

- Q2. What problem is this proposal NOT designed to solve?

- Q3. How is it done today, and what are the limits of current practice?

- Q4. What is new in your approach, and why do you think it will be successful?

- Q5. Who cares? If you are successful, what difference will it make?

- Q6. What are the risks?

- Q7. How long will it take?

- Q8. What are the mid-term and final “exams” to check for success?

- Appendix A. Proposed API Changes. Optional section defining APIs changes, if any. Backward and forward compatibility must be taken into account.

- Appendix B. Optional Design Sketch: How are the goals going to be accomplished? Give sufficient technical detail to allow a contributor to judge whether it's likely to be feasible. Note that this is not a full design document.

- Appendix C. Optional Rejected Designs: What alternatives were considered? Why were they rejected? If no alternatives have been considered, the problem needs more thought.

### 讨论 KPIP

KPIP 的所有讨论都应在公共的论坛上进行，最好是附在票证上的讨论。任何离线进行的讨论都应通过总结讨论的会议记录在线提供给公众。

### 实施 KPIP

应通过 [贡献指南](/zh/issue_tracking.html) 进行实施。需要 KPIP 的变更通常还需要编写和审查设计文档。
