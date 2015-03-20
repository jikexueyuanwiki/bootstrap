# 编译 CSS 和 JavaScript 文件

Bootstrap 使用 Grunt 作为编译系统，并且对外提供了一些方便的方法用于编译整个框架。下面讲解的就是如何编译源码、运行测试用例等内容。

## 安装 Grunt
安装 Grunt 前，你需要首先下载并安装 node.js （npm 已经包含在内）。npm 是 node packaged modules 的简称，它的作用是基于 node.js 管理扩展包之间的依赖关系。

然后在命令行中输入以下命令：
在全局环境中安装 `grunt-cli` ：`npm install -g grunt-cli `。
进入 `/bootstrap/` 根目录，然后执行 `npm install` 命令。npm 将读取 `package.json` 文件并自动安装此文件中列出的所有被依赖的扩展包。
上述步骤完成后，你就可以运行 Bootstrap 所提供的各个 Grunt 命令了。

## 可用的 Grunt 命令
`grunt dist` （仅编译 CSS 和 JavaScript 文件）
重新生成 `/dist/` 目录，并将编译压缩后的 CSS 和 JavaScript 文件放入这个目录中。作为一名 Bootstrap 用户，大部分情况下你只需要执行这一个命令。

`grunt watch` （监测文件的改变，并运行指定的 Grunt 任务）
监测 Less 源码文件的改变，并自动重新将其编译为 CSS 文件。

`grunt test` （运行测试用例）
在 PhantomJS 环境中运行 JSHint 和 QUnit 自动化测试用例。

`grunt docs` （编译并测试文档中的资源文件）
编译并测试 CSS、JavaScript 和其他资源文件。在本地环境下通过 jekyll serve 运行 Bootstrap 文档时需要用到这些资源文件。

`grunt` （重新构建所有内容并运行测试用例）
编译并压缩 CSS 和 JavaScript 文件、构建文档站点、对文档做 HTML5 校验、重新生成定制工具所需的资源文件等，都需要 Jekyll 工具。这些只有在你对 Bootstrap 深度研究时才有用。

## 除错
如果你在安装依赖包或者运行 Grunt 命令时遇到了问题，请首先删除 npm 自动生成的 `/node_modules/` 目录，然后，再次运行 `npm install `命令。