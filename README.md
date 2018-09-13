# maven-repo
My personal maven repository.

## Usage

pom.xml

> 1) config repository

    <repositories>
        <repository>
            <id>gary5z-maven-repo</id>
            <url>https://raw.githubusercontent.com/gary5z/maven-repo/master</url>
        </repository>
    </repositories>

> 2) config dependency

    <dependencies>
        <dependency>
            <groupId>com.oracle</groupId>
            <artifactId>ojdbc14</artifactId>
            <version>10.2.0.4.0</version>
        </dependency>
        <dependency>
            <groupId>org.jdesktop </groupId>
            <artifactId>appframework</artifactId>
            <version>1.0.3</version>
        </dependency>
        <dependency>
            <groupId>org.xvolks</groupId>
            <artifactId>JNative</artifactId>
            <version>1.0.0</version>
        </dependency>
        <dependency>
            <groupId>org.jdesktop </groupId>
            <artifactId>swing-worker</artifactId>
            <version>1.1</version>
        </dependency>
    </dependencies>

