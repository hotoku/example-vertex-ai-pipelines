```shell
gcloud iam service-accounts create exp-vai \
    --description="vertex ai example" \
    --display-name="vertex ai example" \
    --project=example-vertex-ai-pipelines
```

```shell
gcloud projects add-iam-policy-binding example-vertex-ai-pipelines \
    --member="serviceAccount:exp-vai@example-vertex-ai-pipelines.iam.gserviceaccount.com" \
    --role="roles/aiplatform.user"
```

```shell
gcloud iam service-accounts add-iam-policy-binding \
    exp-vai@example-vertex-ai-pipelines.iam.gserviceaccount.com \
    --member="user:hotoku@inctore.com" \
    --role="roles/iam.serviceAccountUser"
```

```shell
gcloud projects add-iam-policy-binding example-vertex-ai-pipelines \
    --member="serviceAccount:exp-vai@example-vertex-ai-pipelines.iam.gserviceaccount.com" \
    --role="roles/ml.serviceAgent"
```

```shell
gsutil mb -p example-vertex-ai-pipelines -l asia-northeast1 gs://exp-vai
```

```shell
gsutil iam ch \
serviceAccount:exp-vai@example-vertex-ai-pipelines.iam.gserviceaccount.com:roles/storage.objectCreator,objectViewer \
gs://exp-vai

gsutil iam ch \
serviceAccount:exp-vai@example-vertex-ai-pipelines.iam.gserviceaccount.com:roles/storage.objectViewer \
gs://exp-vai
```
