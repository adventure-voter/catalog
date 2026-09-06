---
id: the-secret
type: story
next: ending-kcp
---

# She Asked Kubernetes

You deploy External Secrets Operator. Once. Nobody in this room needs to see that manifest.

Then you do the same trick you just did with databases, because it is the same trick.

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

One operator. Forty tenants. Alice binds it and gets `ExternalSecret`, and nothing else. She cannot write a `ClusterSecretStore`. She cannot read one. The stores her team is permitted to draw from are simply what is in her catalog, and there is no portal enforcing that, because there is still no portal.

That `permissionClaims` block is the entire trust boundary, and she agreed to it when she bound the API.

This is the only object she writes all week.

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

`SELECT 1` returns `1`. From a real database. It took her ninety seconds.

Now count what Alice did **not** do.

She did not log into Vault. She has no AWS account. She learned no CLI, raised no ticket, waited for no human, and read no Confluence page.

She could not tell you whether that credential came from Vault, AWS, GCP or Azure, and swapping it tomorrow is a change to an object she is not allowed to see.

When the credential rotates, the Secret changes underneath her running pods. **She never finds out**, because there is nothing for her to find out.

The provider credential exists in exactly one place, and that place is not a developer's laptop.

**No new CLI. No portal. No wizard. No dialect.** She asked Kubernetes for a secret, and Kubernetes gave her a secret.
