===============
Deploy locally
================

$ cld env create env1 environment-rds-local.yaml

$ cld app deploy greetings <env-id> --port 5000


===============
Deploy on AWS
================

$ cld env create env-2 environment-rds-ecs.yaml

$ cld app deploy greetings <env-id> --port 5000



