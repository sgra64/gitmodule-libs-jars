# gitmodule-libs-jars

[*Git-submodule*](https://www.atlassian.com/git/tutorials/git-submodule)
with *.jar* libraries for SE-1 *Java* projects grouped into packages:

- `jackson`: for processing *JSON* data in Java.

- `jacoco`: code coverage library for Java.

- `junit`: libraries for JUnit tests.

- `junit-platform-console-standalone-1.9.2.jar`: JUnit test runner.

- `log4j`: logging library for Java.

- `lombok`: library to inject constructors, getter and setter methods, see
    [*Project Lombok*](https://projectlombok.org).


Check-out this *git module* into sub-directory `libs` with:

```sh
git submodule add -f -- https://github.com/sgra64/gitmodule-libs-jars.git libs

ls -la libs                 # show content of libs folder holding the git module
```
```
total 2592
drwxr-xr-x 1       0 Aug 24 20:13 ./
drwxr-xr-x 1       0 Aug 24 18:37 ../
-rw-r--r-- 1     569 Aug 24 20:34 .bom          <-- 'bill-of-materials' file
drwxr-xr-x 1       0 Aug 24 18:39 .git/
-rw-r--r-- 1     518 Oct 21 12:15 .gitignore
drwxr-xr-x 1       0 Aug 24 20:14 jackson/
drwxr-xr-x 1       0 Aug 24 18:31 jacoco/
drwxr-xr-x 1       0 Aug 24 20:32 junit/
-rw-r--r-- 1 2614420 Aug 24 20:10 junit-platform-console-standalone-1.9.2.jar
drwxr-xr-x 1       0 Aug 24 20:16 log4j/
drwxr-xr-x 1       0 Aug 24 20:15 lombok/
-rw-r--r-- 1    7740 Aug 24 20:36 README.md
```

In addition, git has created a `.gitmodules` file in the project directory
and added the new gitmodule:

```sh
cat .gitmodules             # show .gitmodules file
```

Output shows the new git module registered with the project:

```
[submodule "libs"]
        path = libs
        url = https://github.com/sgra64/gitmodule-libs-jars.git
```

```sh
git submodule                       # list git submodules registered with the project
git submodule foreach git status    # show status of each registered submodule
```
```
d197ffc742fccc0e427b5b847041f94a0a11d911 libs (heads/main)

Entering 'libs'
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```


&nbsp;

## Module Scaffold

The scaffold of library packages and *.jar*-files in the `libs` directory is:

```sh
<libs>                  # branch directory
 |
 +--.bom                # 'bill-of-materials' (BOM) with list of '.jar'-files
 +--.gitignore          # file with patterns for git to ignore
 |
 +-<jackson>                    # library for processing JSON data in Java
 |  +--jackson-annotations-2.19.0.jar
 |  +--jackson-core-2.19.0.jar
 |  +--jackson-databind-2.19.0.jar
 |
 +-<jacoco>                     # code coverage library for Java
 |  +--jacocoagent.jar
 |  +--jacococli.jar
 |
 +-<junit>                      # libraries for JUnit tests
 |  +--apiguardian-api-1.1.2.jar
 |  +--junit-jupiter-api-5.12.2.jar
 |  +--junit-platform-commons-1.9.2.jar
 |  +--opentest4j-1.3.0.jar
 |                              # JUnit test runner
 +--junit-platform-console-standalone-1.9.2.jar
 |
 +-<log4j>                      # log4j2 logging library for Java
 |  +--log4j-api-2.24.3.jar
 |  +--log4j-core-2.24.3.jar
 |  +--log4j-slf4j2-impl-2.24.3.jar
 |  +--slf4j-api-2.0.17.jar
 |
 +-<lombok>                     # lombok library
    +--lombok-1.18.38.jar
```


List content of *.jar* files:

```sh
find libs -name '*.jar'
```

Output shows the list of *.jar* files for which download URL's are included
in the [*.bom*](.bom) (bill-of-materials) file:

```
libs/jackson/jackson-annotations-2.19.0.jar
libs/jackson/jackson-core-2.19.0.jar
libs/jackson/jackson-databind-2.19.0.jar
libs/jacoco/jacocoagent.jar
libs/jacoco/jacococli.jar
libs/junit/apiguardian-api-1.1.2.jar
libs/junit/junit-jupiter-api-5.12.2.jar
libs/junit/junit-platform-commons-1.9.2.jar
libs/junit/opentest4j-1.3.0.jar
libs/junit-platform-console-standalone-1.9.2.jar
libs/log4j/log4j-api-2.24.3.jar
libs/log4j/log4j-core-2.24.3.jar
libs/log4j/log4j-slf4j2-impl-2.24.3.jar
libs/log4j/slf4j-api-2.0.17.jar
libs/lombok/lombok-1.18.38.jar
```


&nbsp;

## Maven Repository

Files are sourced from the central [*Maven Repository*](https://mvnrepository.com).

- `jackson`:

  - [jackson-annotations](https://mvnrepository.com/artifact/com.fasterxml.jackson.core/jackson-annotations)-[2.19.0](https://mvnrepository.com/artifact/com.fasterxml.jackson.core/jackson-annotations/2.19.0).[jar](https://repo1.maven.org/maven2/com/fasterxml/jackson/core/jackson-annotations/2.19.0/jackson-annotations-2.19.0.jar)

  - [jackson-core](https://mvnrepository.com/artifact/com.fasterxml.jackson.core/jackson-core)-[2.19.0](https://mvnrepository.com/artifact/com.fasterxml.jackson.core/jackson-core/2.19.0).[jar](https://repo1.maven.org/maven2/com/fasterxml/jackson/core/jackson-core/2.19.0/jackson-core-2.19.0.jar)

  - [jackson-databind](https://mvnrepository.com/artifact/com.fasterxml.jackson.core/jackson-databind)-[2.19.0](https://mvnrepository.com/artifact/com.fasterxml.jackson.core/jackson-databind/2.19.0).[jar](https://repo1.maven.org/maven2/com/fasterxml/jackson/core/jackson-databind/2.19.0/jackson-databind-2.19.0.jar)


- `jacoco`:

  - [jacocoagent](https://mvnrepository.com/artifact/org.jacoco/org.jacoco.agent)-[0.8.13](https://mvnrepository.com/artifact/org.jacoco/org.jacoco.agent/0.8.13).[jar](https://repo1.maven.org/maven2/org/jacoco/org.jacoco.agent/0.8.13/org.jacoco.agent-0.8.13.jar)

  - [jacococli](https://mvnrepository.com/artifact/org.jacoco/org.jacoco.cli)-[0.8.13](https://mvnrepository.com/artifact/org.jacoco/org.jacoco.cli/0.8.13).[jar](https://repo1.maven.org/maven2/org/jacoco/org.jacoco.cli/0.8.13/org.jacoco.cli-0.8.13.jar)


- `junit`:

  - [apiguardian-api](https://mvnrepository.com/artifact/org.apiguardian/apiguardian-api)-[1.1.2](https://mvnrepository.com/artifact/org.apiguardian/apiguardian-api/1.1.2).[jar](https://repo1.maven.org/maven2/org/apiguardian/apiguardian-api/1.1.2/apiguardian-api-1.1.2.jar)

  - [junit-jupiter-api](https://mvnrepository.com/artifact/org.junit.jupiter/junit-jupiter-api)-[5.12.2](https://mvnrepository.com/artifact/org.junit.jupiter/junit-jupiter-api/5.12.2).[jar](https://repo1.maven.org/maven2/org/junit/jupiter/junit-jupiter-api/5.12.2/junit-jupiter-api-5.12.2.jar)

  - [junit-platform-commons](https://mvnrepository.com/artifact/org.junit.platform/junit-platform-commons)-[1.9.2](https://mvnrepository.com/artifact/org.junit.platform/junit-platform-commons/1.9.2).[jar](https://repo1.maven.org/maven2/org/junit/platform/junit-platform-commons/1.9.2/junit-platform-commons-1.9.2.jar)

  - [opentest4j](https://mvnrepository.com/artifact/org.opentest4j/opentest4j)-[1.3.0](https://mvnrepository.com/artifact/org.opentest4j/opentest4j/1.3.0).[jar](https://repo1.maven.org/maven2/org/opentest4j/opentest4j/1.3.0/opentest4j-1.3.0.jar)


- JUnit Code Runner:

  - [junit-platform-console-standalone](https://mvnrepository.com/artifact/org.junit.platform/junit-platform-console-standalone)-[1.9.2](https://mvnrepository.com/artifact/org.junit.platform/junit-platform-console-standalone/1.9.2).[jar](https://repo1.maven.org/maven2/org/junit/platform/junit-platform-console-standalone/1.9.2/junit-platform-console-standalone-1.9.2.jar)


- `log4j`:

  - [log4j-api](https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-api)-[2.24.3](https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-api/2.24.3).[jar](https://repo1.maven.org/maven2/org/apache/logging/log4j/log4j-api/2.24.3/log4j-api-2.24.3.jar)

  - [log4j-core](https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-core)-[2.24.3](https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-core/2.24.3).[jar](https://repo1.maven.org/maven2/org/apache/logging/log4j/log4j-core/2.24.3/log4j-core-2.24.3.jar)

  - [log4j-slf4j2-impl](https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-slf4j2-impl)-[2.24.3](https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-slf4j2-impl/2.24.3).[jar](https://repo1.maven.org/maven2/org/apache/logging/log4j/log4j-slf4j2-impl/2.24.3/log4j-slf4j2-impl-2.24.3.jar)

  - [slf4j-api](https://mvnrepository.com/artifact/org.slf4j/slf4j-api)-[2.0.17](https://mvnrepository.com/artifact/org.slf4j/slf4j-api/2.0.17).[jar](https://repo1.maven.org/maven2/org/slf4j/slf4j-api/2.0.17/slf4j-api-2.0.17.jar)


- `lombok`:

  - [lombok](https://mvnrepository.com/artifact/org.projectlombok/lombok)-[1.18.38](https://mvnrepository.com/artifact/org.projectlombok/lombok/1.18.38).[jar](https://repo1.maven.org/maven2/org/projectlombok/lombok/1.18.38/lombok-1.18.38.jar)

