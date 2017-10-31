================
Local-and-Cloud
================

Deploy application locally and use database from AWS (RDS)

$ cp Dockerfile.aws Dockerfile

$ cld env create env1 environment-rds-local.yaml

$ cld app deploy greetings <env-id> --port 5000


===============
Deploy on AWS
================

$ cp Dockerfile.aws Dockerfile

$ cld env create env-2 environment-rds-ecs.yaml

$ cld app deploy greetings <env-id> --port 5000


=====================
Deploy on Google GKE
=====================

Modify environment-cloudsql-gke.yaml with your project-id
and preferred zone name. Then follow these steps:

$ cp Dockerfile.gcloud Dockerfile

$ cld env create env-google environment-cloudsql-gke.yaml

$ cld app deploy greetings <env-id> --port 5000


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

$ cp Dockerfile.gcloud Dockerfile

$ cld env create cross-env environment-ecs-cloudsql-open.yaml

$ cld app deploy greetings <env-id> --port 5000



