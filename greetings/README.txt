===============
Deploy locally
================

$ cld environment create env1 environment-local.yaml

$ cld app deploy greetings <env-id>

Enter application port number as 5000 when prompted


===============
Deploy on AWS
================

$ cld environment create env-2 environment-rds-ecs.yaml

$ cld app deploy greetings <env-id>

Enter application port number as 5000 when prompted

