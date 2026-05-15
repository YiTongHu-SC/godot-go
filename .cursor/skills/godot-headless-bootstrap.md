# Skill: Godot Headless Bootstrap

## 何时使用

- 新仓库首次在 Cursor Cloud 打开。
- `.godot/` 缓存缺失、损坏或切换分支后需要重建。

## 目标

- 在无图形界面的前提下完成项目导入并进入可验证状态。

## 标准步骤

1. 在仓库根目录执行导入：
   - `godot --headless --import`
2. 若需验证脚本解析链路，执行：
   - `godot --headless --check-only -s <script.gd>`
3. 若需运行逻辑，显式指定场景：
   - `godot --headless <scene.tscn>`

## 注意事项

- 不要使用 `godot --headless --quit` 作为探活。
- 不要假设存在 main scene；始终显式给出场景路径。

## 完成标准

- 导入命令退出码为 0。
- 后续脚本/场景验证命令可正常执行，无启动级错误。
