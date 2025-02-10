# Kubernetes-CI-CD-using-Jenkins

In this project, we will build an effective Devops pipeline with multiple stages:
     -   Building the artifact
     - Create the container
     - Push the container
     - Apply Security checks

Once the developper pushing the code in an application repository (github), Jenkins will be notified, build and test the application (Java) using Maven. Once the application completed building, we will use Sonarqube as a static Code analysis to check any smell, security issues and help developpers remediate any problem before code is pushed to production. if everything is successful, we will build and push a docker image in our docker hub registry. At the same time, we will also scan the docker image with Trivy Artifact using to identify any vulnerabilities in the container (this is another security check before our docker image sent to our kubernetes cluster). We will update a set of manifests files with each successful pipeline build to have the latest version of the tag, resided in a separate repository (Devops repository). This repository will contain Deploy manifest and service manifest.   Once the tag is been updated, ArgoCd will monitor that repository for any change. As soon as a new tag is detected, it will deploy the latest version of the tag in our kubernetes cluster. We will send the slack notification, if the deployment and build is successful or if there is any problems during the build step along the way. We will use a declarative pipelines in Jenkins.


1. Create our virtual Machine in AWS and install Jenkins
     

