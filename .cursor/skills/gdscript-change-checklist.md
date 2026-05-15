# Skill: GDScript Change Checklist

## 何时使用

- 任意 `*.gd` 文件被新增、修改、重命名后。

## 目标

- 在提交前确保脚本格式、风格与语法都通过最小质量门禁。

## 标准步骤

1. 格式检查：
   - `gdformat --check <file.gd>`
2. Lint 检查：
   - `gdlint <file.gd>`
3. Godot 语法检查：
   - `godot --headless --check-only -s <file.gd>`
4. 若第 1 步失败，执行自动格式化并重跑 1~3：
   - `gdformat <file.gd>`

## 多文件批量建议

- 按改动文件逐个执行，避免“全量检查”带来的噪声。
- 对同一目录可先 `rg --files -g "*.gd" <dir>` 收集清单，再逐个检查。

## 完成标准

- 所有被改动的 `*.gd` 文件均通过三项检查。
- 终端输出无 error 级别报错。
