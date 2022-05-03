# Release Strategy

Experimentatal release strategy for a React app

Topics:

- versioning
- branching
- release
- dependency management

## semantic-release

[semantic-release](https://github.com/semantic-release/semantic-release) is run via [GitHub Actions](https://github.com/features/actions)

## commitlint

[commitlint](https://github.com/conventional-changelog/commitlint) is run as a pre-commit hook using [husky](https://github.com/typicode/husky) to enforce commit message format

## Deployment to dev

When a PR is created targeting the main branch the changes are automatically deployed to a temporary environment. When the PR is closed the temporary environment is destroyed. If the PR is merged the changes are deployed to the dev environment.

## Deployment to staging

Create a new release branch:

```bash
git checkout -b releases/1
git push origin releases/1
```
