# utf8-resources

Java Extension mechanism to load resource bundles as UTF-8 files.
                                                                
## Usage

This maven project generates a jar when included as a Java Extension in the JavaVM Runtime will load resource bundles as UTF-8.
By default it will load as UTF-8 all bundles that start with `resources`. (e.g. `resources.ApplicationResources`).
The default value can be overridden defining the system property `utf8.resources.base.names` as a comma separated list of baseName prefixes (e.g `-Dutf8.resources.base.names=resources,contents`)
will load all bundles that start with `resources` or `contents` as `UTF-8` encoded files.

## Building

1. Create jar file : `mvn clean package`
2. Testing : `mvn clean package integration-test`

## Running Java using this extension

1. Check the latest release [*HERE*](https://repo.fenixedu.org/fenixedu-maven-repository/org/fenixedu/utf8-resources/) and download the jar file.
2. Place it in some $PATH_TO_JAR_LOCATION directory (note: this directory should contain only the jar file for the extension mechanism to work properly) 
3. Choose your poison

### Install in JRE

1. copy the jar file to `$JAVA_HOME/jre/lib/ext` and pray

### Maven

1. `export MAVEN_OPTS="$MAVEN_OPTS -Djava.ext.dirs=$JAVA_HOME/jre/lib/ext:$PATH_TO_JAR_LOCATION"`

### Adding extension when running java in the command line

1. `java -jar -Djava.ext.dirs=$JAVA_HOME/jre/lib/ext:$PATH_TO_JAR_LOCATION sample-app.jar`
