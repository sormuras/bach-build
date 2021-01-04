# bach-build

This action builds modular Java projects via calling [Bach](https://github.com/sormuras/bach).

It requires a [JDK 16 Early-Access Build](https://jdk.java.net/16) to be installed.

## Inputs

```yaml
  bach-version:
    description: 'The version of Bach to use.
      Find available versions listed at https://github.com/sormuras/bach/releases'
    required: true
  bach-action:
    description: 'Bach action to execute, defaults to `build`'
    required: true
    default: 'build'
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
    description: 'Working directory, defaults to the common GitHub workspace directory'
    required: true
    default: ${{ github.workspace }}
```

## Outputs

_None, yet._

## Examples

### Minimal

Minimal example

```yaml
- uses: actions/checkout@v2
- uses: actions/setup-java@v1
  with:
    java-version: 16-ea
- uses: sormuras/bach-build@v1
  with:
    bach-version: 16.0.1
```
