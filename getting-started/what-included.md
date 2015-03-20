# 包含的内容

Bootstrap 提供了两种形式的压缩包，在下载下来的压缩包内可以看到以下目录和文件，这些文件按照类别放到了不同的目录内，并且提供了压缩与未压缩两种版本。

`Bootstrap 插件全部依赖 jQuery`
请注意，**Bootstrap 的所有 JavaScript 插件都依赖 jQuery**，因此 jQuery 必须在 Bootstrap 之前引入，就像在基本模版中所展示的一样。在 `bower.json `文件中 列出了 Bootstrap 所支持的 jQuery 版本。
##预编译版
下载压缩包之后，将其解压缩到任意目录即可看到以下（压缩版的）目录结构：

```
bootstrap/
├── css/
│   ├── bootstrap.css
│   ├── bootstrap.css.map
│   ├── bootstrap.min.css
│   ├── bootstrap-theme.css
│   ├── bootstrap-theme.css.map
│   └── bootstrap-theme.min.css
├── js/
│   ├── bootstrap.js
│   └── bootstrap.min.js
└── fonts/
    ├── glyphicons-halflings-regular.eot
    ├── glyphicons-halflings-regular.svg
    ├── glyphicons-halflings-regular.ttf
    ├── glyphicons-halflings-regular.woff
    └── glyphicons-halflings-regular.woff2
```        
上面展示的就是 Bootstrap 的基本文件结构：预编译文件可以直接使用到任何 web 项目中。我们提供了编译好的 CSS 和 JS (`bootstrap.*`) 文件，还有经过压缩的 CSS 和 JS (`bootstrap.min.*`) 文件。同时还提供了 CSS 源码映射表 (`bootstrap.*.map`) ，可以在某些浏览器的开发工具中使用。同时还包含了来自 Glyphicons 的图标字体，在附带的 Bootstrap 主题中使用到了这些图标。

##Bootstrap 源码
Bootstrap 源码包含了预先编译的 CSS、JavaScript 和图标字体文件，并且还有 LESS、JavaScript 和文档的源码。具体来说，主要文件组织结构如下：

```
bootstrap/
├── less/
├── js/
├── fonts/
├── dist/
│   ├── css/
│   ├── js/
│   └── fonts/
└── docs/
    └── examples/
```
`less/`、`js/` 和 `fonts/` 目录分别包含了 CSS、JS 和字体图标的源码。`dist/` 目录包含了上面所说的预编译 Bootstrap 包内的所有文件。`docs/` 包含了所有文档的源码文件，`examples/` 目录是 Bootstrap 官方提供的实例工程。除了这些，其他文件还包含 Bootstrap 安装包的定义文件、许可证文件和编译脚本等。