---
sidebar_label: 'Github Actions'
---

### Как подключить schemistry к существующим flow

```yaml title="workflow.yml"
name: Schema check

on:
  push:
    branches: [ "master" ]
  pull_request:
    branches: [ "master" ]

jobs:
  use-plugin:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Проверка контрактов на соблюдение соглашений оформления
        uses: docker://imbofaker007/schemistry_github_lint
        with:
          message: "Hello from GitHub Actions workflow!"
      - name: Проверка обратной совместимости контрактов
        uses: docker://imbofaker007/schemistry_github_break_cheker

      - name: Регистрация изменений контрактов
        uses: docker://imbofaker007/schemistry_github_push
```