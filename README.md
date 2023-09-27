# auto-back-merge
masterにマージした際に自動的にdevelopにコミットをバックマージするPRを作成する
※現在、開発中です。



## 使い方
```yaml
name: "Auto Create Back Merge PR"

on:
  push:
    branches:
      - master

jobs:
  auto-back-merge:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
        with:
          fetch-depth: 0

      - name: Auto Back Merge
        uses: chimiketsu/auto-back-merge@v0.1.1
        with:
          head: master
          base: develop
```
