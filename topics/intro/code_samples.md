[//]: # (title: 示例代码)

<!-- Copyright 2000-2022 JetBrains s.r.o. and other contributors. Use of this source code is governed by the Apache 2.0 license that can be found in the LICENSE file. -->

本指南包含了一些和 [intellij-sdk-code-samples](https://github.com/JetBrains/intellij-sdk-code-samples) GitHub 仓库相关的插件示例代码.

阅读 <path>README.md</path> 列出了所有的示例代码并带有简单描述.

Each sample is stored in a dedicated folder and is accompanied by its own <path>README.md</path>.
Links to the corresponding tutorial or reference page in this tutorial, as well as a list of relevant show-cased elements are provided.

## 使用 Gradle

所有示例插件都基于 Gradle, 参考 [Building Plugins with Gradle](gradle_build_system.md) 来开始.

Additionally, the screencast *Working with Gradle in IntelliJ IDEA* offers a thorough introduction to Gradle functionality inside IntelliJ IDEA.

<video href="6V6G3RyxEMk" title="Working with Gradle in IntelliJ IDEA" width="300"/>

## 设置示例代码

确保开发工具安装启用了插件 _Git_, _Gradle_, 和 _Plugin DevKit_.

使用菜单 <control>Git | Clone...</control>克隆 [intellij-sdk-code-samples](https://github.com/JetBrains/intellij-sdk-code-samples) GitHub 仓库.
克隆成功后, IDE会建议打开项目.

Select the code sample(s) to import via the [Gradle tool window](https://www.jetbrains.com/help/idea/gradle.html#link_gradle_project).

Alternatively, import _all_ code samples available by choosing <path>_gradleCompositeBuild</path>, which links all Gradle projects in a Composite Build.

After successful import, the project appears in the <control>Gradle</control> tool window tree as a new node.
Assign a Java 11 SDK in <menupath>Preferences | Build, Execution, Deployment | Build Tools | Gradle</menupath> for <control>Gradle JVM</control>.
Invoke <control>Reload All Gradle Projects</control> from the Gradle tool window toolbar if necessary.

## 运行代码示例

Run the plugin by using the Gradle [`runIde`](gradle_prerequisites.md#executing-the-plugin) task shown under the corresponding project's <control>Tasks</control> node in the <control>Gradle</control> tool window.
