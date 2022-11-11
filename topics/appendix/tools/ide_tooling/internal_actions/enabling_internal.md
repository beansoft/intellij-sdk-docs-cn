[//]: # (title: 启用内部模式)

<!-- Copyright 2000-2022 JetBrains s.r.o. and other contributors. Use of this source code is governed by the Apache 2.0 license that can be found in the LICENSE file. -->

某些工具例如内部操作菜单, 只有在IntelliJ IDEA的内部模式启用时才能看到.

<procedure title="配置内部模式">

1. 启动 IntelliJ IDEA.  <note>译著: 或 WebStorm 等的操作类似</note>
2. 从IDEA的主菜单, 选择  <path>Help | Edit Custom Properties(帮助 | 编辑自定义属性...) </path>.
如果还没打开任何项目, 则从欢迎屏幕, 点击 **选项菜单** 小齿轮然后选择 <path>编辑自定义属性...</path>.
这将打开IntelliJ IDEA的 <path>idea.properties</path> 文件. 如果文件不存在, 会提示创建一个.
3. 在 <path>idea.properties</path> 文件编辑器中, 追加下列配置:

```properties
idea.is.internal=true
```
4. 保存 <path>idea.properties</path> 文件并重启 IntelliJ IDEA.

5. 内部操作菜单此时可见, 路径: <path>Tools | Internal Actions</path>.

</procedure>
