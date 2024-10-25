# Cloud manager tests
<!--- mandatory --->
> E2E tests.

## Overview
<!--- mandatory section --->

> BDD test using [Gherkin syntax](https://cucumber.io/docs/gherkin/reference/).

## Usage

Example script to run tests from the local machine:

```
mkdir test
cp features/<feature-filename>.feature test
export SHOOT=<shoot-id>
export PROVIDER=<provider-id, probably azure, aws or gcp>
export KUBECONFIG=<path-to-cube-config of above shoot>
export ENV=dev
go mod tidy
go mod download
go build -o bin/kfr cmd/main.go
./bin/kfr \
-godog.paths $(pwd)/test \
-godog.tags="@all,@allProviders,@$PROVIDER&&@all,@allShoots,@$SHOOT&&@all,@allEnvs,@$ENV"
```

## Contributing
<!--- mandatory section - do not change this! --->

See [CONTRIBUTING.md](CONTRIBUTING.md).

## Code of Conduct
<!--- mandatory section - do not change this! --->

See [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).

## Licensing
<!--- mandatory section - do not change this! --->

See the [LICENSE file](./LICENSE).
