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

