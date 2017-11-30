JavaScript + REST API
----------------------

This example shows how a web application that uses HTML+JavaScript frontend
and Java REST API can be deployed using CloudARK.

The Dockerfile defines the application build steps.

Three environment yaml files are available in the folder:
a) environment-local.yaml should be used for local deployment
b) environment-ecs.yaml should be used for AWS ECS deployment
e) environment-gke.yaml - for deployments on Google Container Engine (GKE)


===============
Deploy Locally
===============

$ cld env create envlocal environment-local.yaml

$ cld container create container1 local

$ cld container show container1

Edit app-local.yaml to include image id obtained from output of
cld container show 

$ cld app deploy hello-world-1 envlocal app-local.yaml

$ cld app show hello-world-1

$ curl <app-url>/test.html

$ curl <app-url>/ajaxexample.html

$ cld app logs hello-world-1

$ cld app delete hello-world-1


===========================
Deploying locally on Mac
===========================

If you are using Mac OS, the application URL consisting of localhost:<port>
may not respond because of a known issue in Docker for Mac. As a result cld server
will wait for your application to become responsive and will eventually timeout.

You can get around this issue by using the IP address of the VM which is created
by Docker for Mac. 

You can find out IP of VM by executing following command: docker-machine ip default

You can curl application url using the IP address as shown below:

$ curl http://192.168.99.100:<port>/test.html

$ curl http://192.168.99.100:<port>/ajaxexample.html


=====================
Deploying on AWS ECS
=====================

$ cld env create envaws environment-ecs.yaml

$ cld container create container2 ecr

$ cld container show container2

Edit app-aws.yaml to include image url obtained from output of
cld container show

$ cld app deploy hello-world-2 envaws app-aws.yaml

$ cld app show hello-world-2

$ curl <app_ip_url>/test.html

$ curl <app_ip_url>/ajaxexample.html

$ curl <app_url>/test.html

$ curl <app_url>/ajaxexample.html

$ cld app logs hello-world-2

$ cld app delete hello-world-2

$ cld env delete envaws


========================
Deploying on Google GKE
========================

Add name of your Google cloud project and zone in environment-gke.yaml.
Then follow these steps

$ cld env create envgke environment-gke.yaml

$ cld container create container3 gcr

$ cld container show container3

Edit app-gke.yaml to include image url obtained from output of
cld container show

$ cld app deploy hello-world-3 envgke app-gke.yaml

$ cld app show hello-world-3

$ curl <app_url>/test.html

$ curl <app_url>/ajaxexample.html

$ cld app logs hello-world-3

$ cld app delete hello-world-3

$ cld env delete envgke
