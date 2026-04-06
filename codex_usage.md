# 如何让 Codex 在执行前尽量遵循 AGENTS.md

简短结论：仅靠 `AGENTS.md` 不能做到 100% 强制，但可以通过“规则 + 提示 + 校验”三层方式，让 Codex 在执行前基本按规范工作。

1. 在仓库根目录放置 `AGENTS.md`  
路径建议：`/var/opt/repos/github/py38top/hello-world/AGENTS.md`  
让 Codex 能在项目上下文中直接读取到约束。

2. 每次任务开头显式要求先读规则  
固定开场语可用：  
`先读取 AGENTS.md，列出你将遵守的约束，再开始执行任务。`

3. 用 CI 做最终强制门禁  
即使 Codex 漏掉某条规则，也通过自动检查阻止合并（如 lint、test、格式化、安全检查）。  
当前仓库已包含一个基础门禁：`.github/workflows/quality.yml`。

4. 在任务模板中加入“执行前检查”  
在 `plans/TASK_TEMPLATE.md` 的第一步写明：  
`先读取 AGENTS.md 并复述本次范围与约束。`

5. 需要更强约束时，使用本地包装命令  
通过脚本或 alias 固定给 Codex 追加前置指令，例如：  
`codex "先读取 AGENTS.md 并遵守其规则。<你的任务>"`

## 推荐实践

- 把 `AGENTS.md` 当“行为约束层”。  
- 把任务开场提示当“执行触发层”。  
- 把 CI 当“结果验证层”。  

三层同时存在时，效果最好、稳定性最高。
