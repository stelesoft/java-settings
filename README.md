This directory contains IDE-specific Maven settings.

Which settings are loaded, depends on the value of the ``<dev.env>`` property. This can be passed into Maven via command line parameter:

```
mvn -Ddev.env=<ide_value>
```
where ``<ide_value>`` is a value that identifies a given development environment

The following environments are supported:

| Environment            | ``<ide_value>`` |
| ---------------------- | --------------- |
| NetBeans 11 (or newer) | netbeans-11     |

## Installation

1) Add this project as a Git submodule inside your Java Maven project
    * It must be cloned as a directory named ``java-settings``, placed as a peer of your project's POM file

1) In your project's POM file, add the following code. This will make the ``java-settings`` project a parent of your project, causing its settings to be automatically loaded into your project
```
    <!-- Load IDE-specific settings (from parent project) -->
    <parent>
        <groupId>com.stelesoft</groupId>
        <artifactId>java-ide-settings</artifactId>
        <version>0.1.0</version>
        <relativePath>./java-settings/pom.xml</relativePath>
    </parent>
```
