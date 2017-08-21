=================
Deploy locally
=================

$ cld app deploy hello-world local


===============
Deploy on AWS
================

$ cld environment create env-1 environment-ecs.yaml

$ cld app deploy hello-world aws --env-id <env-id>

