# gitcleared-demo

A demo repository for App Store review of
[GitCleared](https://github.com/hollandcloud/gitcleared), the menu bar app that
clears held GitHub deployments and merges green pull requests.

**Nothing here is real.** The "site" is one static page and the "deploy" only
prints a line. The repository exists so that, signed in with a token scoped to
it, GitCleared has something to show:

- **Holding** — a run of *Deploy* waiting at the `production` environment, which
  requires approval.
- **Ready to merge** — an open pull request whose check has passed.
- **In flight** — a draft pull request.
- **Start a workflow** — *Deploy* can be started by hand, with inputs.

## Before each review

Approving the held deployment uses it up, and GitHub drops a waiting run after
30 days. To put one back:

```sh
gh workflow run deploy.yml -R hollandcloud/gitcleared-demo
```
