=================
Deploy locally
=================

$ cld environment create local-env environment-local.yaml

$ cld app deploy hello-world <env-id>

Enter application port as 8080 when prompted.

===============
Deploy on AWS
================

$ cld environment create env-aws environment-ecs.yaml

$ cld app deploy hello-world <env-id>

Enter application port as 8080 when prompted.
