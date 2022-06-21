---
title: Useful Developer Tools
menu:
   main:
      name: "Useful Developer Tools"
      parent: "development"
---
<!---
  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this file except in compliance with the License.
  You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License. See accompanying LICENSE file.
-->

## Building Kyuubi

### Building Kyuubi with Apache Maven

**Kyuubi** is built based on [Apache Maven](http://maven.apache.org),

```
./build/mvn clean package -DskipTests
```

This results in the creation of all sub-modules of Kyuubi project without running any unit test.

If you want to test it manually, you can start Kyuubi directly from the Kyuubi project root by running

```
bin/kyuubi start
```

### Building a Submodule Individually

For instance, you can build the Kyuubi Common module using:

```
build/mvn clean package -pl :kyuubi-common -DskipTests
```

### Building Submodules Individually

For instance, you can build the Kyuubi Common module using:

```
build/mvn clean package -pl :kyuubi-common,:kyuubi-ha -DskipTests
```

### Skipping Some modules

For instance, you can build the Kyuubi modules without Kyuubi Codecov and Assembly modules using:

```
 mvn clean install -pl '!:kyuubi-codecov,!:kyuubi-assembly' -DskipTests
```

### Building Kyuubi against Different Apache Spark versions

Since v1.1.0, Kyuubi support building with different Spark profiles,

Profile     | Default  | Since
----------- | -------- | --- 
-Pspark-3.0 | No       | 1.0.0
-Pspark-3.1 | No       | 1.1.0
-Pspark-3.2 | Yes      | 1.4.0
-Pspark-3.3 | No       | 1.6.0


### Defining the Apache Mirror for Spark

By default, we use `https://archive.apache.org/dist/spark/` to download the built-in Spark release package,
but if you find it hard to reach, or the downloading speed is too slow, you can define the `spark.archive.mirror`
property to a suitable Apache mirror site. For instance,

```
build/mvn clean package -Dspark.archive.mirror=https://mirrors.bfsu.edu.cn/apache/spark/spark-3.2.1
```

Visit [Apache Mirrors](http://www.apache.org/mirrors/) and choose a mirror based on your region.

Specifically for developers in China mainland, you can use the pre-defined profile named `mirror-cdn` which use
`mirrors.bfsu.edu.cn` to speed up Spark Binary downloading. For instance,

```
build/mvn clean package -Pmirror-cn
```

## Building a Runnable Distribution

To create a Kyuubi distribution like those distributed by [Kyuubi Release Page](https://github.com/apache/incubaotr-kyuubi/releases),
and that is laid out so as to be runnable, use `./build/dist` in the project root directory.

For more information on usage, run `./build/dist --help`

```logtalk
./build/dist - Tool for making binary distributions of Kyuubi

Usage:
+------------------------------------------------------------------------------------------------------+
| ./build/dist [--name <custom_name>] [--tgz] [--flink-provided] [--spark-provided] [--hive-provided]  |
|              [--mvn <maven_executable>] <maven build options>                                        |
+------------------------------------------------------------------------------------------------------+
name:           -  custom binary name, using project version if undefined
tgz:            -  whether to make a whole bundled package
flink-provided: -  whether to make a package without Flink binary
spark-provided: -  whether to make a package without Spark binary
hive-provided:  -  whether to make a package without Hive binary
mvn:            -  external maven executable location
```

For instance,

```
./build/dist --name custom-name --tgz
```

This results a Kyuubi distribution named `kyuubi-{version}-bin-custom-name.tar.gz` for you.

If you are planing to deploy Kyuubi where `spark` is provided, in other word, it's not required to bundle spark binary, use

```
./build/dist --tgz --spark-provided
```

Then you will get a Kyuubi distribution without spark binary named `kyuubi-{version}-bin.tar.gz`.

## Building Kyuubi Documentation

Follow the steps below and learn how to build the Kyuubi documentation as the one you are watching now.

### Install & Activate `virtualenv`

Firstly, install `virtualenv`, this is optional but recommended as it is useful to create an independent environment to resolve dependency issues for building the documentation.

```
pip install virtualenv
```

Switch to the `docs` root directory.

```
cd $KTUUBI_HOME/docs
```

Create a virtual environment named 'kyuubi' or anything you like using `virtualenv` if it's not existing.

```
virtualenv kyuubi
```

Activate it,

```
 source ./kyuubi/bin/activate
```

### Install all dependencies

Install all dependencies enumerated in the `requirements.txt`

```
pip install -r requirements.txt
```

### Create Documentation

```
make html
```

If the build process succeed, the HTML pages are in `_build/html`.

### View Locally

Open the `_build/html/index.html` file in your favorite web browser.

## Running Tests

**Kyuubi** can be tested based on [Apache Maven](http://maven.apache.org) and the ScalaTest Maven Plugin,
please refer to the [ScalaTest documentation](http://www.scalatest.org/user_guide/using_the_scalatest_maven_plugin),

### Running Tests Fully

The following is an example of a command to run all the tests:

```
./build/mvn clean test
```

### Running Tests for a Module

```
./build/mvn clean test -pl :kyuubi-common
```

### Running Tests for a Single Test

When developing locally, it’s convenient to run one single test, or a couple of tests, rather than all.

With Maven, you can use the -DwildcardSuites flag to run individual Scala tests:

```
./build/mvn install `test -Dtest=none -DwildcardSuites=org.apache.kyuubi.service.FrontendServiceSuite
```

If you want to make a single test that need integrate with kyuubi-spark-sql-engine module, please build the package for kyuubi-spark-sql-engine module at first.

You can leverage the ready-made tool for creating a binary distribution.

```
./build/dist
```

## Debugging Kyuubi

You can use the [Java Debug Wire Protocol](https://docs.oracle.com/javase/8/docs/technotes/guides/jpda/conninv.html#Plugin) to debug Kyuubi
with your favorite IDE tool, e.g. Intellij IDEA.

### Debugging Server

We can configure the JDWP agent in `KYUUBI_JAVA_OPTS` for debugging.


For example,
```
KYUUBI_JAVA_OPTS=-agentlib:jdwp=transport=dt_socket,server=y,suspend=y,address=5005 \
bin/kyuubi start
```

In the IDE, you set the corresponding parameters(host&port) in debug configurations, for example,
<div align=center>

![](../imgs/idea_debug.png)

</div>

### Debugging Apps

- Spark Driver

```
spark.driver.extraJavaOptions   -agentlib:jdwp=transport=dt_socket,server=y,suspend=y,address=5005
```

- Spark Executor
```
spark.executor.extraJavaOptions   -agentlib:jdwp=transport=dt_socket,server=y,suspend=y,address=5005
```

## Developer Tools

### Update Project Version

```

build/mvn versions:set -DgenerateBackupPoms=false
```

### Update Document Version

Whenever Project version updates, please also update the document version at `docs/conf.py` to target the upcoming release.

For example,

```
release = '1.2.0'
```

### Update Dependency List

Kyuubi uses the `dev/dependencyList` file to indicates what upstream dependencies will actually go to the server-side classpath.

For Pull requests, a linter for dependency check will be automatically executed in GitHub Actions.


You can run `build/dependency.sh` locally first to detect the potential dependency change first.

If the changes look expected, run `build/dependency.sh --replace` to update `dev/dependencyList` in your Pull request.
