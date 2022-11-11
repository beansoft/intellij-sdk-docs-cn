[9//]: # (title: 创建主题插件)
<excerpt>从零创建简单主题插件.</excerpt>
主题插件是创建难度最小的插件, 可以不选择JDK(当然也可以和别的插件代码组合在一起).


> 参考 [博客文章](https://blog.jetbrains.com/platform/2021/10/themes-in-intellij-based-ides/) 了解更多信息(英文).
>
> 示例代码: [IDE 简单示例](https://github.com/JetBrains/intellij-sdk-docs/tree/main/code_samples/theme_basics)
>
> 下载更多主题(大部分都开源): [https://plugins.jetbrains.com/search?tags=Theme](https://plugins.jetbrains.com/search?tags=Theme)
>
{style="note"}

## 创建插件

选择菜单 <path>文件 | 新建 | 项目... </path>, 选择 **IDE 插件**, 然后点击右侧 **主题** 即可完成创建.
![](new_theme_prj.png){thumbnail="true" thumbnail-same-file="true"}{border-effect="rounded"}

[//]: # (> 如果首次创建, JDK列表可能为空, 参考下图进行操作)

[//]: # (> ![img.png]&#40;select_platform_sdk_cn.png&#41;)

[//]: # (>)

[//]: # ({style="note"})

##  plugin.xml 内容简介

```xml
<!-- 插件配置文件. 读取 https://plugins.jetbrains.com/docs/intellij/plugin-configuration-file.html -->
<idea-plugin>
    <!-- 插件唯一ID, 发不同版本时不能修改. 建议用com.xxx.xxx格式 -->
    <id>jb_demo_theme</id>
  <!-- 版本号: 主版本号.次版本号.修订号 https://semver.org/lang/zh-CN/ -->
    <version>1.0.0</version>

    <!-- 插件名字必须用英文且不能有标点, 可有空格和数字如 My Notes, 不能包含 plugin 字样.
         详细解释: https://plugins.jetbrains.com/docs/marketplace/plugin-overview-page.html#plugin-name -->
    <name>Jb_demo_theme</name>
    <!-- 类别 -->
    <category>UI</category>

    <!-- 插件页显示的供应商名称, 邮件和网址. -->
    <vendor email="support@yourcompany.com" url="https://www.yourcompany.com">YourCompany</vendor>

    <!-- 兼容的IDEA版本范围, 发版前请务必测试 -->
    <idea-version since-build="213" until-build="223.*"/>

    <!-- 插件网页和开发工具中的插件描述内容, 只能用简单HTML标记(文本格式, 段落和列表), 不支持CSS和JS, 不支持iframe.
         必须要有简短的英文描述, 之后可以放中文, 否则会审核不通过.
         完整内容: https://plugins.jetbrains.com/docs/marketplace/plugin-overview-page.html#plugin-description -->
    <description><![CDATA[
    Enter short description for your theme here.<br>
    <em>most HTML tags may be used</em>
  ]]></description>

    <!-- 更改备注, 建议每个版本更新, 支持中英文 -->
    <change-notes><![CDATA[
    Initial release of the theme.
  ]]></change-notes>

    <!-- 产品和插件依赖兼容(这部分比较复杂).
         Read more: https://plugins.jetbrains.com/docs/intellij/plugin-compatibility.html -->
    <depends>com.intellij.modules.platform</depends>

  <!-- 扩展列表 -->
    <extensions defaultExtensionNs="com.intellij">
      <!-- 主题提供者, ID需要唯一 -->
        <themeProvider id="jb_demo_theme" path="/theme/jb_demo_theme.theme.json"/>
    </extensions>
</idea-plugin>
```

## 主题的实时调试
打开文件 `*.theme.json`, 即可实时修改并运行预览效果.

## 打包主题
选择菜单 <path>构建 | 为部署准备插件模块 'xxxx' </path>, 即可打包完成产生jar文件.

## 测试主题
本地安装后测试效果.

## 发布主题
打开插件网站 [https://plugins.jetbrains.com/](https://plugins.jetbrains.com/), 点击 Sign In 后上传.

如果没有账号, 参考下列步骤注册:
![img.png](login_jbcn.png)

## 等待审核通过即可

## 技巧

* [LaF Defaults (主题默认设置) ](internal_ui_laf_defaults.md) 提供一种查找 UI 组件的键值对的方法, 以及修改 UI组件原型的能力(可直接修改颜色查看效果)
![LaF 主题默认设置](laf_defaults_cn.png){thumbnail="true" thumbnail-same-file="true" }

* 代码自动补齐

![自动补齐](https://blog.jetbrains.com/wp-content/uploads/2021/10/attr.png){thumbnail="true" thumbnail-same-file="true"}
