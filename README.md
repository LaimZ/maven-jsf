maven-jsf
=========

Maven, JSF, Tomcat

This is a simple Maven (and Eclipse) Tomcat JSF project. For 03 NOV 2014 it doesn't use Maven Tomcat Plugin.

**To compile with Maven**, run **mvn package**.

**To run project:**
- Copy JavaServerFaces from **~/target** to your Tomcat webapp directory, for example **"C:\Program Files\apache-tomcat-7.0.56\webapps"**. You can either copy **JavaServerFaces.war**, but it doesn't work for me now.
- Then run Tomcat **<windows>"%CATALINA_HOME%\bin\startup.bat"</windows>**. **%CATALINA_HOME%** is an administrator system variable, for me it is **C:\Program Files\apache-tomcat-7.0.56**. Only this variable is nessesary for Tomcat to work.
- After start **Tomcat Server** : **"%CATALINA_HOME%\bin\startup.bat"**.

Now you can go to [http://localhost:8080/JavaServerFaces/hello.xhtml](http://localhost:8080/JavaServerFaces/hello.xhtml "http://localhost:8080/JavaServerFaces/hello.xhtml") and see your form! Before next copying don't forget to shutdown **Tomcat Server** : **"%CATALINA_HOME%\bin\shutdown.bat"**.

To set up deploy follow next steps: [http://www.mkyong.com/maven/how-to-deploy-maven-based-war-file-to-tomcat/](http://www.mkyong.com/maven/how-to-deploy-maven-based-war-file-to-tomcat/ "http://www.mkyong.com/maven/how-to-deploy-maven-based-war-file-to-tomcat/")

To deploy it from Eclipse For Java EE you need:
- Import this project as Maven project
- Near button Run press arrow and click **Run Configurations**, select **Maven Build** and create new with Right Mouse Button. Set goal as tomcat7:redeploy and Base directory as project root directory. User settings as ........\apache-maven-3.2.3\conf\settings.xml.

Note, that tomcat server should be runned as asministrator in this case and straight from this directory, no any %CATALINA_HOME%, for example 
```
C:\.....\tomcat....\bin\>startup.bat
```

This project was created step-by-step, according to [http://www.mkyong.com/jsf2/jsf-2-0-hello-world-example/](http://localhost:8080/JavaServerFaces/hello.xhtml "http://localhost:8080/JavaServerFaces/hello.xhtml"), thanks very much!
