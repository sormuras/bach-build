# bach-build

This action builds modular Java projects via calling [Bach](https://github.com/sormuras/bach).

It requires a [JDK 16](https://jdk.java.net/16) to be installed.

## Inputs

```yaml
  bach-arguments:
    description: 'The arguments to be passed to Bach.
                  Defaults to `build`.'
    required: true
    default: 'build'
  bach-version:
    description: 'The version of Bach to initialize.
                  Find available versions listed at https://github.com/sormuras/bach/releases.
                  Defaults to `17-ea`.'
    required: true
    default: '17-ea'
  working-directory:
    description: 'The working directory to change into.
                  Defaults to the common GitHub workspace directory'
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
    java-version: 16
- uses: sormuras/bach-build@v1
  with:
    bach-version: 17-ea
```
