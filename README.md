# godot-go

**Godot 4.6 starter — GitHub template for new games.**

面向中文使用者的 Godot **4.6** 空白模板仓库，适合在 GitHub 上通过 **Use this template** 快速开新仓库。

## 环境要求

- [Godot 4.6](https://godotengine.org/download)（与 [`project.godot`](project.godot) 中 `config/features` 一致）
- 本模板使用 **GL Compatibility** 渲染；Windows 上默认使用 **D3D12** 作为渲染设备驱动（见 `project.godot` 的 `[rendering]`）

## Cursor：Godot MCP（可选）

本仓库在 [`.cursor/mcp.json`](.cursor/mcp.json) 中配置了 [Coding-Solo/godot-mcp](https://github.com/Coding-Solo/godot-mcp)，用于在 Cursor Agent 中启动编辑器、运行项目、抓取调试输出等（需本机已安装 Godot 与 Node.js）。

**前置条件**（与上游 README 一致）：

- 本机已安装 **Godot**（建议 4.x，与项目版本接近）
- **Node.js ≥ 18** 与 **npm**（供 `npx` 拉取 `@coding-solo/godot-mcp`）

**使用步骤**：

1. 重启 Cursor 或重新加载窗口，打开 **设置 → MCP**，确认 **godot** 已启用；必要时点击刷新以加载工具列表。
2. 若提示找不到 Godot，在 MCP 服务器环境变量中设置 **`GODOT_PATH`** 为 Godot 可执行文件的完整路径（Windows 示例：`C:\Program Files\Godot\Godot_v4.x_win64.exe`），或编辑 `.cursor/mcp.json` 里 `godot.env`（勿提交含个人路径的改动，可仅用本地覆盖）。
3. 在 **Agent** 对话中使用相关工具；首次会通过 `npx` 下载包，请保持网络可用。

官方说明与排错见：[godot-mcp README](https://github.com/Coding-Solo/godot-mcp#cursor)。

## 如何使用本模板

1. 在 GitHub 打开本仓库，点击 **Use this template**，创建你的新仓库。
2. 克隆新仓库到本地。
3. 用 Godot 4.6 **导入或打开** 项目根目录（包含 `project.godot` 的目录）。
4. 重命名项目：在编辑器中选择 **项目 → 项目设置 → 应用 → 配置名称**，或编辑 `project.godot` 里的 `config/name`（当前为 `godot-go`）。

## 版本控制说明

- **`.godot/`** 已被 [`.gitignore`](.gitignore) 忽略，不会提交到 Git。首次用编辑器打开项目时会自动生成；换机器克隆后同样会自动生成。
- 资源旁的 **`*.import`** 文件建议**保留在 Git 中**，用于统一导入设置（本仓库的 `.gitignore` **没有**忽略它们）。
- **`export_presets.cfg`** 已被忽略，避免把本机路径或敏感导出信息提交进仓库。需要导出时，在编辑器里 **项目 → 导出** 新建预设即可。若团队需要共享「无密钥」的预设，可自行维护 `export_presets.cfg.example` 并在文档中说明复制方式。

## 仓库内容（简要）

| 路径 | 说明 |
|------|------|
| `project.godot` | 项目配置 |
| `icon.svg` | 默认应用图标 |
| `.gitignore` | Git 忽略规则 |
| `.editorconfig` / `.gitattributes` | 文本与换行约定 |
| `.vscode/` | （可选）VS Code 工作区设置 |
| `.cursor/mcp.json` | （可选）Cursor MCP：Notion、Godot |

## 疑难

若历史上曾误把 `.godot/` 提交进 Git，可在仓库根目录执行：

```bash
git rm -r --cached .godot
```

然后提交变更；之后 `.godot/` 只留在本机。

## 许可证

本模板**不**附带固定许可证；使用本模板创建的项目，请由你或你的组织自行选择并添加 `LICENSE` 等文件。
