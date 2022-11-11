[//]: # (title: 关于SDK文档指南)

<!-- Copyright 2000-2022 JetBrains s.r.o. and other contributors. Use of this source code is governed by the Apache 2.0 license that can be found in the LICENSE file. -->

<excerpt>简介和SDK平台内容概览.</excerpt>

通过阅读IntelliJ源代码，大致将代码分为以下几部分，此划分非出自官方难免有些纰漏，了解各部分的功能会对开发工作有很大帮助。
*   Base Platform：包括基础平台支持，多线程任务，消息传递，Project Structure工程结构，library，SDK等。
*   Action System：Action动作系统，开发者可以通过插件向菜单和工具栏添加新项目来自定义IntelliJ平台UI。
*   PSI：构建丰富的代码语法和语义模型，代码完成代码检测都是基于此完成。
*   VFS：它封装了大部分对活动文件的处理操作，在不同平台上提供了统一的文件API。
*   GUI： 常用界面的封装，对话框，工具栏，文件选择器，Notification等。
*   Editor Basics：获取文档，文本操作，代码定位，编辑器事件处理系统。
*   Plugin：插件机制，让第三方可以扩展IDE功能。
*   Others：其他功能，代码检测，代码完成等其他工具代码。

本指南分为几个部分,类似于教科书.
每个部分都基于前一部分的内容,但没有必要按顺序阅读指南.
[Key Topics](key_topics.md)页面旨在链接到能够理解体系结构并开始构建插件所必需的页面.

All source links and reference lists target IntelliJ Platform %ijPlatform%.

> 浏览本指南时,您会注意到有些主题是灰色的.
遗憾的是,该指南并不完整,并包含某些主题的占位符.
我们正在努力提高覆盖率,但如果因内容缺失而陷入困境,请参阅[获得帮助](getting_help.md)部分,了解有关如何再次移动的详细信息.
>
> 该指南也是[GitHub上的开源](https://github.com/JetBrains/intellij-sdk-docs),我们非常感谢收到新内容或更新的请求.
拉取请求不需要完全全面 - 如果稍微更新对您有帮助,它也将帮助其他开发人员!
所有拉取请求将在被接受之前进行审核,因此不必担心不准确.
> 请参阅 [Contributing](intellij-sdk-docs-original_CONTRIBUTING.md) 页面了解更多信息.
>
{style="note"}

> 参考 [](glossary.md) 了解常见术语手册.
>
{style="tip"}

#### 第一部分 — 插件

描述如何创建可以扩展 _IntelliJ Platform_ 的插件.
包括有关如何设置项目,注册扩展点,确定 _IntelliJ Platform_ 的特定版本以及如何打包,部署和测试插件的详细信息.

#### 第二部分 — 基础平台

描述了体系结构的基础层,它提供了许多功能和实用程序,例如组件模型,用户界面,文档和编辑器,虚拟文件系统,设置和线程以及后台任务.
基础平台层基本上包含 _IntelliJ Platform_ 的功能,该功能不针对语言功能或解析.

#### 第三部分 — 项目模型

项目模型文档,它表示当前加载的项目的文件和配置,以及用于构建项目的构建系统.

#### 第四部分 —  PSI

Program Structure Interface 程序结构接口(PSI)为许多不同的文件类型构建语法和语义模型.
本节介绍如何使用PSI,导航和操作语法树,还介绍了强大的引用系统,它允许语法树节点引用语义模型中的项.
它还详细说明了PSI如何创建和使用索引.

#### 第五部分 — 功能

Describes how to extend and interact with various features that use the PSI layer, such as code completion, navigation, <shortcut>Alt+Enter</shortcut> items, intentions, refactorings, and more.
See also the section on Custom Languages below for language-specific features that are only applicable when adding support for a new language.

#### 第六部分 — 测试

描述用于编写涵盖插件功能的自动化测试的可用基础结构.

#### 第七部分 — 自定义语言

插件经常扩展对现有语言的支持,例如向Java文件添加检查.
本节介绍如何为 _IntelliJ Platform_ 添加对新语言的支持, 从默认情况下不支持该语言,创建解析器,语法和语义模型以及构建在顶层的所有功能.

#### 第八部分 — 产品特定

_IntelliJ Platform_ 中的许多功能都是语言和产品无关的.
例如,代码检查在Java中的工作方式与在Ruby中的工作方式相同,只是语法树和语义信息不同.
本节介绍产品特定功能,例如特定项目模型差异以及如何在插件中定位它们.

#### 第九部分 — 自定义IDE

记录如何使用 _IntelliJ Platform_ 创建新的自定义IDE, 而不是给现有产品添加插件,例如 WebStorm或Android Studio.

#### 附录I — 资源

链接到[有用的资源](useful_links.md), [](glossary.md), [](extension_point_list.md),  [](explore_api.md) 如何浏览API的技巧以及 [](learning_resources.md).

#### 附录 II — API和兼容性

了解 [](verifying_plugin_compatibility.md) 和 [backwards-incompatible](api_changes_list.md) API 改动以及每个主要IntelliJ Platform版本中的 [值得留意的API改动以及新功能](api_notable.md).

#### 附录 III — 工具

常用的有用工具及指南 [](tools_gradle_intellij_plugin.md).
