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

> 2) adding dependency

    <dependencies>
        <dependency>
            <groupId>com.ckfinder</groupId>
            <artifactId>ckfinder</artifactId>
            <version>2.3</version>
        </dependency>
    </dependencies>

## How

> 1) create new folder as a local maven repository

```bash
d:\>mkdir git-maven-repo
```

> 2) deploy jar to local maven repository

```bash
e.g: deploy ojdbc14-10.2.0.4.0.jar to git-maven-repo

d:\>mvn deploy:deploy-file -Dmaven.test.skip=true -Dfile=d:/ojdbc14-10.2.0.4.0.jar -DgroupId=com.oracle -DartifactId=ojdbc14 -Dversion=10.2.0.4.0 -Dpackaging=jar -DrepositoryId=gary5z-maven-repo -Durl=file://d:/git-maven-repo/
[INFO] Scanning for projects...
[INFO]
[INFO] ------------------------------------------------------------------------
[INFO] Building Maven Stub Project (No POM) 1
[INFO] ------------------------------------------------------------------------
[INFO]
[INFO] --- maven-deploy-plugin:2.7:deploy-file (default-cli) @ standalone-pom ---
Uploading: file://d:/git-maven-repo/com/oracle/ojdbc14/10.2.0.4.0/ojdbc14-10.2.0.4.0.jar
Uploaded: file://d:/git-maven-repo/com/oracle/ojdbc14/10.2.0.4.0/ojdbc14-10.2.0.4.0.jar (1520 KB at 13096.7 KB/sec)
Uploading: file://d:/git-maven-repo/com/oracle/ojdbc14/10.2.0.4.0/ojdbc14-10.2.0.4.0.pom
Uploaded: file://d:/git-maven-repo/com/oracle/ojdbc14/10.2.0.4.0/ojdbc14-10.2.0.4.0.pom (395 B at 64.3 KB/sec)
Downloading: file://d:/git-maven-repo/com/oracle/ojdbc14/maven-metadata.xml
Uploading: file://d:/git-maven-repo/com/oracle/ojdbc14/maven-metadata.xml
Uploaded: file://d:/git-maven-repo/com/oracle/ojdbc14/maven-metadata.xml (307 B at 37.5 KB/sec)
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 1.146 s
[INFO] Finished at: 2018-09-05T10:21:00+08:00
[INFO] Final Memory: 7M/123M
[INFO] ------------------------------------------------------------------------
```

> 3) upload to my github repository

create new bat file: deploy.bat
```bash
@echo off

cd d:/git-maven-repo

git init
git add d:/git-maven-repo/*
git commit -m "first commit"
git remote add origin https://github.com/gary5z/maven-repo.git
git push -u origin master

pause

```

## more about maven [deploy](https://maven.apache.org/plugins/maven-deploy-plugin/)
- [deploy:deploy](https://maven.apache.org/plugins/maven-deploy-plugin/deploy-mojo.html)  is used to automatically install the artifact, its pom and the attached artifacts produced by a particular project. Most if not all of the information related to the deployment is stored in the project's pom.
- [deploy:deploy-file](https://maven.apache.org/plugins/maven-deploy-plugin/deploy-file-mojo.html) is used to install a single artifact along with its pom. In that case the artifact information can be taken from an optionally specified pomFile, but can be completed/overriden using the command line.


