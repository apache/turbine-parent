# About Turbine Parent

This is the parent for Turbine-Core, Site and most of Fulcrum components and inherits [Apache Parent POM](https://infra.apache.org/publishing-maven-artifacts.html).


## USAGE

- Parent module to align dependencies in Fulcrum nand Turbine

- Based on last released [commons parent versions](http://svn.apache.org/repos/asf/commons/proper/commons-parent/trunk).

### CAVEAT

- Check turbine-parent-assembly module dependency, which overwrites Apache module (still needed in 2017)

- Check versions with Maven Versions Plugin:

    - mvn versions:display-plugin-updates
    - mvn versions:display-property-updates
    - mvn versions:display-dependency-updates
    
### Owasp

If process hangs up, check or remove all files in maven repo in folder org/owasp/dependency-check-data/<VERSION> and 
run to check separately:

    mvn org.owasp:dependency-check-maven:check 

## RELEASE

- Normally, this module (and turbine-parent-assembly) could be released lazily (add [LAZY][VOTE] in release voting phase).

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
