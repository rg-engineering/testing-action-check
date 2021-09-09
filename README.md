# testing-action-check

Shared Github Actions for ioBroker testing workflows: Check and lint step

## Inputs

| Input                   | Description                                              | Required? |      Default      |
| ----------------------- | -------------------------------------------------------- | --------- | :---------------: |
| `node-version`          | Node.js version to use in tests. Should be LTS.          | ✔         |         -         |
| `install-command`       | Overwrite the default install command                    | ❌        |    `'npm ci'`     |
| `type-checking`         | Set to `'true'` when the adapter should be type-checked  | ❌        |     `'false'`     |
| `type-checking-command` | Overwrite the default type checking command              | ❌        | `'npm run check'` |
| `lint`                  | Set to `'true'` when the adapter has a linter configured | ❌        |     `'false'`     |
| `lint-command`          | Overwrite the default lint command                       | ❌        | `'npm run lint'`  |

## Usage

```yml
# ... rest of your workflow ...

jobs:
  check-and-lint:
    runs-on: ubuntu-latest

    steps:
      - uses: ioBroker/testing-action-check@v1
        with:
          node-version: "14.x" # This should be LTS
          # type-checking: 'true' # optional
          # lint: 'true' # optional

  # ... other jobs
```
