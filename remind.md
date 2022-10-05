# 一、html元素

## 1、元素的分类

html可分为块级、行内、行内块元素

**块级标签**：默认独占一行，可以设置它的宽高；如果不设置，宽度会默认为它的父级元素的宽度。

**行内标签**：默认由宽高由其内容撑开，直接设置宽高无效；一行可以放多个行内标签；

　　　　   通常块级标签内可以放置行内标签，但行内标签里不能放块级标签

　　　　（<a>标签除外，a标签虽然是行内标签，但是它可以放块级标签，但是a标签内不能放a标签）

**行内块元素**：行内块有块级标签和行内标签的特性，它可以设置宽高，也可以一行显示多个。

　　　　　   不过行内块会在标签前面留一个小缝隙。

**去除方法**：

1.可以将上一个元素的闭合标签与行内块元素的开始标签写在同一行去除

2.将其父元素的字体大小改为0（font-size: 0），子元素单独设置字体大小

3.将本元素变成浮动（float:left 或者 float:right）

4.将其父元素变成弹性盒子（在css里面给它的父盒子加display:flex）

![66494316417](C:\Users\86131\AppData\Local\Temp\1664943164179.png)

行内块元素：img、input、button、textarea、select一般有内在尺寸，所以具有width和height，可以设定。

**img**标签是图片标签，src属性是必填的属性，写明图片的路径。

 alt属性是替换文本，指当文本不能正常显示的时候，网页上会显示一个裂开的图标，旁边显示“替换文本”这几个字，把鼠标放在图片上时，会显示“提示文本”这几个字

**<input>**标签是输入表单元素，是个单标签，里面的type属性是必填属性

<input type="属性值">

**type属性值**　　　　　　　　**描述**

button　　　　　　　　　　 普通的按钮

checkbox　　　　　　　　　复选框

radio　　　　　　　　　　　单选框（需要单选框用同一个name值，才能生效，不然单选框也能多选）

password　　　　　　　　　密码框

text　　　　　　　　　　  　文本框

reset　　　　　　　　　　　重置按钮

submit　　　　　       　　　 提交按钮

input除了type属性外，还有其他属性

**属性　　　　　　属性值　　　　描述**

name　　　     　自定义　　　　自己取一个input的名称（注意：同一组的单选框或复选框要设置相同的name值）

value　　　　　 自定义　　　　 自己去一个input值

checked　　　　checked　　　 加上这个属性后，该选项会默认选中，主要针对单选框和复选框

maxlength　　　 正整数　　　　规定输入文字的最大字数（用的少）

**<button>...</button>**　　　　普通按钮，和<input type="button">基本一样，不过是从单标签变成双标签

当然，无论行内元素还是块元素亦或者行内块元素，都不是完全固定的，他们之间是可以相互转换的，只需要在CSS里面加上：　　　　

display: inline; 　　　　 转换为行内元素

display: inline-block;　  转换为行内块元素

display: block;　　　　转换为块元素

## 2、html5新特性

![66494361419](C:\Users\86131\AppData\Local\Temp\1664943614194.png)

# 二、盒模型

## 1、什么是盒模型？ 

**盒模型是css布局的基石，它规定了网页元素如何显示以及元素间相互关系。css定义所有的元素都可以拥有像盒子一样的外形和平面空间。即都包含内容区content、补白（填充）padding、边框border、边界(外边距)margin,这就是盒模型。**

![img](https://img-blog.csdnimg.cn/20200223144626685.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1Byb2dyYW1taW5nV2hpdGU=,size_16,color_FFFFFF,t_70)

## 2、盒模型的分类

盒模型一共分为两种：标准盒模型和怪异盒模型，**只要在代码头部添加了doctype声明，浏览器就会默认该页面为标准盒模型**。

也可以通过box-sizing属性设置。
box-sizing:content-box(标准盒模型)\border-box(怪异盒模型)

1、标准盒模型：(w3c盒子模型)是一般网页经常使用的一种。
一个盒子的总宽度= width + padding(左右) + border(左右)+ margin(左右)

 2、怪异盒模型：(ie盒子模型)主要表现在IE内核的浏览器	
当不对doctype进行定义时，会触发怪异模式。
一个盒子的总宽度= width + margin(左右)
（即width已经包含了padding和border值）

![66494487481](C:\Users\86131\AppData\Local\Temp\1664944874818.png)

# 三、BFC

## 1、什么是BFC

BFC全称Block Formatting Context,名为块级格式化上下文。
简单来说BFC是一个完全独立的空间（布局环境），让空间里的子元素不会影响到外面的布局。
如果一个元素符合触发BFC的条件，则BFC中的元素布局不受外部影响。

## 2、BFC创建

- 根元素或包含根元素的元素
- 浮动元素 float ＝ left | right 或 inherit**（≠ none）**
- 绝对定位元素 position ＝ absolute 或 fixed
- display ＝ inline-block | flex | inline-flex | table-cell 或 table-caption
- overflow ＝ hidden | auto 或 scroll **(≠ visible)**

## 3、BFC的特性是什么

- BFC 是一个独立的容器，容器内子元素不会影响容器外的元素。反之亦如此。
- 盒子从顶端开始垂直地一个接一个地排列，盒子之间垂直的间距是由 margin 决定的。
- 在同一个 BFC 中，两个相邻的块级盒子的垂直外边距会发生重叠。
- BFC 区域不会和 float box 发生重叠。
- BFC 能够识别并包含浮动元素，当计算其区域的高度时，浮动元素也可以参与计算了。

## 4、BFC的作用是什么

1、清除浮动

- 浮动元素会脱离文档流(绝对定位元素也会脱离文档流)，导致无法计算准确的高度，这种问题称为**高度塌陷**。
- 解决高度塌陷问题的前提是能够识别并包含浮动元素，也就是**清除浮动**。

2、导致外边距坍陷

**相邻**的两个盒子（可能是兄弟关系也可能是祖先关系）的垂直边距相遇时， 它们将形成一个外边距。这个外边距的高度等于两个发生折叠的外边距的高度中的**较大者**。

3、避免外边距折叠

**外边距折叠（Margin collapsing）只会发生在属于同一BFC的块级元素之间**。如果它们属于不同的 BFC，它们之间的外边距则不会折叠。所以通过**创建一个不同的 BFC** ，就可以避免外边距折叠。

# 四、css优先级

## 1、CSS选择器的优先级关系是:

继承 < 通配符选择器 < 标签选择器 < 类选择器 < id选择器 < 行内（内联）样式 < !important

> 内联 > ID选择器 > 类选择器 > 标签选择器。

优先级是由 `A` 、`B`、`C`、`D` 的值来决定的，其中它们的值计算规则如下：

1. 如果存在内联样式，那么 `A = 1`, 否则 `A = 0`;
2. `B` 的值等于 `ID选择器` 出现的次数;
3. `C` 的值等于 `类选择器` 和 `属性选择器` 和 `伪类` 出现的总次数;
4. `D` 的值等于 `标签选择器` 和 `伪元素` 出现的总次数 。

 **比较规则是: 从左往右依次进行比较 ，较大者胜出，如果相等，则继续往右移动一位进行比较 。如果4位全部相等，则后面的会覆盖前面的**

## 2、优先级的特殊情况

经过上面的优先级计算规则，我们可以知道内联样式的优先级是最高的，但是外部样式有没有什么办法覆盖内联样式呢？有的，那就要 `!important` 出马了。因为一般情况下，很少会使用内联样式 ，所以 `!important` 也很少会用到！如果不是为了要覆盖内联样式，建议尽量不要使用 `!important` 。

 /* !important不要给继承的添加，自己有样式无法继承父级样式 */

# 五、清除浮动

## 1、为什么要清除浮动

由于浮动元素不再占用原文档流的位置，所以它会对后面的元素排版产生影响，为了解决这些问题，此时就需要在该元素中清除浮动。准确地说，并不是清除浮动，而是清除浮动后造成的影响。

清除浮动的本质:主要为了解决父级元素因为子级浮动引起内部高度为0的问题。

这句话再解释下就是在标准流下面一个父p没有设置高度属性,那么它的高度就会被子元素的高度撑开。但是如果这个父p中的子元素是浮动的话，如果父p下面再有一个兄弟p，那么这个兄弟p就会遮挡这个父元素。这个现象也叫浮动溢出。

## 2、清除浮动的方法

1、利用clear样式

~~~css
.textDiv {
    color: blue;
    border: 2px solid blue;

    clear: left;
}
~~~

~~~html
<div class="topDiv">
    <div class="textDiv">...</div>
    <div class="floatDiv">float left</div>
</div>
<div class="bottomDiv">...</div>
~~~



2、父元素结束标签之前插入清除浮动的块级元素(额外标签法)

HTML结构如下，在有浮动的父级元素的末尾插入了一个没有内容的块级元素div：

~~~css
      .clearfix {
            /* 清除左右两侧浮动的影响 */
            clear:both;
        }
~~~

~~~html
<!-- 父子级标签，子级浮动，父级没有高度，后面的标准流盒子会受影响，显示到上面的位置 -->
    <div class="top">
        <div class="left"></div>
        <div class="right"></div>
        <div class="clearfix"></div>
    </div>
    <div class="bottom"></div>
~~~

3、 利用伪元素（clearfix）(单伪元素标签法)

~~~css
/* 单伪元素清除浮动 和 额外标签法原理是一样的 */
        .clearfix::after {
            content: '';

            /* 伪元素添加的标签是行内的，要求块 */
            display: block;
            clear: both;

            /* 补充代码：网页中看不到伪元素 (无影响)*/
            height: 0;
            visibility: hidden;
        }
~~~

~~~html
<!-- 父子级标签，子级浮动，父级没有高度，后面的标准流盒子会受影响，显示到上面的位置 -->
    <div class="top clearfix">
        <div class="left"></div>
        <div class="right"></div>
        <!-- 通过css 添加标签 -->
    </div>
    <div class="bottom"></div>
~~~

4、双伪元素标签法

~~~css
/* .clearfix::before 作用：解决外边距塌陷问题
 外边距塌陷：父子标签，都是块级，子级加margin会影响父级的位置 */
        /* 清除浮动 */
        .clearfix::before,
        .clearfix::after {
            content: '';
            display: table;
        }

        /* 真正清除浮动的标签 */
        .clearfix::after {
            clear: both;
        }
~~~

5、利用overflow清除浮动

~~~css
.topDiv {
    width: 500px;
    padding: 4px;
    border: 2px solid black;

    // 区别在这里
    overflow: auto;
}
~~~

~~~html
<div class="topDiv">
    <div class="floatDiv">float left</div>
    <div class="textDiv">...</div>
</div>
<div class="bottomDiv">...</div>
~~~

# 六、css实现水平垂直居中的方法

## 1、实现元素的水平垂直居中方法

1、absolute + 负margin

绝对定位的百分比是相对于父元素的宽高，通过这个特性可以让子元素的居中显示，但绝对定位是基于子元素的左上角，期望的效果是子元素的中心居中显示。

为了修正这个问题，可以借助外边距的负值，负的外边距可以让元素向相反方向定位，通过指定子元素的外边距为子元素宽度一半的负值，就可以让子元素居中了。

~~~css
.wp {
    position: relative;
}
.box {
    position: absolute;;
    top: 50%;
    left: 50%;
    margin-left: -50px;
    margin-top: -50px;
}
~~~

2、absolute + margin auto

这种方式通过设置各个方向的距离都是0，此时再讲margin设为auto，就可以在各个方向上居中了。

这种方法兼容性也很好，缺点是需要知道子元素的宽高。

~~~css
.wp {
    position: relative;
}
.box {
    position: absolute;;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    margin: auto;
}
~~~

3、absolute + calc

这种方式也要求居中元素的宽高必须固定。既然top的百分比是基于元素的左上角，那么在减去宽度的一半就好了。

这种方法兼容性依赖calc的兼容性，缺点是需要知道子元素的宽高。

~~~css
.wp {
    position: relative;
}
.box {
    position: absolute;;
    top: calc(50% - 50px);
    left: calc(50% - 50px);
}
~~~

4、absolute + transform

还是绝对定位，但这个方法不需要子元素固定宽高。

修复绝对定位的问题，还可以使用css3新增的transform，transform的translate属性也可以设置百分比，其是相对于自身的宽和高，所以可以讲translate设置为-50%，就可以做到居中了。

~~~css
.wp {
    position: relative;
}
.box {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
~~~

5、flex

~~~css
.wp {
    display: flex;
    justify-content: center;
    align-items: center;
}
~~~

6、grid

~~~css
.wp {
    display: grid;
}
.box {
    align-self: center;
    justify-self: center;
}
~~~

## 2、实现内容的水平垂直居中

~~~css
.div {
            width: 400px;
            height: 400px;
            background-color: pink;
            /* background-color: green; */
            text-align: center;
            /* 文字是单行的 */
            /* 垂直居中技巧：设置行高属性值 = 自身高度属性值 */
            line-height: 400px;
            font-size: 50px;
        }
~~~

# 七、flex布局

## 1、Flex 布局是什么

Flex 是 Flexible Box 的缩写，意为"弹性布局"，用来为盒状模型提供最大的灵活性。

任何一个容器都可以指定为 Flex 布局。

注意，设为 Flex 布局以后，子元素的`float`、`clear`和`vertical-align`属性将失效。

## 2、基本概念

采用 Flex 布局的元素，称为 Flex 容器（flex container），简称"容器"。它的所有子元素自动成为容器成员，称为 Flex 项目（flex item），简称"项目"。

![66494835042](C:\Users\86131\AppData\Local\Temp\1664948350427.png)

容器默认存在两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）。主轴的开始位置（与边框的交叉点）叫做`main start`，结束位置叫做`main end`；交叉轴的开始位置叫做`cross start`，结束位置叫做`cross end`。

项目默认沿主轴排列。单个项目占据的主轴空间叫做`main size`，占据的交叉轴空间叫做`cross size`。

## 3、flex的属性

- flex-direction
- flex-wrap
- flex-flow
- justify-content
- align-items
- align-content

1、`flex-direction`属性决定主轴的方向（即项目的排列方向）。

- `row`（默认值）：主轴为水平方向，起点在左端。
- `row-reverse`：主轴为水平方向，起点在右端。
- `column`：主轴为垂直方向，起点在上沿。
- `column-reverse`：主轴为垂直方向，起点在下沿。

2、`flex-wrap`属性定义，如果一条轴线排不下，如何换行。

（1）`nowrap`（默认）：不换行。

（2）`wrap`：换行，第一行在上方。

（3）`wrap-reverse`：换行，第一行在下方。

3、`flex-flow`属性是`flex-direction`属性和`flex-wrap`属性的简写形式，默认值为`row nowrap`。

4、`justify-content`属性定义了项目在主轴上的对齐方式。

- `flex-start`（默认值）：左对齐
- `flex-end`：右对齐
- `center`： 居中
- `space-between`：两端对齐，项目之间的间隔都相等。
- `space-around`：每个项目两侧的间隔相等。所以，项目之间的间隔比项目与边框的间隔大一倍。

5、`align-items`属性定义项目在交叉轴上如何对齐。

- `flex-start`：交叉轴的起点对齐。
- `flex-end`：交叉轴的终点对齐。
- `center`：交叉轴的中点对齐。
- `baseline`: 项目的第一行文字的基线对齐。
- `stretch`（默认值）：如果项目未设置高度或设为auto，将占满整个容器的高度。

6、`align-content`属性定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。

- `flex-start`：与交叉轴的起点对齐。
- `flex-end`：与交叉轴的终点对齐。
- `center`：与交叉轴的中点对齐。
- `space-between`：与交叉轴两端对齐，轴线之间的间隔平均分布。
- `space-around`：每根轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间隔大一倍。
- `stretch`（默认值）：轴线占满整个交叉轴。

# 八、rem适配

## 1、什么是rem

`rem(font size of the root element)`,是 css3 中新增的一个大小单位，即相对于根元素 font-size 值的大小。

思路就是动态的计算出页面的fontsize从而改变rem的大小。

## 2、思路

首先拿 1920 * 1080 的标准屏幕大小为例。将屏幕分为`10`份，先计算`rem的基准值:` 1920 / 10 = 192 ,然后把所有元素的长，宽，位置，字体大小等原来的 px 单位全部转换成 rem, 网页加载后，用 js 去计算当前浏览器的宽度，并设置 html 的 font-size 为 (`当前浏览器窗口宽度 / 10`),这样的话10rem就刚好等于浏览器窗口的宽度。也就可以保证100%宽度，等比例缩放设计稿的页面了。

两件事：

1. 获得 rem 的基准值。这边默认设置容器宽度为1920 * 1080，然后用1920 / 192 来计算rem的值
2. 页面内写一段js代码，动态的计算`html根元素的font-size`
