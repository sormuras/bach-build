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
  project-name:
    description: 'Name of the project'
    required: false
  project-version:
    description: 'Version of the project'
    required: false
  project-main-release:
    description: 'Compile main modules for the specified Java SE release'
    required: false
  project-main-jarslug:
    description: 'String suffix used within the JAR file name, defaults to the project-version'
    required: false
    default: '!'
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
    bach-version: ea
    project-version: 1.2.3
    project-main-release: 11
```
