###About Zero-Config Sample

This is a sample project to use fabric8-maven-plugin without doing any configuration.

###Steps to use Zero-Config Sample

Before using Zero-Config Sample, make sure that you have followed basic steps.

First you need to move to samples/zero-config folder
```
cd samples/zero-config
```

Now you can check in pom.xml file that no other configuration is provided except mentioning the fabric8-maven-plugin
```
cat pom.xml
```

You can check that the version of fabric8-maven-plugin specified is a SNAPSHOT version. That's why you need to follow the base steps. You can specify any version available on maven central and skip the basic steps.

Make sure that Kubernetes/OpenShift cluster or Minikube/minishift is running. In case, if anything of this is not running, you can run minishift to test this application by using following command.
```
minishift start
```

Below command will create your OpenShift and Kubernetes resource descriptors.
```
mvn clean fabric8:resource  
```

Now create image by hitting the build goal.
```
mvn package fabric8:build
```

Below command will deploy your application on Kubernetes/Openshift cluster.
```
mvn fabric8:deploy
```

Now that your service has been deployed, let’s access it by querying pod, service from Kubernetes or OpenShift.

```
oc get pods
NAME                                           READY     STATUS      RESTARTS   AGE
fabric8-maven-sample-zero-config-1-jrtxj       1/1       Running     0          20s
fabric8-maven-sample-zero-config-s2i-1-build   0/1       Completed   0          4m
```
```
oc get service
NAME                               CLUSTER-IP     EXTERNAL-IP   PORT(S)    AGE
fabric8-maven-sample-zero-config   172.30.189.4   <none>        8080/TCP   1m
```

Lets access the Application
```
minishift openshift service --in-browser fabric8-maven-sample-zero-config
Created the new window in existing browser session.
```

It will open your application endpoint in default browser.

If you are using Openshift, you can access the application using route also.
```
oc get route
NAME                               HOST/PORT                                                          PATH      SERVICES                           PORT      TERMINATION   WILDCARD
fabric8-maven-sample-zero-config   fabric8-maven-sample-zero-config-myproject.192.168.42.139.nip.io             fabric8-maven-sample-zero-config   8080                    None

```

You can try the curl command to get the output of the route. (Use the HOST/PART of the previous commands output to use curl)
```
curl fabric8-maven-sample-zero-config-myproject.192.168.42.139.nip.io
Greetings from Spring Boot!
```

You will see the same output what you just saw in the browser.