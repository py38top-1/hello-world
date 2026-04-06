Feature A

---

Fixed bug from `fix_bug/feature-A`

fix B

## `git reflog` 常用法

`git reflog` 用来查看本地 `HEAD` 和分支引用的变更历史。即使某次提交在 `git log` 看不到（例如被 reset 或 rebase 后），通常也可以在 `reflog` 找回。

常用命令：

- 查看最近操作记录：`git reflog`
- 查看某个分支的引用历史：`git reflog show feature-A`
- 结合日期过滤：`git reflog --date=local`

常见恢复场景：

- 误执行 `git reset --hard` 后恢复：
  1. 先用 `git reflog` 找到 reset 前的提交，如 `abc1234`
  2. 执行 `git reset --hard abc1234` 回到该提交
- 误删分支后恢复：
  1. 用 `git reflog` 找到原分支最后一次提交哈希
  2. 执行 `git checkout -b <new-branch> <commit>` 重新建分支

注意：`reflog` 是本地记录，不会推送到远程；记录会按 Git 垃圾回收策略过期。
