# AGENTS.md

## Project conventions

- This repository contains Zsh and tmux configuration. See `README.md` for
  dependencies, installation, and usage; update it when setup changes.
- Keep ordinary tmux customizations in `.tmux.conf.local`; `.tmux.conf` is the
  bundled Oh my tmux! base configuration.
- Preserve nearby formatting, section comments, quoting, tmux format expressions,
  and version guards. Use four spaces in Zsh conditional bodies, lowercase helper
  names, uppercase exported settings, and existing `tmux_conf_*` options.
- Keep personal settings in `~/.workrc/rc.local`. Never commit credentials or
  machine-specific secrets; preserve existing configuration during installation.

## Validation

- Run `zsh -n .zshrc` for Zsh changes, `sh -n setup.sh` for setup script changes,
  and `git diff --check` for all changes. There is no build or automated test suite.
- Manually exercise affected shell behavior, tmux bindings, popups, and status
  colors. Report the OS, terminal, and tmux version for manual checks, and include
  screenshots for visual changes. Distinguish manual checks from syntax checks.
- For isolated tmux validation, run
  `tmux -L term-conf-review -f "$PWD/.tmux.conf" new-session` and exit when done.

## Commits and pull requests

- Use focused Conventional Commits: `type(scope): description`.
- Pull requests should describe behavior changes, affected files, validation,
  dependency or version requirements, and relevant issues.

## Commit attribution

- When preparing a commit message for changes that Codex contributed to, append
  the following trailer after a blank line:

  ```text
  Co-authored-by: Codex <noreply@openai.com>
  ```

- Preserve the human author's Git identity and any existing co-author trailers.
- Do not attribute changes to Codex when it did not contribute to them.
- This attribution rule does not authorize committing, pushing, or rewriting
  existing commits; perform those actions only when explicitly requested.
