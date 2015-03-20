# 栅格系统

Bootstrap 提供了一套响应式、移动设备优先的流式栅格系统，随着屏幕或视口（viewport）尺寸的增加，系统会自动分为最多12列。它包含了易于使用的预定义类，还有强大的mixin 用于生成更具语义的布局。

## 简介
栅格系统用于通过一系列的行（row）与列（column）的组合来创建页面布局，你的内容就可以放入这些创建好的布局中。下面就介绍一下 Bootstrap 栅格系统的工作原理：

“行（row）”必须包含在 `.container` （固定宽度）或 `.container-fluid` （100% 宽度）中，以便为其赋予合适的排列（aligment）和内补（padding）。
通过“行（row）”在水平方向创建一组“列（column）”。
你的内容应当放置于“列（column）”内，并且，只有“列（column）”可以作为行（row）”的直接子元素。
类似 `.row` 和 `.col-xs-4` 这种预定义的类，可以用来快速创建栅格布局。Bootstrap 源码中定义的 mixin 也可以用来创建语义化的布局。
通过为“列（column）”设置 `padding` 属性，从而创建列与列之间的间隔（gutter）。通过为 `.row` 元素设置负值 `margin` 从而抵消掉为 `.container` 元素设置的 `padding`，也就间接为“行（row）”所包含的“列（column）”抵消掉了`padding`。
The negative margin is why the examples below are outdented. It's so that content within grid columns is lined up with non-grid content.
Grid columns are created by specifying the number of twelve available columns you wish to span. For example, three equal columns would use three `.col-xs-4`.
如果一“行（row）”中包含了的“列（column）”大于 12，多余的“列（column）”所在的元素将被作为一个整体另起一行排列。
Grid classes apply to devices with screen widths greater than or equal to the breakpoint sizes, and override grid classes targeted at smaller devices. Therefore, e.g. applying any `.col-md-*` class to an element will not only affect its styling on medium devices but also on large devices if a `.col-lg-*` class is not present.
通过研究后面的实例，可以将这些原理应用到你的代码中。

## 媒体查询
在栅格系统中，我们在 Less 文件中使用以下媒体查询（media query）来创建关键的分界点阈值。

```
    /* 超小屏幕（手机，小于 768px） */
    /* 没有任何媒体查询相关的代码，因为这在 Bootstrap 中是默认的（还记得 Bootstrap 是移动设备优先的吗？） */

    /* 小屏幕（平板，大于等于 768px） */
    @media (min-width: @screen-sm-min) { ... }

    /* 中等屏幕（桌面显示器，大于等于 992px） */
    @media (min-width: @screen-md-min) { ... }

    /* 大屏幕（大桌面显示器，大于等于 1200px） */
    @media (min-width: @screen-lg-min) { ... }
```

我们偶尔也会在媒体查询代码中包含 `max-width` 从而将 CSS 的影响限制在更小范围的屏幕大小之内。

```
    @media (max-width: @screen-xs-max) { ... }
    @media (min-width: @screen-sm-min) and (max-width: @screen-sm-max) { ... }
    @media (min-width: @screen-md-min) and (max-width: @screen-md-max) { ... }
    @media (min-width: @screen-lg-min) { ... }
```
## 栅格参数
通过下表可以详细查看 Bootstrap 的栅格系统是如何在多种屏幕设备上工作的。

超小屏幕 手机 (<768px)	小屏幕 平板 (≥768px)	中等屏幕 桌面显示器 (≥992px)	大屏幕 大桌面显示器 (≥1200px)
栅格系统行为	总是水平排列	开始是堆叠在一起的，当大于这些阈值时将变为水平排列C
`.container` 最大宽度	None （自动）	750px	970px	1170px
类前缀	`.col-xs-`	`.col-sm-`	`.col-md-`	`.col-lg-`
列（column）数	12
最大列（column）宽	自动	~62px	~81px	~97px
槽（gutter）宽	30px （每列左右均有 15px）
可嵌套	是
偏移（Offsets）	是
列排序	是
## 实例：从堆叠到水平排列
使用单一的一组 `.col-md-*` 栅格类，就可以创建一个基本的栅格系统，在手机和平板设备上一开始是堆叠在一起的（超小屏幕到小屏幕这一范围），在桌面（中等）屏幕设备上变为水平排列。所有“列（column）必须放在 ” `.row` 内。

.col-md-1.col-md-1.col-md-1.col-md-1.col-md-1.col-md-1.col-md-1.col-md-1.col-md-1.col-md-1.col-md-1.col-md-1
.col-md-8.col-md-4
.col-md-4.col-md-4.col-md-4
.col-md-6.col-md-6

```
    <div class="row">
      <div class="col-md-1">.col-md-1</div>
      <div class="col-md-1">.col-md-1</div>
      <div class="col-md-1">.col-md-1</div>
      <div class="col-md-1">.col-md-1</div>
      <div class="col-md-1">.col-md-1</div>
      <div class="col-md-1">.col-md-1</div>
      <div class="col-md-1">.col-md-1</div>
      <div class="col-md-1">.col-md-1</div>
      <div class="col-md-1">.col-md-1</div>
      <div class="col-md-1">.col-md-1</div>
      <div class="col-md-1">.col-md-1</div>
      <div class="col-md-1">.col-md-1</div>
    </div>
    <div class="row">
      <div class="col-md-8">.col-md-8</div>
      <div class="col-md-4">.col-md-4</div>
    </div>
    <div class="row">
      <div class="col-md-4">.col-md-4</div>
      <div class="col-md-4">.col-md-4</div>
      <div class="col-md-4">.col-md-4</div>
    </div>
    <div class="row">
      <div class="col-md-6">.col-md-6</div>
      <div class="col-md-6">.col-md-6</div>
    </div>
```
## 实例：流式布局容器
将最外面的布局元素 `.container` 修改为 `.container-fluid`，就可以将固定宽度的栅格布局转换为 100% 宽度的布局。

```
    <div class="container-fluid">
      <div class="row">
        ...
      </div>
    </div>
```
## 实例：移动设备和桌面屏幕
是否不希望在小屏幕设备上所有列都堆叠在一起？那就使用针对超小屏幕和中等屏幕设备所定义的类吧，即 `.col-xs-*` 和 `.col-md-*`。请看下面的实例，研究一下这些是如何工作的。

.col-xs-12 .col-md-8.col-xs-6 .col-md-4
.col-xs-6 .col-md-4.col-xs-6 .col-md-4.col-xs-6 .col-md-4
.col-xs-6.col-xs-6

```
    <!-- Stack the columns on mobile by making one full-width and the other half-width -->
    <div class="row">
      <div class="col-xs-12 col-md-8">.col-xs-12 .col-md-8</div>
      <div class="col-xs-6 col-md-4">.col-xs-6 .col-md-4</div>
    </div>

    <!-- Columns start at 50% wide on mobile and bump up to 33.3% wide on desktop -->
    <div class="row">
      <div class="col-xs-6 col-md-4">.col-xs-6 .col-md-4</div>
      <div class="col-xs-6 col-md-4">.col-xs-6 .col-md-4</div>
      <div class="col-xs-6 col-md-4">.col-xs-6 .col-md-4</div>
    </div>

    <!-- Columns are always 50% wide, on mobile and desktop -->
    <div class="row">
      <div class="col-xs-6">.col-xs-6</div>
      <div class="col-xs-6">.col-xs-6</div>
    </div>
```

## 实例：手机、平板、桌面
在上面案例的基础上，通过使用针对平板设备的 `.col-sm-*` 类，我们来创建更加动态和强大的布局吧。

.col-xs-12 .col-sm-6 .col-md-8.col-xs-6 .col-md-4
.col-xs-6 .col-sm-4.col-xs-6 .col-sm-4.col-xs-6 .col-sm-4

```
    <div class="row">
      <div class="col-xs-12 col-sm-6 col-md-8">.col-xs-12 .col-sm-6 .col-md-8</div>
      <div class="col-xs-6 col-md-4">.col-xs-6 .col-md-4</div>
    </div>
    <div class="row">
      <div class="col-xs-6 col-sm-4">.col-xs-6 .col-sm-4</div>
      <div class="col-xs-6 col-sm-4">.col-xs-6 .col-sm-4</div>
      <!-- Optional: clear the XS cols if their content doesn't match in height -->
      <div class="clearfix visible-xs-block"></div>
      <div class="col-xs-6 col-sm-4">.col-xs-6 .col-sm-4</div>
    </div>
```

## 实例：多余的列（column）将另起一行排列
如果在一个 `.row` 内包含的列（column）大于12个，包含多余列（column）的元素将作为一个整体单元被另起一行排列。

.col-xs-9.col-xs-4
Since 9 + 4 = 13 > 12, this 4-column-wide div gets wrapped onto a new line as one contiguous unit..col-xs-6
Subsequent columns continue along the new line.

```
    <div class="row">
      <div class="col-xs-9">.col-xs-9</div>
      <div class="col-xs-4">.col-xs-4<br>Since 9 + 4 = 13 &gt; 12, this 4-column-wide div gets wrapped onto a new line as one contiguous unit.</div>
      <div class="col-xs-6">.col-xs-6<br>Subsequent columns continue along the new line.</div>
    </div>
```

## Responsive column resets
With the four tiers of grids available you're bound to run into issues where, at certain breakpoints, your columns don't clear quite right as one is taller than the other. To fix that, use a combination of a `.clearfix` and our responsive utility classes.

.col-xs-6 .col-sm-3 
Resize your viewport or check it out on your phone for an example. .col-xs-6 .col-sm-3.col-xs-6 .col-sm-3.col-xs-6 .col-sm-3

```
    <div class="row">
      <div class="col-xs-6 col-sm-3">.col-xs-6 .col-sm-3</div>
      <div class="col-xs-6 col-sm-3">.col-xs-6 .col-sm-3</div>

      <!-- Add the extra clearfix for only the required viewport -->
      <div class="clearfix visible-xs-block"></div>

      <div class="col-xs-6 col-sm-3">.col-xs-6 .col-sm-3</div>
      <div class="col-xs-6 col-sm-3">.col-xs-6 .col-sm-3</div>
    </div>
```

In addition to column clearing at responsive breakpoints, you may need to **reset offsets, pushes, or pulls**. See this in action in the grid example.

```
    <div class="row">
      <div class="col-sm-5 col-md-6">.col-sm-5 .col-md-6</div>
      <div class="col-sm-5 col-sm-offset-2 col-md-6 col-md-offset-0">.col-sm-5 .col-sm-offset-2 .col-md-6 .col-md-offset-0</div>
    </div>

    <div class="row">
      <div class="col-sm-6 col-md-5 col-lg-6">.col-sm-6 .col-md-5 .col-lg-6</div>
      <div class="col-sm-6 col-md-5 col-md-offset-2 col-lg-6 col-lg-offset-0">.col-sm-6 .col-md-5 .col-md-offset-2 .col-lg-6 .col-lg-offset-0</div>
    </div>
```

## 列偏移
使用 `.col-md-offset-* `类可以将列向右侧偏移。这些类实际是通过使用 `* `选择器为当前元素增加了左侧的边距（margin）。例如，`.col-md-offset-4 `类将 `.col-md-4` 元素向右侧偏移了4个列（column）的宽度。

.col-md-4.col-md-4 .col-md-offset-4
.col-md-3 .col-md-offset-3.col-md-3 .col-md-offset-3
.col-md-6 .col-md-offset-3

```
    <div class="row">
      <div class="col-md-4">.col-md-4</div>
      <div class="col-md-4 col-md-offset-4">.col-md-4 .col-md-offset-4</div>
    </div>
    <div class="row">
      <div class="col-md-3 col-md-offset-3">.col-md-3 .col-md-offset-3</div>
      <div class="col-md-3 col-md-offset-3">.col-md-3 .col-md-offset-3</div>
    </div>
    <div class="row">
      <div class="col-md-6 col-md-offset-3">.col-md-6 .col-md-offset-3</div>
    </div>
```

## 嵌套列
为了使用内置的栅格系统将内容再次嵌套，可以通过添加一个新的 `.row` 元素和一系列 `.col-sm-*` 元素到已经存在的 `.col-sm-*` 元素内。被嵌套的行（row）所包含的列（column）的个数不能超过12（其实，没有要求你必须占满12列）。

Level 1: .col-sm-9
Level 2: .col-xs-8 .col-sm-6 Level 2: .col-xs-4 .col-sm-6

```
    <div class="row">
      <div class="col-sm-9">
        Level 1: .col-sm-9
        <div class="row">
          <div class="col-xs-8 col-sm-6">
            Level 2: .col-xs-8 .col-sm-6
          </div>
          <div class="col-xs-4 col-sm-6">
            Level 2: .col-xs-4 .col-sm-6
          </div>
        </div>
      </div>
    </div>
```

## 列排序
通过使用 `.col-md-push-*`和 `.col-md-pull-*` 类就可以很容易的改变列（column）的顺序。

.col-md-9 .col-md-push-3.col-md-3 .col-md-pull-9

```
    <div class="row">
      <div class="col-md-9 col-md-push-3">.col-md-9 .col-md-push-3</div>
      <div class="col-md-3 col-md-pull-9">.col-md-3 .col-md-pull-9</div>
    </div>
```
## Less mixin 和变量
除了用于快速布局的预定义栅格类，Bootstrap 还包含了一组 Less 变量和 mixin 用于帮你生成简单、语义化的布局。

### 变量

通过变量来定义列数、槽（gutter）宽、媒体查询阈值（用于确定合适让列浮动）。我们使用这些变量生成预定义的栅格类，如上所示，还有如下所示的定制 mixin。

```
    @grid-columns:              12;
    @grid-gutter-width:         30px;
    @grid-float-breakpoint:     768px;
```

### mixin


mixin 用来和栅格变量一同使用，为每个列（column）生成语义化的 CSS 代码。

```
    // Creates a wrapper for a series of columns
    .make-row(@gutter: @grid-gutter-width) {
      // Then clear the floated columns
      .clearfix();

      @media (min-width: @screen-sm-min) {
        margin-left:  (@gutter / -2);
        margin-right: (@gutter / -2);
      }

      // Negative margin nested rows out to align the content of columns
      .row {
        margin-left:  (@gutter / -2);
        margin-right: (@gutter / -2);
      }
    }

    // Generate the extra small columns
    .make-xs-column(@columns; @gutter: @grid-gutter-width) {
      position: relative;
      // Prevent columns from collapsing when empty
      min-height: 1px;
      // Inner gutter via padding
      padding-left:  (@gutter / 2);
      padding-right: (@gutter / 2);

      // Calculate width based on number of columns available
      @media (min-width: @grid-float-breakpoint) {
        float: left;
        width: percentage((@columns / @grid-columns));
      }
    }

    // Generate the small columns
    .make-sm-column(@columns; @gutter: @grid-gutter-width) {
      position: relative;
      // Prevent columns from collapsing when empty
      min-height: 1px;
      // Inner gutter via padding
      padding-left:  (@gutter / 2);
      padding-right: (@gutter / 2);

      // Calculate width based on number of columns available
      @media (min-width: @screen-sm-min) {
        float: left;
        width: percentage((@columns / @grid-columns));
      }
    }

    // Generate the small column offsets
    .make-sm-column-offset(@columns) {
      @media (min-width: @screen-sm-min) {
        margin-left: percentage((@columns / @grid-columns));
      }
    }
    .make-sm-column-push(@columns) {
      @media (min-width: @screen-sm-min) {
        left: percentage((@columns / @grid-columns));
      }
    }
    .make-sm-column-pull(@columns) {
      @media (min-width: @screen-sm-min) {
        right: percentage((@columns / @grid-columns));
      }
    }

    // Generate the medium columns
    .make-md-column(@columns; @gutter: @grid-gutter-width) {
      position: relative;
      // Prevent columns from collapsing when empty
      min-height: 1px;
      // Inner gutter via padding
      padding-left:  (@gutter / 2);
      padding-right: (@gutter / 2);

      // Calculate width based on number of columns available
      @media (min-width: @screen-md-min) {
        float: left;
        width: percentage((@columns / @grid-columns));
      }
    }

    // Generate the medium column offsets
    .make-md-column-offset(@columns) {
      @media (min-width: @screen-md-min) {
        margin-left: percentage((@columns / @grid-columns));
      }
    }
    .make-md-column-push(@columns) {
      @media (min-width: @screen-md-min) {
        left: percentage((@columns / @grid-columns));
      }
    }
    .make-md-column-pull(@columns) {
      @media (min-width: @screen-md-min) {
        right: percentage((@columns / @grid-columns));
      }
    }

    // Generate the large columns
    .make-lg-column(@columns; @gutter: @grid-gutter-width) {
      position: relative;
      // Prevent columns from collapsing when empty
      min-height: 1px;
      // Inner gutter via padding
      padding-left:  (@gutter / 2);
      padding-right: (@gutter / 2);

      // Calculate width based on number of columns available
      @media (min-width: @screen-lg-min) {
        float: left;
        width: percentage((@columns / @grid-columns));
      }
    }

    // Generate the large column offsets
    .make-lg-column-offset(@columns) {
      @media (min-width: @screen-lg-min) {
        margin-left: percentage((@columns / @grid-columns));
      }
    }
    .make-lg-column-push(@columns) {
      @media (min-width: @screen-lg-min) {
        left: percentage((@columns / @grid-columns));
      }
    }
    .make-lg-column-pull(@columns) {
      @media (min-width: @screen-lg-min) {
        right: percentage((@columns / @grid-columns));
      }
    }
```

## 实例展示

你可以重新修改这些变量的值，或者用默认值调用这些 mixin。下面就是一个利用默认设置生成两列布局（列之间有间隔）的案例。

```
    .wrapper {
      .make-row();
    }
    .content-main {
      .make-lg-column(8);
    }
    .content-secondary {
      .make-lg-column(3);
      .make-lg-column-offset(1);
    }
```

```
    <div class="wrapper">
      <div class="content-main">...</div>
      <div class="content-secondary">...</div>
    </div>
```
