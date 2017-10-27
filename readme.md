# A simple, minimal Maven example: Hello Marketo

***NOTE: This project uses the Java 1.8 JDK, make sure it is built with Java 1.8.***


Maven Command Options:

Running 'mvn clean' will get us back to only the source Java and the 'pom.xml':

    marketo$ mvn clean --quiet

    marketo$ ack -a -f

pom.xml

src/main/java/com/marketo/app/App.java

src/test/java/com/marketo/app/AppTest.java

 


Running 'mvn compile' produces a class file:

    marketo$ mvn compile --quiet

    marketo$ ack -a -f

pom.xml

src/main/java/com/marketo/app/App.java

src/test/java/com/marketo/app/AppTest.java

target/classes/com/marketo/app/App.class



Running 'mvn package' does a compile and creates the target directory, including a jar:

    marketo$ mvn clean --quiet

    marketo$ mvn package > /dev/null

    marketo$ ack -a -f 

pom.xml

src/main/java/com/marketo/app/App.java

src/test/java/com/marketo/app/AppTest.java

target/classes/com/marketo/app/App.class

target/maven-archiver/pom.properties

target/marketo-1.0-SNAPSHOT.jar

target/surefire-reports/com.marketo.app.AppTest.txt

target/surefire-reports/TEST-com.marketo.app.AppTest.xml

target/test-classes/com/marketo/app/AppTest.class



Once the jar has been created, it can be run with: 'java -jar target/marketo-1.0-SNAPSHOT.jar' 
