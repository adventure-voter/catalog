---
id: the-secret
type: story
next: ending-kcp
---

# Ask Kubernetes

You deploy External Secrets Operator. Once.

Then, repeat and rinse. It's just another API.

```yaml
apiVersion: apis.kcp.io/v1alpha1
kind: APIExport
metadata:
  name: external-secrets.io
spec:
  latestResourceSchemas:
    - v250901.externalsecrets.external-secrets.io
  permissionClaims:
    - group: ""
      resource: secrets
      all: true
```

Permissions, RBAC, tenancy, all done. Just request a secret.

(If you want even nicer things, like a catalog of SecretStores, you can also add that.)

```yaml
apiVersion: external-secrets.io/v1
kind: ExternalSecret
metadata:
  name: postgres
spec:
  secretStoreRef:
    name: postgres-dev
    kind: ClusterSecretStore
  target:
    name: postgres
  data:
    - secretKey: host
      remoteRef:
        key: db/alice/postgres
        property: host
    - secretKey: password
      remoteRef:
        key: db/alice/postgres
        property: password
```

Four seconds later:

```console
$ kubectl get secret postgres
NAME       TYPE     DATA   AGE
postgres   Opaque   2      4s

$ kubectl get secret postgres -o jsonpath='{.data.host}' | base64 -d
db-alice-7f3.eu-west-1.rds.amazonaws.com
```

_No new tools, no new CLI, no new auth flow._
