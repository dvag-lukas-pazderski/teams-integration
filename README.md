[![Java_CI_mit_Maven](https://github.com/dvag/maven-lib-on-github/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/dvag/maven-lib-on-github/actions/workflows/ci.yml)

# Java/Kotlin Library Template
Diese Repository dient als Beispiel/Template zum Bauen und Deployen eines JAR-Files in die [Github Package Registry](https://github.com/dvag/maven-lib-on-github/packages/1000927), die **Workflows** sind mit Hilfe des [maven-lib-workflow-generator](https://github.com/dvag/maven-lib-workflow-generator) aufgesetzt, dort befindet sich auch eine [Beschreibung der Workflows](https://github.com/dvag/maven-lib-workflow-generator/blob/main/Workflows.md).

## Notwendige Apassungen
In der pom.xml müssen ein paar Projekt-spezifische Eckdaten angepasst werden:
1. [Artifakt Koordinaten](https://github.com/dvag/maven-lib-on-github/blob/main/pom.xml#L7-L10)
```
    <artifactId>your-artifact-id</artifactId>
    <groupId>your-group-id</groupId>
```

2. [Sonar Key](https://github.com/dvag/maven-lib-on-github/blob/main/pom.xml#L22)
```
   <properties>
   ...
     <sonar.projectKey>your-sonar-key</sonar.projectKey>
```
3. [Package Repository](https://github.com/dvag/maven-lib-on-github/blob/main/pom.xml#L50)
```
    <distributionManagement>
        <repository>
            <id>github-dvag</id>
            <name>GitHub Packages</name>
            <url>https://maven.pkg.github.com/dvag/your-repository-name</url>
        </repository>
    </distributionManagement>
```

## DVAG Nexus
Werden Dependencies vom DVAG Nexus benötigt, so müssen kleine Anpassungen durchgeführt werden. Der Branch [dvag-nexus](https://github.com/dvag/maven-lib-on-github/tree/dvag-nexus) zeigt und beschreibt die Nutzung.

## CI Workflows

Die Workflows wurden mit dem [Workflow Setup](https://github.com/dvag/workflow-setup) erstellt und verwendet die [Reusable Workflows](https://github.com/dvag/workflow-center).
