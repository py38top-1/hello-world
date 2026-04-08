# Git Flow - 以发布为中心的开发模式

## 便于理解的标准流程

[Reference](https://nvie.com/posts/a-successful-git-branching-model/)

1. 从开发分支(develop)创建工作分支(feature branches),进行功能的实现或修正
2. 工作分支(feature branches)的修改结束后, 与开发分支进行合并
3. 重复上述两个步骤, 不断实现功能直到可以发布
4. 创建用于发布的分支(release branches), 处理发布的各项工作
5. 发布工作完成后与main/master分支合并, 打上版本标签(tag)进行发布
6. 如果发布的软件出现BUG, 以打了标签的版本为基础进行修正(hotfixes)
7. 以上流程的最大亮点在于考虑了紧急的BUG应对措施

## 有时显得过于复杂

这个开发流程的问题在于需要记忆的分支状态很多, 在实施前必须对整个开发流程进行系统地学习.

辅助工具:

[git-flow](https://github.com/nvie/gitflow)

---

## 规范化工作流（简明）

### 分支职责

- `main`: 仅存放已发布版本（生产可用）
- `develop`: 日常集成分支（下一版本基线）
- `feature/*`: 新功能开发
- `release/*`: 发布准备（仅允许版本号、文档、修复）
- `hotfix/*`: 线上紧急修复（从 `main` 拉出）

### 标准步骤

1. 从 `develop` 创建 `feature/<name>`，开发完成后通过 PR 合并回 `develop`
2. 需要发布时从 `develop` 创建 `release/<version>`
3. 在 `release/*` 完成发布前检查后，合并到 `main` 并打标签：`vX.Y.Z`
4. 将 `release/*` 再回合并到 `develop`，确保变更不丢失
5. 线上故障时从 `main` 创建 `hotfix/<name>`，修复后同时合并到 `main` 与 `develop`，并更新补丁标签

### 最小规则

- 禁止直接 push 到 `main`/`develop`，统一走 PR
- 发布和热修复合并必须带版本标签
- CI 未通过不得合并
