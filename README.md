# SCC Code Report Action

[SCC](https://github.com/boyter/scc) provides helpful metrics line complexity, effort and cost for a codebase. This GitHub Action runs SCC to generate a code metrics report and publishes the result as a GitHub Check. 

Note: The check can be run on commit, etc - but the output is based on the state of the entire codebase.

## Usage

```yaml
name: SCC Code Report

on:
  push:
    branches:
      - master

permissions: # Set permissions at workflow level
  contents: read
  checks: write

jobs:
  scc_count:
    runs-on: ubuntu-latest
    steps:
      - name: Run SCC Code Report
        uses: hyperlaunch/scc-check-action@v1
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
