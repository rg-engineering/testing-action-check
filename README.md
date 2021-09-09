# iobroker-testing-action-check

Shared Github Actions for ioBroker testing workflows: Check and lint step

## Inputs

| Input          | Description                                              | Required? | Default   |
| -------------- | -------------------------------------------------------- | --------- | --------- |
| `node-version` | Node.js version to use in tests. Should be LTS.          | ✔         | -         |
| `typescript`   | Set to `'true'` when this is a TypeScript adapter        | ❌        | `'false'` |
| `lint`         | Set to `'true'` when the adapter has a linter configured | ❌        | `'false'` |

## Usage

```yml
# ... rest of your workflow ...

jobs:
  check-and-lint:
    runs-on: ubuntu-latest

    strategy:
      matrix:
        node-version: [14.x]

    steps:
      - uses: AlCalzone/iobroker-testing-action-check@v1
        with:
          node-version: [14.x] # This should be LTS
          # typescript: 'true' # optional
          # lint: 'true' # optional

  # ... other jobs
```
