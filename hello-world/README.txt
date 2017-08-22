=================
Deploy locally
=================

$ cld app deploy hello-world --deploylocal true

Enter application port as 8080 when prompted.

===============
Deploy on AWS
================

$ cld environment create env-1 environment-ecs.yaml

$ cld app deploy hello-world --env-id <env-id>

Enter application port as 8080 when prompted.
