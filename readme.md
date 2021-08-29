Business App Initial Content
=============================
Reference: https://access.redhat.com/documentation/en-us/red_hat_process_automation_manager/7.10/html/integrating_red_hat_process_automation_manager_with_other_products_and_components/creating-self-contained-image-proc_business-applications

CHAPTER 6. CREATING A SELF-CONTAINED RED HAT PROCESS AUTOMATION MANAGER SPRING BOOT JAR FILE

Kie Version :   7.44.0.Final
//application.properties
kieserver.classPathContainer=true
kieserver.autoScanDeployments=true

kieserver.deployments[0].alias=evaluation_v1
kieserver.deployments[0].containerId=evaluation_v1
kieserver.deployments[0].artifactId=evaluation
kieserver.deployments[0].groupId=evaluation
kieserver.deployments[0].version=1.0.0-SNAPSHOT

kieserver.deployments[1].alias=evaluation_v2
kieserver.deployments[1].containerId=evaluation_v2
kieserver.deployments[1].artifactId=evaluation
kieserver.deployments[1].groupId=evaluation
kieserver.deployments[1].version=2.0.0-SNAPSHOT

Steps:
1. modify pom.xml 
2. modify application.properties
3. install 2 kjars evaluation_v1,evaluation_v2 from business central to maven repository
4. run command from folder business-application-service>  mvn install
5. cd target
6. java -jar business-application-service-1.0-SNAPSHOT.jar

check for containers autodeployed from classpath: http://localhost:8090/rest/server/containers