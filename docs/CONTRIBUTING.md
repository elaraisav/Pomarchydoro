# Contributing to Pomarchydoro

Thanks for your interest in contributing. Pomarchydoro is a Pomodoro timer and task tracker plugin for [Omarchy](https://github.com/omacom/omarchy), written in QML for [quickshell](https://quickshell.org/). It is a fork of [Omodoro](https://github.com/Pnkm0nK/Omodoro) by Pnkm0nK and is licensed under GPL-3.0.

## Workflow at a glance

1. [Fork](https://github.com/elaraisav/Pomarchydoro/fork) the repository and clone your fork:
   ```bash
   gh repo fork elaraisav/Pomarchydoro --clone
   ```
2. To keep your fork up to date, fetch from the `upstream` remote before starting a new branch. `gh` adds this remote for you; if `git remote -v` doesn't list it, add it:
   ```bash
   git remote add upstream https://github.com/elaraisav/Pomarchydoro.git
   ```
   Then fetch:
   ```bash
   git fetch upstream
   ```
3. Create a branch, ideally from an up-to-date `main`, named as described in [Branch naming](#branch-naming).
4. Make your change in small, focused commits ([Commit messages](#commit-messages)).
5. Push the branch to your fork:
   ```bash
   git push -u origin <branch>
   ```
6. Open a pull request from your branch to `main` in this repository, either with the "Compare & pull request" button on GitHub or with:
   ```bash
   gh pr create
   ```
7. The change is reviewed and merged by the maintainer. A change that works, follows these guidelines and fits the project's goals will most likely be merged without fuss. If something needs adjusting, you'll be asked to change it.

## Protected `main`

`main` is protected: changes go through pull requests and are not pushed directly. Automated checks (such as code scanning) run on pull requests.

Please don't change files under `.github/` without discussing it in an issue first.

## Branch naming

Use `<prefix>/<short-kebab-case-description>`, for example `feature/countdown-in-bar`.

| Prefix      | Use for                                                          |
|-------------|------------------------------------------------------------------|
| `feature/`  | New features or functionality                                    |
| `bugfix/`   | Fixing bugs in the code                                          |
| `hotfix/`   | Urgent patches that cannot wait                                  |
| `design/`   | User interface or user experience updates                        |
| `refactor/` | Improving code structure without changing behaviour              |
| `test/`     | Writing or improving automated tests                             |
| `doc/`      | Documentation updates                                            |
| `chore/`    | Repository maintenance with no user-facing effect (CI, dependencies, tooling, configuration) |

### Keep branches focused

As a rule of thumb, each branch and pull request does one thing. If a change fits more than one prefix, use the one that describes its main purpose.

For example:

- Documentation that describes your change (a README line for your new feature) usually belongs in the same pull request, as its own `docs:` commit.
- Unrelated fixes, formatting or cleanups are usually better in their own branch and pull request.

These are guidelines, not strict rules. Use your judgment, and the maintainer may ask you to split or combine changes if it makes review easier.

## Commit messages

This project follows [Conventional Commits](https://www.conventionalcommits.org/): `<type>: <summary>`, in the imperative mood, for example `fix: keep timer in sync across monitors`.

| Branch prefix        | Commit type       |
|----------------------|-------------------|
| `feature/`           | `feat`            |
| `bugfix/`, `hotfix/` | `fix`             |
| `design/`            | `feat` or `style` |
| `refactor/`          | `refactor`        |
| `test/`              | `test`            |
| `doc/`               | `docs`            |
| `chore/`             | `chore`           |

If the title fully explains the change, that is enough. Otherwise add a short body explaining what changed and why, using bullets rather than prose where possible.

## Pull requests

- Target `main` and keep the pull request focused on one change.
- Describe what changed and why. Link a related issue if there is one.
- For code changes, say how you tested it.
- For UI changes, attach a screenshot to the pull request itself. Do not commit screenshots to the repository.

## AI-assisted contributions

Using AI tools is fine. What matters is that the code follows good practice and that you have reviewed and tested it yourself before submitting. You are responsible for what you submit.

## Testing a change

There is no automated test suite. Before opening a pull request:

- Check the plugin against Omarchy's rules:
  ```bash
  omarchy plugin validate .
  ```
- Run your change in Omarchy and try the affected feature.

Omarchy reloads a plugin when you save a file in its folder under `~/.config/omarchy/plugins/`. If you keep your clone elsewhere and symlink it into that folder, Omarchy doesn't watch it, so reload the Omarchy shell yourself after each change.

See the [Omarchy shell plugins manual](https://omarchy.org/manual/shell-plugins/). Use whatever setup works for you.

## Licensing

Contributions are licensed under [GPL-3.0](../LICENSE). Do not remove the existing copyright and attribution notices.

## Bugs

Open a GitHub issue with steps to reproduce and your Omarchy version.

## Security issues

Please don't report vulnerabilities in public issues. See the [security policy](SECURITY.md).
