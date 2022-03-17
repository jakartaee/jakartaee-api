Jakarta EE APIs
===============

This project generates the Jakarta EE API jar files and javadocs
by combining the artifacts produced by the individual API projects.

To update the version of an API that's included, update the corresponding
property in the top level pom.xml file.

To add or remove an API, all pom.xml files will need to be updated.

The file `src/main/javadoc/doc-files/speclicense.html` should have the content of
`EPL.html` for non-final releases, and should have the
content of `EFSL.html` for final releases.
Currently, this selection is controlled by the [Jenkins release build script](https://ci.eclipse.org/jakartaee-platform/job/release/).

Note that the glassfishbuild-maven-plugin is used to create "clean"
pom.xml files to be published for each of the projects.

Building
--------

Prerequisites:

* JDK11+ (Jakarta EE 10 and above)
* JDK8+ (Jakarta EE 8, 9, and 9.1)
* Maven 3.0.3+

Use the staging profile if necessary to pull in staged versions of artifacts.

Run the full build:

- mvn -Pstaging install javadoc:javadoc 
`or`
- mvn -Pstaging install javadoc:jar

Locate the API jar files:
- jakartaee-api/target/jakartaee-api-{version}.jar
- jakartaee-core-api/target/jakartaee-core-api-{version}.jar
- jakartaee-web-api/target/jakartaee-web-api-{version}.jar

Locate the javadocs:
- jakartaee-api/target/apidocs
- jakartaee-core-api/target/apidocs
- jakartaee-web-api/target/apidocs
`or`
- jakartaee-api/target/jakartaee-api-{version}-javadoc.jar
- jakartaee-web-api/target/jakartaee-core-api-{version}-javadoc.jar
- jakartaee-web-api/target/jakartaee-web-api-{version}-javadoc.jar


Locate the Bill Of Materials (BOM) file:
- jakartaee-bom/target/pom.xml
