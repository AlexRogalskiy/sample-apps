Application code taken from https://github.com/awslabs/ecs-demo-php-simple-app 

Directions on how to launch this sample app on Amazon ECS can be found in the documentation: [Docker basics](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/docker-basics.html).

======================
Deploy using CloudARK
======================

$ cld environment create env-1 environment-ecs.yaml

$ cld app deploy ecs-php-demo <env-id>

Enter application port as 80 when prompted.
