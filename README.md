# Provider ZoneHero

`provider-zonehero-v2` is a [Crossplane](https://crossplane.io/) provider that
is built using [Upjet](https://github.com/crossplane/upjet) code
generation tools and exposes XRM-conformant managed resources for the
ZoneHero API.

## Getting Started

Install the provider by using the following command after changing the image tag
to the [latest release](https://marketplace.upbound.io/providers/footprint-it-solutions/provider-zonehero-v2):
```
crossplane xpkg install provider xpkg.crossplane.io/footprint-it-solutions/provider-zonehero-v2:v0.1.0
```

Alternatively, you can use declarative installation:
```
cat <<EOF | kubectl apply -f -
apiVersion: pkg.crossplane.io/v1
kind: Provider
metadata:
  name: provider-zonehero-v2
spec:
  package: xpkg.crossplane.io/footprint-it-solutions/provider-zonehero-v2:v0.1.0
EOF
```

Notice that in this example Provider resource is referencing ControllerConfig with debug enabled.

You can see the API reference [here](https://doc.crds.dev/github.com/footprint-it-solutions/provider-zonehero-v2).

## Developing

Run code-generation pipeline:
```console
go run cmd/generator/main.go "$PWD"
```

Run against a Kubernetes cluster:

```console
make run
```

Build, push, and install:

```console
make all
```

Build binary:

```console
make build
```

## Report a Bug

For filing bugs, suggesting improvements, or requesting new features, please
open an [issue](https://github.com/footprint-it-solutions/provider-zonehero-v2/issues).
