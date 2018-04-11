# Jenkins Slave to build Node.js 6 apps (RHEL7 based)
Project for creating a Node.js 6 based Jenkins Slave container image (for use in OpenShift).
<img src="https://www.openshift.com/images/logos/openshift/Logotype_RH_OpenShift_wLogo_RGB_Gray.svg" alt="OCP logo" height="70" >

Build it yourself or try using the Dockerhub version.

[![docker hub stats](http://dockeri.co/image/dudash/jenkins-slave-nodejs6-rhel7)](https://hub.docker.com/r/dudash/jenkins-slave-nodejs6-rhel7/)

## Versions available
This is targeted towards OpenShift 3.7 and later, RHEL7, and Node.js 6.

## Using this image
Assuming you already have an OpenShift cluster up and running and a Jenkins pipeline setup.  We need to:
1. Get the image into your cluster
2. TBD setup Jenkins Kubernetes plugin
3. TBD pipeline step example

## References
If you want to read more about that Jenkins slave builder images see below links.

For OpenShift Origin:
* https://docs.openshift.org/latest/using_images/other_images/jenkins.html#using-the-jenkins-kubernetes-plug-in-to-run-jobs

For the production version - OpenShift Container Platform:
* https://docs.openshift.com/container-platform/3.9/using_images/other_images/jenkins_slaves.html

