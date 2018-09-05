# maven-repo
My personal maven repository.

## Usage

pom.xml

> 1) config repository

    <repositories>
        <repository>
            <id>gary5z-maven-repo</id>
            <url>https://raw.githubusercontent.com/gary5z/maven-repo/master/repository</url>
        </repository>
    </repositories>

> 2) config dependency

    <dependencies>
        <dependency>
            <groupId>com.oracle</groupId>
            <artifactId>ojdbc14</artifactId>
            <version>10.2.0.4.0</version>
        </dependency>
    </dependencies>

