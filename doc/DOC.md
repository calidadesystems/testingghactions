create a directory 
.github/workflows

in this directory each yml file will be an github action

for example create a file called repolinter with this content

name: Lint repository
on: [push]

jobs:
  repo-lint:
    name: "repolint"
    runs-on: ubuntu-latest
    steps:
      - name: "checkout repo"
        uses: actions/checkout@v2.0.0
        with:
          fetch-depth: 0
      - name: Test repolinter
        uses: philips-labs/github-action-repolinter@master

from this point any new commit with run a repolinter job
