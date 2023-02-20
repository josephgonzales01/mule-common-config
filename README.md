# Mule common config

Mule application project may inherit from this parent Maven POM configuration. In 
addition to some global settings and repository references, this config also 
defines the versions of all MuleSoft connectors and modules used by 
applications.

## Installation instructions

**Note:** If you need to make changes to this asset you **must** update the 
version number to avoid having stale references in your local or remote 
Maven repositories

For applications to reference the new version, you will need to either install 
the updated POM into your local Maven repository or deploy it to a remote
one (e.g., Exchange, Private Nexus).

To deploy to Exchange, first update the group ID reference in the project's `pom.xml` 
to reference the target business group you want to deploy to.

To deploy to a remote Maven repository you will need to supply the appropriate
distribution repository reference along with the desired group ID value.

## Usage reference

To reference this parent POM in any of the child projects, specify the `parent`
section in the child `pom.xml` as follows:
```
<parent>
    <groupId>com.my.company/groupId>
    <artifactId>mule-parent-config</artifactId>
    <version>1.0.0</version>
</parent>
```
Replace the `groupId` value to match the new group ID you gave the parent. Also 
update `version ` to match the new version number you gave the parent POM.

## Updating dependency versions

Use the following commands to find out if there are version updates to any of the 
Mule Connectors, Modules or Plugins referenced by this POM:
```
mvn versions:display-dependency-updates
mvn versions:display-plugin-updates
```
Be sure to consult the release notes and analyze the version changes carefully 
before actually updating any versions.
