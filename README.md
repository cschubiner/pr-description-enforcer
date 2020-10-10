# Pull Request Description Enforcer

github action for enforcing description on pull requests

## Usage

### Create Workflow

Create a workflow (eg: `.github/workflows/pr-description-enforcer.yml` see [Creating a Workflow file](https://help.github.com/en/articles/configuring-a-workflow#creating-a-workflow-file)) to utilize the action with content:

```
# This workflow will enforce description on pull requests.

name: 'PR Description Enforcer'
on:
    pull_request:
        types: [opened, edited, reopened]

jobs:
    enforce:
        runs-on: ubuntu-latest

        steps:
            - uses: derkinderfietsen/pr-description-enforcer@v1
              with:
                  repo-token: '${{ secrets.GITHUB_TOKEN }}'

```

_Note: This grants access to the `GITHUB_TOKEN` so the action can make calls to GitHub's rest API_