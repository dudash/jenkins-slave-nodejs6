# Jenkins Slave to build Node.js 6 apps (CentOS/RHEL7 based)
Project for creating a Node.js 6 based Jenkins Slave container image (for use in OpenShift).
<img src="https://www.openshift.com/images/logos/openshift/Logotype_RH_OpenShift_wLogo_RGB_Gray.svg" alt="OCP logo" height="70" >

Build it yourself or try using the Dockerhub version.

[![docker hub stats](http://dockeri.co/image/dudash/jenkins-slave-nodejs6)](https://hub.docker.com/r/dudash/jenkins-slave-nodejs6/)

## Versions available
This is targeted towards OpenShift 3.7 and later, CentOS/RHEL7, and Node.js 6.

## Using this image
Assuming you already have an OpenShift cluster up and running and a Jenkins pipeline setup.  You need to:
1. Update the Jenkins Kubernetes plugin to reference the builder image.  In ```Jenkins->Manage Jenkins->Configure System```. Then look in ```Cloud->Kubernetes->Kubernetes Pod Template```.  Depending on where your container image lives, the new setup should look something like this:

![Screenshot](./.screens/jenkins-plugin.png?raw=true)


2. Update your pipeline to reference the correct slave image by name.  Something like:
    
    ```
    pipeline {
        agent {
            node {
                // spin up a node.js slave pod to run this build on
                label 'nodejs6'
            }
        }

        [THE STAGES AND STEPS...]
    ```
    
    or with the older syntax:
    
    ```
    node('nodejs6') {
        stage('build') {
            openshiftBuild(buildConfig: '${NAME}', showBuildLogs: 'true')
        }
        
        [OTHER STAGES...]
    ```

## References
If you want to read more about the Jenkins slave builder images see below links.

For OpenShift Origin:
* https://docs.openshift.org/latest/using_images/other_images/jenkins.html#using-the-jenkins-kubernetes-plug-in-to-run-jobs

For the production version - OpenShift Container Platform:
* https://docs.openshift.com/container-platform/3.9/using_images/other_images/jenkins_slaves.html

