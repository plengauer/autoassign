A Github action to automatically autoassign stale PRs to the repo owner.

Use it like this:
```yaml
name: Autoassign

on:
  schedule:
    - cron: '0 0 * * 0' # TODO autoassign stale PRs

jobs:
  assign:
    runs-on: ubuntu-slim
    permissions:
      pull-requests: write
    steps:
      - uses: plengauer/autoassign@main # TODO pin to a version if needed
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }} # TODO token for GITHUB for the user to approve the PRs with (if a custom token is used that is not the built-in token, set permissions above)
```
