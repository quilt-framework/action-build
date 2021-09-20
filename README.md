# Quilt build GitHub Action

This repo contains a [GitHub Action](https://github.com/features/actions) that you can use to run [Quilt’s `build` command](https://github.com/lemonmade/quilt/blob/main/documentation/features/builds) on your repo. This action will checkout the repo, install your dependencies, and run Quilt’s `build` command.

To use this action, create a [new workflow](https://docs.github.com/en/actions/quickstart#creating-your-first-workflow), and include this repo’s action as one of the steps:

```yml
name: CI
on: [push]
jobs:
  build:
    name: Build 🏗
    runs-on: ubuntu-latest
    steps:
      - uses: quilt-framework/action-build@v1
        name: Build
```
