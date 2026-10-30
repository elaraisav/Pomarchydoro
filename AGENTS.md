# AGENTS.md

Pomarchydoro is a Pomodoro timer and task tracker plugin for Omarchy, written in QML for quickshell. It is a GPL-3.0 fork of Omodoro by Pnkm0nK.

## Layout

- `manifest.json`: plugin identity and entry points
- `Service.qml`: timer logic, notifications, sounds, and state persistence (`~/.local/state/omarchy/pomarchydoro.json`)
- `BarWidget.qml`: the bar widget
- `Panel.qml`: the panel UI
- `sounds/`: bundled tick sounds (credits in `CREDITS.md`)
- `docs/`: `CONTRIBUTING.md` and `SECURITY.md`

## Rules

- Follow `docs/CONTRIBUTING.md`: work on a prefixed branch and use Conventional Commits. Never push directly to `main`; changes go through pull requests.
- The plugin ID (`elaraisav.pomarchydoro`) appears in `manifest.json`, the three QML files and the README. Keep them in sync, and don't rename the ID or the state file unless asked, because that breaks installs and saved data.
- Keep `LICENSE`, the README attribution and `CREDITS.md` intact.
- Don't change anything under `.github/` unless the maintainer has agreed, for example in an issue.
- There is no automated test suite. Run `omarchy plugin validate .` and try the change in Omarchy. If the clone is symlinked into the plugins folder, reload the Omarchy shell after edits.
- Don't force-push, merge pull requests or delete branches on your own initiative. Do it only when the person you're working with asks.
- AI-assisted changes must be reviewed and tested by the person who submits them.
