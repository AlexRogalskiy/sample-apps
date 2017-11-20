===============
Deploy Locally
===============

Deploy application locally and connect to RDS

$ cld env create env-local environment-local.yaml

$ cld container create cont1 local

$ cld container show cont1

Edit app-local.yaml to include image id obtained from output of
cld container show command

$ cld app deploy greetings-local env-local app-local.yaml


==================
Deploy on AWS ECS
==================

$ cld env create env-aws environment-rds-ecs.yaml

$ cld container create cont2 ecr

$ cld container show cont2

Edit app-aws.yaml to include image url obtained from output of
cld container show command

$ cld app deploy greetings-aws env-aws app-aws.yaml


=====================
Deploy on Google GKE
=====================

Modify environment-cloudsql-gke.yaml with your project-id
and preferred zone name. Then follow these steps:

$ cld env create env-gcloud environment-cloudsql-gke.yaml

$ cld container create cont3 gcr

$ cld container show cont3

Edit app-gcloud.yaml to include image url obtained from output of
cld container show command

$ cld app deploy greetings-gke env-gcloud app-gcloud.yaml
