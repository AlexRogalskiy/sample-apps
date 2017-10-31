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

==================
Deploying locally
==================

$ cld env create local-env environment-local.yaml
$ cld app deploy hello-world <env-id> --port 8080
$ curl http://localhost:<port>/

===========================
Deploying locally (on Mac)
===========================
If you are using Mac OS, the application URL consisting of localhost:<port>
may not respond because of a known issue [1] in Docker for Mac.

You can get around this issue by using the IP address of the VM which is created
by Docker for Mac as shown below:

curl http://192.168.99.100:<port>/

(You can find out IP of VM by executing following command: docker-machine ip default)

Note that CloudARK does not internally implement this workaround. As a result cloudark
will wait for your application to become responsive and will eventually timeout.

=====================
Deploying on AWS ECS
=====================

$ cld env create env-aws environment-ecs.yaml
$ cld app deploy hello-world <env-id> --port 8080
$ curl <app_ip_url> / curl <app_url>

==========================================
Deploying on Google Container Engine (GKE)
==========================================

Add name of your Google cloud project and zone in environment-gke.yaml.
Then follow these steps

$ cld env create env-gke environment-gke.yaml
$ cld app deploy hello-world <env-id> --port 8080
$ curl <app_url>
