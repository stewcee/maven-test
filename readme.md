# A simple, minimal Maven example: hello world

To create the files in this git repo we've already run `mvn archetype:generate` from http://maven.apache.org/guides/getting-started/maven-in-five-minutes.html

    mvn archetype:generate -DgroupId=com.marketo.app -DartifactId=marketo -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false

Now, to print "Hello World!", type either...

    cd marketo
    mvn compile
    java -cp target/classes com.marketo.app.App

or...

    cd marketo
    mvn package
    java -cp target/marketo-1.0-SNAPSHOT.jar com.marketo.app.App

Running `mvn clean` will get us back to only the source Java and the `pom.xml`:

    marketo$ mvn clean --quiet
    marketo$ ack -a -f
    pom.xml
    src/main/java/com/marketo/app/App.java
    src/test/java/com/marketo/app/AppTest.java

Running `mvn compile` produces a class file:

    marketo$ mvn compile --quiet
    marketo$ ack -a -f
    pom.xml
    src/main/java/com/marketo/app/App.java
    src/test/java/com/marketo/app/AppTest.java
    target/classes/com/marketo/app/App.class
    marketo$ 
    marketo$ java -cp target/classes com.marketo.app.App
    Hello World!

Running `mvn package` does a compile and creates the target directory, including a jar:

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
    marketo$ 
    marketo$ java -cp target/marketo-1.0-SNAPSHOT.jar com.marketo.app.App
    Hello World!

Running `mvn clean compile exec:java` requires http://mojo.codehaus.org/exec-maven-plugin/

Running `java -jar target/marketo-1.0-SNAPSHOT.jar` requires http://maven.apache.org/plugins/maven-shade-plugin/
