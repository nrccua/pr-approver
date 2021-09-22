## PR Approver

Github action to auto-approve PRs based on labels.

## How to use

- Create a github actions workflow in your project
- Define a job that runs on `ubuntu-latest`
- Use this repo's latest release as a reference
- Add the variables `token`, `label-list` and optionally `label-exclusion-list`

Example:
```
# <project>/.github/workflows/<action_name.yml>

name: <name>
on:
  pull_request:
    types: [opened]
jobs:
  <job_name>:
    runs-on: ubuntu-latest
    steps:
      - name: <name>
        uses: nrccua/pr_approver@v1
        with:
          token: ${{ secrets.GITHUB_TOKEN }}
          label-list: sync
          label-exclusion-list: conflict,error
```
