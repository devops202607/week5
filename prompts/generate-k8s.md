# Generate Kubernetes manifests for the go-demo-app

You are a DevOps engineer. 
Generate a complete set of Kubernetes manifests (YAML) for the resources described below.

Where a manifest references a ConfigMap or Secret, create it as well.

All resources must be created in the `week5-5` namespace. Set `metadata.namespace: week5-5` for every namespaced resource.

Create the following resources:

1. Pod `app` — image `gcr.io/k8s-k3s/demo:v1.0.0`, HTTP port 8000.
2. Pod `config` (image `redis`) + ConfigMap `app-config` — a pod consuming a config value from the ConfigMap both as an env var and as a mounted volume.
3. CronJob `cronjob` — image `bash`, runs a hello command every 5 minutes.
4. Job `job-rsync` — image `google/cloud-sdk:275.0.0-alpine`, one-off job that rsyncs data from a GCS bucket into a persistent disk volume.
5. Pod `livenessprob` — image `gcr.io/k8s-k3s/demo:v1.0.0`, with an HTTP liveness probe.
6. Pod `multi-containers` — two containers (`nginx` and `debian`) sharing an emptyDir volume (one writes, one serves).
7. Pod `readinessprob` — image `gcr.io/k8s-k3s/demo:v2.0.0`, with HTTP liveness and readiness probes.
8. Pod `resource` — image `gcr.io/kuar-demo/kuard-amd64:1`, with CPU/memory requests and limits.
9. Pod `secret-env` (image `redis`) + Secret `mysecret1` — pod reading secrets as env vars.
10. Pod `secret` (image `redis`) + Secret `simple-secret` — pod mounting a secret as a volume.
11. Pod `volume` — image `gcr.io/kuar-demo/kuard-amd64:1`, pod with a hostPath volume.

Deliver one YAML file per resource group (or a single multi-document file) with proper `apiVersion` and `kind` for each manifest.
