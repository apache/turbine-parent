# About Turbine Parent

This is the parent for Turbine-Core, Site and most of Fulcrum components and inherits [Apache Parent POM](https://infra.apache.org/publishing-maven-artifacts.html).


## USAGE

- Parent module to align dependencies in Fulcrum and Turbine modules

- Based on last released [commons parent versions](https://commons.apache.org/proper/commons-parent/).

- Based on [ASF parent pom](https://maven.apache.org/pom/asf/index.html)

### CAVEAT

- Check turbine-parent-assembly module dependency, which overwrites Apache module (still needed in 2024?)

- Check versions with Maven Versions Plugin:

    - mvn versions:display-plugin-updates
    - mvn versions:display-property-updates
    - mvn versions:display-dependency-updates
    
### Owasp

If process hangs up, check or remove all files in maven repo in folder org/owasp/dependency-check-data/<VERSION> and 
run to check separately:

    mvn org.owasp:dependency-check-maven:check 

## RELEASE

- This module as any Apache release has to use the [VOTE] release voting phase, in this case in the Turbine dev mailing list.

### Notes 

Since v.9

- Java 8: include explicitely cobertura if needed: mvn clean site install -Papache-release,cobertura

Since v10

- Profile owasp, which enables the by default disabled dependency check.

Since v11

- Requires Java 11 minimal.

Since v12

- Exclude jacoco if jvm > 18, 
- Add cyclonedx for apache-release

Since v13

- Requires Java 17
