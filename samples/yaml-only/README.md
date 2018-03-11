### About YAML-ONLY Sample

This is a sample project to use fabric8-maven-plugin to generate resources only for the yaml files specified.

### Steps to use YAML-ONLY Sample

Before using Yaml-Only Sample, make sure that you have followed basic [steps](../). But as this is related to resource generation, you need to install fabric8-maven-plugin only, no need of Cluster.

First you need to move to samples/yaml-only folder
```
cd samples/yaml-only
```

Now you can check in pom.xml file that along with fabric8-maven-plugin there is configuration for profile raw which will help to generate resources only for yaml specified and also resource goal which means this goal will be executed every time by default.
```
cat pom.xml
```

You can check that the version of fabric8-maven-plugin specified is a SNAPSHOT version. That's why you need to follow the base steps. You can specify any version available on maven central and skip the basic steps.

You can also check that only secret.yml is specified here.
```
tree
```

Below command will create your OpenShift and Kubernetes resource descriptors.
```
mvn clean fabric8:resource  
```

You can check that Kubernetes and OpenShift yaml has been generated.
```
tree
```

You can check the content of the file as this this will only generate the resource according to yaml specified i.e. only secret.
```
cat target/classes/META-INF/fabric8/openshift.yml
```

You can also hit below command as we have specified resource goal to be executed every time
```
mvn clean install
```

You can again check the contents by hitting the previous commands and you will see that the resources has been generated as the resource goal has been executed.