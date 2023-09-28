# 前端小笔记

## 前端组件库：

- H-ui（admin组件样式库）
- Element-ui（pc端组件样式库）
- Vant（安卓端组件样式库）
- Color-UI（微信小程序样式库）
- Bootstrap（目前最受欢迎的前端框架，基于HTML、CSS、Javascript）
- LayUi（组件库样式库）
- EasUi（jQuery的组件库）
- Weui（微信小程序组件）
- mui (移动H5端)

## 前端框架：

- Vue

- React

  JS库：

  - jQuery 就是封装的JS
- Lodash 工具库
  

跨端开发：

  - uniapp: 支持多端(H5、百度小程序、微信小程序、字节小程序、Android、iOS...)
  - taro: 支持多端小程序
- flutter: 支持多端(web端、移动端、桌面和嵌入式平台)
  
  

## HTML小笔记：

**inert属性：**inert 属性是 HTMLElement 的一个布尔属性，意为"惰性"，简单来说，可以禁用一切交互，包括鼠标点击、选中、拖拽、键盘操作等。

例如：

```html

<!-- 给div加了inert属性后，这个div里的所有属性都不能交互了，不能触发事件 -->
<div inert>
    <input type="text" />
    <button>
		click        
    </button>
</div>

<!--以下都为true-->
<div inert>...</div>
<div inert="true">...</div>
<div inert="false">...</div>
<!--以下才是false-->
<div>...</div>

<!-- 只有不加inert属性后，div里所有属性可以交互，可以触发事件 -->
<div>
    <button>
        handleClick
    </button>
</div>

```



## CSS小笔记：

**属性选择器：**

- 选择包含某一属性的元素
- a[title]{color:red;} 选择包含title的a标签
- a[title][href]{color:red;} 选择包含title和href的a标签

​    输入伪类选择器：input:focus{color:red;}（ 键盘输入焦点 ）

**其他伪类选择器：**

- p:first-child{color:red;} （第一个p）
- :before （在元素之前添加内容）
- :after （在元素之后添加内容
- p:last-child{ color:blue; } ( 最后一个P )
- p:nth-child(3){ color:green; } ( 第三个p )

#### css文字文本属性：

```scss
font-style: normal/ italic; 					 // 设置文本为斜体
font-weight: normal(100-500)/ bold(600-900); 	 // 设置文本为粗体
font-family: “文本字体1”,”文本字体2”; 			  // 文本类型
text-align: left/center/right;				     // 文本水平对齐方式
vertical-align:top/middle/bottom;				 // 垂直对齐方式
line-height: 25px;								 // 设置文本在一行内的高度
color：#FFF;										// 设置字体颜色
letter—spacing：1em;								// 定义字符间隔
```

**文字省略号**：

```scss
overflow: hidden; 			// 溢位隐藏
text-overflow: ellipsis; 	// 文字溢位隐藏为省略号
-webkit-line-clamp: 3; 		// 设置行数为第三行
white-space: nowrap;		// 设置行数为单行

display: -webkit-box; 		
-webkit-box-orient: vertical;
```

**设置文本简写方式：**

```scss
text-decoration: none; 	// 文本修饰

// 属性
none 					// 没有属性
underline				// 添加下划线
overline				// 添加上划线
line-through			// 添加删除线
text-indent				// 首行缩进

```

**文本大小写：**

text-transform:

uppercase 单词都大写

lowercase 单字都小写

capitalize 每个单词首字母大写



***单位 描述：***

% 百分比

in 英寸

cm 厘米

mm 毫米

em 1em=当前的字体尺寸，2em=当前字体尺寸的两倍（在CSS中，em可以自动适应用户所使用的字体）

ex 一个ex是一个字体的x-height（x-height通常是字体尺寸的一半）

pt 1pt=1/72英寸（是一个标准的长度单位）

pc 1pc=12点（12点活字）

px 像素

vmin 

vmax

| 单位   | 基于...                                                      |
| :----- | :----------------------------------------------------------- |
| `em`   | 元素的字号                                                   |
| `ex`   | 字体的 X 字高（x-height）                                    |
| `cap`  | 字体中大写字母的标称高度                                     |
| `ch`   | Average character advance of a narrow glyph in the element’s font, as represented by the “0” (ZERO, U+0030) glyph. |
| `ic`   | Average character advance of a full width glyph in the element’s font, as represented by the“水” (CJK water ideograph, U+6C34) glyph. |
| `rem`  | 根元素的字体大小。                                           |
| `lh`   | 元素的行高。                                                 |
| `rlh`  | 根元素的行高。                                               |
| `vw`   | 1% of viewport's width.                                      |
| `vh`   | 1% of viewport's height.                                     |
| `vi`   | 1% of viewport's size in the root element's inline axis.     |
| `vb`   | 1% of viewport's size in the root element's block axis.      |
| `vmin` | 1% of viewport's smaller dimension.                          |
| `vmax` | 1% of viewport's larger dimension.                           |

| Unit | Name                | Equivalent to       |
| :--- | :------------------ | :------------------ |
| `cm` | Centimeters         | 1cm = 96px/2.54     |
| `mm` | Millimeters         | 1mm = 1/10th of 1cm |
| `Q`  | Quarter-millimeters | 1Q = 1/40th of 1cm  |
| `in` | Inches              | 1in = 2.54cm = 96px |
| `pc` | Picas               | 1pc = 1/16th of 1in |
| `pt` | Points              | 1pt = 1/72th of 1in |
| `px` | Pixels              | 1px = 1/96th of 1in |

<img src="/img/css_unit.jpg"/>

#### CSS自定义属性 变量：

声明变量 用 --name

使用时 用 var(--name)

例如：

```css
element {
    /* 声明一个变量 */
    --ColorName: red;
    /* 使用变量 */
    color: var(--ColorName);
}
```

#### CSS 颜色：

十六进制透明度：   FF 100%透明度 完全不透明； 00 0%透明度 完全透明

根据十六进制计算，每增加 1 大约增加 6% 的透明度。 每增加 10 大约增加 60% 的透明度

​			

```css
background-color: #FFFFFF;    /* 白色 */
color: #FFFFFF<透明度值>;      /* 后面两位值设置透明度 */
/* 例如 */
color: #00000050;			 /* 黑色 透明度50% */
```



**透明度对照表**

透明度 —— 十六进制后两位值

100% — FF

99% — FC

98% — FA

97% — F7

96% — F5

95% — F2

94% — F0

93% — ED

92% — EB

91% — E8

90% — E6

89% — E3

88% — E0

87% — DE

86% — DB

85% — D9

84% — D6

83% — D4

82% — D1

81% — CF

80% — CC

79% — C9

78% — C7

77% — C4

76% — C2

75% — BF

74% — BD

73% — BA

72% — B8

71% — B5

70% — B3

69% — B0

68% — AD

67% — AB

66% — A8

65% — A6

64% — A3

63% — A1

62% — 9E

61% — 9C

60% — 99

59% — 96

58% — 94

57% — 91

56% — 8F

55% — 8C

54% — 8A

53% — 87

52% — 85

### CSS3 新增：

**filter ：** 滤镜给图片添加滤镜属性

### 属性 Background:

``` css
body {
    /* 在一个元素中设置多个背景（并指定位置） */
    background:#00ff00 url("backimg.png") no-repeat fixed center;
}
```



| 值                                                           | 说明                                             | CSS  |
| :----------------------------------------------------------- | :----------------------------------------------- | :--- |
| *[background-color](https://www.runoob.com/cssref/pr-background-color.html)* | 指定要使用的背景颜色                             | 1    |
| *[background-position](https://www.runoob.com/cssref/pr-background-position.html)* | 指定背景图像的位置                               | 1    |
| *[background-size](https://www.runoob.com/cssref/css3-pr-background-size.html)* | 指定背景图片的大小                               | 3    |
| *[background-repeat](https://www.runoob.com/cssref/pr-background-repeat.html)* | 指定如何重复背景图像                             | 1    |
| *[background-origin](https://www.runoob.com/cssref/css3-pr-background-origin.html)* | 指定背景图像的定位区域                           | 3    |
| *[background-clip](https://www.runoob.com/cssref/css3-pr-background-clip.html)* | 指定背景图像的绘画区域                           | 3    |
| *[background-attachment](https://www.runoob.com/cssref/pr-background-attachment.html)* | 设置背景图像是否固定或者随着页面的其余部分滚动。 | 1    |
| *[background-image](https://www.runoob.com/cssref/pr-background-image.html)* | 指定要使用的一个或多个背景图像                   | 1    |

#### cursor用法：

 cursor：pointer  更改鼠标经过时鼠标指针的样式

**cursor　值　列表：**

| 值        | 描述                                                         |
| :-------- | :----------------------------------------------------------- |
| *url*     | 需使用的自定义光标的 URL。注释：请在此列表的末端始终定义一种普通的光标，以防没有由 URL 定义的可用光标。 |
| default   | 默认光标（通常是一个箭头）                                   |
| auto      | 默认。浏览器设置的光标。                                     |
| crosshair | 光标呈现为十字线。                                           |
| pointer   | 光标呈现为指示链接的指针（一只手）                           |
| move      | 此光标指示某对象可被移动。                                   |
| e-resize  | 此光标指示矩形框的边缘可被向右（东）移动。                   |
| ne-resize | 此光标指示矩形框的边缘可被向上及向右移动（北/东）。          |
| nw-resize | 此光标指示矩形框的边缘可被向上及向左移动（北/西）。          |
| n-resize  | 此光标指示矩形框的边缘可被向上（北）移动。                   |
| se-resize | 此光标指示矩形框的边缘可被向下及向右移动（南/东）。          |
| sw-resize | 此光标指示矩形框的边缘可被向下及向左移动（南/西）。          |
| s-resize  | 此光标指示矩形框的边缘可被向下移动（南）。                   |
| w-resize  | 此光标指示矩形框的边缘可被向左移动（西）。                   |
| text      | 此光标指示文本。                                             |
| wait      | 此光标指示程序正忙（通常是一只表或沙漏）。                   |
| help      | 此光标指示可用的帮助（通常是一个问号或一个气球）。           |



#### transform用法： transform: none | transform-functions;

| 值                                                           | 描述                                    |
| ------------------------------------------------------------ | --------------------------------------- |
| none                                                         | 定义不进行转换。                        |
| matrix(*n*,*n*,*n*,*n*,*n*,*n*)                              | 定义 2D 转换，使用六个值的矩阵。        |
| matrix3d(*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*) | 定义 3D 转换，使用 16 个值的 4x4 矩阵。 |
| translate(*x*,*y*)                                           | 定义 2D 转换。                          |
| translate3d(*x*,*y*,*z*)                                     | 定义 3D 转换。                          |
| translateX(*x*)                                              | 定义转换，只是用 X 轴的值。             |
| translateY(*y*)                                              | 定义转换，只是用 Y 轴的值。             |
| translateZ(*z*)                                              | 定义 3D 转换，只是用 Z 轴的值。         |
| scale(*x*[,*y*]?)                                            | 定义 2D 缩放转换。                      |
| scale3d(*x*,*y*,*z*)                                         | 定义 3D 缩放转换。                      |
| scaleX(*x*)                                                  | 通过设置 X 轴的值来定义缩放转换。       |
| scaleY(*y*)                                                  | 通过设置 Y 轴的值来定义缩放转换。       |
| scaleZ(*z*)                                                  | 通过设置 Z 轴的值来定义 3D 缩放转换。   |
| rotate(*angle*)                                              | 定义 2D 旋转，在参数中规定角度。        |
| rotate3d(*x*,*y*,*z*,*angle*)                                | 定义 3D 旋转。                          |
| rotateX(*angle*)                                             | 定义沿着 X 轴的 3D 旋转。               |
| rotateY(*angle*)                                             | 定义沿着 Y 轴的 3D 旋转。               |
| rotateZ(*angle*)                                             | 定义沿着 Z 轴的 3D 旋转。               |
| skew(*x-angle*,*y-angle*)                                    | 定义沿着 X 和 Y 轴的 2D 倾斜转换。      |
| skewX(*angle*)                                               | 定义沿着 X 轴的 2D 倾斜转换。           |
| skewY(*angle*)                                               | 定义沿着 Y 轴的 2D 倾斜转换。           |
| perspective(*n*)                                             | 为 3D 转换元素定义透视视图。            |

**input框去除聚焦框：outline: none;**

**textarea文本域去除右下角三角：resize:none;**

**display属性：常见的有：block块级元素、inline内联元素、inline-block行内块元素、none元素不显示**

#### display属性大全：

| 值                 | 描述                                                         |
| ------------------ | ------------------------------------------------------------ |
| none               | 此元素不会被显示。                                           |
| block              | 此元素将显示为块级元素，此元素前后会带有换行符。             |
| inline             | 默认。此元素会被显示为内联元素，元素前后没有换行符。         |
| inline-block       | 行内块元素。（CSS2.1 新增的值）                              |
| list-item          | 此元素会作为列表显示。                                       |
| run-in             | 此元素会根据上下文作为块级元素或内联元素显示。               |
| compact            | CSS 中有值 compact，不过由于缺乏广泛支持，已经从 CSS2.1 中删除。 |
| marker             | CSS 中有值 marker，不过由于缺乏广泛支持，已经从 CSS2.1 中删除。 |
| table              | 此元素会作为块级表格来显示（类似 <table>），表格前后带有换行符。 |
| inline-table       | 此元素会作为内联表格来显示（类似 <table>），表格前后没有换行符。 |
| table-row-group    | 此元素会作为一个或多个行的分组来显示（类似 <tbody>）。       |
| table-header-group | 此元素会作为一个或多个行的分组来显示（类似 <thead>）。       |
| table-footer-group | 此元素会作为一个或多个行的分组来显示（类似 <tfoot>）。       |
| table-row          | 此元素会作为一个表格行显示（类似 <tr>）。                    |
| table-column-group | 此元素会作为一个或多个列的分组来显示（类似 <colgroup>）。    |
| table-column       | 此元素会作为一个单元格列显示（类似 <col>）                   |
| table-cell         | 此元素会作为一个表格单元格显示（类似 <td> 和 <th>）          |
| table-caption      | 此元素会作为一个表格标题显示（类似 <caption>）               |
| inherit            | 规定应该从父元素继承 display 属性的值。                      |

#### vertical-align ：属性设置元素的垂直对齐方式。

**说明：**该属性定义行内元素的基线相对于该元素所在行的基线的垂直对齐方式

**属性列表：**

| 值          | 描述                                                         |
| :---------- | :----------------------------------------------------------- |
| baseline    | 默认。元素放置在父元素的基线上。                             |
| sub         | 垂直对齐文本的下标。                                         |
| super       | 垂直对齐文本的上标                                           |
| top         | 把元素的顶端与行中最高元素的顶端对齐                         |
| text-top    | 把元素的顶端与父元素字体的顶端对齐                           |
| middle      | 把此元素放置在父元素的中部。                                 |
| bottom      | 把元素的顶端与行中最低的元素的顶端对齐。                     |
| text-bottom | 把元素的底端与父元素字体的底端对齐。                         |
| length      |                                                              |
| %           | 使用 "line-height" 属性的百分比值来排列此元素。允许使用负值。 |
| inherit     | 规定应该从父元素继承 vertical-align 属性的值。               |



#### Position：属性 指定了元素的定位类型

**属性值有：**

1. static HTML默认值 即没有定位，遵循正常文档流对象。
2. fixed  元素位置相对于浏览器固定位置 即使窗口滚动它也不会动
3. relative  相对定位元素的定位是相对其他正常位置
4. absolute  绝对定位的元素相对于最近的已定位的父元素，如果没有已定父元素，那么它的位置相对于<HTML>
5. sticky  粘性定位，该定位基于用户滚动的位置。滚轮往下滚时，拥有sticky的元素会被粘在最顶部。



## HTML部分：

### HTML元素：

标准文档流：指元素根据块元素或行内元素的特性按从上到下，从左到右的方式自然排列。这也是元素默认的排列方式

元素：

1. 块级元素（block）：<h1>…<h6>、<p>、<div>、列表
2. 内联元素(也叫行内元素)（inline）：<span>、<a>、<img/>、<strong>...

***HTML DOM：***HTML DOM是HTML Document Object Model（文档对象模型）

***XHTML：***更严格更纯净的基于 XML 的 HTML 版本。

***XML：***被设计用来传输和存储数据。

***HTML：***被设计用来显示数据。

***SOPA：***允许应用程序在 HTTP 之上交换信息的基于 XML 的协议。

***XML DOM：***访问和操作 XML 的标准文档模型。

***Xpath：***用于在 XML 文档中导航的语言。

***Xquery:*** XQuery 之于 XML 作用就类似于 SQL 之于数据库的作用。XQuery 被设计用来查询 XML 数据。



***Xpath语法：***XPath 使用路径表达式在 XML 文档中选取节点。节点是通过沿着路径或者 step 来选取的。

``` xquery
Xpath语句： 又称Xquery
//div                     选取当前div 
//div[@class='test']/*    选取当前div 类名为 test 里面所有的 内容
```
#### Xpath 参考语法手册：

| 表达式   | 描述                                                       |
| -------- | ---------------------------------------------------------- |
| nodename | 选取此节点的所有子节点。                                   |
| /        | 从根节点选取。                                             |
| //       | 从匹配选择的当前节点选择文档中的节点，而不考虑它们的位置。 |
| .        | 选取当前节点。                                             |
| ..       | 选取当前节点的父节点。                                     |
| @        | 选取属性。                                                 |

实例：在下面的表格中，我们已列出了一些路径表达式以及表达式的结果：

| 路径表达式      | 结果                                                         |
| --------------- | ------------------------------------------------------------ |
| bookstore       | 选取 bookstore 元素的所有子节点。                            |
| /bookstore      | 选取根元素 bookstore。注释：假如路径起始于正斜杠( / )，则此路径始终代表到某元素的绝对路径！ |
| bookstore/book  | 选取属于 bookstore 的子元素的所有 book 元素。                |
| //book          | 选取所有 book 子元素，而不管它们在文档中的位置。             |
| bookstore//book | 选择属于 bookstore 元素的后代的所有 book 元素，而不管它们位于 bookstore 之下的什么位置。 |
| //@lang         | 选取名为 lang 的所有属性。                                   |

谓语：谓语用来查找某个特定的节点或者包含某个指定的值的节点。谓语被嵌在方括号中。

实例：

| 路径表达式                         | 结果                                                         |
| ---------------------------------- | ------------------------------------------------------------ |
| /bookstore/book[1]                 | 选取属于 bookstore 子元素的第一个 book 元素。                |
| /bookstore/book[last()]            | 选取属于 bookstore 子元素的最后一个 book 元素。              |
| /bookstore/book[last()-1]          | 选取属于 bookstore 子元素的倒数第二个 book 元素。            |
| /bookstore/book[position()<3]      | 选取最前面的两个属于 bookstore 元素的子元素的 book 元素。    |
| //title[@lang]                     | 选取所有拥有名为 lang 的属性的 title 元素。                  |
| //title[@lang='eng']               | 选取所有 title 元素，且这些元素拥有值为 eng 的 lang 属性。   |
| /bookstore/book[price>35.00]       | 选取 bookstore 元素的所有 book 元素，且其中的 price 元素的值须大于 35.00。 |
| /bookstore/book[price>35.00]/title | 选取 bookstore 元素中的 book 元素的所有 title 元素，且其中的 price 元素的值须大于 35.00。 |

选取未知节点：

| 通配符 | 描述                 |
| ------ | -------------------- |
| *      | 匹配任何元素节点。   |
| @*     | 匹配任何属性节点。   |
| node() | 匹配任何类型的节点。 |

实例：

| 路径表达式   | 结果                              |
| ------------ | --------------------------------- |
| /bookstore/* | 选取 bookstore 元素的所有子元素。 |
| //*          | 选取文档中的所有元素。            |
| //title[@*]  | 选取所有带有属性的 title 元素。   |

选取若干路径：通过在路径表达式中使用“|”运算符，您可以选取若干个路径。

| 路径表达式                       | 结果                                                         |
| -------------------------------- | ------------------------------------------------------------ |
| //book/title \| //book/price     | 选取 book 元素的所有 title 和 price 元素。                   |
| //title \| //price               | 选取文档中的所有 title 和 price 元素。                       |
| /bookstore/book/title \| //price | 选取属于 bookstore 元素的 book 元素的所有 title 元素，以及文档中所有的 price 元素。 |

### Canvas画布：

用于图形的绘制，通过JavaScript脚本来完成的；<canvas></canvas> 标签只是图形容器，必须使用脚本来绘制图形。

```html
<!-- 创建一个画布 -->

<canvas id="myCanvas" width="500" height="500"></canvas>

<script>
var c = document.getElementById("myCanvas");
    
var ctx = c.getContext(2d);
    
</script>
```

##### 颜色、样式和阴影

| 属性                                                         | 描述                                       |
| :----------------------------------------------------------- | :----------------------------------------- |
| [fillStyle](https://www.runoob.com/tags/canvas-fillstyle.html) | 设置或返回用于填充绘画的颜色、渐变或模式。 |
| [strokeStyle](https://www.runoob.com/tags/canvas-strokestyle.html) | 设置或返回用于笔触的颜色、渐变或模式。     |
| [shadowColor](https://www.runoob.com/tags/canvas-shadowcolor.html) | 设置或返回用于阴影的颜色。                 |
| [shadowBlur](https://www.runoob.com/tags/canvas-shadowblur.html) | 设置或返回用于阴影的模糊级别。             |
| [shadowOffsetX](https://www.runoob.com/tags/canvas-shadowoffsetx.html) | 设置或返回阴影与形状的水平距离。           |
| [shadowOffsetY](https://www.runoob.com/tags/canvas-shadowoffsety.html) | 设置或返回阴影与形状的垂直距离。           |



| 方法                                                         | 描述                                      |
| :----------------------------------------------------------- | :---------------------------------------- |
| [createLinearGradient()](https://www.runoob.com/tags/canvas-createlineargradient.html) | 创建线性渐变（用在画布内容上）。          |
| [createPattern()](https://www.runoob.com/tags/canvas-createpattern.html) | 在指定的方向上重复指定的元素。            |
| [createRadialGradient()](https://www.runoob.com/tags/canvas-createradialgradient.html) | 创建放射状/环形的渐变（用在画布内容上）。 |
| [addColorStop()](https://www.runoob.com/tags/canvas-addcolorstop.html) | 规定渐变对象中的颜色和停止位置。          |

##### 线条样式

| 属性                                                         | 描述                                       |
| :----------------------------------------------------------- | :----------------------------------------- |
| [lineCap](https://www.runoob.com/tags/canvas-linecap.html)   | 设置或返回线条的结束端点样式。             |
| [lineJoin](https://www.runoob.com/tags/canvas-linejoin.html) | 设置或返回两条线相交时，所创建的拐角类型。 |
| [lineWidth](https://www.runoob.com/tags/canvas-linewidth.html) | 设置或返回当前的线条宽度。                 |
| [miterLimit](https://www.runoob.com/tags/canvas-miterlimit.html) | 设置或返回最大斜接长度。                   |

##### 矩形

| 方法                                                         | 描述                           |
| :----------------------------------------------------------- | :----------------------------- |
| [rect()](https://www.runoob.com/tags/canvas-rect.html)       | 创建矩形。                     |
| [fillRect()](https://www.runoob.com/tags/canvas-fillrect.html) | 绘制"被填充"的矩形。           |
| [strokeRect()](https://www.runoob.com/tags/canvas-strokerect.html) | 绘制矩形（无填充）。           |
| [clearRect()](https://www.runoob.com/tags/canvas-clearrect.html) | 在给定的矩形内清除指定的像素。 |

##### 路径

| 方法                                                         | 描述                                                      |
| :----------------------------------------------------------- | :-------------------------------------------------------- |
| [fill()](https://www.runoob.com/tags/canvas-fill.html)       | 填充当前绘图（路径）。                                    |
| [stroke()](https://www.runoob.com/tags/canvas-stroke.html)   | 绘制已定义的路径。                                        |
| [beginPath()](https://www.runoob.com/tags/canvas-beginpath.html) | 起始一条路径，或重置当前路径。                            |
| [moveTo()](https://www.runoob.com/tags/canvas-moveto.html)   | 把路径移动到画布中的指定点，不创建线条。                  |
| [closePath()](https://www.runoob.com/tags/canvas-closepath.html) | 创建从当前点回到起始点的路径。                            |
| [lineTo()](https://www.runoob.com/tags/canvas-lineto.html)   | 添加一个新点，然后在画布中创建从该点到最后指定点的线条。  |
| [clip()](https://www.runoob.com/tags/canvas-clip.html)       | 从原始画布剪切任意形状和尺寸的区域。                      |
| [quadraticCurveTo()](https://www.runoob.com/tags/canvas-quadraticcurveto.html) | 创建二次贝塞尔曲线。                                      |
| [bezierCurveTo()](https://www.runoob.com/tags/canvas-beziercurveto.html) | 创建三次贝塞尔曲线。                                      |
| [arc()](https://www.runoob.com/tags/canvas-arc.html)         | 创建弧/曲线（用于创建圆形或部分圆）。                     |
| [arcTo()](https://www.runoob.com/tags/canvas-arcto.html)     | 创建两切线之间的弧/曲线。                                 |
| [isPointInPath()](https://www.runoob.com/tags/canvas-ispointinpath.html) | 如果指定的点位于当前路径中，则返回 true，否则返回 false。 |

##### 转换

| 方法                                                         | 描述                                             |
| :----------------------------------------------------------- | :----------------------------------------------- |
| [scale()](https://www.runoob.com/tags/canvas-scale.html)     | 缩放当前绘图至更大或更小。                       |
| [rotate()](https://www.runoob.com/tags/canvas-rotate.html)   | 旋转当前绘图。                                   |
| [translate()](https://www.runoob.com/tags/canvas-translate.html) | 重新映射画布上的 (0,0) 位置。                    |
| [transform()](https://www.runoob.com/tags/canvas-transform.html) | 替换绘图的当前转换矩阵。                         |
| [setTransform()](https://www.runoob.com/tags/canvas-settransform.html) | 将当前转换重置为单位矩阵。然后运行 transform()。 |

##### 文本

| 属性                                                         | 描述                                       |
| :----------------------------------------------------------- | :----------------------------------------- |
| [font](https://www.runoob.com/tags/canvas-font.html)         | 设置或返回文本内容的当前字体属性。         |
| [textAlign](https://www.runoob.com/tags/canvas-textalign.html) | 设置或返回文本内容的当前对齐方式。         |
| [textBaseline](https://www.runoob.com/tags/canvas-textbaseline.html) | 设置或返回在绘制文本时使用的当前文本基线。 |



| 方法                                                         | 描述                         |
| :----------------------------------------------------------- | :--------------------------- |
| [fillText()](https://www.runoob.com/tags/canvas-filltext.html) | 在画布上绘制"被填充的"文本。 |
| [strokeText()](https://www.runoob.com/tags/canvas-stroketext.html) | 在画布上绘制文本（无填充）。 |
| [measureText()](https://www.runoob.com/tags/canvas-measuretext.html) | 返回包含指定文本宽度的对象。 |

##### 图像绘制

| 方法                                                         | 描述                           |
| :----------------------------------------------------------- | :----------------------------- |
| [drawImage()](https://www.runoob.com/tags/canvas-drawimage.html) | 向画布上绘制图像、画布或视频。 |

##### 像素操作

| 属性                                                         | 描述                                                  |
| :----------------------------------------------------------- | :---------------------------------------------------- |
| [width](https://www.runoob.com/tags/canvas-imagedata-width.html) | 返回 ImageData 对象的宽度。                           |
| [height](https://www.runoob.com/tags/canvas-imagedata-height.html) | 返回 ImageData 对象的高度。                           |
| [data](https://www.runoob.com/tags/canvas-imagedata-data.html) | 返回一个对象，其包含指定的 ImageData 对象的图像数据。 |



| 方法                                                         | 描述                                                        |
| :----------------------------------------------------------- | :---------------------------------------------------------- |
| [createImageData()](https://www.runoob.com/tags/canvas-createimagedata.html) | 创建新的、空白的 ImageData 对象。                           |
| [getImageData()](https://www.runoob.com/tags/canvas-getimagedata.html) | 返回 ImageData 对象，该对象为画布上指定的矩形复制像素数据。 |
| [putImageData()](https://www.runoob.com/tags/canvas-putimagedata.html) | 把图像数据（从指定的 ImageData 对象）放回画布上。           |

##### 合成

| 属性                                                         | 描述                                     |
| :----------------------------------------------------------- | :--------------------------------------- |
| [globalAlpha](https://www.runoob.com/tags/canvas-globalalpha.html) | 设置或返回绘图的当前 alpha 或透明值。    |
| [globalCompositeOperation](https://www.runoob.com/tags/canvas-globalcompositeoperation.html) | 设置或返回新图像如何绘制到已有的图像上。 |

##### 其他

| 方法          | 描述                             |
| :------------ | :------------------------------- |
| save()        | 保存当前环境的状态。             |
| restore()     | 返回之前保存过的路径状态和属性。 |
| createEvent() |                                  |
| getContext()  |                                  |
| toDataURL()   |                                  |

Canvas教程：[https://developer.mozilla.org/zh-CN/docs/Web/API/Canvas_API/Tutorial](https://developer.mozilla.org/zh-CN/docs/Web/API/Canvas_API/Tutorial)

### DOM：

**XQuery： 基于 XML 的用于查询 XML 数据的语言。**



## JavaScript 小笔记：

### JS中let、var、const的区别：

JS中作用域有：全局作用域、函数作用域。没有块作用域的概念。ECMAScript 6(简称ES6)中新增了块级作用域。块作用域由 { } 包括，if语句和for语句里面的{ }也属于块作用域。



#### Var：

var定义的变量可以修改，如果不初始化会输出undefined，不会报错。
``` js
var a = 1; 
// var a;//不会报错 
console.log('函数外var定义a：' + a); 	//可以输出a=1 
function change(){
    a = 4; 
    console.log('函数内var定义a：' + a);//可以输出a=4 
} 
change();
console.log('函数调用后var定义a为函数内部修改值：' + a);//可以输出a=4


//var 声明全局变量，换句话理解就是，声明在for循环中的变量，跳出for循环同样可以使用。声明在for循环内部的sum，跳出for循环一样可以使用，不会报错正常弹出结果
for(var i=0;i<=1000;i++){ 
    var sum=0;  
    sum+=i; 
}
alert(sum);
```


#### Let:

同一个变量，不可在声明之前调用，必须先定义再使用，否则会报错，循环体中可以用let

let是块级作用域，函数内部使用let定义后，对函数外部无影响。并且let不能定义同名变量，否则会报错。

``` js
let c = 3; 
console.log('函数外let定义c：' + c);//输出c=3 
function change(){ 
    let c = 6;
    console.log('函数内let定义c：' + c);//输出c=6
}  
change();
console.log('函数调用后let定义c不受函数内部定义影响：' + c);//输出c=3
```


#### Const:

const：用于声明常量，也具有块级作用域 ，也可声明块级。const定义的变量不可以修改，而且必须初始化。
``` js
const b = 2;//正确 
// const b;//错误，必须初始化 
console.log('函数外const定义b：' + b);//有输出值 
// b = 5; 
// console.log('函数外修改const定义b：' + b);//无法输出

//它和let一样，也不能重复定义同一个变量，const一旦定义，无法修改.let和const属于局部变量，不会出现变量提升的情况，全局定义的let和const变量，不属于顶层变量，不属于window的属性
```


### CSS一些写法：

width:100px !important;   //不使用引入的样式

**CSS函数 参考手册：**

| 函数                                                         | 描述                                                         | CSS 版本 |
| ------------------------------------------------------------ | ------------------------------------------------------------ | -------- |
| [attr()](https://www.runoob.com/cssref/func-attr.html)       | 返回选择元素的属性值。                                       | 2        |
| [calc()](https://www.runoob.com/cssref/func-calc.html)       | 允许计算 CSS 的属性值，比如动态计算长度值。                  | 3        |
| [cubic-bezier()](https://www.runoob.com/cssref/func-cubic-bezier.html) | 定义了一个贝塞尔曲线(Cubic Bezier)。                         | 3        |
| [hsl()](https://www.runoob.com/cssref/func-hsl.html)         | 使用色相、饱和度、亮度来定义颜色。                           | 3        |
| [hsla()](https://www.runoob.com/cssref/func-hsla.html)       | 使用色相、饱和度、亮度、透明度来定义颜色。                   | 3        |
| [linear-gradient()](https://www.runoob.com/cssref/func-linear-gradient.html) | 创建一个线性渐变的图像                                       | 3        |
| [radial-gradient()](https://www.runoob.com/cssref/func-radial-gradient.html) | 用径向渐变创建图像。                                         | 3        |
| [repeating-linear-gradient()](https://www.runoob.com/cssref/func-repeating-linear-gradient.html) | 用重复的线性渐变创建图像。                                   | 3        |
| [repeating-radial-gradient()](https://www.runoob.com/cssref/func-repeating-radial-gradient.html) | 类似 radial-gradient()，用重复的径向渐变创建图像。           | 3        |
| [rgb()](https://www.runoob.com/cssref/func-rgb-css.html)     | 使用红(R)、绿(G)、蓝(B)三个颜色的叠加来生成各式各样的颜色。  | 2        |
| [rgba()](https://www.runoob.com/cssref/func-rgba.html)       | 使用红(R)、绿(G)、蓝(B)、透明度(A)的叠加来生成各式各样的颜色。 | 3        |
| [var()](https://www.runoob.com/cssref/func-var.html)         | 用于插入自定义的属性值。                                     | 3        |

## HTML转义字符：

| 特殊字符  |   描述    | 实体名称 |
| :-------: | :-------: | :------: |
| 【空格】  |   空格    |  &nbsp;  |
| 【Tab键】 |   Tab键   |  &emsp;  |
|     >     |  大于号   |   &gt;   |
|     <     |  小于号   |   &lt;   |
|    《     | 书名号-前 | &laquo;  |
|    》     | 书名号-后 | &raquo;  |
|     &     |   和号    |  &amp;   |
|     "     |   引号    |  &quot;  |
|     '     |  单引号   |  &apos;  |
|    ￥     |  人民币   |  &yen;   |
|     $     | 美元符号  |  &#36;   |
|     %     |  百分号   |  &#37;   |
|     ©     |   版权    |  &copy;  |
|     ®     | 注册商标  |  &reg;   |
|     ™     |   商标    | &trade;  |
|     x     |   乘号    | &times;  |
|     ÷     |   除号    | &divide; |
|     ±     |  正负号   | &plusmn; |
|     °     |  摄氏度   |  &deg;   |
|     ²     |   平方    |  &sup2;  |
|     ³     |   立方    |  &sup3;  |



**鱼皮整理的 前端学习路线：**



<img src="img/learning_route.png"/>





### Snow moon 分享的前端学习路线

[https://objtube.github.io/front-end-roadmap/#/](https://objtube.github.io/front-end-roadmap/#/)



## ES6 参考文档

90%的前端都会使用ES6来简化代码[https://mp.weixin.qq.com/s/ty5dTSwHLVpkAJYT4InOSg](https://mp.weixin.qq.com/s/ty5dTSwHLVpkAJYT4InOSg)