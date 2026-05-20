# Workspace Linking — ARG Slash Commands

Link any workspace to this repo's `.windsurf/` folder so all `/arg-*` slash commands are available there without copying files.

## Symlink Command (Linux / macOS)

```bash
ln -s /home/smit/TestBench/ARG-Researcher/.windsurf /path/to/YOUR_PROJECT/.windsurf
```

## Examples

```bash
# Skeleton Research Paper
ln -s /home/smit/TestBench/ARG-Researcher/.windsurf /home/smit/TestBench/Skeleton_Research_Paper/.windsurf

# Any new project
ln -s /home/smit/TestBench/ARG-Researcher/.windsurf /home/smit/YOUR_PROJECT/.windsurf
```

## How It Works

- Windsurf reads `.windsurf/workflows/` in the active workspace for slash commands.
- The symlink makes the target workspace point to this repo's `.windsurf/` directory.
- Any updates to workflows here are instantly reflected in all linked workspaces.

## Remove a Link

```bash
rm /path/to/YOUR_PROJECT/.windsurf
```

> **Note:** Use `rm`, not `rm -rf` — you're removing the symlink, not the actual folder.
