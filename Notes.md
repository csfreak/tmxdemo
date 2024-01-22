To create production cluster:

```bash:
hcp create cluster aws \
  --name production \
  --infra-id prod-${GUID} \
  --region us-west-1 \
  --zones us-west-1b,us-west-1a \
  --instance-type m6a.large \
  --root-volume-type gp3 \
  --root-volume-size 100 \
  --etcd-storage-class gp3-csi \
  --control-plane-availability-policy SingleReplica \
  --infra-availability-policy SingleReplica \
  --network-type OVNKubernetes \
  --release-image quay.io/openshift-release-dev/ocp-release:4.14.3-x86_64 \
  --node-pool-replicas 1 \
  --namespace local-cluster \
  --secret-creds aws-credentials \
  --auto-repair \
  --generate-ssh
```

To create staging cluster:

```bash:
hcp create cluster aws \
  --name staging \
  --infra-id stage-${GUID} \
  --region us-west-1 \
  --zones us-east-2b,us-east-2c,us-east-2d \
  --instance-type m6a.large \
  --root-volume-type gp3 \
  --root-volume-size 100 \
  --etcd-storage-class gp3-csi \
  --control-plane-availability-policy SingleReplica \
  --infra-availability-policy SingleReplica \
  --network-type OVNKubernetes \
  --release-image quay.io/openshift-release-dev/ocp-release:4.14.9-x86_64 \
  --node-pool-replicas 1 \
  --namespace local-cluster \
  --secret-creds aws-credentials \
  --auto-repair \
  --generate-ssh
```