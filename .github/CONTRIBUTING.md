# eslint-plugin-vue-i18n-ex Contributing Guide

- [Issue Reporting Guidelines](#issue-reporting-guidelines)
- [Pull Request Guidelines](#pull-request-guidelines)
- [Development Setup](#development-setup)

## Issue Reporting Guidelines

- The issue list of this repo is **exclusively** for bug reports and feature requests. Non-conforming issues will be closed immediately.

  - For simple beginner questions, you can get quick answers from [`#vue-i18n-ex` channel of Discord](https://chat.vuejs.org/)

  - For more complicated questions, you can use [the official forum](http://forum.vuejs.org/) or StackOverflow. Make sure to provide enough information when asking your questions - this makes it easier for others to help you!

- Try to search for your issue, it may have already been answered or even fixed in the development branch.

- Check if the issue is reproducible with the latest stable version of ESLint. If you are using a pre-release, please indicate the specific version you are using.

- It is **required** that you clearly describe the steps necessary to reproduce the issue you are running into. Issues with no clear repro steps will not be triaged. If an issue labeled "need repro" receives no further input from the issue author for more than 5 days, it will be closed.

- For bugs that involves build setups, you can create a reproduction repository with steps in the README.

- If your issue is resolved but still open, don’t hesitate to close it. In case you found a solution by yourself, it could be helpful to explain how you fixed it.

## Pull Request Guidelines

- The `master` branch is basically just a snapshot of the latest stable release. All development should be done in dedicated branches. **Do not submit PRs against the `master` branch.**

- Checkout a topic branch from the relevant branch, e.g. `master`, and merge back against that branch.

- It's OK to have multiple small commits as you work on the PR - we will let GitHub automatically squash it before merging.

- Make sure `pnpm test` passes. (see [development setup](#development-setup))

- If adding new feature:

  - Add accompanying test case.
  - Provide convincing reason to add this feature. Ideally you should open a suggestion issue first and have it greenlighted before working on it.

- If fixing a bug:
  - Provide detailed description of the bug in the PR. Live demo preferred.
  - Add appropriate test coverage if applicable.

### Work Step Example

- Fork the repository from [@intlify/eslint-plugin-vue-i18n](https://github.com/intlify/eslint-plugin-vue-i18n-ex) !
- Create your topic branch from `master`: `git branch my-new-topic origin/master`
- Add codes and pass tests !
- Commit your changes: `git commit -am 'Add some topic'`
- Push to the branch: `git push origin my-new-topic`
- Submit a pull request to `dev` branch of `@intlify/eslint-plugin-vue-i18n` repository !

## Development Setup

You will need [Node.js](http://nodejs.org) and [pnpm](https://pnpm.io/)

After cloning the repo, run:

    $ pnpm install

### Commonly used scirpt with `pnpm`

    # lint source codes and docs
    $ pnpm lint
    $ pnpm lint:docs

    # run vitepress
    $ pnpm docs

    # run the test suite
    $ pnpm test

There are some other scripts available in the `scripts` section of the `package.json` file.

The default test script will do the following: lint with ESLint -> unit tests with coverage. **Please make sure to have this pass successfully before submitting a PR.** Although the same tests will be run against your PR on the CI server, it is better to have it working locally beforehand.
