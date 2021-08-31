# bach-build

This action builds modular Java projects via calling [Bach](https://github.com/sormuras/bach).

It requires [JDK 17](https://jdk.java.net/17) or higher to be installed.

## Inputs

```yaml
  bach-arguments:
    required: true
    default: 'build'
    description: 'The arguments to be passed to Bach.
                  Defaults to `build`.'

  bach-version:
    required: true
    default: '17-ea'
    description: 'The version of Bach to initialize.
                  Find available versions listed at https://github.com/sormuras/bach/releases.
                  Defaults to `17-ea`.'

  working-directory:
    required: true
    default: ${{ github.workspace }}
    description: 'The working directory to change into.
                  Defaults to the common GitHub workspace directory'
```

## Outputs

_None, yet._

## Examples

### Minimal

Minimal example

```yaml
- uses: actions/checkout@v2
- uses: actions/setup-java@v2
  with:
    java-version: 17-ea
    distribution: 'zulu'
- uses: sormuras/bach-build@v1
  with:
    bach-version: 17-M1
```
