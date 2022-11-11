[//]: # (title: 插件类型)

<!-- Copyright 2000-2022 JetBrains s.r.o. and contributors. Use of this source code is governed by the Apache 2.0 license. -->

基于 *IntelliJ Platform* 的产品可以通过添加插件进行修改和调整以用于自定义目的..
所有可下载的插件都可以在 [JetBrains Marketplace](https://plugins.jetbrains.com/) 找到.

最常见的插件类型包括:
* 自定义语言支持
* 框架集成
* 工具集成
* 用户界面附加组件
* 界面主题

> 某些情况下, 可能并不需要实现一个真正的 IntelliJ Platform 插件, 因为存在 [替代解决方案](plugin_alternatives.md).
>
{type="tip"}

## 自定义语言支持

自定义语言支持提供了使用特定编程语言的基本功能, 这包括:
* 文件类型识别
* 词法分析
* 语法高亮显示
* 格式化
* 代码洞察和代码补齐
* 检查和快速修复
* 意图动作

插件也可以增强现有的(内置)自定义语言, 例如通过提供额外的检查,意图及其它功能.
> 译著: [Markdown Editor](https://plugins.jetbrains.com/plugin/17254-markdown-editor) 国产开源插件展示了如何向现有文件类型添加一个新标签页.
> ![img.png](https://plugins.jetbrains.com/files/17254/screenshot_54755b4b-6a55-4fff-9a9d-c1cfe0823ff3)
>
{style="note"}


参阅 [自定义语言支持教程](custom_language_support_tutorial.md) 以了解有关该主题的更多信息.

## 框架集成

框架集成包括改进的代码洞察功能,这些功能对于给定的框架是典型的,以及直接从IDE使用框架特定功能的选项.
有时它还包括自定义语法或DSL的语言支持元素.

* 特定的代码洞察
* 直接访问特定于框架的功能

请参阅[Struts 2插件](https://plugins.jetbrains.com/plugin/1698)作为框架集成的示例.
可以在 [JetBrains Marketplace](https://plugins.jetbrains.com/search?orderBy=update%20date&shouldHaveSource=true&tags=Framework)找到更多插件.

## 工具集成

通过工具集成,可以直接从IDE操作第三方工具和组件,而无需切换上下文. 这意味着:
* 实现额外动作
* 相关的UI组件
* 访问外部资源

请参阅 [Gerrit 集](https://plugins.jetbrains.com/plugin/7272) 插件作为示例.

## 用户界面附加组件

此类别中的插件会对IDE的标准用户界面应用各种更改.
一些新添加的组件是交互式的并提供新功能,而其他组件仅限于视觉修改.
[背景图片](https://plugins.jetbrains.com/plugin/9692-random-background) 插件可以作为一个例子.

## UI 主题

[UI 主题](themes_intro.md) 给设计师定制内置开发工具界面元素的能力.
自定义 UI 主题可以:

* 替换图标,
* 修改图标和UI控件的颜色,
* 修改UI控件的边框和装饰物,
* 提供自定义编辑器主题,
* 添加背景图.

[可供下载的UI 主题](https://plugins.jetbrains.com/search?headline=164-theme&tags=Theme) 展示了可能的创意.
