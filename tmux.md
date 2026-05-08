# tmux 基本用法

基于上海交大 HPC 文档整理，面向快速上手。

## 1. tmux 是什么

`tmux` 是终端复用器。你可以在一个 SSH 会话里创建多个会话/窗口/面板，并且断线后继续恢复现场。

## 2. 会话管理

- 新建会话：`tmux new -s mysession`
- 查看会话：`tmux ls`
- 连接会话：`tmux attach -t mysession`
- 从会话暂时离开（不结束任务）：`Ctrl-b d`
- 结束会话：`tmux kill-session -t mysession`

说明：`Ctrl-b` 是默认前缀键，后续快捷键都先按前缀键。

## 3. 窗口（window）操作

- 新建窗口：`Ctrl-b c`
- 切换下一个窗口：`Ctrl-b n`
- 切换上一个窗口：`Ctrl-b p`
- 按编号切换窗口：`Ctrl-b 0~9`
- 重命名当前窗口：`Ctrl-b ,`
- 关闭当前窗口：`Ctrl-b &`

## 4. 面板（pane）操作

- 水平分屏：`Ctrl-b "`
- 垂直分屏：`Ctrl-b %`
- 在面板间切换：`Ctrl-b 方向键`
- 关闭当前面板：`exit` 或 `Ctrl-d`
- 临时放大/还原当前面板：`Ctrl-b z`

## 5. 复制与滚动（Copy Mode）

- 进入复制模式：`Ctrl-b [`
- 在复制模式中用方向键或 `PageUp/PageDown` 滚动
- 退出复制模式：`q`

常见终端里可直接用鼠标选中复制；如果启用了 tmux 鼠标模式，也可在 copy mode 中完成选择。

## 6. 退出与恢复

- 断开但保留任务：`Ctrl-b d`
- 重新连接：`tmux attach -t <session>`
- 服务器断线后，重新 SSH 登录再 `attach` 即可恢复

## 7. 最小上手流程

```bash
# 1) 登录服务器后创建会话
tmux new -s work

# 2) 在窗口 1 跑训练/编译任务
python train.py

# 3) 新开窗口查看日志
# 按 Ctrl-b c
tail -f train.log

# 4) 临时离开会话（任务继续跑）
# 按 Ctrl-b d

# 5) 下次登录恢复
tmux attach -t work
```

## 8. 速查键位

- 前缀键：`Ctrl-b`
- 分离会话：`Ctrl-b d`
- 新窗口：`Ctrl-b c`
- 分屏：`Ctrl-b "` / `Ctrl-b %`
- 切 pane：`Ctrl-b 方向键`
- 复制模式：`Ctrl-b [`

## 9. Copy Mode 实操（如何复制文本）

默认配置下可按下面步骤操作：

1. 按 `Ctrl-b [` 进入 copy mode
2. 移动光标到复制起点（方向键或 `PageUp/PageDown`）
3. 按 `Space` 开始选择
4. 移动光标到复制终点
5. 按 `Enter` 完成复制（内容进入 tmux buffer）
6. 在目标位置按 `Ctrl-b ]` 粘贴

补充：

- 退出 copy mode：`q`
- 如果配置为 `vi` 键位，常见是 `v` 开始选择、`y` 复制（取决于配置）
