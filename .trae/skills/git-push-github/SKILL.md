---
name: git-push-github
description: 提交当前项目并通过 git commit 和 push 推送到 GitHub 远程仓库 https://github.com/dgagda/guanzhongyu.git。当用户要求"提交到github"、"push到github"、"上传到github"、"github推送"、"提交代码到github"等 git 提交推送操作时使用此技能。
---

## 功能
将当前项目所有变更提交并推送到 GitHub 远程仓库。

## 工作流程

1. **检查状态**：运行 `git status` 查看当前变更
2. **配置远程仓库**：检查是否已配置远程地址（`git remote -v`），若未配置则添加：
   ```
   git remote add github git@github.com:dgagda/guanzhongyu.git
   ```
   若已配置但地址不对，使用 `git remote set-url github` 更新
3. **暂存文件**：`git add .`
4. **提交变更**：`git commit -m "提交信息"`（提交信息应简洁描述本次变更内容）
5. **推送到远程**：`git push -u github master`（首次推送）或 `git push github`（后续推送）

## 注意事项
- 推送前确认所有文件已暂存
- 提交信息使用中文，简洁明了
- 如果推送被拒绝（远程有更新），先 `git pull github master --rebase` 再推送
- 不要提交敏感信息（密码、密钥等）
- SSH 公钥已配置，优先使用 SSH 地址（git@github.com:dgagda/guanzhongyu.git）免密推送
