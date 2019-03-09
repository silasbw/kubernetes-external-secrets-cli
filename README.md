# external-secrets-cli

CLI for converting [Kubernetes Secrets](https://kubernetes.io/docs/concepts/configuration/secret/) to
[Kubernetes ExternalSecrets](https://github.com/godaddy/kubernetes-external-secrets).

## Install

```
npm i -g external-secrets-cli
```

## Usage

Get the `Secret` object you'd like to managed as an `ExternalSecret`:

```
kubectl -n my-app get secret my-app -o json > secret.json
```

Decode secret data from your `Secret`; print commands to load that
data into your secret store (*e.g.*, AWS Secrets Manager); and create
an `ExternalSecret` manifest:

```
mkdir data
external-secrets-cli --input secret.json --ouput data
```
