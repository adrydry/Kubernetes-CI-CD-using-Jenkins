# Kubernetes-CI-CD-using-Jenkins

In this project, we will build an effective Devops pipeline with multiple stages:
     -   Building the artifact
     - Creating the container
     - Pushing the container
     - Security checks

Once the developper pushing the code in an application repository (github), Jenkins will be notified, build and test the application using Maven. Once the application completed building, we will use Sonarqube as a static Code analysis to check any smell, security issues and help developpers remediate any problem before code sent to production. if everything is successful, we will build and push a docker image in our docker hub registry. At the same time, we will also scan the docker image with Trivy Artifact using to identify any vulnerabilities in the container (this is another security check before our docker image sent to our kubernetes cluster). We will update a set of manifests files with each successful pipeline build to have the latest version of the tag, resided in a separate repository (Devops repository). Once the tag is been
updated, ArgoCd will monitoring that repository for any change. As soon as a new tag is detected, it will deploy the latest version of the tag in our kubernetes cluster. We will send the slack notification, if the deployment and build is successful or if there is any problems during the build step
     

