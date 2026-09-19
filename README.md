# DEVOS — Developer Workspace

<p align="center">
  <a href="https://github.com/Itz-Npg/Devops-apps/releases/latest"><img alt="Download DEVOS 1.0.0" src="https://img.shields.io/badge/Download-DEVOS%201.0.0-blue?style=for-the-badge&logo=github" /></a>
  <img alt="Platform" src="https://img.shields.io/badge/platform-Windows%2010%2F11%20x64-0078D4?style=for-the-badge" />
  <img alt="License" src="https://img.shields.io/badge/license-MIT-green?style=for-the-badge" />
</p>

<p align="center">
  <strong>A local-first Windows desktop developer workspace.</strong><br/>
  Projects · Terminal · Git · Dev Servers · Docker · Databases · API Client · Environments · System Monitor
</p>

---

## ⬇️ Download & install

1. Go to the **[latest release](https://github.com/Itz-Npg/Devops-apps/releases/latest)**.
2. Download **`DEVOS_1.0.0_x64-setup.exe`** from the release assets.
3. Run it — that's all.

**No admin rights needed** (installs just for your user), **no extra downloads** (WebView2 is
downloaded automatically during setup if you don't have it), **no account or sign-in of any kind**.
You get a Start Menu entry, an optional desktop shortcut, and a clean uninstaller in Windows
Settings → Apps.

> Don't want the installer? A portable-style MSI (`DEVOS_1.0.0_x64_en-US.msi`) is also attached
> to the release for environments that prefer MSI deployment.

### Updating

DEVOS checks GitHub releases automatically and tells you in-app when a new version is out —
one click updates it in place. You never need to visit this page again unless you want to.

## What is DEVOS?

DEVOS is a production-quality desktop application for Windows that puts your whole dev workflow
in one window. It is not a dashboard mockup: every control performs a real operation on your
machine — real PTY terminals, real Git operations via libgit2, real process spawning and
tracking, real Docker CLI calls, and real SQL execution. When an external dependency is missing,
DEVOS says so plainly and tells you how to fix it instead of faking success.

## Features

### Workspace
- **Dashboard** — live current-project status, dev servers, Git state, CPU/RAM, Docker summary, quick actions
- **Project manager** — create, import, favorite, archive, tag, and remove projects (files are never deleted without explicit confirmation)
- **Auto-detection** — detects Node, npm/pnpm/yarn/bun, TypeScript, Python/Poetry/uv/venv, Rust/Cargo, Java/Maven/Gradle, PHP/Composer, Go, .NET, Docker, .env files
- **Project scripts** — reads `package.json` scripts and runs them as managed processes with live logs
- **Template bootstrap** — scaffolds React+Vite, Next.js, Node, Rust, Python or empty projects using the official CLIs, after verifying the required runtime is installed

### Development
- **Terminal** — real PTY sessions (PowerShell, CMD, Git Bash, WSL) rendered with xterm.js; multiple tabs, ANSI colors, resize, search, copy/paste, kill
- **Dev server manager** — start/stop/restart managed servers with PID, port, uptime, exit codes, and streaming stdout/stderr; optional bounded auto-restart
- **Port manager** — live listening-port table with owning process names; terminate with confirmation (protected system processes are always refused)
- **Git** — status, stage/unstage/discard, commit, branches (create/checkout/delete), log, unified diff viewer, stash/pop, reset, fetch/pull/push, remotes, tags, clone/init
- **Docker** — containers and images via the Docker CLI with start/stop/restart/pause/remove, logs, and inspect; honest "not installed" state with setup guidance
- **Databases** — saved connections for SQLite, PostgreSQL, MySQL; SQL editor with results grid, timing, and query history (passwords are never stored)
- **API client** — GET/POST/PUT/PATCH/DELETE/HEAD with headers, bodies, response status/time/size, headers and body panes, and request history

### Tools
- **Environment manager** — per-project variables with secret masking, .env import/export, reveal protection for secrets
- **Process manager** — searchable process list with CPU/RAM/command, terminate with confirmation and a protected-process allowlist
- **System monitor** — CPU/RAM/network/uptime meters with history charts, disk usage, and one-click diagnostics export
- **Log center** — unified application log with level filters, search, export, and clear
- **Task manager** — Todo / In Progress / Blocked / Done board with priorities, due dates, tags, project links
- **File search** — filename and content search with regex support and standard exclusions (`node_modules`, `.git`, `target`, …)
- **File explorer** — browse, preview, and edit project files with a saveable preview pane
- **Command palette** — `Ctrl+K` global search across views, projects, and commands
- **Crash recovery** — detects processes left running from a previous DEVOS session and offers Stop All / Ignore

## Security & privacy

- **Local-first:** your projects, credentials, and data never leave your machine. DEVOS talks to
  GitHub only to check for updates.
- **No secrets stored:** database passwords are asked for at connect time and never persisted;
  environment secrets are masked by default.
- **Protected processes:** system-critical processes are always refused for termination, with
  or without confirmation.
- Full security model: see [SECURITY.md](SECURITY.md).

## Troubleshooting

| Symptom | Resolution |
| --- | --- |
| "Docker is not installed or unavailable" | Install/launch Docker Desktop and ensure `docker` is on PATH, then refresh |
| "executable 'npm' was not found on PATH" | Install Node.js or fix PATH; DEVOS never guesses your toolchain |
| Terminal shows "No shells detected" | DEVOS looks for PowerShell/CMD/Git Bash/WSL on PATH; install at least one |
| Git push fails with credential error | Configure an SSH agent or Git credential helper; DEVOS uses your existing credentials, never stored ones |
| App claims a port is in use | Port Manager shows the owning PID; confirm before terminating |
| Installer asks about WebView2 | Let it download automatically — it's Microsoft's official bootstrapper |

## Release notes — 1.0.0

First stable release. Highlights versus earlier builds:

- File Explorer preview pane is now **editable with save**
- Fixed folder expansion in File Explorer, updater endpoint, and error surfacing
- Installer is now **per-user** — no administrator prompt, WebView2 handled automatically
- Built-in auto-updater enabled (signed updates from this repository)

## License

MIT — see [LICENSE](LICENSE). This repository distributes installer releases only; the
application is provided as a ready-to-run download.
