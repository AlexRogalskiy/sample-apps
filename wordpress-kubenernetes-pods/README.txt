==============
Deploy on GKE
==============

wp-pod.yaml: Application definition consisting of Pods defined for wordpress and mysql containers using publicly available images.

environment-gke.yaml: Environment definition consisting of GKE cluster definition

Deploy:
-------

$ cld env create envgke environment-gke.yaml --project-id <your-project-id>

$ cld app deploy appgke envgke wp-pod.yaml


Track / Debug:
---------------

$ cld env show envgke

$ cld app show appgke

$ cld app logs appgke

$ cld env shell envgke

  > help
  > kubectl get services
  > kubectl get pods
  > kubectl logs some-wordpress wordpress
  > kubectl logs some-wordpress mysql
  > exit


Cleanup:
---------

$ cld app delete appgke

$ cld env delete envgke


Verify:
-------

$ cld app show appgke

$ cld app list

$ cld env show envgke

$ cld env list


