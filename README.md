# Getting started with Django on Cloud Run

[![Open in Cloud Shell][shell_img]][shell_link]

[shell_img]: http://gstatic.com/cloudssh/images/open-btn.png
[shell_link]: https://console.cloud.google.com/cloudshell/open?git_repo=https://github.com/GoogleCloudPlatform/python-docs-samples&page=editor&open_in_editor=run/django/README.md

This repository is an example of how to run a [Django](https://www.djangoproject.com/) 
app on Google Cloud Run (fully managed). 

The Django application used in this tutorial is the [Writing your first Django app](https://docs.djangoproject.com/en/3.0/#first-steps), after completing [Part 1](https://docs.djangoproject.com/en/3.0/intro/tutorial01/) and [Part 2](https://docs.djangoproject.com/en/3.0/intro/tutorial02/).


# Tutorial
See our [Running Django on Cloud Run (fully managed)](https://cloud.google.com/python/django/run) tutorial for instructions for setting up and deploying this sample application.

docker build --tag cloudrun-django:python .

docker run --rm -p 9090:8080 -e PORT=8080 cloudrun-django:python

```sh
# Set an environment variable with your GCP Project ID
export GOOGLE_CLOUD_PROJECT=<PROJECT_ID>

# Submit a build using Google Cloud Build
gcloud builds submit --tag gcr.io/${GOOGLE_CLOUD_PROJECT}/cloudrun-django

# Deploy to Cloud Run
gcloud run deploy cloudrun-django \
--image gcr.io/${GOOGLE_CLOUD_PROJECT}/cloudrun-django
```
