# k3s-new
New k3s

## CouchDB

CouchDB runs as a standalone Argo CD application in the `couchdb` namespace.
It uses a 10Gi `moosefs-storage` volume and is exposed over HTTPS at
`couchdb.16w.eu` and `couchdb.tech.eus`.

Before syncing the application, create the `couchdb-admin` Secret in the
`couchdb` namespace with `username` and `password` keys. Keep the credentials
out of Git and store the generated password securely. The template is in
[`examples/couchdb-admin-secret.yaml`](./examples/couchdb-admin-secret.yaml).
Copy it outside the repository, replace the example password, then apply that
copy with `kubectl apply -f`. The namespace must exist first.
