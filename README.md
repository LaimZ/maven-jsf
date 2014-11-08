maven-jsf
=========

Maven, JSF, Tomcat, Glassfish

This is a simple Maven (and Eclipse) Tomcat/Glassfish JSF project. For 03 NOV 2014 it doesn't use Maven Tomcat Plugin.
For 08 NOV 2014 it uses both Tomcat and Glassfish maven plugins. Tomcat plugin can work with remote server.

**To compile with Maven**, run **mvn package**.

**To run project with Tomcat:**
- Copy JavaServerFaces from **~/target** to your Tomcat webapp directory, for example **"C:\Program Files\apache-tomcat-7.0.56\webapps"**. You can either copy **JavaServerFaces.war**, but it doesn't work for me now.
- Then run Tomcat **<windows>"%CATALINA_HOME%\bin\startup.bat"</windows>**. **%CATALINA_HOME%** is an administrator system variable, for me it is **C:\Program Files\apache-tomcat-7.0.56**. Only this variable is nessesary for Tomcat to work.
- After start **Tomcat Server** : **"%CATALINA_HOME%\bin\startup.bat"**.

Now you can go to [http://localhost:8080/JavaServerFaces/hello.xhtml](http://localhost:8080/JavaServerFaces/hello.xhtml "http://localhost:8080/JavaServerFaces/hello.xhtml") and see your form! Before next copying don't forget to shutdown **Tomcat Server** : **"%CATALINA_HOME%\bin\shutdown.bat"**.

**To set up Tomcat deploy, follow next steps:** [http://www.mkyong.com/maven/how-to-deploy-maven-based-war-file-to-tomcat/](http://www.mkyong.com/maven/how-to-deploy-maven-based-war-file-to-tomcat/ "http://www.mkyong.com/maven/how-to-deploy-maven-based-war-file-to-tomcat/")

To deploy it from Eclipse For Java EE you need:
- Import this project as Maven project
- Near button Run press arrow and click **Run Configurations**, select **Maven Build** and create new with Right Mouse Button. Set goal as tomcat7:redeploy and Base directory as project root directory. User settings as ........\apache-maven-3.2.3\conf\settings.xml.

Note, that tomcat server should be runned as asministrator in this case and straight from this directory, no any %CATALINA_HOME%, for example 
```
C:\.....\tomcat....\bin\>startup.bat
```

**To run this project with Glassfish:**

As I understand, Glassfish plugin 2.1 doesn't support deploying project to remote server. But it can do this in a local machine, using **asadmin.bat** on Windows. The main problem is to tell that plugin that it should use  **asadmin.bat**, not **asadmin**. To solve this problem, rename **glassfish/bin/asadmin**. So, you should only run **mvn glassfish:redeploy**. If any error occur, be shure, that in pom.xml you have correct information about glassfish path, it's domain, login, password, port (4848).


This project was created step-by-step, according to [http://www.mkyong.com/jsf2/jsf-2-0-hello-world-example/](http://localhost:8080/JavaServerFaces/hello.xhtml "http://localhost:8080/JavaServerFaces/hello.xhtml"), thanks very much!
