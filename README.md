# Custom `fluentd` Docker image

## Build

```shell
→ # Alpine
→ docker build -t m99coder/fluentd-alpine ./alpine

→ # Debian
→ docker build -t m99coder/fluentd-debian ./debian
```

## Inspecting layers

### Alpine

```shell
→ brew install dive
→ dive m99coder/fluentd-alpine
```

|Key|Value|
|---|---|
|Image name|m99coder/fluentd-alpine|
|Total Image size|67 MB|
|Potential wasted space|552 kB|
|Image efficiency score|99 %|

### Debian

```shell
→ brew install dive
→ dive m99coder/fluentd-debian
```

|Key|Value|
|---|---|
|Image name|m99coder/fluentd-debian|
|Total Image size|243 MB|
|Potential wasted space|6.6 MB|
|Image efficiency score|98 %|

## Custom

```shell
→ docker build -t m99coder/fluentd-custom ./custom
→ dive m99coder/fluentd-custom
```

|Key|Value|
|---|---|
|Image name|m99coder/fluentd-custom|
|Total Image size|98 MB|
|Potential wasted space|1.9 MB|
|Image efficiency score|98 %|
