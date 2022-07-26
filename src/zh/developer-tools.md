---
title: 有用的开发者工具
menu:
   main:
      name: "有用的开发者工具"
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

## 构建 Kyuubi

### 使用 Apache Maven 构建 Kyuubi

**Kyuubi** 是基于 [Apache Maven](http://maven.apache.org) 构建的，使用命令：

```
./build/mvn clean package -DskipTests
```

这会构建 Kyuubi 项目的所有子模块而无需运行任何单元测试。

如果要手动测试，可以直接在 Kyuubi 项目的根目录下运行 Kyuubi 启动：

```
bin/kyuubi start
```

### 单独构建子模块

例如，构建 Kyuubi Common 模块，可以使用命令:

```
build/mvn clean package -pl :kyuubi-common -DskipTests
```

### 单独构建多个子模块

例如，使用构建 Kyuubi Common、Kyuubi Ha 模块，可以使用命令:

```
build/mvn clean package -pl :kyuubi-common,:kyuubi-ha -DskipTests
```

### 跳过一些模块

例如，构建没有 Kyuubi Codecov 和 Assembly 模块，可以使用命令:

```
 mvn clean install -pl '!:kyuubi-codecov,!:kyuubi-assembly' -DskipTests
```

### 针对不同的 Apache Spark 版本构建 Kyuubi

从 v1.1.0 开始，Kyuubi 可以支持使用不同的 Spark 配置文件构建：

Profile | Default  | Since
--- | --- | --- 
-Pspark-3.0 | Yes | 1.0.0
-Pspark-3.1 | No | 1.1.0


### 配置 Apache Spark 的镜像

我们默认使用 `https://archive.apache.org/dist/spark/` 下载内置 Spark 发布包，
但是如果发现下载速度很慢或者无法下载，可以使用配置 `spark.archive.mirror` 配置到合适的镜像地址从而加速下载。 例如：

```
build/mvn clean package -Dspark.archive.mirror=https://mirrors.bfsu.edu.cn/apache/spark/spark-3.0.1
```

专门针对中国大陆的开发者，可以使用名为 `mirror-cn` 的预定义配置，该配置文件使用 `mirrors.bfsu.edu.cn` 来加速 Spark 二进制文件的下载。例如，
```
build/mvn clean package -Pmirror-cn
```

## 构建可运行的发行版

创建一个 Kyuubi 发行版，就像 [Kyuubi Release Page](https://github.com/apache/incubator-kyuubi/releases)
中展示的一样，在项目根目录中使用 `./build/dist` 构建。

有关使用的更多信息，请运行 `./build/dist --help`

```logtalk
./build/dist - Tool for making binary distributions of Kyuubi Server

Usage:
+--------------------------------------------------------------------------------------+
| ./build/dist [--name <custom_name>] [--tgz] [--spark-provided] <maven build options> |
+--------------------------------------------------------------------------------------+
name:           -  custom binary name, using project version if undefined
tgz:            -  whether to make a whole bundled package
spark-provided: -  whether to make a package without Spark binary
```

例如：

```
./build/dist --name custom-name --tgz
```

这会为你构建一个 Kyuubi 的发行版的包名为 `kyuubi-{version}-bin-custom-name.tar.gz`。

如果你想部署 Kyuubi 地方在已经有了 `Spark`，换句话说，你不需要内置捆绑下载的 `Spark`，则可以使用命令：

```
./build/dist --tgz --spark-provided
```

然后你会得到一个没有 Spark 二进制包 Kyuubi 发行版 `kyuubi-{version}-bin-without-spark.tar.gz`。

## 构建 Kyuubi 文档

按照以下步骤，学习如何构建 Kyuubi 文档。

### 安装和激活 `virtualenv`

首先，安装 `virtualenv`，这是可选的，但还是建议创建一个独立的环境来解决构建文档的依赖问题。

```
pip install virtualenv
```

切换到根目录下的 `docs`：

```
cd $KTUUBI_HOME/docs
```

创建一个名为`kyuubi`的虚拟环境，或者你也可以使用别的名字，只是不要和当前目录的文件夹冲突：

```
virtualenv kyuubi
```

激活它，

```
 source ./kyuubi/bin/activate
```

### 安装所有依赖项

安装所有的依赖项 `requirements.txt`

```
pip install -r requirements.txt
```

### 构建文档

```
make html
```

如果构建过程成功，则 HTML 页面位于 `_build/html`。

### 本地查看

使用你喜欢的浏览器打开它 `_build/html/index.html`。

## 运行测试

**Kyuubi** 可以基于 [Apache Maven](http://maven.apache.org) 和 ScalaTest Maven Plugin 进行测试，
请参考 [ScalaTest documentation](http://www.scalatest.org/user_guide/using_the_scalatest_maven_plugin)。

### 完全运行测试

以下是运行所有测试的命令示例：

```
./build/mvn clean test
```

### 为模块运行测试

```
./build/mvn clean test -pl :kyuubi-common
```

### 为单个测试运行测试

在本地开发时，运行一个测试或几个测试而不是全部测试很方便。

使用 Maven，可以使用 -DwildcardSuites 标志来运行单个 Scala 测试：

```
./build/mvn test -Dtest=none -DwildcardSuites=org.apache.kyuubi.service.FrontendServiceSuite
```

如果你想做一个需要与 kyuubi-spark-sql-engine 模块集成的单个测试，请先构建 kyuubi-spark-sql-engine 模块的包。

可以利用现成的工具来构建二进制发行版。

```
./build/dist
```

## 调试 Kyuubi

你可以使用 [Java Debug Wire Protocol](https://docs.oracle.com/javase/8/docs/technotes/guides/jpda/conninv.html#Plugin) 来调试 Kyuubi，可以使用你最喜欢的 IDE 工具，例如Intellij IDEA

### 远程调试

我们可以在 `KYUUBI_JAVA_OPTS` 中配置 JDWP 代理进行调试。

例如，
```
KYUUBI_JAVA_OPTS=-agentlib:jdwp=transport=dt_socket,server=y,suspend=y,address=5005 \
bin/kyuubi start
```

在 IDE 调试配置中设置相应的参数（主机和端口），例如，
<div align=center>

![](../imgs/idea_debug.png)

</div>

### 调试应用

- Spark Driver

```
spark.driver.extraJavaOptions   -agentlib:jdwp=transport=dt_socket,server=y,suspend=y,address=5005
```

- Spark Executor
```
spark.executor.extraJavaOptions   -agentlib:jdwp=transport=dt_socket,server=y,suspend=y,address=5005
```

## 开发者工具

### 更新项目版本

```
build/mvn versions:set -DgenerateBackupPoms=false
```

### 更新文档版本

每当项目版本更新时，请同时更新 `docsconf.py` 中的文档版本以针对即将发布的版本。

例如：

```
release = '1.2.0'
```

### 更新依赖列表

Kyuubi 使用 `dev/dependencyList` 文件指示哪些上游依赖项会实际上进入服务器端的类路径。

对于 PR，用于依赖检查的 linter 将在 GitHub Actions 中自动执行。

所以你可以先本地运行 `build/dependency.sh` 来检测潜在的依赖变化。

如果更改看起来符合预期，请运行 `build/dependency.sh --replace` 在你的 PR 中去更新 `dev/dependencyList`。
