# Maven Ecore Modeling Example

This example shows how to generate and build code from an Ecore/Genmodel (Meta-)Model with [Maven](https://maven.apache.org/).
It can be used to generate and compile the code from an Eclipse modeling project with the help of a CI pipeline and without the need to run Eclipse tasks manually.

[![CI](https://github.com/maxkratz/maven-ecore-modeling-example/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/maxkratz/maven-ecore-modeling-example/actions/workflows/ci.yml)


## Structure

| Name                                                                     | Type                      | Purpose                                                             |
| ------------------------------------------------------------------------ | ------------------------- | ------------------------------------------------------------------- |
| [org.example.model](org.example.model)                                   | Eclipse (plug-in) project | Contains the Ecore and the Genmodel files to generate code from.    |
| [ci.yml](.github/workflows/ci.yml)                                       | File                      | Example GitHub Actions configuration to build and push the project. |
| [pom.xml](org.example.model/pom.xml)                                     | File                      | Maven configuration file that contains the porject's configuration. |
| [GenerateModel.mwe2](org.example.model/src/main/java/Generatemodel.mwe2) | File                      | MWE2 file to generate the source code from the Ecore/Genmodel file. |


## How to build

- Generate code + build the project:
  `$ mvn clean package`
- Build + install the project to the local `.m2/` folder:  
  `$ mvn clean install`
- Change the version of the plug-in to a new semver (e.g., before publishing a new release):  
  `$ mvn versions:set -DnewVersion=0.0.2-SNAPSHOT`


## License

This project is licensed under the Eclipse Public License - v1.0 - see the [LICENSE](LICENSE) file for more details.
