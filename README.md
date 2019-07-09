# k8s-prometheus-file-exporter
A Prometheus exporter for K8s that serves metrics from a plain text file

## Usage

1. Create your own metrics file following Prometheus [text format](https://github.com/prometheus/docs/blob/master/content/docs/instrumenting/exposition_formats.md#text-format-example).
2. Upload it to any cloud storage (it could be a Github Gist). 
3. Set the `METRICS_FILE_URL` env var value located in [deploy/deployment.yaml](deploy/deployment.yaml) to the URL of the recently uploaded file.

Then run:

```bash
kubectl apply -f deploy
```

## FAQ

### Why not using a Kubernetes ConfigMap?
The reason for not using a config map is that it has a limitation of up to 1MB.
