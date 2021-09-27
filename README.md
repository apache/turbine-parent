# About Turbine Parent

This is the parent for Turbine-Core, Site and most of Fulcrum components and inherits [Apache Parent POM](https://infra.apache.org/publishing-maven-artifacts.html).


## USAGE

- Parent module to align dependencies in Fulcrum nand Turbine

- Based on last released [commons parent versions](http://svn.apache.org/repos/asf/commons/proper/commons-parent/trunk).

### CAVEAT

- Check turbine-parent-assembly module dependency, which overwrites Apache module (still needed in 2017)

## RELEASE

- Normally, this module (and turbine-parent-assembly) could be released lazily (add [LAZY][VOTE] in release voting phase).

### Notes 

Since v.9

- Java 8: include explicitely cobertura if needed: mvn clean site install -Papache-release,cobertura
