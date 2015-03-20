# 排版

## 标题
HTML 中的所有标题标签，`<h1>` 到 `<h6>` 均可使用。另外，还提供了 `.h1` 到 `.h6` 类，为的是给内联（inline）属性的文本赋予标题的样式。



```
    <h1>h1. Bootstrap heading</h1>
    <h2>h2. Bootstrap heading</h2>
    <h3>h3. Bootstrap heading</h3>
    <h4>h4. Bootstrap heading</h4>
    <h5>h5. Bootstrap heading</h5>
    <h6>h6. Bootstrap heading</h6>
```
在标题内还可以包含 `<small>` 标签或赋予 `.small` 类的元素，可以用来标记副标题。



```
    <h1>h1. Bootstrap heading <small>Secondary text</small></h1>
    <h2>h2. Bootstrap heading <small>Secondary text</small></h2>
    <h3>h3. Bootstrap heading <small>Secondary text</small></h3>
    <h4>h4. Bootstrap heading <small>Secondary text</small></h4>
    <h5>h5. Bootstrap heading <small>Secondary text</small></h5>
    <h6>h6. Bootstrap heading <small>Secondary text</small></h6>
```
## 页面主体
Bootstrap 将全局 `font-size` 设置为 14px，`line-height` 设置为 1.428。这些属性直接赋予 `<body>` 元素和所有段落元素。另外，`<p>` （段落）元素还被设置了等于 1/2 行高（即 10px）的底部外边距（margin）。



```
    <p>...</p>
```

###中心内容
通过添加 `.lead` 类可以让段落突出显示。




```
    <p class="lead">...</p>
```
###使用 Less 工具构建
**variables.less** 文件中定义的两个 Less 变量决定了排版尺寸：`@font-size-base` 和 @line-height-base。第一个变量定义了全局 font-size 基准，第二个变量是 line-height 基准。我们使用这些变量和一些简单的公式计算出其它所有页面元素的 margin、 padding 和 line-height。自定义这些变量即可改变 Bootstrap 的默认样式。

##内联文本元素
###Marked text
For highlighting a run of text due to its relevance in another context, use the `<mark>` tag.




```
    You can use the mark tag to <mark>highlight</mark> text.
```
###被删除的文本
对于被删除的文本使用 `<del>` 标签。




```
    <del>This line of text is meant to be treated as deleted text.</del>
```
###无用文本
对于没用的文本使用 `<s>` 标签。




```
    <s>This line of text is meant to be treated as no longer accurate.</s>
```
###插入文本
额外插入的文本使用 `<ins>` 标签。




```
    <ins>This line of text is meant to be treated as an addition to the document.</ins>
```
###带下划线的文本
为文本添加下划线，使用 `<u>` 标签。




```
    <u>This line of text will render as underlined</u>
```
利用 HTML 自带的表示强调意味的标签来为文本增添少量样式。

###小号文本
对于不需要强调的inline或block类型的文本，使用 `<small>` 标签包裹，其内的文本将被设置为父容器字体大小的 85%。标题元素中嵌套的 `<small>` 元素被设置不同的 `font-size` 。

你还可以为行内元素赋予 `.small` 类以代替任何 `<small>` 元素。




```
    <small>This line of text is meant to be treated as fine print.</small>
```
###着重
通过增加 font-weight 值强调一段文本。



```
    <strong>rendered as bold text</strong>
```
###斜体
用斜体强调一段文本。



```
    <em>rendered as italicized text</em>
```

**Alternate elements**

在 HTML5 中可以放心使用 `<b>` 和 `<i>` 标签。`<b>` 用于高亮单词或短语，不带有任何着重的意味；而 `<i>` 标签主要用于发言、技术词汇等。
##对齐
通过文本对齐类，可以简单方便的将文字重新对齐。




```
    <p class="text-left">Left aligned text.</p>
    <p class="text-center">Center aligned text.</p>
    <p class="text-right">Right aligned text.</p>
    <p class="text-justify">Justified text.</p>
    <p class="text-nowrap">No wrap text.</p>
```
##改变大小写
通过这几个类可以改变文本的大小写。




```
    <p class="text-lowercase">Lowercased text.</p>
    <p class="text-uppercase">Uppercased text.</p>
    <p class="text-capitalize">Capitalized text.</p>
```
##缩略语
当鼠标悬停在缩写和缩写词上时就会显示完整内容，Bootstrap 实现了对 HTML 的 `<abbr>` 元素的增强样式。缩略语元素带有 `title` 属性，外观表现为带有较浅的虚线框，鼠标移至上面时会变成带有“问号”的指针。如想看完整的内容可把鼠标悬停在缩略语上（对使用辅助技术的用户也可见）, 但需要包含 title 属性。

###基本缩略语




```
    <abbr title="attribute">attr</abbr>
```
###首字母缩略语
为缩略语添加 `.initialism` 类，可以让 font-size 变得稍微小些。




```
    <abbr title="HyperText Markup Language" class="initialism">HTML</abbr>
```
##地址
让联系信息以最接近日常使用的格式呈现。在每行结尾添加 `<br>` 可以保留需要的样式。




```
    <address>
      <strong>Twitter, Inc.</strong><br>
      795 Folsom Ave, Suite 600<br>
      San Francisco, CA 94107<br>
      <abbr title="Phone">P:</abbr> (123) 456-7890
    </address>

    <address>
      <strong>Full Name</strong><br>
      <a href="mailto:#">first.last@example.com</a>
    </address>
```
##引用
在你的文档中引用其他来源的内容。

###默认样式的引用
将任何 HTML 元素包裹在 `<blockquote>` 中即可表现为引用样式。对于直接引用，我们建议用 `<p>` 标签。




```
    <blockquote>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
    </blockquote>
```
###Blockquote options
Style and content changes for simple variations on a standard `<blockquote>`.

####Naming a source

Add a `<footer>` for identifying the source. Wrap the name of the source work in `<cite>`.





```
    <blockquote>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
      <footer>Someone famous in <cite title="Source Title">Source Title</cite>
    </footer>
    </blockquote>
```
####Alternate displays




```
    <blockquote class="blockquote-reverse">
      ...
    </blockquote>
```
##列表
###无序列表
####排列顺序无关紧要的一列元素。




```
    <ul>
      <li>...</li>
    </ul>
```
###有序列表
####顺序至关重要的一组元素。





```
    <ol>
      <li>...</li>
    </ol>
```
###无样式列表
移除了默认的 `list-style` 样式和左侧外边距的一组元素（只针对直接子元素）。**这是针对直接子元素的**，也就是说，你需要对所有嵌套的列表都添加这个类才能具有同样的样式。




```
    <ul class="list-unstyled">
      <li>...</li>
    </ul>
```
###内联列表
通过设置 `display: inline-block;` 并添加少量的内补（padding），将所有元素放置于同一行。




```
    <ul class="list-inline">
      <li>...</li>
    </ul>
```
###描述
带有描述的短语列表。




```
    <dl>
      <dt>...</dt>
      <dd>...</dd>
    </dl>
```
####水平排列的描述

`.dl-horizontal` 可以让 `<dl>` 内的短语及其描述排在一行。开始是像 `<dl>` 的默认样式堆叠在一起，随着导航条逐渐展开而排列在一行。





```
    <dl class="dl-horizontal">
      <dt>...</dt>
      <dd>...</dd>
    </dl>
```
自动截断
通过 `text-overflow` 属性，水平排列的描述列表将会截断左侧太长的短语。在较窄的视口（viewport）内，列表将变为默认堆叠排列的布局方式。
