# AGENTS.md

## Cursor Cloud specific instructions

### Project overview

This is a **Godot 4.6** blank game template (`godot-go`). It uses **GL Compatibility** renderer and **Jolt Physics**. See `README.md` for full details.

### Godot binary

Godot 4.6 is installed at `/usr/local/bin/godot`. Verify with `godot --version`.

### Running the project headlessly

Since the Cloud VM has no display, always use `--headless`:

- **Import / regenerate cache:** `godot --headless --import` (run from repo root)
- **Run a scene:** `godot --headless <scene.tscn>`
- **Check GDScript syntax:** `godot --headless --check-only -s <script.gd>`

The blank template has no main scene by default; you must specify a scene file or script explicitly.

### Linting and formatting GDScript

`gdtoolkit` is installed (`pip install "gdtoolkit==4.*"`):

- **Lint:** `gdlint <file.gd>`
- **Format check:** `gdformat --check <file.gd>`
- **Auto-format:** `gdformat <file.gd>`

`gdtoolkit` binaries are in `~/.local/bin`; ensure this is on `PATH`.

### Gotchas

- `godot --headless --quit` hangs if no main scene is defined in `project.godot`. Always specify a scene file explicitly or use `--import` for project initialization.
- Godot's `Engine.get_version_info()["string"]` returns a `Variant`; use explicit `var x: String = ...` rather than `:=` for type-safe assignment.
- The `.godot/` directory is gitignored and regenerated automatically by `godot --headless --import`.
