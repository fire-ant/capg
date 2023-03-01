### CAPI CLUSTER-API-PROVIDER-GCP Infrastructure Provider Chart

This chart is derived from the cluster-api-provider-gcp infrastructure provider of the [Cluster API](https://cluster-api.sigs.k8s.io) project 

see https://github.com/kubernetes-sigs/cluster-api-provider-gcp

### Values
for Chart Values see [here](charts/capg/README.md)

#### Notes

Note that Chart releases correlate image versions with CRDs and as such may need to upgrade/replace CRD versions over time.
the cluster-api-provider-gcp project requires a bootstrap secret/credential which is hardcoded to:
```
apiVersion: v1
data:
  credentials.json: <GCP_B64ENCODED_CREDENTIALS>
kind: Secret
metadata:
  labels:
    cluster.x-k8s.io/provider: infrastructure-gcp
  name: capg-manager-bootstrap-credentials
  namespace: capg-system
type: Opaque
```
The credentials will need to be generated separately and managed outside of the chart.
