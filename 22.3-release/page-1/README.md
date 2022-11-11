# Getting Started

GraalVM是一个高性能的JDK, 是为了提高Java程序的性能以及更充分的利用资源而设计的.
GraalVM提供两种运行java程序的方式: 一种是用Graalvm JIT编译器动态的解释字节码的方式运行在HotSpot虚拟机之上, 另一种是用AOT编译成本地可执行文件.
除了Java，它还提供了JavaScript、Ruby、Python和其他一些流行语言的运行时。GraalVM的多语言功能使得在一个应用程序中混合编程语言成为可能，同时消除了任何语言相互调用成本。

在这里，您将找到有关安装 GraalVM 社区版、使用它运行基本应用程序以及添加对随附功能的支持的信息。此外，您将了解 GraalVM 的多语言功能，并了解如何构建特定于平台的 Java 应用程序的本机可执行文件。

如果您是 GraalVM 新手，我们建议您从 GraalVM 简介开始[Introduction to GraalVM](https://www.graalvm.org/22.3/docs/introduction/)，您将在其中找到有关 GraalVM 架构、可用发行版、支持的平台、核心和附加功能等的信息。

如果您已经安装了 GraalVM 并且有使用它的经验，您可以跳过此入门指南并继续阅读深入的参考手册 [Reference Manuals](https://www.graalvm.org/22.3/reference-manual/)。

## 安装 GraalVM

安装GraalVM需要几分钟:
- Linux
- maxOS
- windows
- Docker Container
- SDKMan

## 运行程序

GraalVM的核心发行版包括JVM和GraalVM编译器。下载并安装GraalVM之后，您就可以不加修改地运行任何Java应用程序了。
其他语言支持可以根据要求安装，使用gu - GraalVM Updater工具安装其他语言运行时和实用程序。
接下来你会发现如何添加其他可选的GraalVM运行时的信息，包括JavaScript, Node.js, LLVM, Ruby, R, Python和WebAssembly。

## Run Java

java启动器使用GraalVM默认编译器- Graal运行JVM。
```shell
java -version
```

```java
public class HelloWorld  {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```
运行以下命令,将class转换成字节码,然后运行Java程序
```shell
javac HelloWorld.java
java HelloWorld
```

You can find a collection of larger Java examples on the Examples Applications page. 
For more information on the GraalVM compiler, go to Compiler. For more extensive documentation on running Java, proceed to JVM Languages.

## 运行JavaScript和Node.js

GraalVM支持运行JavaScript应用程序。JavaScript运行时是可选的，可以通过以下命令安装:

```shell
gu install js
```
它将js启动器安装在$GRAALVM_HOME/bin目录中。安装了JavaScript运行时，你就可以执行纯JavaScript代码了，包括REPL模式和直接执行脚本文件:
```shell
# 启动交互模式
$GRAALVM_HOME/bin/js
```

GraalVM还支持运行Node.js应用程序。默认情况下不安装Node.js支持，但可以通过以下命令轻松添加:
```shell
gu install nodejs
```
node和npm启动器都可以在$GRAALVM_HOME/bin目录中使用。
```shell
$GRAALVM_HOME/bin/node -v
$GRAALVM_HOME/bin/npm show <package name> version
```
超过100,000个npm包被定期测试，并与GraalVM兼容，包括诸如express、react、async、request、browserify、grunt、mocha和下划线等模块。
要安装node. js模块，请使用$GRAALVM_HOME/bin中的npm可执行文件，该文件与node一起安装。npm命令相当于默认的Node.js命令，支持所有Node.js api。

### Examples
使用npm Install安装colors、ansispan和express模块。安装模块后，您可以从应用程序中使用它们。
```shell
$GRAALVM_HOME/bin/npm install colors ansispan express
```




