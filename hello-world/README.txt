Hello World
------------

This example shows how a web application written using Python Flask
framework can be deployed using CloudARK.

The Dockerfile defines the application build steps.

Several environment yaml files are available in the folder:
a) environment-local.yaml should be used for local deployment
b) environment-ecs.yaml should be used for AWS ECS deployment
c) environment-ecs-instance-type.yaml shows how to customize the
   instance type of the ECS cluster VMs (default instancy type is
   t2.micro)
d) environment-ecs-size-2.yaml shows how to customize the size
   of the ECS cluster (default cluster size is 1)
e) environment-gke.yaml - for deployments on Google Container Engine (GKE)


===============
Deploy Locally
===============

$ cld env create env-local environment-local.yaml

$ cld container create cont1 local

$ cld container show cont1

Edit app.yaml to include image id obtained from output of
cld container show command

$ cld app deploy hello-world-1 env-local app.yaml

$ curl http://localhost:<port>/


===========================
Deploying locally on Mac
===========================

If you are using Mac OS, the application URL consisting of localhost:<port>
may not respond because of a known issue in Docker for Mac [1].
Note that CloudARK does not internally implement this workaround. As a result cld server
will wait for your application to become responsive and will eventually timeout.

You can get around this issue by using the IP address of the VM which is created
by Docker for Mac. You can curl application url as shown below:

curl http://192.168.99.100:<port>/

You can find out IP of VM by executing following command: docker-machine ip default


=====================
Deploying on AWS ECS
=====================

$ cld env create env-aws environment-ecs.yaml

$ cld container create cont2 ecr

$ cld container show cont2

Edit app.yaml to include image url obtained from output of
cld container show command

$ cld app deploy hello-world-2 env-aws app.yaml

$ cld app show hello-world-2

$ curl <app_url>


========================
Deploying on Google GKE
========================

Add name of your Google cloud project and zone in environment-gke.yaml.
Then follow these steps

$ cld env create env-gke environment-gke.yaml

$ cld container create cont3 gcr

$ cld containre show cont3

Edit app.yaml to include image url obtained from output of
cld container show command

$ cld app deploy hello-world-3 env-gke app.yaml

$ cld app show hello-world-3

$ curl <app_url>
