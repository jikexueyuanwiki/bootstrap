# 浏览器和设备的支持情况

Bootstrap 的目标是在最新的桌面和移动浏览器上有最佳的表现，也就是说，在较老旧的浏览器上可能会导致某些组件表现出的样式有些不同，但是功能是完整的。

## 被支持的浏览器
特别注意，我们坚决支持这些浏览器的**最新版本**。在 Windows 平台，我们支持 **Internet Explorer 8-11**。请看下面列出的详细信息。

|Chrome  |Firefox  |Internet Explorer	|Opera|Safari
|--------|--------|----------|------------|------
|Android	 |支持	| 支持	|N/A	| 不支持 |	N/A



iOS	 支持	N/A	 不支持	 支持
Mac OS X	 支持	 支持	 支持	 支持
Windows	 支持	 支持	 支持	 支持	 不支持
Bootstrap 在 Chromium 和 Linux 版 Chrome、Linux 版 Firefox 和 Internet Explorer 7 上的表现也是很不错的，虽然我们不对其进行官方支持。

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

浏览器 bug 列表中列出了影响 Bootstrap 正常功能的浏览器 bug。

## Internet Explorer 8 和 9
Internet Explorer 8 和 9 是被支持的，然而，你要知道，很多 CSS3 属性和 HTML5 元素 -- 例如，圆角矩形和投影 -- 是肯定不被支持的。另外， **Internet Explorer 8 需要 Respond.js 配合才能实现对媒体查询（media query）的支持。**

Feature	Internet Explorer 8	Internet Explorer 9
border-radius	 不支持	 支持
box-shadow	 不支持	 支持
transform	 不支持	 支持, with -ms prefix
transition	 不支持
placeholder	 不支持
请参考 Can I use... 以获取详细的 CSS3 和 HTML5 特性在各个浏览器上的支持情况。

## Internet Explorer 8 与 Respond.js
在开发环境和生产（线上）环境需要支持 Internet Explorer 8 时，请务必注意下面给出的警告。

Respond.js 与 跨域（cross-domain） CSS 的问题

如果 Respond.js 和 CSS 文件被放在不同的域名或子域名下面（例如，使用CDN）时需要一些额外的设置。请参考 Respond.js 文档 获取详细信息。

Respond.js 与 `file://` 协议

由于浏览器的安全机制，Respond.js 不能在通过 `file://` 协议（打开本地HTML文件所用的协议）访问的页面上发挥正常的功能。如果需要测试 IE8 下面的响应式特性，务必通过 http 协议访问页面（例如搭建 apache、nginx 等）。请参考 Respond.js 文档获取更多信息。

Respond.js 与 `@import` 指令

Respond.js 不支持通过 `@import` 指令所引入的 CSS 文件。例如，Drupal 一般被配置为通过 `@import` 指令引入CSS文件，Respond.js 对其将无法起到作用。请参考 Respond.js 文档获取更多信息。

## Internet Explorer 8 与 box-sizing 属性
当 box-sizing: border-box; 与 min-width、max-width、min-height 或 max-height 一同使用时，IE8 不能完全支持 box-sizing 属相。由于此原因，从 Bootstrap v3.0.1 版本开始，我们不再为 .container 赋予 max-width 属性。

## Internet Explorer 8 与 @font-face
当 `@font-face` 与 `:before` 在 IE8 下共同使用时会出现问题。由于 Bootstrap 对 Glyphicons 的样式设置使用了这一组合方式，如果某个页面被浏览器缓存了，并且此页面不是通过点击“刷新”按钮或通过 iframe 加载的，那么就会导致字体文件尚未加载的情况下就开始绘制此页面。当鼠标滑过页面（body）时，页面上的某些图标就会显现，鼠标滑过其他没有显现的图标时，这些图标就能显示出来了。请参考 issue #13863 了解详细信息。

## IE 兼容模式
Bootstrap 不支持 IE 古老的兼容模式。为了让 IE 浏览器运行最新的渲染模式下，建议将此 `<meta> `标签加入到你的页面中：

```
    <meta http-equiv="X-UA-Compatible" content=`"IE=edge"`>
```
按 `F12 `键打开 IE 的调试工具，就可以看到 IE 当前的渲染模式是什么。

此 meta 标签被包含在了所有 Bootstrap 文档和实例页面中，为的就是在每个被支持的 IE 版本中拥有最好的绘制效果。

请参考 这个发表在 StackOverflow 上的问题。

国产浏览器高速模式
国内浏览器厂商一般都支持兼容模式（即 IE 内核）和高速模式（即 webkit 内核），不幸的是，所有国产浏览器都是默认使用兼容模式，这就造成由于低版本 IE （IE8 及以下）内核让基于 Bootstrap 构建的网站展现效果很糟糕的情况。幸运的是，国内浏览器厂商逐渐意识到了这一点，某些厂商已经开始有所作为了！

将下面的 `<meta>` 标签加入到页面中，可以让部分国产浏览器默认采用高速模式渲染页面：

```
    <meta name="renderer" content="webkit">
```
目前只有360浏览器支持此` <meta> `标签。希望更多国内浏览器尽快采取行动、尽快进入高速时代！

## Windows 8 中的 Internet Explorer 10 和 Windows Phone 8
Internet Explorer 10 并没有对 **屏幕的宽度 和 视口（viewport）的宽度** 进行区分，这就导致 Bootstrap 中的媒体查询并不能很好的发挥作用。为了解决这个问题，你可以引入下面列出的这段 CSS 代码暂时修复此问题：

```
    @-ms-viewport       { width: device-width; }
```
然而，这样做并不能对 Windows Phone 8 Update 3 (a.k.a. GDR3) 版本之前的设备起作用，由于这样做将导致 Windows Phone 8 设备按照桌面浏览器的方式呈现页面，而不是较窄的“手机”呈现方式，为了解决这个问题，还需要加入以下 **CSS 和 JavaScript** 代码来化解此问题。

```
    @-webkit-viewport   { width: device-width; }
    @-moz-viewport      { width: device-width; }
    @-ms-viewport       { width: device-width; }
    @-o-viewport        { width: device-width; }
    @viewport           { width: device-width; }
```
```
if (navigator.userAgent.match(/IEMobile\/10\.0/)) {
  var msViewportStyle = document.createElement('style')
  msViewportStyle.appendChild(
    document.createTextNode(
      '@-ms-viewport{width:auto!important}'
    )
  )
  document.querySelector('head').appendChild(msViewportStyle)
	}
```
请查看 Windows Phone 8 and Device-Width 以了解更多信息。

作为提醒，我们将上面的代码加入到了所有 Bootstrap 文档和实例页面中。

## Safari 对百分比数字凑整的问题
OS X 上搭载的 v7.1 以前 Safari 和 iOS v8.0 上搭载的 Safari 浏览器的绘制引擎对于处理 `.col-*-1 `类所对应的很长的百分比小数存在 bug。也就是说，如果你在一行（row）之中定义了12个单独的列（.col-*-1），你就会看到这一行比其他行要短一些。除了升级 Safari/iOS 外，有以下几种方式来应对此问题：

为最后一列添加 `.pull-right` 类，将其暴力向右对齐
手动调整百分比数字，让其针对Safari表现更好（这比第一种方式更困难）
## 模态框、导航条和虚拟键盘
### Overflow and scrolling

`<body>` 元素在 iOS 和 Android 上对 `overflow: hidden` 的支持很有限。结果就是，在这两种设备上的浏览器中，当你滚动屏幕超过模态框的顶部或底部时，`<body>` 中的内容将开始随着滚动。

### 虚拟键盘

还有，如果你正在使用 fixed 定位的导航条或在模态框上面使用输入框，还会遇到 iOS 在页面绘制上的 bug，当触发虚拟键盘之后，其不会更新 fixed 定位的元素的位置。这里有几种解决方案，包括将 fixed 定位转变为 `position: absolute` 定位，或者启动一个定时器手工修正组件的位置。这些没有加入 Bootstrap 中，因此，需要由你自己选择最好的解决方案并加入到你的应用中。

### 导航条上的下拉菜单

在 iOS 设备上，由于导航组件（nav）的复杂的 z-indexing 属性，.dropdown-backdrop 元素并未被使用。因此，为了关闭导航条上的下拉菜单，必须直接点击下拉菜单上的元素（或者任何其他能够触发 iOS 上 click 事件的元素）。

## 浏览器的缩放功能
页面缩放功能不可避免的会将某些组件搞得乱七八糟，不光是 Bootstrap ，整个互联网上的所有页面都是这样。针对具体问题，我们或许可以修复它（如果有必要的话，请先搜索一下你的问题，看看是否已有解决方案，然后在向我们提交 issue）。然而，我们更倾向于忽略这些问题，由于这些问题除了一些 hack 手段，一般没有直接的解决方案。

## 打印
即便是在某些很现代的浏览器中，打印页面功能也还是存在很多陷阱。

举个例子，从 Chrome v32 开始，打印一个支持媒体查询的页面时，不管如何设置留白，Chrome 总是使用一个远远小于实际页面尺寸的视口宽度的值作为页面宽度。这就导致被打印的页面总是被呈现为在超小屏幕（extra-small）上的效果（也就是激活了 Bootstrap 针对超小屏幕的栅格排布方式）。 参考 #12078 了解更多信息。 推荐解决方案：

让你的页面在超小（extra-small）屏幕上看起来不那么太差劲。
修改 `@screen-*` Less 变量的值，让你的页面总是大于 extra-small
添加额外的媒体查询代码，针对打印机修改栅格阈值。
另外，从Safari v8.0 开始，固定宽度的 `.container` 会导致 Safari 使用非常小的字号来打印页面。参见 #14868 了解跟多信息。下面这段 CSS 代码提供了一个临时解决方案：

```
    @media print {
      .container {
        width: auto;
      }
    }
```
## Android stock browser
Out of the box, Android 4.1 (and even some newer releases apparently) ship with the Browser app as the default web browser of choice (as opposed to Chrome). Unfortunately, the Browser app has lots of bugs and inconsistencies with CSS in general.

## Select menus

On `<select> `elements, the Android stock browser will not display the side controls if there is a `border-radius` and/or `border` applied. (See this StackOverflow question for details.) Use the snippet of code below to remove the offending CSS and render the` <select>` as an unstyled element on the Android stock browser. The user agent sniffing avoids interference with Chrome, Safari, and Mozilla browsers.


```
 <script>
  $(function () {
  var nua = navigator.userAgent
  var isAndroid = (nua.indexOf('Mozilla/5.0') > -1 && nua.indexOf('Android ') > -1 && nua.indexOf('AppleWebKit') > -1 && nua.indexOf('Chrome') === -1)
  if (isAndroid) {
    $('select.form-control').removeClass('form-control').css('width', '100%')
  }
 })
 </script>
```
见 JS Bin 上的 demo。

W3C 页面源码校验
为了在老旧的浏览器上尽量提供最好的展现，Bootstrap 针对浏览器使用了一些 CSS hack 手段，为的是针对特定浏览器版本弥补浏览器自身的 bug。这些 CSS hack 手段在 CSS 校验器那里会被认为是无效代码。还有一些地方，我们使用了某些未被完全标准化的 CSS 特性，纯粹是为了实现渐进式增强的思路。

上面提到的这些校验器报告的警告信息并不会对实际使用造成影响，因为非 hack 部分的 CSS 是完全合格的，hack 部分不会对非 hack 部分的功能产生影响，这就是我们故意无视这些校验器警告的原因。

同样，我们的 HTML 文档中也有一些针对 Firefox bug 的 hack 代码，在 HTML 校验时也会被警告。