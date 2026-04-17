# 交接说明：给 SakuraChat 仓库的 Agent / 协作者

本文档总结**人类用户与本仓库相关的工作目标**、**已完成项**，以及建议你（另一 Agent）**接下来做什么**。读完应能独立继续「从零手敲复刻 Sky-Chat 型 AI 聊天应用」而不依赖口头上下文。

---

## 1. 项目是什么

| 项 | 说明 |
|----|------|
| 名称 | **SakuraChat** |
| 背景 | 武汉大学，个人**从零手敲**的练习项目 |
| 方向 | 整体产品形态、技术选型**对齐**本地参考仓库 **Sky-Chat**（Next.js App Router、Postgres、Prisma、NextAuth、shadcn 等），**不要求逐文件相同**，允许实现顺序与细节差异 |
| 与 Sky-Chat 关系 | Sky-Chat 是**只读参考**；本仓库**独立 Git**，代码不混在 Sky-Chat 里 |

远程仓库：<https://github.com/twilight411/SakuraChat>

---

## 2. 用户侧「我们已经做到哪了」

- [x] 练习项目从 Sky-Chat 旁侧拆出，目录 **`D:\AAAagent\SakuraChat`**（与 `D:\AAAagent\Sky-Chat` 并列）。
- [x] 本仓库已 `git init`、默认分支 **`main`**，已 **`git push`** 到 `origin`（远端现为**空壳 + 元文件**，尚无 Next 应用代码）。
- [x] 根目录已有 **`README.md`**、**`.gitignore`**、**`GITHUB-SETUP.md`**（推送说明，可选用后删除）。
- [x] Sky-Chat 根目录 **`.gitignore`** 含 **`/SakuraChat/`**，防止误把练习目录再塞进参考仓库。

**尚未开始（由你接手）**：在 **`SakuraChat` 根目录** 用官方脚手架创建 Next.js 应用、装依赖、`pnpm dev` 跑通——对应教程 **「03 第一阶段」** 及以后。

---

## 3. 分阶段教程在哪里（唯一详细步骤）

详细手敲流程写在 **Sky-Chat 仓库** 里（本仓库**不重复**全文，避免双份维护）：

| 说明 | 路径（本机若与用户对齐） |
|------|-------------------------|
| 总目录 | `D:\AAAagent\Sky-Chat\docs\Azero-shot-learn\README.md` |
| 你的第一步 | `...\03-第一阶段-创建Next脚手架.md` |

> 文件夹名仍叫 `docs/Azero-shot-learn` 表示「教程合集」；**练习项目仓库名**即为 **SakuraChat**。

若你只有本仓库、无 Sky-Chat 克隆：请让用户提供该路径，或将 `docs/Azero-shot-learn` 打包/复制进本仓库（可选，非必须）。

---

## 4. 建议你在本仓库执行的任务（按顺序）

### P0 · 脚手架（必做）

1. 工作目录确认为 **`SakuraChat` 根目录**（与 `README`、`.git` 同级）。
2. 按 `03-第一阶段-创建Next脚手架.md`：**`pnpm create next-app@latest`**（App Router、TypeScript、Tailwind、ESLint、`@/*`、无 `src` 等与文一致）。
3. `pnpm install`（若 create 未完成）→ **`pnpm dev`** 能打开欢迎页。
4. 提交：`git add` → `commit` → **`push`**。

### P1 · 目录与 UI 基线

- 建 `features/`、`server/`、`lib/`（见教程 `04`～`06`）。
- **shadcn** `init`，风格对齐参考项目的 `components.json` 思路（见 Sky-Chat）。

### P2 · 数据与认证

- PostgreSQL、`prisma init`、`.env` 中 **`DATABASE_URL`**（教程 `07`）。
- **NextAuth**、 **`AUTH_SECRET`**、OAuth 变量名以 **Sky-Chat `server/auth/auth.ts`** 为准（勿用错误过的 `AUTH_GOOGLE_ID` 等旧名）。

### P3 · 业务能力

- 会话、聊天 API、SSE、持久化等按教程 `09` **里程碑**拆；不必一次做完。

### 刻意不做（除非用户要求）

- 不必先对接 Sky-Chat 的 **`link:../sky-monitor-sdk`**；监控可后置或自研轻量埋点。

---

## 5. 环境变量命名提醒（对照 Sky-Chat 源码）

| 用途 | 变量名 |
|------|--------|
| Google / GitHub OAuth | `GOOGLE_CLIENT_*`、`GITHUB_CLIENT_*`（不是部分 README 里的 `AUTH_GOOGLE_ID`） |
| JWT / Middleware | `AUTH_SECRET` |
| NextAuth 对外 URL | `NEXTAUTH_URL` |
| 模型 API | `SILICONFLOW_API_KEY` 等，以参考项目为准 |

本仓库 `pnpm db:*` 类若以后与 Sky-Chat 一致封装，会读 **`.env`**；勿与 **`.env.local`** 混用导致 CLI 读不到变量。

---

## 6. Git 协作约定（建议）

- 主分支 **`main`**，小步提交、推送前 **`pnpm lint`**（等脚手架建好脚本后）。
- 不要在 SakuraChat 里 submodule 整个 Sky-Chat；需要时本地分屏打开两个文件夹即可。

---

## 7. 一句话摘要（给用户贴到别的对话）

> SakuraChat 是武汉大学零基础手敲的 AI 聊天项目，对齐本地 Sky-Chat；仓库已建好并 push，**下一步是在仓库根目录用 create-next-app 搭 Next 脚手架**，详细步骤在 **`Sky-Chat/docs/Azero-shot-learn/`**，从 **03** 开始执行。

---

*若本文件与 `README.md` 冲突，以本交接文件为 Agent 任务优先；面向用户的说明以 `README.md` 为准。*
