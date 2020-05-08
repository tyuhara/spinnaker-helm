# Spinnaker-helm

This spinnaker configuration is based on [Install Spinnaker with Helm on Google Kubernetes Engine](https://medium.com/@__yuhara/install-spinnaker-with-helm-on-google-kubernetes-engine-8284eebd0d08).
Please set up GCP resource and Helm seeing above guide if you need.

## Usage

### Generate values.yaml
Run script to generate `values.yaml`.
If there is not service account key named `spinnaker-sa.json`, please put this file under the current directory.

```console
sh generateValuesYaml
```

Then `values.yaml` is generated under the current directory.

### Helm install or upgrade

After generating `values.yaml`, install or upgrade Spinnaker with Helm.
The chart version, which specified with `--version option` is depend on Spinnaker and Halyard version. Therefore, it may not work well due to above reason.
In this case, find the issue and try to specify another version. it should be fine.

```console
helm install -n cd stable/spinnaker -f values.yaml --timeout 600 --namespace=spinnaker --version 2.0.0-rc3 --wait
```

```console
helm install -n cd stable/spinnaker -f spinnaker-config2.yaml --timeout 600 --namespace=spinnaker --version 2.0.0-rc3 --wait
 ```
