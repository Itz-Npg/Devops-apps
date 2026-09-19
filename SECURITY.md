# Security Policy

## Supported versions

| Version | Supported |
| --- | --- |
| 1.0.x | ✅ |

## Reporting a vulnerability

Please open a [private security advisory](https://github.com/Itz-Npg/Devops-apps/security/advisories/new)
or contact the maintainer directly. Do not open a public issue for security problems.

You will get a response within a few days. If the report is accepted, a patched release will be
published through the built-in updater, and you will be credited if you wish.

## Security model

- **Local-first.** All project data, credentials, and logs stay on your machine. The only
  outbound network calls the app makes are: update checks against this repository's releases,
  requests you explicitly make in the API client, database connections you configure, and
  `git fetch/pull/push` against your own remotes using your existing credentials.
- **No stored secrets.** Database passwords are entered at connect time and never written to
  disk. Environment-variable secrets are masked in the UI and require explicit reveal.
- **Updater integrity.** Updates are minisign-signed; the public key is embedded in the app and
  unsigned or wrongly-signed update files are rejected.
- **Process safety.** A protected-process allowlist always refuses to terminate system-critical
  processes. Port termination and process termination both require explicit confirmation.
- **Least privilege.** The installer requires no administrator rights and installs only for the
  current user. Tauri IPC access is capability-scoped in `src-tauri/capabilities`.
