# 豆包 + GitHub｜计划任务 Prompts

这里保存需要由豆包按时间主动触发的任务 Prompt。计划任务负责定义触发时间和 GitHub 记录仓库，具体执行方式仍以对应 Skill 为准。

## 当前任务

- [`weekly-review.md`](weekly-review.md)：每周回看 GitHub 记录仓库中最近七天的 `journals/` 和 `notes/`，把回看档案保存到 `reviews/`，并返回问题与可能发展的方向；不会在定时运行中直接生成文章或在 `practices/` 中创建实践。
- [`break-bubble.md`](break-bubble.md)：每隔一天推荐一个经过核实、与现有关注有距离的资源；完成前不入库，等用户明确说“完成了”后再保存到 GitHub 的 `notes/`。

## 使用前

1. 先按照[上一级 README](../README.md) 添加并授权 GitHub 插件或工具，指定唯一的记录仓库，确认豆包可以真实读取、创建和更新文件。
2. 确认仓库中已有 `journals/` 与 `notes/`；`reviews/` 与 `practices/` 可在首次产生内容时创建。
3. 将所需 Prompt 的完整内容复制给豆包，并按自己的需要调整星期、时间、频率和时区。
4. 建立计划任务前先手动运行一次，确认它使用的是正确的 Skill、GitHub 仓库和目录。
5. 计划任务中写明 `YOUR_GITHUB_USERNAME/YOUR_REPOSITORY`；不要让豆包猜测目标仓库。

## 如何选择

- 想让过去一周的记录定期回来，使用 `weekly-review.md`。
- 想定期接触现有信息源之外的内容，使用 `break-bubble.md`。

计划任务只是触发器。如果要改变如何回看、如何筛选资源或如何写入 GitHub，应修改对应 Skill，而不是把整套工作流重复写进 Prompt。
