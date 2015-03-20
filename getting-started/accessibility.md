# 可访问性

Bootstrap 遵循统一的 web 标准，另外，通过做一些少量的修改，还可以让使用 辅助设备（AT - ASSISTIVE TECHNOLOGY）上网的人群访问你的站点。

##跳过导航区
如果你的导航部分包含很多链接，并且在 DOM 结构上也是排在主内容之前，那么，建议在导航前面添加一个 Skip to main content（直接进入主内容区） 的链接，(这里解释了这样做的原因)。 Using the .sr-only class will visually hide the skip link, and the .sr-only-focusable class will ensure that the link becomes visible once focused (for sighted keyboard users).

```
<body>
  <a href="#content" class="sr-only sr-only-focusable">Skip to main content</a>
  ...
  <div class="container" id="content">
    <!-- The main page content -->
  </div>
</body>
```

## 标题嵌套
当标题嵌套时 (`<h1> `- `<h6>`)，你的文档的主标题应该是 `<h1>` 标签。随后的标题逻辑上就应该使用 `<h2>` - `<h6> `，这样，屏幕阅读器就可以构造出页面的内容列表了。

更多信息请参考： HTML CodeSniffer and Penn State's AccessAbility.

## Color contrast
Currently, some of the default color combinations available in Bootstrap (such as the various styled button classes, some of the code highlighting colors used for basic code blocks, the `.bg-primary` contextual background helper class, and the default link color when used on a white background) have a low contrast ratio (below the recommended ratio of 4.5:1). This can cause problems to users with low vision or who are color blind. These default colors may need to be modified to increase their contrast and legibility.

扩展阅读
"HTML Codesniffer" bookmarklet for identifying accessibility issues
Chrome's Accessibility Developer Tools extension
Colour Contrast Analyser
The A11Y Project
MDN accessibility documentation
