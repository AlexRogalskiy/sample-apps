=================
Deploy locally
=================

$ cld app deploy hello-world local


===============
Deploy on AWS
================

$ cld environment create env-1 environment-ecs.yaml

$ cld app deploy hello-world --env-id <env-id>

