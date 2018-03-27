### CSS定位方式
### display属性
每一个元素都有默认的display属性，使用最多的是block, inline和inline-block，不常用的是table-cell。

根据display属性，我们可以将元素分为块级元素(block)和内联级元素(inline)。它们最大区别是:block元素可以设置宽度，独占一行。inline元素宽度由内容决定，与其他元素并列在一行。

常见的block属性元素有：div, h1-h6, ul, li, ol, dl, dd, dt。

常见的inline属性元素有: span, a, em。

### block
宽高可以自行设置，默认宽度由父容器决定，默认高度有内容决定。自己独占一行。

1、block元素会独占一行，多个block元素会各自新起一行。默认情况下，block元素宽度自动填满其父元素宽度。

2、block元素可以设置width,height属性。块级元素即使设置了宽度,仍然是独占一行。

3、block元素可以设置margin和padding属性。

### inline
宽度和高度都有内容决定，与其他元素共占一行。

1、inline元素不会独占一行，多个相邻的行内元素会排列在同一行里，直到一行排列不下，才会新换一行，其宽度随元素的内容而变化。

2、inline元素设置width,height属性无效。

3、inline元素的margin和padding属性，水平方向的padding-left, padding-right, margin-left, margin-right都产生边距效果；但竖直方向的padding-top, padding-bottom, margin-top, margin-bottom不会产生边距效果。

### inline-block
宽度可以自行设置，类似block，但是与其他元素共占一行，类似inline。长用于设置垂直居中。

怎么让多个span在同一行显示，而且能够固定宽度呢？这就需要用到display:inline-block了。

### table-cell
此属性指让标签元素以表格单元格的形式呈现，单元格有一些比较特殊的属性，可以设置元素的垂直居中等。

### position属性
元素在页面中的布局遵守一套文档流的方式，默认的定位属性值为static。它其实是未被设置定位的。

元素如果被定位了，那么它的top,left,bottom,right值就会生效，能设置定位的属性是relative,absolute和fixed。

需要注意的另一点是被定位的元素层次(z-index)会得到提高。

### relative（相对定位）
设置了相对定位之后，通过修改top,left,bottom,right值，元素会在自身文档流所在位置上被移动，其他的元素则不会调整位置来弥补它偏离后剩下的空隙。

### absolute（绝对定位）
设置了绝对定位之后，元素脱离文档流，其他的元素会调整位置来弥补它偏离后剩下的空隙。元素偏移是相对于是它最近的设置了定位属性（position值不为static）的元素。

且如果元素为块级元素（display属性值为block)，那么它的宽度也会由内容撑开。因为：

默认文档流中块级元素如果没有设置宽度属性，会自动填满整行。

### fixed(固定定位)
设置了固定定位之后，元素相对的偏移的参考是可视窗口，即使页面滚动，元素仍然会在固定位置。