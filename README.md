# custom-tpb

To use this custom build with the OOTB supply chains:

## Create the workload

```
tanzu apps workload create custom-tpb \
  --namespace dev \
  --git-branch main \
  --git-repo https://github.com/garethjevans/custom-tpb \
  --label apps.tanzu.vmware.com/has-tests=true \
  --label app.kubernetes.io/part-of=custom-tpb \
  --type web \
  --param dockerfile=./Dockerfile \
  --param-yaml testing_pipeline_matching_labels='{"apps.tanzu.vmware.com/pipeline":"noop-pipeline"}' \
  --param-yaml testing_pipeline_params='{}' \
  --yes
```
