# Quilt build GitHub Action

This repo contains a [GitHub Action](https://github.com/features/actions) that you can use to run [Quilt’s `build` command](https://github.com/lemonmade/quilt/blob/main/documentation/features/builds) on your repo. This action will run Quilt’s `build` command, and will save any build caches for subsequent runs.

To use this action, create a [new workflow](https://docs.github.com/en/actions/quickstart#creating-your-first-workflow), and include this repo’s action as one of the steps. Note that this action does not checkout your repo or install your dependencies, so you need to make sure you do this yourself, or use the [`quilt-framework/action-prepare`](https://github.com/quilt-framework/action-prepare) GitHub action to set up a standard Quilt workspace:

```yml
name: CI
on: [push]
jobs:
  build:
    name: Build 🏗
    runs-on: ubuntu-latest
    steps:
      - uses: quilt-framework/action-prepare@v1
      - uses: quilt-framework/action-build@v2
```
