# 推到 GitHub：twilight411/Azero-shot-learn

本地已配置：

```text
git remote -v
# origin  https://github.com/twilight411/Azero-shot-learn.git
```

你需要先在 GitHub **创建空仓库**（与本机仓库名一致），否则 `git push` 会报 `Repository not found`。

## 步骤

1. 浏览器打开：<https://github.com/new>
2. **Repository name**：`Azero-shot-learn`
3. **不要**勾选「Add a README」等（避免与本地已有提交冲突）。
4. 创建完成后，在本机执行：

```bash
cd D:\AAAagent\Azero-shot-learn
git push -u origin main
```

5. 若提示登录：使用 **Personal Access Token（fine-grained 或 classic）** 代替密码，或配置 GitHub CLI `gh auth login`。

---

完成后可删除本说明文件，或保留作备忘。
