[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/vfarcic/devops-toolkit)

[![Git](https://app.soluble.cloud/api/v1/public/badges/ad82014b-210c-430d-95bf-49e26805c108.svg?orgId=561911742905)](https://app.soluble.cloud/repos/details/github.com/mollypi/devops-toolkit?orgId=561911742905)  [![CIS](https://app.soluble.cloud/api/v1/public/badges/9319d542-eb3b-4b4f-a246-85bd63e4a07e.svg?orgId=561911742905)](https://app.soluble.cloud/repos/details/github.com/mollypi/devops-toolkit?orgId=561911742905)  [![IaC](https://app.soluble.cloud/api/v1/public/badges/bdbe3424-975d-466d-91f9-fabb0754e784.svg?orgId=561911742905)](https://app.soluble.cloud/repos/details/github.com/mollypi/devops-toolkit?orgId=561911742905)  

# [The DevOps Toolkit Series](http://www.devopstoolkitseries.com)

```bash
make init

make dev

make build

export PROJECT_ID=vfarcic

export VERSION=2.9.10

export IMAGE_DH=vfarcic/devops-toolkit-series

export IMAGE_GCR=gcr.io/$PROJECT_ID/devops-toolkit-series

docker image build -t $IMAGE_DH .

docker image tag $IMAGE_DH $IMAGE_DH:$VERSION

docker image tag $IMAGE_DH $IMAGE_GCR:$VERSION

docker login

docker image push $IMAGE_DH

docker image push $IMAGE_DH:$VERSION

gcloud auth configure-docker

docker image push $IMAGE_GCR:$VERSION

gcloud run deploy \
    devops-toolkit-series \
    --image $IMAGE_GCR:$VERSION \
    --region us-east1 \
    --allow-unauthenticated \
    --port 80 \
    --concurrency 100 \
    --platform managed \
    --project $PROJECT_ID
```

