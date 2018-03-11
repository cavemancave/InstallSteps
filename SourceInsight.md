# 这篇文档用来记录我在使用Source Insight的过程中碰到的问题和解决方法或者一些技巧

# Source Insight 支持lua

1. 选择 Options > Preferences. 然后点击 Languages 标签。
1. 将附件中的 "lua Language.CLF" 文件保存到本地。
1. 点击 Import 按钮，选择刚刚保存的 "lua.CLF" 文件，点击打开；此时，在左侧窗口的语言清单中，你就可以看到 lua了。
1. Languages->Properties-> Custom Parsion 添加
   | Function  |  function\w+\([a-zA-Z][a-zA-Z0-9_:]*\)  |
   |-----------|-----------------------------------------|
   （右方括号前的**下划线**和**冒号**非常重要，否则函数调用关系图可能有问题）（relation窗口中references by functions）
1. 然后点击右下角的 Doc Types.. 按钮，打开 Document Options 对话框。
1. 点击 *Add Type *按钮创建新的lua文件类型描述，比如 "Lua File"。
1. 点击 OK，然后在 file filter 文本框输入通配符，比如 "*.lua"。
1. 手动设置勾选include when adding to project, 并设置Language下为Lua Languages （这一步很重要，不设置的话有些版本不会产生效果）
1. Parsing->Language下拉找到Lua
1. 点击 Close 按钮关闭 Document Options 窗口，
1. 然后点击 OK 关闭 *Preference *窗口。

# Source Insight 4 中文注释乱码
 Options->Preference->Files最后->Default encoding:选择GB2312
