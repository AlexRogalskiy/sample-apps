=================
Deploy locally
=================

$ cld app deploy hello-world local

Enter application port as 8080 when prompted.

===============
Deploy on AWS
================

$ cld environment create env-1 environment-ecs.yaml

$ cld app deploy hello-world aws --env-id <env-id>

Enter application port as 8080 when prompted.
