# helm-charts

## Usage

Helm must be installed to use the charts. Please refer to Helm's documentation to get started.

Add the repository
```
helm repo add recipes https://nliakm.github.io/helm-charts/
```

Install the helm chart into kubernetes cluster
```
helm install recipes recipes/recipes -n <namespace>
```