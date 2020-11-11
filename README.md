# bach-build

This action builds modular Java projects via calling [Bach](https://github.com/sormuras/bach) 16-ea.

It requires a [JDK 16 Early-Access Build](https://jdk.java.net/16) to be installed.

## Inputs

```yaml
  bach-action:
    description: 'Bach action to execute, defaults to build'
    required: true
    default: 'build'

  bach-version:
    description: 'Version of Bach to use, defaults to ea'
    required: true
    default: 'ea'

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
  with:
    java-version: 16-ea
- uses: sormuras/bach-build@main
```

### Explicit

Configure versions to explicit values.

```yaml
- uses: actions/checkout@v2
- uses: actions/setup-java@v1
  with:
    java-version: 16-ea
- uses: sormuras/bach-build@main
  with:
    bach-version: 16.x
    project-version: 1.2.3
    project-java-release: 11
```
