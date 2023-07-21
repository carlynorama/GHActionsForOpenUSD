# GHActionsForOpenUSD

Reusable GitHub Actions for OpenUSD


## Usage

### composite scripts

```yml
on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]
      
jobs:
  build:
    name: Build Linux
    runs-on: ubuntu-latest
    steps:
      - name: Checkout This Repo
        uses: actions/checkout@v3
      - name: Moved to an actions folder in your own repo
        uses: ./actions/hello_action
      - name: Moved to .github/actions in your own repo
        uses: ./.github/actions/hello_action
      - name: Used from here. (No tagged releases yet. caveat usurpator)
        uses: carlynorama/GHActionsForOpenUSD/actions/hello_action@main
```

## Misc Lessons
  - When a github provided action requests a path it's typically a relative path __under $GITHUB_WORKSPACE __ to place the repository.This appears to require a literal, e.g. Cannot take $GITHUB_ENV variable.

## References

### GitHub Docs

- Python Setup and Cacheing - https://docs.github.com/en/actions/automating-builds-and-tests/building-and-testing-python
- Caching effects
  - https://github.com/actions/cache
  - https://github.com/marketplace/actions/cache
- Updating the system path: https://docs.github.com/en/actions/using-workflows/workflow-commands-for-github-actions#adding-a-system-path

### Runner Image Info

- https://docs.github.com/en/actions/using-github-hosted-runners/about-github-hosted-runners
- https://github.com/actions/runner-images/blob/main/images/linux/Ubuntu2204-Readme.md


### Example Actions and Workflows

- https://github.com/pablode/USD/blob/v22.11-ci/.github/workflows/deploy-release.yml
- https://github.com/usd-wg/assets/pull/49
- https://github.com/usd-wg/assets/pull/48 


