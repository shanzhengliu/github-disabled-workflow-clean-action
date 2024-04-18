## Action Introduction
This action is designed to clean up the workflow which has been disabled.

## Use Example
```yaml
name: Clean up workflow
on:
  push
jobs:
    clean:
        runs-on: ubuntu-latest
        steps:
        - name: Checkout
          uses: actions/checkout@v2
        - name: Clean up workflow
          uses: shanzhengliu/github-disabled-workflow-clean-action@v1
          with:
                delete-level: 'repo'
                token: ${{ secrets.GITHUB_TOKEN }}
                owner: ${{ github.repository_owner }}
                repo: ${{ github.event.repository.name }}
                workflow: ''        
```
## Inputs