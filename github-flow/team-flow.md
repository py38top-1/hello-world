# Team GitHub Flow 规范版

## 目标

统一团队协作方式，保证 `main` 随时可发布、变更可追踪、问题可回滚。

## 1) 分支规范

- 长期分支仅保留：`main`
- 任务分支从 `main` 拉出，命名格式：
  - `feature/<ticket>-<short-desc>`
  - `fix/<ticket>-<short-desc>`
  - `chore/<short-desc>`
- 分支生命周期：合并后删除远端分支

## 2) 提交规范

- 使用 Conventional Commits：
  - `feat: ...`
  - `fix: ...`
  - `docs: ...`
  - `refactor: ...`
  - `chore: ...`
- 单次提交保持单一意图（一个提交只做一件事）
- 提交前本地自检通过（格式化、测试、lint）

## 3) Pull Request 规范

- 小步 PR：建议控制在可审查范围内（如 < 300 行有效变更）
- PR 标题遵循提交前缀（`feat:`/`fix:` 等）
- PR 描述至少包含：
  - 变更目的
  - 变更范围
  - 验证步骤
  - 风险与回滚方式
- 关联任务单（Issue/Ticket）为必填项

## 4) 评审与合并门禁

- 至少 1 位 reviewer Approve（核心模块建议 2 位）
- 必须通过 CI（测试、lint、构建）
- 禁止直接 push 到 `main`
- 推荐 `Squash and merge`，保持 `main` 历史简洁

## 5) 发布与回滚

- 合并到 `main` 后自动触发部署
- 发布失败优先回滚到最近稳定版本
- 回滚后必须补充复盘与修复计划

## 6) 标准操作步骤

```bash
# 1. 同步主分支
git switch main
git pull

# 2. 创建任务分支
git switch -c feature/123-add-login-banner

# 3. 开发并提交
git add .
git commit -m "feat: add login banner"
git push -u origin feature/123-add-login-banner

# 4. 发起 PR（在平台上补全描述与检查项）

# 5. 审核通过后合并，删除分支
```

## 7) 团队建议

- 每天至少同步一次 `main`，减少大规模冲突
- 冲突优先在分支内解决，不把冲突带入 `main`
- 避免超大 PR，降低评审成本并提升交付速度
