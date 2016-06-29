# ciwise

[![Build Status: Linux](https://travis-ci.org/ciwise/ciwise.svg?branch=master)](https://travis-ci.org/ciwise/ciwise)

## Introduction

The ciwise POM is a pom project for Apache Maven. It implements the CI Wise Inc. "Organizational POM", 
by locking down the versions of Maven plugins, use of the Spring platform, and other configurations. This POM
also provides plugins for build and reporting that will be used with most projects created by CI Wise Inc.
or the CI Wise ORG team. This is an important best practice for any organization using Maven because it
not only takes care of code re-use, it takes care of Maven configuration re-use as well.

## Usage

The pom is deployed to the Maven Central Repository and can therefore be used by just adding the following
snippet to your new project's pom.xml file..

```xml
<parent>
  <groupId>org.ciwise</groupId>
  <artifactId>ciwise</artifactId>
  <version>${version}</version>
</parent>
```

Find version in GitHub releases.

Once you have established the parent POM, you can reference any plugin without a version and will 
inherit the latest version automatically from the parent POM. 

```xml
<plugin>
  <groupId>org.owasp</groupId>
  <artifactId>dependency-check-maven</artifactId>
</plugin>
```

If, for some reason (unlikely but possible), you can not adopt the latest version 
of a specific plugin, you can and should still use this project as a parent pom 
and just override the one plugin version that is the offender. If you encounter 
this situation be sure to report the issue with the respective plugin.

The same applies for any plugin configuration inherited from this pom.


## Project Versioning and Updates

The first publicly announced release will be 1.0.0. Following versions will always
use http://semver.org[semantic versioning]. Whenever one of the referenced 
plugins upgrades a major version, this project will upgrade major version by one. 
The same process will be followed with minor as well as bugfix versions. 
We also aim for a regular release schedule aiming initially for at least every 3 
months, ideally every month, as well as ad hoc releases whenever often used plugins
provide important updates. 

More details about changes between versions are available from the 
https://github.com/ciwise/ciwise/blob/master/CHANGELOG.md[changelog]

## License

Apache License, Version 2.0

For full text see LICENSE.txt file or http://www.apache.org/licenses/LICENSE-2.0
 
##Contributions

Send a pull request or report issues on GitHub. The suggestion of a useful plugin
in an issue is welcomed. 

## Development

You can check for new plugins and versions with

```
$ mvn versions:display-plugin-updates
$ mvn versions:display-property-updates
```

Deployment and release are done the usual Maven way..

```
$ mvn clean deploy
```

and 

```
mvn release:prepare release:perform
```

This does the full release and deployment to the Central Repository.


## Current Team 
- David L. Whitehurst http://www.dlwhitehurst.com

## Known projects using this parent POM

This is appropriately licensed to be easily used by commercial and open source 
projects alike. Please let us know if you are using this project and would like 
to be listed here.


