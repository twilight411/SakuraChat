# 推到 GitHub：twilight411/SakuraChat

本地已配置：

```text
git remote -v
# origin  https://github.com/twilight411/SakuraChat.git
```

你需要先在 GitHub **创建空仓库**（名称与下面一致），否则 `git push` 会报 `Repository not found`。

## 步骤

1. 浏览器打开：<https://github.com/new>
2. **Repository name**：`SakuraChat`（与本文一致即可）
3. **不要**勾选「Add a README」等（避免与本地已有提交冲突）。
4. 创建完成后，在本机执行：

```bash
cd D:\AAAagent\SakuraChat
git push -u origin main
```

5. 若提示登录：使用 **Personal Access Token（fine-grained 或 classic）** 代替密码，或配置 GitHub CLI `gh auth login`。

---

**说明**：若你更想用全小写仓库名（如 `sakura-chat`），可在 GitHub 上建该名，然后执行：

```bash
git remote set-url origin https://github.com/twilight411/sakura-chat.git
git push -u origin main
```

完成后可删除本说明文件，或保留作备忘。
