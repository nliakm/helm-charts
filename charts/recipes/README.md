## Examples

### Minimal installation
```
recipes:
  ingress:
    enabled: true
```
### Installation with persistent storage
```
recipes:
  ingress:
    enabled: true

  pvc:
    enabled: true
    media:
      storageClass: "default"
    static:
      storageClass: "default"
```



## Configuration

| Parameter                                  | Description                                                                       | Default       |
|--------------------------------------------|-----------------------------------------------------------------------------------|---------------|
| metadata.namespace                         | Namespace where the application will be deployed                                  | recipes       |
| recipes.replicas                           | Number of replicas to deploy                                                      | 1             |
| recipes.image.repository                   | Container image repository to use                                                  | vabene1111/recipes |
| recipes.image.tag                          | Container image tag to use                                                         | 1.5.6         |
| recipes.image.imagePullPolicy              | Image pull policy to use when deploying the application                           | Always        |
| recipes.secretKey.keyString                | A string used as the secret key                                                     | ""            |
| recipes.secretKey.existingSecret           | Name of an existing secret to use for the secret key                               | ""            |
| recipes.allowedHosts                       | Hosts the application can run under                                                 | *             |
| recipes.ingress.enabled                    | Enable or disable ingress for the application                                      | false          |
| recipes.ingress.ingressClassName           | The ingress controller to use (for Kubernetes >= 1.18)                              | ""            |
| recipes.ingress.annotations                | Annotations for the ingress                                                        | {}            |
| recipes.ingress.hostName                   | The hostname for the ingress                                                       | recipes.local |
| recipes.ingress.tls.tlsSecretName          | The name of the secret containing the TLS certificate                              | ""            |
| recipes.pvc.enabled                        | Enable or disable persistent volume claims                                         | false         |
| recipes.pvc.media.existingPvcName          | Name of an existing PVC to use for media storage                                    | ""            |
| recipes.pvc.media.accessMode               | Access mode for media storage                                                       | ReadWriteOnce |
| recipes.pvc.media.storageSize              | Size of the PVC for media storage                                                   | 1Gi           |
| recipes.pvc.media.storageClass             | Storage class for media storage                                                     | ""            |
| recipes.pvc.static.existingPvcName         | Name of an existing PVC to use for static storage                                   | ""            |
| recipes.pvc.static.accessMode              | Access mode for static storage                                                      | ReadWriteOnce |
| recipes.pvc.static.storageSize             | Size of the PVC for static storage                                                  | 5Gi           |
| recipes.pvc.static.storageClass            | Storage class for static storage                                                    | ""            |
| recipes.initChmodData.enable               | Enable or disable running the init container                                        | true          |
| recipes.initChmodData.resources            | Resource requests and limits for initializing the chmod data                       | {}            |
| recipes.nginx.image.repository             | Container image repository to use for the nginx container                           | nginx         |
| recipes.nginx.image.tag                    | Container image tag to use for the nginx container                                  | latest        |
| recipes.nginx.image.imagePullPolicy        | Image pull policy to use when deploying the nginx container                        | Always        |
| recipes.nginx.resources                    | Resource requests and limits for the nginx container                                | {}            |
| recipes.livenessProbe.failureThreshold     | Number of times the application should fail the liveness probe before being restarted | 3             |
| recipes.livenessProbe.httpGet.path         | Path to hit for the liveness probe                                                  | /             |
| recipes.livenessProbe.httpGet.port         | Port to use for the liveness probe                                                  | 8080          |
| recipes.livenessProbe.httpGet.scheme       | Protocol to use for the liveness probe                                              | HTTP          |
| recipes.livenessProbe.periodSeconds        | Time interval in seconds between liveness probes                                    | 30            |
| recipes.readinessProbe.httpGet.path        | Path to hit for the readiness probe                                                 |  /            | 
| recipes.readinessProbe.httpGet.port        | Port to use for the readiness probe                                                 |  8080         | 
| recipes.readinessProbe.httpGet.scheme      | Protocol to use for the readiness probe                                             |  HTTP         | 
| recipes.readinessProbe.periodSeconds       | Time interval in seconds between readiness probes                                   |  30           | 
| postgresql.global.postgresql.auth.username |  Username to use for the PostgreSQL database                                        |   recipes     | 
| postgresql.global.postgresql.auth.database | Database name to use for the PostgreSQL database                                    |   recipes     | 
