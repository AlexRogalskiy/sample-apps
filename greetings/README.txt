========
Local
========

Deploy application locally and connect to RDS

$ cld container create cont1 local

$ cld container show cont1

Edit app-local.yaml to include image id obtained from output of
container show command

$ cld env create env-local environment-rds-local.yaml

$ cld app deploy greetings-local <env-id> app-local.yaml


================
Deploy on AWS
================

$ cld container create cont2 ecr

$ cld container show cont2

Edit app-aws.yaml to include image url obtained from output of
container show command

$ cld env create env-aws environment-rds-ecs.yaml

$ cld app deploy greetings-aws <env-id> app-aws.yaml


=====================
Deploy on Google GKE
=====================

Modify environment-cloudsql-gke.yaml with your project-id
and preferred zone name. Then follow these steps:

$ cld container create cont3 gcr

$ cld container show cont3

Edit app-gcloud.yaml to include image url obtained from output of
container show command

$ cld env create env-gcloud environment-cloudsql-gke.yaml

$ cld app deploy greetings-gke <env-id> app-gcloud.yaml


====================
Cross-cloud (alpha)
====================

Use environment-ecs-cloudsql-open.yaml. This will create CloudSQL
instance on Google cloud and deploy application on Amazon ECS.
Note that this feature is currently experimental. The CloudSQL
instance is currently is open to allow connections from AWS ECS.
Use this feature at your own discretion.

Modify environment-ecs-cloudsql-open.yaml with your preferred project-id
and zone name. Then follow these steps:

$ cld env create cross-env environment-ecs-cloudsql-open.yaml

$ cld app deploy greetings <env-id> --port 5000



