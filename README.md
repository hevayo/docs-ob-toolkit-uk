# docs-ob-toolkit-uk

A Content repo of WSO2 Docs. On the `docs-v2/` branches it holds one Doc space:

| Directory | Doc space | Editions and branches |
|---|---|---|
| `open-banking-uk-toolkit/` | Open Banking UK Toolkit | 1.0.0 on `docs-v2/main` |

Docs releases are tagged `<version>-docs.<n>`; tags carry no `docs-v2/`.

Until the cutover, `main` is still the legacy Docusaurus site and its GitHub Pages deploy, and writers still merge there. `docs-v2/main` is the WSO2 Docs main line. Its pages are converted from the legacy branches by the site rebuild (`tools/rebuild/open-banking/` in the onboarding workspace), not merged: don't edit them by hand until the cutover. At the cutover a PR merges `docs-v2/main` into the default branch and the `docs-v2/` prefix goes.

The Doc space directory holds `docspace.yaml` (the Doc space manifest), `editions.yaml` (per-Edition variables), `redirects.yaml` (page moves), `docs/` (pages; folders are the menu), `partials/` and `assets/` (images and downloads).

The repo root holds only shared files: this README, `CODEOWNERS`, the release workflow (`.github/workflows/docs-bundle-release.yml`; it releases from `docs-v2/main` and the `docs-v2/` release branches), the branch ruleset (`.github/branch-ruleset.json`), the editor settings, the issue templates (`.github/ISSUE_TEMPLATE/`, `issue_template.md`) and the pull request template, and `AGENTS.md` and `CLAUDE.md` for agents (they point to `npx @wso2-enterprise/docs help`). The Platform-managed files come from `templates/content-repo/` in `wso2-enterprise/choreolabs-docs`.

The tools are on GitHub Packages. Once per machine, make a classic personal access token with `read:packages` (authorised for the `wso2-enterprise` organisation's SSO if it asks), then run `npm login --scope=@wso2-enterprise --auth-type=legacy --registry=https://npm.pkg.github.com` with your GitHub user name and the token as the password. This repo's `.npmrc` names the registry for `@wso2-enterprise`; it holds no token.

Get started, from setting up your computer to a Docs release going live: the WSO2 Docs Platform's README, https://github.com/wso2-enterprise/choreolabs-docs#readme.
