[//]: # (title: 内部操作 - UI 检查器)

<!-- Copyright 2000-2022 JetBrains s.r.o. and other contributors. Use of this source code is governed by the Apache 2.0 license that can be found in the LICENSE file. -->

_UI 检查器_ 工具可以用来检测IntelliJ IDEA界面来获取每个元素的内部描述.
_UI 检查器_ 启用时, UI 元素可以通过交互式点击来测试.

[//]: # (<include src="internal_actions_intro.md" include-id="enable_internal_mode_tip"></include>)
> 如果在 IntelliJ IDEA 找不到菜单 `工具 | 内部操作` , 先去 [启用内部模式](enabling_internal.md)
>
{type="tip"}

> UI 检查器最新特性: added-at , 能够显示代码添加的堆栈.
> ![img.png](ui-inspector-added-at-cn.png){thumbnail="true" thumbnail-same-file="true"}{border-effect="rounded"}
>
{style="note"}

## 启用 UI 检查器

使用 _UI 检查器_ 之前, 必须首先通过选择菜单项 <path>工具 | 内部操作 | UI | UI 检查器</path> 来启用.
 _UI 检查器_ 启用状态是一个模态窗口; 它将一直保持启用状态, 除非再次点击 _UI 检查器_ 才可以禁用.

## 使用 UI 检查器

启用后, 将鼠标指针放到 UI 元素上, 然后按下 <shortcut>Control/Cmd+Alt</shortcut>的同时鼠标 _点击_ 元素将会显示 Swing 组件的属性.

例如, 要想获取工具栏按钮上的 _构建项目_ 按钮的图标(锤子)信息 (图中绿色区域所示), 将鼠标放到图标上, 然后按下  <shortcut>Control/Cmd+Alt</shortcut> 的同时点击鼠标.

 _UI 检查器_ 显示图标有一个内部路径 `AllIcons.Actions.Compile`:

![Internal Icon Info](internal_uii_icon_info.png)

## 额外属性

IntelliJ Platform 所使用的各种组件会暴露额外属性.
这对定位底层实现代码的时候很有用, 例如相关动作等.

| Type                                                                                                   | Place        | Properties                                                                                                                                                                                                                                                 |
|--------------------------------------------------------------------------------------------------------|--------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [`AnAction`](basic_action_system.md)                                                                   | 操作按钮<br/>菜单项 | `Action` - [`AnAction`](%gh-ic%/platform/editor-ui-api/src/com/intellij/openapi/actionSystem/AnAction.java) 实现<br/>`Action ID` - Action `id`<br/>`Action Plugin ID` - 实现此功能的插件                                                                             |
| [`ActionToolbar`](basic_action_system.md)                                                              | 操作工具栏        | `Toolbar Group` - Action Group ID<br/>`All Groups` - 所包含的Action Group ID(操作组ID)                                                                                                                                                                            |
| [`DialogWrapper`](dialog_wrapper.md)                                                                   | 模态对话框        | `dialogWrapperClass` - [`DialogWrapper`](%gh-ic%/platform/platform-api/src/com/intellij/openapi/ui/DialogWrapper.java) 实现                                                                                                                                  |
| [`GutterMark`](%gh-ic%/platform/editor-ui-api/src/com/intellij/codeInsight/daemon/GutterMark.java) | 编辑器隔条图标      | `gutter renderer` - [`GutterMark`](%gh-ic%/platform/editor-ui-api/src/com/intellij/codeInsight/daemon/GutterMark.java) 实现                                                                                                                      |
| [`IntentionAction`/`QuickFix`](code_inspections_and_intentions.md)                                     | 编辑器弹出菜单      | `intention action`/`quick fix` - [`IntentionAction`](%gh-ic%/platform/analysis-api/src/com/intellij/codeInsight/intention/IntentionAction.java) / [`QuickFix`](%gh-ic%/platform/analysis-api/src/com/intellij/codeInspection/QuickFix.java) 实现 |
| [`Tree`](lists_and_trees.md)                                                                           | 树            | `treeModelClass` - `javax.swing.tree.TreeModel` 实现                                                                                                                                                                                             |

自定义的 Swing 组件也可以通过实现  [`UiInspectorContextProvider`](%gh-ic%/platform/platform-impl/src/com/intellij/internal/inspector/UiInspectorContextProvider.java) (2020.1+版本) 提供额外属性信息.
