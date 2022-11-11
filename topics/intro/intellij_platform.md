[//]: # (title: IntelliJ 平台)

<!-- Copyright 2000-2022 JetBrains s.r.o. and other contributors. Use of this source code is governed by the Apache 2.0 license that can be found in the LICENSE file. -->

<excerpt>介绍 IntelliJ Platform, 插件, 以及基于它的开发工具.</excerpt>

IntelliJ Platform 本身并不是产品,而是提供构建IDE的平台.
它用于为JetBrains产品提供基础能力, 如[IntelliJ IDEA](https://www.jetbrains.com/idea/),[WebStorm](https://www.jetbrains.com/webstorm/),[RubyMine](https://www.jetbrains.com/ruby/),[DataGrip](https://www.jetbrains.com/datagrip/)和[Rider](https://www.jetbrains.com/rider/).
它也是开源的,第三方可以使用它来构建IDE,例如来自Google的[Android Studio](https://developer.android.com/studio/index.html).

 _IntelliJ Platform_  提供了这些IDE提供丰富语言工具支持所需的所有基础结构.
它提供了一个基于组件驱动,跨平台JVM的应用程序主机,具有高级用户界面工具包,用于创建工具窗口,树视图和列表(支持快速搜索)以及弹出菜单和对话框.

它还包括图像编辑器和全文编辑器,并提供语法突出显示,代码折叠,代码完成和其他富文本编辑功能的抽象实现.

此外,它还包括可插入的API,用于构建通用IDE功能,例如项目模型和构建系统.
它还提供了非常丰富的调试体验的基础结构,具有语言无关的高级断点支持,调用堆栈,监视窗口和表达式评估.

但  _IntelliJ Platform_  的真正力量来自程序结构接口(Program Structure Interface, PSI).
这是一组功能,可用于解析文件和构建代码的丰富语法和语义模型,以及从此数据构建索引.
这提供了许多功能,从快速导航到文件,类型和符号,到代码完成窗口的内容,查找用法,代码检查和代码重写,快速修复或重构,以及许多其他功能.

 _IntelliJ Platform_  包括多种语言的解析器和PSI模型,其可组合性意味着可以添加对其他语言的支持.

## 插件

构建在  _IntelliJ Platform_  上的产品是可组合的应用程序,平台负责组件的创建,以及将依赖项注入类中.
 _IntelliJ Platform_  完全支持插件,JetBrains托管 [JetBrains Marketplace](https://plugins.jetbrains.com) ,可用于分发支持一个或多个产品的插件.
也可以托管自己的存储库,并单独分发插件 [](custom_plugin_repository.md).

插件可以通过多种方式扩展平台,从添加简单的菜单项到添加对完整语言,构建系统和调试器的支持.
 _IntelliJ Platform_  中的许多现有功能都是作为插件编写的,可以根据最终产品的需要包含或排除这些插件.
有关详细信息,请参阅[](basics.md)一节.

> 某些情况下, 可能并不需要实现一个真正的 IntelliJ Platform 插件, 因为存在 [替代解决方案](plugin_alternatives.md).
>
{type="tip"}

## 开源

 _IntelliJ Platform_  是开源在[Apache许可证](upsource:///LICENSE.txt)和[托管在GitHub](https://github.com/JetBrains/intellij-community)之下.


虽然本指南将 _IntelliJ Platform_  作为一个单独的实体引用,但并不存在“IntelliJ平台”GitHub仓库.
相反,该平台被认为与IntelliJ IDEA社区版几乎完全重叠,IntelliJ IDEA社区版是IntelliJ IDEA Ultimate的免费开源版本(上面链接的GitHub repo是[JetBrains/intellij-community](https://github.com/JetBrains/intellij-community)repo).


IntelliJ IDEA Ultimate是IntelliJ IDEA社区版的超集.
它基于社区版,但包括闭源插件([请参阅此功能比较](https://www.jetbrains.com/idea/features/editions_comparison_matrix.html)).
同样,WebStorm和DataGrip等其他产品也基于IntelliJ IDEA Community Edition,但包含一组不同的插件,不包括其他默认插件.


这允许插件针对多个产品,因为每个产品都包含基本功能和IntelliJ IDEA Community Edition仓库中的一系列插件.
这就是我们所说的 _IntelliJ Platform_ .

<note>IDEA团队的工作方式</note>
通常,基于 _IntelliJ Platform_ 的IDE将包含`intellij-community` repo作为Git子模块,并提供配置来描述来自`intellij-community`的哪些插件,以及哪些自定义插件将构成产品.
这就是IDEA Ultimate团队的工作方式,他们为自定义插件和 _IntelliJ Platform_ 本身贡献代码.


当然,因为 _IntelliJ Platform_ 是开源的,我们也接受[pull requests](https://github.com/JetBrains/intellij-community/pulls)到平台本身,而不仅仅是打开视图源.
使用[YouTrack(使用IDEA项目)](https://youtrack.jetbrains.com/issues/IDEA)管理问题跟踪,如果您希望为该平台做出贡献,通常最好打开一个问题
描述在进行更改之前您希望进行的更改 - 这使团队有机会提供反馈和建议.
更多细节可以在[贡献IntelliJ平台](/basics/platform_contributions.md)一节中找到.

## 基于 IntelliJ Platform 的开发工具

IntelliJ Platform 支撑了很多 JetBrains IDE.
IntelliJ IDEA Ultimate 包含了 IntelliJ IDEA Community Edition 的很多功能但是提供了额外的闭源插件 ([see this feature comparison](https://www.jetbrains.com/idea/features/editions_comparison_matrix.html)).
类似的, 其它产品比如 WebStorm 和 DataGrip 也是 IntelliJ IDEA Community Edition, 但是包含了一些插件子集并且排除了某些其它的默认插件.
这样就可以让插件部署到多个产品, 并且每个产品将包含基础的功能, 以及 IntelliJ IDEA Community Edition 代码库中锁包含的一部分选中给你的插件.

> 满足条件的开源项目可以申请JetBrains产品的[申请免费许可](https://www.jetbrains.com/community/opensource/).
>
{style="note"}

下列集成开发工具均基于 IntelliJ Platform:
* JetBrains 集成开发工具:
  * [AppCode](https://www.jetbrains.com/objc/)
  * [CLion](https://www.jetbrains.com/clion/)
  * [DataGrip](https://www.jetbrains.com/datagrip/)
  * [GoLand](https://www.jetbrains.com/go/)
  * [IntelliJ IDEA](https://www.jetbrains.com/idea/)
  * [MPS](https://www.jetbrains.com/mps/)
  * [PhpStorm](https://www.jetbrains.com/phpstorm/)
  * [PyCharm](https://www.jetbrains.com/pycharm/)
  * [Rider](#rider)
  * [RubyMine](https://www.jetbrains.com/ruby/)
  * [WebStorm](https://www.jetbrains.com/webstorm/)
* [Android Studio](https://developer.android.com/studio/index.html) 谷歌开发的 IDE
* [Comma](https://commaide.com/) IDE for Raku (旧的名称是 Perl 6)
* [Jmix Studio](https://www.jmix.io/tools/)

参考 *第八部分 — 产品特定 * 来了解开发工具相关的详情.

### Rider

[Rider](https://www.jetbrains.com/rider/)使用  _IntelliJ Platform_  与其他基于 IntelliJ 的IDE不同.
它使用  _IntelliJ Platform_  为C#和.NET IDE提供用户界面,具有标准的IntelliJ编辑器,工具窗口,调试经验等.
它还集成到标准的查找用法和随处搜索界面中,并使用代码完成,语法突出显示等.

但是,它不会为C#文件创建完整的PSI(语法和语义)模型.
相反,它重用[ReSharper](https://www.jetbrains.com/resharper/)来提供语言功能.
所有C# PSI模型以及所有检查和代码重写(例如快速修复和重构)都在ReSharper的命令行版本中运行.
这意味着为Rider创建插件涉及两个部分 - 一个插件,它位于IntelliJ“前端”以显示用户界面,一个插件位于ReSharper“后端”以分析和使用C# PSI.


幸运的是,许多插件可以简单地使用ReSharper后端--Rider负责显示检查和代码完成的结果,并且可以编写许多不需要IntelliJ UI组件的插件.
更多详细信息,请参见[](rider.md)部分.
