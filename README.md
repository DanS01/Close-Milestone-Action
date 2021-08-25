# Close Milestone Action

Github Action to automatically close milestones linked to pull requests and issues.
This should be triggered upon pull request or issue closure and closes the milestone when there are no open issues remaining on it.

## Example Github Action Workflow File

```
name: Close Milestone

on:
  pull_request:
    types: [closed]
  issues:
    types: [closed]
  workflow_dispatch:

jobs:
  close-milestone:
    name: Close Milestone
    runs-on: ubuntu-latest
    steps:
    - name: Run Close Milestone Action
      id: run-close-milestone-action
      uses: DanS01/Close-Milestone-Action@v1.10
      with:
        secrets-token: ${{ secrets.GITHUB_TOKEN }}
```
