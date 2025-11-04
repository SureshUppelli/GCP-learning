![Screenshot of a comment on a GitHub issue showing an image, added in the Markdown, of an Octocat smiling and raising a tentacle.](https://github.com/SureshUppelli/GCP-learning/blob/main/cloud-build/Cloud-Build.png)

export PROJECT_ID=$(gcloud config get-value project)

export PROJECT_NUMBER=$(gcloud projects describe $PROJECT_ID --format='value(projectNumber)')

export REGION=us-central1

gcloud config set compute/region $REGION


gcloud services enable container.googleapis.com \
    cloudbuild.googleapis.com \
    secretmanager.googleapis.com \
    containeranalysis.googleapis.com


Create an Artifact Registry Docker repository named my-repository in the us-central1 region to store your container images:

gcloud artifacts repositories create my-repository \
  --repository-format=docker \
  --location=$REGION
