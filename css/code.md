## 代码

### 内联代码
通过 `<code>`标签包裹内联样式的代码片段。




```
    For example, <code>&lt;section&gt;</code> should be wrapped as inline.
```
###用户输入
通过 `<kbd>` 标签标记用户通过键盘输入的内容。=



```
    To switch directories, type <kbd>cd</kbd> followed by the name of the directory.<br>
    To edit settings, press <kbd><kbd>ctrl</kbd> + <kbd>,</kbd></kbd>
```
###代码块
多行代码可以使用 `<pre>` 标签。为了正确的展示代码，注意将尖括号做转义处理。



```
    <pre>&lt;p&gt;Sample text here...&lt;/p&gt;</pre>
```
还可以使用 `.pre-scrollable` 类，其作用是设置 max-height 为 350px ，并在垂直方向展示滚动条。

变量
通过 `<var>` 标签标记变量。




```
    <var>y</var> = <var>m</var><var>x</var> + <var>b</var>
```
程序输出
通过 <samp> 标签来标记程序输出的内容。




```
    <samp>This text is meant to be treated as sample output from a computer program.</samp>
```
