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

## Release Process

### Development environment

1. Create a new branch from main
2. Make changes
3. Push the branch
4. Create a PR to main
   i. this triggers the deployment of the changes to a temporary environment
5. Complete the PR with a squash commit once it's approved
   i. this triggers the deployment of the changes to the dev environment
   ii. and destroys the temporary environment the changes were deployed to

### Staging environment

1. Create a new release branch from main e.g. `releases/1`
2. Push the branch
   i. this triggers the deployment of the branch to the staging environment
   ii. and creates a new GitHub release if there have been relevant changes since the last release

### Production release

1. Run the 'prd' workflow on GitHub selecting the appropriate release branch
