=============================
CloudARK Sample Applications
=============================

Sample applications for cloudark (https://github.com/cloud-ark/cloudark.git)

The README file in each application folder contains instructions to deploy the application.


AWS ECS Deployments
--------------------
As part of ECS cluster creation a ssh key is also created. You can use that to login
to the ECS cluster instance as follows:

- Find out location of the .pem file for your cluster

  - cld environment show <env-name>

- cd into the directory where the .pem file is located

- Change permissions of the .pem file

  - chmod 400 <pem file>

- Find out IP of the cluster instance from AWS web console

- SSH into the cluster instance

  - ssh -i "<pem file>" ec2-user@<AWS cluster instance IP>


Issues
-------
If you run into any issues please file them here_

.. _here: https://github.com/cloud-ark/cloudark/issues

Please include following:

- Environment yaml file

- Relevant logs from cld.log (this file is created in the folder where you have installed cloudark)
