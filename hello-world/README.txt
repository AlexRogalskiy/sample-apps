=================
Deploy locally
=================

$ cld environment create local-env environment-local.yaml

$ cld app deploy hello-world <env-id> --port 8080

===============
Deploy on AWS
================

$ cld environment create env-aws environment-ecs.yaml

$ cld app deploy hello-world <env-id> --port 8080


