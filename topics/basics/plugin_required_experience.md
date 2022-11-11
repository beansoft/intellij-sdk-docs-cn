[//]: # (title: 所需经验)

<!-- Copyright 2000-2022 JetBrains s.r.o. and contributors. Use of this source code is governed by the Apache 2.0 license. -->

<note> 主题插件: 只需要了解颜色和JSON文件即可, 也不需要了解Java </note>

<note> 旧版本的纯DevKit插件: 不需要了解Gradle</note>

IntelliJ Platform 是一个 JVM 应用, 大部分代码使用 Java 和 [Kotlin](https://kotlinlang.org)编写.

现阶段还不能使用非JVM语言来开发IntelliJ Platform插件.
开发IntelliJ Platform插件需要下列知识和经验:
- Java, Kotlin, 或其它 JVM 语言(译著: 例如Scala, Groovy),以及标准和第三方库
- [Gradle](https://gradle.org/) 或类似的构建系统 (如 Maven), 新版本插件开发推荐
- [Swing](https://en.wikipedia.org/wiki/Swing_(Java)) 开发用户界面
- [Java 并发模型](https://docs.oracle.com/javase/tutorial/essential/concurrency/index.html)
- 有使用基于 IntelliJ Platform 平台的开发工具 (如 [IntelliJ IDEA](https://www.jetbrains.com/idea/))

请注意IntelliJ Platform是个大工程, 同时文档会尽可能多的涵盖主题, 但不可能在文档中包含每个功能点及其使用方法.
开发插件有时候需要仔细研究 [IDEA平台源码](https://github.com/JetBrains/intellij-community) 以及分析 analyzing the [其它插件中的示例实现方法](https://jb.gg/ipe).

强烈推荐在开发插件之前熟悉 [](explore_api.md) 篇.


> 某些情况下, 实现一个真正的 IntelliJ Platform 插件可能没啥必要, 因为存在 [](plugin_alternatives.md).
>
{type="tip"}
