#This demo shows you how to use config maps with FIS projects on Openshift

The main elements in this example can be seen in the src/main/fabric8/deployment.yml
Make sure you have the configurations to mount the configmap there.

0) Run this project locally and see the logged property myproperty (you can find it in the resources/application.properties file)
	mvn spring-boot:run

1) Install config map on Openshift

	oc create configmap --from-file=configmaps/application.properties techlab-fis-configmap-config

2) deploy the application using the maven fabric8 plugin

	mvn fabric8:deploy

	Check the logs to see that the variable from the configmap has been taken into account.
