# 让记录有下文｜豆包 + GitHub 版

**Capture. Reflect. Practice.**

这是一个与 AI 协作的个人记录、回看与实践系统，也是 **豆包 + GitHub** 路径的独立配置仓库。

在这条路径中：

- 豆包负责接住对话、执行 Skill 和触发计划任务；
- GitHub 负责长期保存 Markdown 记录与后续产物；
- 仓库初始只准备 `journals/` 与 `notes/` 两个记录目录；需要回看或实践时，再由对应 Skill 创建 `reviews/` 或 `practices/`。

## 两类记录

- [journals/](journals/README.md)：发生在自己身上的事，包括经历、感受、身体经验和当时还说不清的东西。
- [notes/](notes/README.md)：来自外部世界的输入，包括书、文章、播客、视频、课程和对话。

二者都按年月保存：

```text
journals/{YYYY}/{YYYYMM}/{YYYYMMDD}-周X-{关键词}.md
notes/{YYYY}/{YYYYMM}/{YYYYMMDD}-{关键词}.md
```

## 包含的 Skills

- [capture-journal](skills/capture-journal/SKILL.md)：记录亲历事件、感受和身体经验，写入 GitHub 仓库的 `journals/`。
- [capture-note](skills/capture-note/SKILL.md)：保存文章、播客、书、视频和对话等外部输入，写入 `notes/`。
- [weekly-review](skills/weekly-review/SKILL.md)：读取最近七天的日记和笔记，提出问题，并在第一次使用时创建 `reviews/` 保存回看档案。
- [new-article](skills/new-article/SKILL.md)：围绕选定主题召回材料、追问表达，并持续更新文章草稿。
- [develop-practice](skills/develop-practice/SKILL.md)：把有重复、行动或反馈证据的线索发展为持续实践。
- [bubble-breaker](skills/bubble-breaker/SKILL.md)：发现一个陌生资源，完成后再留下轻量记录。

GitHub 版本统一保存 Markdown，因此不包含飞书版专用的 `capture-journal-feishudoc`。

## 开始使用

1. 如果要保存真实日记，建议先把仓库设为 **Private**。
2. 填写 [PROFILE.md](PROFILE.md) 中的时区、语言与隐私边界。
3. 创建或打开一个豆包智能体，添加能够读取和写入 GitHub 仓库的插件或工具，并完成 GitHub 授权。
4. 打开准备使用的 `skills/<skill-name>/SKILL.md`，先把其中的 `YOUR_GITHUB_USERNAME/YOUR_REPOSITORY` 替换成自己的 `owner/repository`，再把完整内容安装为豆包 Skill。
5. 先安装并测试 `capture-journal` 或 `capture-note`：使用一条不敏感的内容，确认豆包能读取目标仓库、创建或更新 Markdown 文件，并返回真实的 GitHub 文件链接或 commit 结果。
6. 基础读写确认成功后，再根据[计划任务说明](scheduled-task-prompts/README.md)配置 `weekly-review` 或 `bubble-breaker`。

只有 GitHub 返回写入或提交成功，才算持久化完成。豆包运行环境中的临时文件、待复制正文或模拟命令都不算已经保存。

> 豆包没有 Project Settings，单独安装的 Skill 也不会自动继承本 README。因此目标仓库必须写进每一份 Skill。这里的重复是有意保留的，不能只在一处配置。

## GitHub 写入约定

- 每次操作前确认目标仓库；没有已配置仓库时先询问，不猜测用户名或仓库名。
- 默认在仓库的默认分支上创建或更新文件；若仓库规则要求 Pull Request，则遵循仓库规则。
- 更新已有文件前先读取最新内容，保留不属于本轮的原文，并避免覆盖并发修改。
- 同一条记录优先更新原路径，不创建 `v2`、`final` 或重复副本。
- 成功后返回仓库相对路径，以及 GitHub 文件链接或 commit 结果。

## 术语约定

- `journal entry`、`note`、`review` 和 `practice` 表示单个内容或概念。
- `journals/`、`notes/`、`reviews/` 和 `practices/` 表示 GitHub 仓库中的真实目录；目录名始终使用小写复数、反引号和结尾斜杠。
- Skill 名称使用小写连字符并放在反引号中，例如 `capture-note` 和 `weekly-review`。

## 仓库目录

```text
.
├── journals/                 # 初始记录目录
├── notes/                    # 初始记录目录
├── skills/
│   ├── capture-journal/
│   ├── capture-note/
│   ├── weekly-review/
│   ├── new-article/
│   ├── develop-practice/
│   └── bubble-breaker/
├── scheduled-task-prompts/
│   ├── weekly-review.md
│   └── break-bubble.md
├── PROFILE.md
└── README.md
```

`reviews/` 与 `practices/` 不在初始结构中占位；第一次真正产生相应内容时再创建。

## 其他版本

- [豆包 + 飞书版](https://github.com/sunling/capture-reflect-practice-doubao-feishu)
- [ChatGPT + GitHub 版](https://github.com/sunling/capture-reflect-practice)

## 隐私提醒

- 不要把密码、身份证件、支付信息、住址等敏感信息写入仓库。
- 公开仓库的 Git 历史会保留曾经提交过的内容；之后删除文件，并不等于历史中的内容自动消失。
- 分享截图或示例前，检查姓名、联系方式、二维码和第三方隐私。
- 真实记录是否进入 GitHub，以及仓库是否公开，由使用者自己决定。

本项目采用 [MIT License](LICENSE)。
