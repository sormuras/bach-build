# bach-build

This action builds modular Java projects via calling [Bach](https://github.com/sormuras/bach).

## Inputs

```yaml
  bach-action:
    description: 'Bach action to execute, defaults to build'
    required: true
    default: 'build'

  bach-version:
    description: 'Version of Bach to use, defaults to HEAD'
    required: true
    default: 'HEAD'

  project-java-release:
    description: 'Compile for the specified Java SE release.'
    required: false

  project-name:
    description: 'Name of the project'
    required: false

  project-version:
    description: 'Version of the project'
    required: false

  working-directory:
    description: 'Working directory, defaults to github.workspace'
    required: true
    default: ${{ github.workspace }}
```

## Outputs

_None, yet._

## Examples

### Minimal

Using default environment configuration and built-in versions.

```yaml
- uses: actions/checkout@v2
- uses: actions/setup-java@v1
- uses: sormuras/bach-build@v1
```

### Explicit

Configure versions to explicit values.

```yaml
- uses: actions/checkout@v2
- uses: actions/setup-java@v1
  with:
    java-version: 15
- uses: sormuras/bach-build@v1
  with:
    bach-version: 11.9
    project-version: 1.2.3
    project-java-release: 11
```
