# helm-charts

## Usage

Helm must be installed to use the charts. Please refer to Helm's documentation to get started.

Add the repository
```
helm repo add nliakm-charts https://nliakm.github.io/helm-charts/
```

Install the helm chart into kubernetes cluster
```
helm install my-release nliakm-charts/<chart> -n <namespace>
```