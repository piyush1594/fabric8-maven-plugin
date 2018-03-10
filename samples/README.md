## Fabric8-Maven-Plugin

<p align="center">
  <a href="http://fabric8.io/">
  	<img src="https://raw.githubusercontent.com/fabric8io/fabric8/master/docs/images/cover/cover_small.png" alt="fabric8 logo"/>
  </a>
</p>

### Introduction
This Maven plugin is a one-stop-shop for building and deploying Java applications for Docker, Kubernetes and OpenShift. It brings your Java applications on to Kubernetes and OpenShift. It provides a tight integration into maven and benefits from the build configuration already provided. It focuses on three tasks:
+ Building Docker images
+ Creating OpenShift and Kubernetes resources
+ Deploy application on Kubernetes and OpenShift

### How to use QuickStarts

To use quickstart you should have OpenShift/Kubernetes Cluster Up and Running.

Now in order to try fabric8 maven plugin samples, you need to have fabric8-maven-plugin installed:

Clone the project.
```
    git clone https://github.com/fabric8io/fabric8-maven-plugin
```

Move to project folder.
```
    cd fabric8-maven-plugin
```

Hit the install command/
```
    mvn clean install
```

To install fast, you can skip the tests
```
    mvn clean install -DskipTests
```

Now you are set to use all the quickstart, make sure that you have OpenShift/Kubernetes Cluster Up and Running. Go to the sample project you want to try and follow the README.

Thanks for trying out fabric8 maven plugin.
