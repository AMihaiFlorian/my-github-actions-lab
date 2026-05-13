# my-github-actions-lab

[![GitHub Actions Workflow](https://github.com/AMihaiFlorian/my-github-actions-lab/actions/workflows/workflow.yml/badge.svg)](https://github.com/AMihaiFlorian/my-github-actions-lab/actions/workflows/workflow.yml)

A small practice repository for learning the basics of GitHub Actions.

The current workflow checks out the repository, prints useful GitHub Actions
context, lists files on the Ubuntu runner, and verifies that this `README.md`
file exists.

## Workflow

The workflow is defined in [`.github/workflows/workflow.yml`](.github/workflows/workflow.yml).

It runs on:

- Pushes to `main`
- Pushes to `feature/github-actions-test`
- Pull requests targeting `main`
- Manual runs from the GitHub Actions tab

The job runs on `ubuntu-latest` and performs these steps:

1. Checks out the repository with `actions/checkout@v4`
2. Prints repository, branch, actor, and runner information
3. Lists files in the repository and prints Ubuntu release details
4. Confirms that `README.md` exists

## Repository Structure

```text
.
├── .github/
│   └── workflows/
│       └── workflow.yml
├── .gitignore
└── README.md
```

## Running the Workflow

To trigger the workflow automatically, push a commit to one of the configured
branches:

```bash
git add README.md .github/workflows/workflow.yml
git commit -m "Update GitHub Actions lab"
git push
```

You can also run it manually from GitHub:

1. Open the repository on GitHub.
2. Go to the **Actions** tab.
3. Select **GitHub Actions Workflow**.
4. Click **Run workflow**.

## Notes

This repository does not include an application or test suite yet. It is focused
on experimenting with workflow triggers, runner commands, and basic validation
steps.
