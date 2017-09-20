=================
Deploy locally
=================

$ cld env create local-env environment-local.yaml

$ cld app deploy hello-world <env-id> --port 8080

===============
Deploy on AWS
================

$ cld env create env-aws environment-ecs.yaml

$ cld app deploy hello-world <env-id> --port 8080


