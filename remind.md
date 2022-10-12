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

### 1、语义化标签

<header><header/> 定义文档的头部

 <nav><nav/> 定义导航链接

 <section><section/> 定义文档中的节，段落，

 <article><article/> 定义页面独立内容区域

 <aside><aside/> 定义页面的侧边栏内容

 <detailes><detailes/> 定义文档某部分细节

<summary><summary/> 标签包含了details元素的标题

<dialog><dialog/> 定义对话框，提示框

![66494361419](C:\Users\86131\AppData\Local\Temp\1664943614194.png)

### 2、新增Input[表单](https://so.csdn.net/so/search?q=%E8%A1%A8%E5%8D%95&spm=1001.2101.3001.7020)的类型、和属性

- ## 类型

~~~html
<!-- 输入格式也限制为不同模式 -->
            <!-- 输入必须为邮箱类型 -->
            <li>email邮箱：<input type="email"></li>
            <!-- 输入必须为网址类型 -->
            <li>url网络地址：<input type="url"></li>
            <!-- 输入必须为日期类型 -->
            <li>date日期：<input type="date"></li>
            <!-- 输入必须为时间类型 -->
            <li>time时间：<input type="time"></li>
            <!-- 输入必须为数值类型 -->
            <li>number数量：<input type="number" min="5" max="20"></li>
            <!-- 输入必须为数值类型 -->
            <li>tel电话号码：<input type="tel"></li>
            <li>color颜色：<input type="color"></li>
            <li>周/年：<input type="week"></li>
            <li>月/年：<input type="month"></li>
            <li>范围：<input type="range"></li>
~~~

- ## 属性

~~~html
<!-- 新增表单属性 
                required 表单必填属性，
                placeholder 提示文本 
                autofocus页面加载完成自动聚焦输入框 
                autocomplete 当用户输入信息时显示历史输入信息on/off
                pattern 属性，描述了一个正则表达式用于验证<input> 元素的值
                multiple 规定<input> 元素中可选择多个值。
                min 和 max 属性，设置元素最小值与最大值。
                step 属性，为输入域规定合法的数字间隔。
                height 和 width 属性，用于 image 类型的 <input> 标签的图像高度和宽度。
            -->
            <li>search搜索框：<input type="search" required="required" placeholder="请输入文字" autofocus='autofocus' autocomplete="on"></li>
            <li><input type="submit" value="提交"></li>
            <!-- multiple 提交多文件 -->
            <li><input type="file" value="提交" multiple="multiple"></li>
~~~

### 3、audio、video[音频](https://so.csdn.net/so/search?q=%E9%9F%B3%E9%A2%91&spm=1001.2101.3001.7020)和视频

~~~html
<!-- 
        src 文件路径/url
        autoplay 是否自动播放，
        controls 播放控件， 
        mute 静音播放，
        宽度、高度，
        loop 是否循环播放，
        poster 预加载图片...... -->
    <h1>多媒体音频标签audio</h1><br>
    <audio src="关羽.mp3" autoplay = "autoplay" controls = "controls" muted = "muted" width = "700px" height="350px" poster="3.jpg"></audio>
    <audio autoplay>
        <source src="关羽.mp3" type="audio/mpeg">
        <source src="关羽.ogg" type="audio/ogg">
        <source src="关羽.wav" type="audio/wav">
    </audio>
~~~

### 4、[Canvas](https://so.csdn.net/so/search?q=Canvas&spm=1001.2101.3001.7020)绘图

1、Canvas的定义

<canvas> 标签只是图形容器，您必须使用脚本来绘制图形。你可以通过多种方法使用 canvas 绘制路径,盒、圆、字符以及添加图像。一个画布在网页中是一个矩形框，通过 <canvas> 元素来绘制。

**注意:** 默认情况下 <canvas> 元素没有边框和内容。

<canvas>简单实例如下:

~~~html
<canvas id="myCanvas" width="200" height="100"></canvas>
~~~

- id 是canvas元素的标识；
- height是canvas画布的高度，单位为像素；
- width是canvas画布的宽度，单位为像素。

2、使用JavaScript获取网页中的Canvas对象

获取对象的方法：**document.getElementById(对象id)**

获取canvas对象的2D绘图上下文：**getContext（“2d”)**

（1）绘制直线

- 调用beginPath()方法，指示开始绘图路径： **ctx.beginPath()**;
- 调用moveTo()方法将坐标移至直线起点： **ctx.moveTo(x,y)**;
- 调用lineTo()方法绘制直线： **ctx.lineTo(x,y)**;
- 调用stroke()方法，绘制图形的边界轮廓： **ctx.stroke()**;
- 调用closePath()方法，指示闭合绘图路径: **ctx.closePath()**;

（2）绘制矩形

绘制矩形：rect(x,y,width,height)； 

绘制矩形边框：strokeRect(x, y, width, height);

绘制填充矩形：fillRect(x, y, width, height);

擦除指定矩形区域：clearRect(x, y, width, height);

- x:矩形左上角的X坐标；
- y:矩形左上角的y坐标；
- width:矩形的宽度；
- height:矩形的高度

（3）绘制圆弧

arc(centerx,centery,radius,startAngle,endAngle,antiClockwise);

- centerx,centery    圆弧中心点坐标
- Radius 半径
- startAngle  起始弧度
- endAngle  终止弧度
- antiClockwise  是否按逆时针方向绘图，    是一个可选参数，默认为false（即顺时针方向绘图）
- 弧度 = 角度* ( Math.PI / 180 )

（4）填充和描边

1.描边

strokeStyle指定描边颜色（三种颜色方式均可）

lineWidth指定描边宽度（像素为单位）

2.填充

fillStyle指定填充颜色（三种颜色方式均可）

### 5、[SVG](https://so.csdn.net/so/search?q=SVG&spm=1001.2101.3001.7020)绘图

- SVG 指可伸缩矢量图形 (Scalable Vector Graphics)
- SVG 用于定义用于网络的基于矢量的图形
- SVG 使用 XML 格式定义图形
- SVG 图像在放大或改变尺寸的情况下其图形质量不会有损失
- SVG 是万维网联盟的标准   


- SVG 图像可通过文本编辑器来创建和修改
- SVG 图像可被搜索、索引、脚本化或压缩
- SVG 是可伸缩的
- SVG 图像可在任何的分辨率下被高质量地打印
- SVG 可在图像质量不下降的情况下被放大

### 6、地理定位

### 7、拖拽[API]

拖放是一种常见的特性，即抓取对象以后拖到另一个位置。

在 HTML5 中，拖放是标准的一部分，任何元素都能够拖放。

首先，为了使元素可拖动，把 draggable 属性设置为 true ：

<img draggable="true">

在上面的例子中，ondragstart 属性调用了一个函数，drag(event)，它规定了被拖动的数据。

dataTransfer.setData() 方法设置被拖数据的数据类型和值：

~~~javascript
function drag(event)
{
    event.dataTransfer.setData("Text",event.target.id);
}
~~~

ondragover 事件规定在何处放置被拖动的数据。

默认地，无法将数据/元素放置到其他元素中。如果需要设置允许放置，我们必须阻止对元素的默认处理方式。

这要通过调用 ondragover 事件的 event.preventDefault() 方法：

event.preventDefault()

当放置被拖数据时，会发生 drop 事件。

在上面的例子中，ondrop 属性调用了一个函数，drop(event)：

```javascript
function drop(event)
{
    event.preventDefault();
    var data=event.dataTransfer.getData("Text");
    event.target.appendChild(document.getElementById(data));
}
```

- 调用 preventDefault() 来避免浏览器对数据的默认处理（drop 事件的默认行为是以链接形式打开）
- 通过 dataTransfer.getData("Text") 方法获得被拖的数据。该方法将返回在 setData() 方法中设置为相同类型的任何数据。
- 被拖数据是被拖元素的 id ("drag1")
- 把被拖元素追加到放置元素（目标元素）中

### 8、WebStorage（web存储）

使用HTML5可以在本地存储用户的浏览数据。早些时候本地存储使用的是cookies。cookie只有4kb大小，它是一种纯文本文件每次发起http请求都会携带cookie，而且cookies有安全问题，如果cookie被拦截了，那就可获得session的所有信息，只有转发cookie就能达到目的。

LocalStorage和SessionStorage都是HTML5提出的存储方案。大小一般为5MB，可以存储更多信息。均受到同源策略的限制。

SessionStorage 主要用于临时保存同一窗口的数据，刷新不会删除，，但是页面关闭或者窗口关闭，SessionStorage就会被清除。

LocalStorage 主要用于长期保存数据，可以在同一浏览器不同窗口使用，永久存储，除非手动删除，不然不会清除。

HTML5还提供了相应的操作webStorage 的 API：

setItem(key,value)        保存数据

getItem(key)                读取数据

removeItem(key)        删除单个数据

clear()                        清除所有数据

key(index)                获取某个索引的key

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

1、容器上的属性

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

2、项目上的属性

- `order`
- `flex-grow`
- `flex-shrink`
- `flex-basis`
- `flex`
- `align-self`

1 、order属性

`order`属性定义项目的排列顺序。数值越小，排列越靠前，默认为0。

> ```css
> .item {
>   order: <integer>;
> }
> ```

2、 flex-grow属性

`flex-grow`属性定义项目的放大比例，默认为`0`，即如果存在剩余空间，也不放大。

> ```css
> .item {
>   flex-grow: <number>; /* default 0 */
> }
> ```

3 、flex-shrink属性

`flex-shrink`属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。

> ```css
> .item {
>   flex-shrink: <number>; /* default 1 */
> }
> ```

如果所有项目的`flex-shrink`属性都为1，当空间不足时，都将等比例缩小。如果一个项目的`flex-shrink`属性为0，其他项目都为1，则空间不足时，前者不缩小。

负值对该属性无效。

4、flex-basis属性

`flex-basis`属性定义了在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为`auto`，即项目的本来大小。

> ```css
> .item {
>   flex-basis: <length> | auto; /* default auto */
> }
> ```

它可以设为跟`width`或`height`属性一样的值（比如350px），则项目将占据固定空间。

5 、flex属性

`flex`属性是`flex-grow`, `flex-shrink` 和 `flex-basis`的简写，默认值为`0 1 auto`。后两个属性可选。

> ```css
> .item {
>   flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
> }
> ```

该属性有两个快捷值：`auto` (`1 1 auto`) 和 none (`0 0 auto`)。

建议优先使用这个属性，而不是单独写三个分离的属性，因为浏览器会推算相关值。

6 、align-self属性

`align-self`属性允许单个项目有与其他项目不一样的对齐方式，可覆盖`align-items`属性。默认值为`auto`，表示继承父元素的`align-items`属性，如果没有父元素，则等同于`stretch`。

> ```css
> .item {
>   align-self: auto | flex-start | flex-end | center | baseline | stretch;
> }
> ```

## 4、实现三点分布、3个子div实现一个对角线布局

~~~css
.wrap-box {
    width: 500px;
    height: 500px;
    overflow: hidden;
    background-color: green;
    display: flex;
    justify-content: space-between;
}
 .wrap-box .item-1,
  .wrap-box .item-2,
  .wrap-box .item-3 {
    width: 100px;
    height: 100px;
    background-color: red;
}
.wrap-box .item-2 {
  align-self: center; // 垂直居中
}
.wrap-box .item-3 {
  align-self: flex-end; // 靠右
}
~~~

# 八、rem适配

## 1、什么是rem

`rem(font size of the root element)`,是 css3 中新增的一个大小单位，即相对于根元素 font-size 值的大小。

思路就是动态的计算出页面的fontsize从而改变rem的大小。

## 2、思路

首先拿 1920 * 1080 的标准屏幕大小为例。将屏幕分为`10`份，先计算`rem的基准值:` 1920 / 10 = 192 ,然后把所有元素的长，宽，位置，字体大小等原来的 px 单位全部转换成 rem, 网页加载后，用 js 去计算当前浏览器的宽度，并设置 html 的 font-size 为 (`当前浏览器窗口宽度 / 10`),这样的话10rem就刚好等于浏览器窗口的宽度。也就可以保证100%宽度，等比例缩放设计稿的页面了。

两件事：

1. 获得 rem 的基准值。这边默认设置容器宽度为1920 * 1080，然后用1920 / 192 来计算rem的值
2. 页面内写一段js代码，动态的计算`html根元素的font-size`

# 九、src和href的区别

src和href的作用都是用于请求资源。
区别：
**1.请求资源类型不同**
href，超文本引用，用于建立文档与资源的联系，常用的有：link、a。
src，将其所指向的资源下载并应用到当前页面，常见的有script、img。
**2.作用结果不同**
href，用于文档与资源之间确立联系。
src，请求到的资源替换当前内容。
**3.浏览器的解析不同**

1. 当浏览器遇到href会并行下载资源并且不会停止对当前文档的处理。(同时也是为什么建议使用 link 方式加载 CSS，而不是使用 @import 方式)
2. 当浏览器解析到src ，会暂停其他资源的下载和处理，直到将该资源加载或执行完毕。(这也是script标签为什么放在底部而不是头部的原因)

# 十、重绘和回流

## 1、浏览器是如何进行界面渲染的

![66504465481](C:\Users\86131\AppData\Local\Temp\1665044654819.png)

- 解析（Parser）HTML，生成DOM树(DOM Tree)
- 同时解析（Parser） CSS，生成样式规则 (Style Rules)
- 根据DOM树和样式规则，生成渲染树(Render Tree)
- 进行布局 Layout(回流/重排):根据生成的渲染树，得到节点的几何信息（位置，大小）
- 进行绘制 Painting(重绘): 根据计算和获取的信息进行整个页面的绘制
- Display: 展示在页面上

## 2、重绘和回流(重排)

1、回流(重排)
当 Render Tree 中部分或者全部元素的尺寸、结构、布局等发生改变时，浏览器就会重新渲染部分或全部文档的过
程称为 回流。
2、重绘
由于节点(元素)的样式的改变并不影响它在文档流中的位置和文档布局时(比如：color、background-color、
outline等), 称为重绘。
3、重绘不一定引起回流，而回流一定会引起重绘。

## 3、会导致回流（重排）的操作

- 页面的首次刷新
- 浏览器的窗口大小发生改变
- 元素的大小或位置发生改变
- 改变字体的大小
- 内容的变化（如：input框的输入，图片的大小）
- 激活css伪类 （如：:hover）
- 脚本操作DOM（添加或者删除可见的DOM元素）
- 简单理解影响到布局了，就会有回流

## 4、减少页面重绘和回流的方法

1.尽量使用css属性简写:如：用boder代替boder-width，boder-style，boder-color

2.批量修改元素样式 elem.className

3.尽量避免用table布局(table元素一旦触发回流就会导致table里所有的其它元素回流)

4.需要创建多个DOM节点时,使用DocumentFragment创建。

因为:每次创建一个页面就会发生回流，所以采用DocumentFragment批量创建

5.尽量去写css表达式。因为每次调用都会重新计算值(包括加载页面)

# 十一、script标签上使用 defer和 async的区别

defer和 [async](https://so.csdn.net/so/search?q=async&spm=1001.2101.3001.7020)的使用,可以用于提升网页性能。
script标签存在两个属性，defer和async，因此 script标签的使用分为三种情况：

1. `<script src="example.js"></script>`
   没有defer或async属性，浏览器会立即加载并执行相应的脚本。
   不等待后续加载的文档元素，读到就开始加载和执行，此举会阻塞后续文档的加载

2. `<script async src="example.js"></script>`
   有了async属性，表示后续文档的加载和渲染与js脚本的加载和执行是并行进行的，即异步执行；

3. `<script defer src="example.js"></script>`
   有了defer属性，加载后续文档的过程和js脚本的加载是并行进行的(异步)，此时的js脚本仅加载不
   执行, js脚本的执行需要等到文档所有元素解析完成之后，DOMContentLoaded事件触发执行之
   前。
   下图是使用了 defer、async、和未使用时的运行情况对比：![img](https://img-blog.csdnimg.cn/c78314887538458496efc135123874fb.png#pic_center)

   **绿线：HTML的解析时间**

   **蓝线：JS脚本的加载时间**

   **红色：JS脚本的执行时间**

   从图中我们可以明确一下几点：
   1.defer和async在网络加载过程是一致的，都是异步执行的；(放在页面顶部,也不会阻塞页面的加
   载,与页面加载同时进行)
   2.两者的区别,脚本加载完成之后, async是立刻执行, defer会等一等 (等前面的defer脚本执行,等dom的加载)
   所以, js脚本加上 async或 defer,放在头部可以减少网页的下载加载时间,如果不考虑兼容性,可以用于优化页面加载的性能

# 十二、如何实现图片的懒加载

我们经常遇到这样的需求——检测一个元素是否可见或者两个元素是否相交，如

- 图片懒加载——当图片滚动到可见时才进行加载
- 内容无限滚动——也就是用户滚动到接近内容底部时直接加载更多，而无需用户操作翻页，给用户一种网页可以无限滚动的错觉
- 检测广告的曝光情况——为了计算广告收益，需要知道广告元素的曝光情况
- 在用户看见某个区域时执行任务或播放动画

### Element.getBoundingClientRect()

返回一个 DOMRect 对象，其提供了元素的大小及其相对于视口的位置。

缺点：事件[监听](https://so.csdn.net/so/search?q=%E7%9B%91%E5%90%AC&spm=1001.2101.3001.7020)和调用都是在主线程上运行，因此频繁触发、调用，造成浏览器频繁的重绘和回流，给网站带来相当大的卡顿

### Intersection Observer API

window对象上有一个Intersection Observer API，
它会注册一个[回调](https://so.csdn.net/so/search?q=%E5%9B%9E%E8%B0%83&spm=1001.2101.3001.7020)函数，每当被监视的元素进入或者退出另外一个元素时 (或者 viewport )，或者两个元素的相交部分大小发生变化时，该回调方法会被触发执行。这样，我们网站的主线程不需要再为了监听元素相交而辛苦劳作，浏览器会自行优化元素相交管理。

1、创建一个 intersection observer

- 创建一个 IntersectionObserver 对象，并传入相应参数和回调用函数，该回调函数将会在目标 (target) 元素和根 (root) 元素的交集大小超过阈值 (threshold) 规定的大小时候被执行。

~~~javascript
let options = {
  root: document.querySelector('#scrollArea'),
  rootMargin: '0px',
  threshold: 1.0
}
//回调函数只会在元素达到thresholds 规定的阈值时才会执行。
let observer = new IntersectionObserver(callback, options);

~~~

2. 给定一个目标元素进行观察

```javascript
let target = document.querySelector('#listItem');
observer.observe(target);
//unobserve()	停止监听特定目标元素
123
```

请留意，你注册的回调函数将会在主线程中被执行。所以该函数执行速度要尽可能的快。如果有一些耗时的操作需要执行，建议使用 Window.requestIdleCallback() 方法

3. 停止监听特定目标元素

```javascript
observer.unobserve(target);//例如图片懒加载时，加载完后即停止监听该元素
1
```

4. IntersectionObserver对象停止全部监听工作

```javascript
observer.disconnect();
```

# 十三、link和@import的区别

1、从属关系区别

@import是 CSS 提供的语法规则，只有导入[样式表](https://so.csdn.net/so/search?q=%E6%A0%B7%E5%BC%8F%E8%A1%A8&spm=1001.2101.3001.7020)的作用；link是HTML提供的标签，不仅可以加载 CSS 文件，还可以定义 RSS、rel 连接属性等。

2、加载顺序区别

加载页面时，link标签引入的 CSS 被同时加载；@import引入的 CSS 将在页面加载完毕后被加载。

3、兼容性区别

@import是 CSS2.1 才有的语法，故只可在 IE5+ 才能识别；link标签作为 HTML 元素，不存在兼容性问题。

4、DOM可控性区别

可以通过 JS 操作 DOM ，插入link标签来改变样式；由于 DOM 方法是基于文档的，无法使用@import的方式插入样式。

# 十四、对css sprites的理解

## 1、为什么要使用Sprites(精灵图)？

网页通常包含多个图像。这些包括图标，按钮，徽标，相关图片和其他图形。当页面中加载图像时，浏览器向服务器发出HTTP请求。分别加载每个图像需要多次调用HTTP服务器，这可能导致下载时间变慢以及带宽使用率过高。

CSS Sprites会将多个图像组合成一个称为精灵表或拼贴图的单个图像，用户不下载多个文件，而是下载单个文件并通过偏移文件显示必要的图像(或精灵图)。

这样可以减少对服务器的调用、减少呈现网页所需的下载次数，节省带宽并缩短用户端的下载时间，减少网络拥塞。

## 2、如何使用CSS Sprites(精灵图)？

因为CSS Sprites是一张多个图像组合成单个图像，在精灵表中多个图像会被放置在网格状图案里，呈现网状分布。

当需要特定图像(精灵图)时，一般会通过CSS background-images属性引用精灵表，在通过CSS background-position属性对其进行偏移定位得到所需的精灵图，然后以[像素](https://so.csdn.net/so/search?q=%E5%83%8F%E7%B4%A0&spm=1001.2101.3001.7020)为单位定义精灵图的大小。

# 十五、实现两栏布局的方式

一般两栏布局指的是**左边一栏宽度固定，右边一栏宽度自适应**。两栏布局的具体实现有以下几种方式：

## ① 利用浮动

- 利用**浮动**，将左边元素宽度设置为200px，并且设置向左浮动。
- 将右边元素的`margin-left`设置为200px，宽度设置为auto（默认为auto，撑满整个父元素）。

```css
.container {
  height: 100px;
}
.left {
  float: left;
  width: 200px;
  height: 100px;
  background: tomato;
}
.right {
  margin-left: 200px;
  width: auto;
  height: 100px;
  background: gold;
}
```

以下给出html模板：

```html
<div class="container">
     <div class="left"></div>
     <div class="right"></div>
</div>
```

## ② 浮动 + BFC

- 利用**浮动**，左侧元素设置固定大小，并左浮动。
- 右侧元素设置`overflow: hidden`; 这样右边就触发了**BFC**，**BFC**的区域不会与浮动元素发生重叠，所以两侧就不会发生重叠。
- 对BFC不了解的，可以参考[关于BFC的理解](https://blog.csdn.net/weixin_47750287/article/details/124674483?spm=1001.2014.3001.5501)

```css
.left{
     float: left;
     width: 100px;
     height: 200px;
     background: tomato;
 }
 .right{
     overflow: hidden;//触发BFC
     height: 300px;
     background: gold;
 }
```

## ③ 利用flex布局

利用**flex**布局，将左边元素设置为固定宽度200px，将右边的元素设置为flex:1。

```css
.container {
  display: flex;
  height: 100px;
}
.left {
  width: 200px;
  background: tomato;
}
.right {
  flex: 1;
  background: gold;
}
```

## ④ 利用绝对定位

- 利用**绝对定位**，将父级元素设置为**相对定位**。
- 左边元素设置为`absolute`定位，并且固定宽度设置为200px，`left`值设置为0。
- 将右边元素的`left`值设置为左边固定宽度200px，`right`值设置为0。

```css
.container {
    position: relative;
    box-sizing: border-box;
}
.left {
    position: absolute;
    left: 0;
    width: 200px;
    height: 200px;
    background: tomato;
}
.right {
    position: absolute;
    left: 200px;
    right: 0;
    height: 300px;
    background: gold;
} 
```

## ⑤ 利用网格布局

使用**Grid网格布局**实现两栏布局的要点在于列数为2，且首列的宽度根据需要自行设置，第二列使用片段"fr"属性进行自适应即可。
行数不需要指定，每行会根据内容高度进行自适应缩放。

- 现在给类名为`"container"`的盒子添加`"display: grid"`属性，使该盒子成为容器。
- 再给该容器添加`"grid-template-columns: 100px 1fr"`属性，表示第一列宽度始终为100px，第二列的宽度为剩余的所有空间。
- 此时可以看到整个容器的高度因为首列的内容被撑开了，并且右边内容区实现了自适应。

```css
.container {
    display: grid;
    grid-template-columns: 100px 1fr;
    box-sizing: border-box;
}
.left {
    width: 100px;
    height: 200px;
    background: tomato;
}
.right {
    height: 300px;
    background: gold;
}
```

# 十六、响应式布局的概念及原理

## 1、响应式布局的介绍

响应式布局（respond layout）是Ethan Marcotte在2010年5月份提出的一个概念，简而言之，就是**一个网站能够兼容多个终端（pc、手机、平板）**

## 2、**响应式开发的原理**

动态根据当前屏幕的宽度，自动改变页面中盒子的宽度、盒子的显示或隐藏

## 3、设备屏幕的分类

![img](https://img-blog.csdnimg.cn/20191019103716707.png)

## 4、媒体查询

> 响应式原理是：**\*动态根据当前屏幕的宽度，自动改变页面中盒子的宽度、盒子的显示或隐藏***
>
> 所以需要根据不同屏幕的宽度改变样式。
>
> 可以通过css3中新增的媒体查询完成效果。

**媒体查询（Media Query)**：是CSS3新增的方法，可以通过动态查询屏幕的宽度，根据不同的屏幕宽度设置样式是否生效！！

**语法：**

```css
@media screen and (条件) {
    选择器......
}
```

**作用：** 只有当屏幕宽度满足条件时，媒体查询中的选择器才能生效！！！

**注意点：** 媒体查询仅仅只是控制选择器是否生效，不会提升选择器的优先级！！

**条件：**

- `min-width`：样式生效的屏幕最小宽度

  > 只有当屏幕宽度大于等于该宽度时，样式才会生效

```css
/* 样式生效的最小宽为600px——》只有当屏幕宽度大于等于600px时，样式才会生效！！*/
@media screen and (min-width:600px) {
    div {
        width: 400px;
        height: 400px;
        background-color: green;
    }
}
```

- `max-width` ：样式生效的屏幕最大宽度

  > 只有当屏幕宽度小于等于该宽度时，样式才会生效

```css
/* 样式生效的最大宽为800px——》只有当屏幕宽度小于等于800px时，样式才会生效*/
@media screen and (max-width:800px) {
    div {
        width: 400px;
        height: 400px;
        background-color: blue;
    }
}
```

- `width` ：样式生效的宽度

  > 只有当屏幕宽度正好等于该宽度时，样式才会生效

```css
/* 样式只在700px宽度的时候才会生效 */
@media screen and (width:700px) {
    div {
        width: 400px;
        height: 400px;
        background-color: purple;
    }
}
```

**一个媒体查询中可以同时写多个条件，中间通过and连接即可**

```css
/* 样式在 600~800中间生效 */
@media screen and (min-width:600px) and (max-width:800px) {
    div {
        width: 400px;
        height: 400px;
        background-color: orange;
    }
}
```

# 十七、css超出隐藏

## 1、单行超出隐藏

~~~css
div {
  overflow:hidden; //超出的文本隐藏
  text-overflow:ellipsis; //用省略号显示
  white-space:nowrap; //不换行
}
~~~

## 2、多行超出隐藏

```css
div{
  overflow:hidden; 
  text-overflow:ellipsis;
  display:-webkit-box;    //将对象作为弹性伸缩盒子模型显示。
  -webkit-box-orient:vertical;  // 从上到下垂直排列子元素
  -webkit-line-clamp:2; //显示的行数
}
```

## 3、表格中单行超出隐藏

~~~css
table{width:100%;table-layout:fixed;/* 只有定义了表格的布局算法为fixed，下面td的定义才能起作用。 */}
td{
  width:100%;
  word-break:keep-all;   // 不换行
  white-space:nowrap;   // 不换行
  overflow:hidden;
  text-overflow:ellipsis;
}
~~~

# 十八、设置小于12px的字体

CSS的最小尺寸为1px，所以理论上可以将font-size设置为1px，但是实际上如果将font-size属性缩小到12px以下就没有效果了，这是因为浏览器限制了最小字体大小，这只是PC端的浏览器进行的限制，手机端默认没有开启该限制，还是可以直接通过CSS设置最小字体的。

用 transform的scale缩放属性将字体缩放，**实际上并没有改变字体大小，只是将标签缩放了**，这样看起来就小了很多。

~~~css
p {
  font-size: 12px;
  line-height: 36px;
  transform: scale(0.8);//缩放0.8，
}
~~~

# 十九、背景图片的设置

background属性总结：

CSS 背景属性用于定义HTML元素的背景，常用的背景属性用法有以下几种：

## 1.background-color(背景颜色）

```css
div{background-color:red;}
```

## 2.background-image（背景图片） 

```css
div{background-image:url("./img/banner.jpg");}
```

**注**：url小括号里是图片的地址，需要加引号

## 3. background-repeat（背景平铺）

默认情况下，背景图片会从水平和垂直两个方向重复铺满整个区域

| 值        | 作用                                         |
| --------- | -------------------------------------------- |
| repeat    | 默认值，在水平方向和垂直方向都重复（默认值） |
| no-repeat | 不重复背景图像                               |
| repeat-x  | 只有水平位置会重复背景图像                   |
| repeat-y  | 只有垂直方向会重复背景图像                   |

 

## 4.background-attachment（背景图片固定）

**background-attachment**属性定义了元素的背景图片是否固定或随着页面的其余部分滚动，有如下取值：

| 值      | 作用                                                |
| ------- | --------------------------------------------------- |
| scroll  | 背景图片随着页面的滚动而滚动（默认）。              |
| fixed   | 背景图片不会随着页面的滚动而滚动。                  |
| local   | 背景图片会随着元素内容的滚动而滚动。                |
| initial | 设置该属性的默认值。                                |
| inherit | 指定 background-attachment 的设置应该从父元素继承。 |

```css
设置一个固定的背景图片
body
{ 
    background-image:url("./img/picture.jpg");
    background-repeat:no-repeat;
    background-attachment:fixed;
}
```

## 5.background-position（背景图片位置）

background-position属性设置背景图像的起始位置,有三种取值方式：

| 值               | 解释                                                         |
| ---------------- | ------------------------------------------------------------ |
| *xpos ypos*      | 关键字定位，应用对齐规则。水平方向有left/center/right;垂直方向有top/center/bottom;取一个值时另外一个默认为center;xpos为left表示图像的左边与对象的左边对齐，同理，ypos为top时表示图像的顶部与对象的顶部对齐 |
| x(长度）y(长度） | 第一个值是水平位置，第二个值是垂直位置。左上角是0。单位可以是像素（0px0px）或任何其他 css单位。如果仅指定了一个值，其他值将是50％。将背景图像的左上角，放置在对象背景区域（x,y）所指定的位置，即定义的是背景图片的左上角相对于背景区域左上角的偏移量 |
| x%y%             | 第一个值是水平位置，第二个值是垂直位置。左上角是0％0％。右下角是100％100％。如果仅指定了一个值，其他值将是50％。 默认值为：0％0％ |

```css
div{background-position:center;}
表示背景图片的中心与背景区域的中心对齐
div{background-position:20px 30px;}
表示背景图片的左上角顶点相对于对象背景区域的左上角顶点在x轴向右移20px,在y轴下移30px
```

## 6.background-size 属性（设置背景图片大小）

| 值         | 描述                                                         |
| ---------- | ------------------------------------------------------------ |
| length     | 设置背景图片高度和宽度。第一个值设置宽度，第二个值设置的高度。如果只给出一个值，第二个是设置为auto(自动) |
| percentage | 将计算相对于背景定位区域的百分比。第一个值设置宽度，第二个值设置的高度。如果只给出一个值，第二个是设置为"auto(自动)" |
| cover      | 此时会保持图像的纵横比并将图像缩放成将完全覆盖背景定位区域的最小大小。 |
| contain    | 此时会保持图像的纵横比并将图像缩放成将适合背景定位区域的最大大小。 |

```css
div{background-image:url("./img/banner.jpg");
    background-size:60px 50px;
    }
背景图片宽度为60px,高度为50px
```

## 7.background-clip 属性

.background-clip 属性定义背景的显示区域

| 值          | 描述                                   |
| ----------- | -------------------------------------- |
| border-box  | 默认值。背景剪切在边框盒内             |
| padding-box | 背景绘制在填充盒内（剪切成填充方框）   |
| content-box | 背景绘制在内容盒内（剪切成内容方框）。 |

## 8.background-origin 属性

background-origin定义背景的渲染区域

| 值          | 描述                   |
| ----------- | ---------------------- |
| border-box  | 边框盒的左上角开始渲染 |
| padding-box | 填充盒的左上角开始渲染 |
| content-box | 内容盒的左上角开始渲染 |

# 二十、自定义属性

自定义属性的目的：为了保存并使用数据，有些数据可以保存到数据库中

## 1、自定义属性的获取是通过 getAttribute(‘属性’) 获取；

[getAttribute()](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/getAttribute)
但是有的自定义属性很容易引起歧义，不容易判断是元素内置属性还是自定义属性；
如果直接调用自定义属性会有问题 显示undefined

```html
<body>
    <div getTime="20"></div>
    <script>
        var div = document.querySelector('div');
        console.log(div.getTime);
    </script>
</body>
```

## 2、设置H5自定义属性：

H5 规定了自定义属性[data-](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Global_attributes/data-*)开头作为属性名并赋值 这样使自定义属性更加方便区分
H5新增element.[dataset.](https://developer.mozilla.org/zh-CN/docs/Web/API/HTMLOrForeignElement/dataset)*index* 或者 element.dataset[*‘index’*] ie11才开始支持

```html
<body>
    <div getTime="20" data-index="02"></div>
    <script>
        var div = document.querySelector('div');
        console.log(div.getTime);
        console.log('---------');
        console.log(div.getAttribute('getTime'));
        console.log(div.getAttribute('data-index'));
        div.setAttribute('data-Time', 20);
        console.log(div.getAttribute('data-Time'));
        // h5 新增的获取自定义属性的方法
        console.log(div.dataset.index);
    </script>
</body>
```

# 二十一、reset.css

## 2、为什么要用reset.css

因为在不同的浏览器中，HTML标签会有一些默认的属性值，但是各个浏览器会渲染出各不一样的效果，例如边距不一致、字体颜色大小行高不一样等等。为了防止出现这种情况，其实主要是为了减少代码的重复定义，提高代码复用率，提高开发效率，重设各个浏览器的默认样式，还可以解决其引起的耦合问题。
总结就是高复用，低耦合，文件小。

## 2、怎么用

独立新建一个css文档来储存重置样式，就是reset.css里面只存放重置样式，其他样式可以根据[前言](https://www.cnblogs.com/tc310/p/16226663.html#01)分类分开存放css属性。这里有一个是本人参考了各大网站的reset.css整理写的[reset.css](https://link.juejin.cn/?target=https%3A%2F%2Fgithub.com%2FBelieveXIA%2Fblog%2Fblob%2Fmaster%2FCSS%2Freset.css)，文档没有绝对标准性的，很多都是根据项目的具体需求写，我总结的只是一些非常常用的重置样式，可以适用大部分项目，当然最好是理解了，每次自己根据项目需求对reset.css进行编写。

[](https://www.cnblogs.com/tc310/p/16226663.html#_labelTop)

## 3、reset.css说明

```css
@charset 'utf-8';
/*这些元素都建议重新初始化*/
body,div,dl,dt,dd,ul,ol,li,tr,td,th,
h1,h2,h3,h4,h5,h6,hr,br,img,table,
input,form,a,p,textarea{
    padding:0;
    margin:0;
    font-family:Arial,'Microsoft YaHei','宋体';
}
/*去掉列表默认排列*/
ul,ol,li{
    list-style:none;
}
/*去掉底部横线*/
/*把a元素更改设置成块级元素，这个根据实际情况决定要不要*/
a{
    text-decoration:none;
    display:block;
}
/*img标签要清除border。*/
/*display设为block设置为块级元素，默认为display:inline;
存在下边线多出4px状况,所以一般设为block*/
img{
    border:0;
    display:block;
}
/*清除浮动破坏带来的塌陷问题*/
/*清除浮动的兼容IE*/
.clearfloat {
	zoom: 1;
}
.clearfloat:after {
	display:block;
	clear:both;
	content:"";
	visibility:hidden;
	height:0;
}
```

# 二十二、如何实现三栏布局

三栏布局：两边固定，中间自适应

## 1、流体布局（float布局）

1.首先绘制左右两栏，左栏左浮动，右栏右浮动

![img](https://img-blog.csdnimg.cn/e526bc76081d44e9930d566868409ee0.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5LuZ5aWz54ix5ZCD6bG8,size_20,color_FFFFFF,t_70,g_se,x_16)

2.再绘制中间一栏，留出左右两栏距离与间距

![img](https://img-blog.csdnimg.cn/bd55df2963414da0870a6c004b1221e3.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5LuZ5aWz54ix5ZCD6bG8,size_20,color_FFFFFF,t_70,g_se,x_16)

## 2、BFC布局

我们先把左右两栏元素浮动，中间栏不做其他属性，发现中间栏默认撑满全屏，这时候我们就可以利用BFC不会和浮动元素重叠的规则，把中间元素改成一个BFC，使用overflow:hidden或者display: flex达到中间栏自适应。

![img](https://img-blog.csdnimg.cn/a25bb497d0d3460b96d19dfbc3fa3bc5.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5LuZ5aWz54ix5ZCD6bG8,size_20,color_FFFFFF,t_70,g_se,x_16)

## 3、flex布局

flex属性的完整写法是:flex-grow项目放大比例、flex-shrink项目缩小比例 、flex-basis项目占据属性

1.项目绘制按照左中右排列

2.父元素使用flex属性

3.(1)左右两栏固定宽度
赋值给元素width属性
赋值给元素flex属性：flex: 0 1 200px(放大比例0，缩小比例1，项目宽度200px）
(2)中间使用flex:1占据剩余空间

~~~html
<style>
 .container {
    border: 1px solid red;
    display: flex;
  }
  .left {
    width: 200px;
    height: 200px;
    background-color: aqua;
  }
  .right { 
    width: 200px;
    height: 200px;
    background-color: aquamarine;
  }
  .mid {
    background-color: cadetblue;
    height: 200px;
    flex-grow: 1;
    margin-left: 20px; 
    margin-right: 20px;
  } 
</style>

<body>
  <div class="container">
    <div class="left">left</div>
    <div class="mid">mid</div>
    <div class="right">right</div>
  </div>
</body>
~~~

4、position定位

1.父元素使用相对定位
2.两侧子元素使用绝对定位
3.中间元素不做定位处理，只留出空间就好

~~~html
 .container {
    position: relative;
  }

  .left {
    position: absolute;
    width: 200px;
    height: 200px;
    left: 0;
    top: 0; 
    background-color: aqua;
  }

  .right {
    position: absolute;
    top: 0;
    right: 0;
    width: 200px;
    height: 200px;
    background-color: aquamarine;
  }

  .mid {
    background-color: cadetblue;
    height: 200px;
	margin: 0 220px;
  }
</style>
<body>
  <div class="container">
    <div class="mid">mid</div>
    <div class="left">left</div>
    <div class="right">right</div>
  </div>
</div>
</body>
~~~

# 二十三、JavaScript的数据类型

## 1、分类

按照类型来分有基本数据类型和引用数据类型：

**基本数据类型：**`String`、`Number`、`Boolean`、`Null`、`Undefined`、`Symbol`、BIgInt

**引用数据类型：**`Object`【Object是个大类，function函数、array数组、date日期...等都归属于Object】

## 2、数据类型的判断

**typeof, instanceof, constructor, Object.prototype.toString.call()**

1. `typeof:` 基本类型大部分都能被准确检测并返回正确的字符串（`除了 Null 类型`，其返回 object 字符串），而引用类型大部分都不能够被准确检测（`除了 Function 类型能够准确返回 function 字符串外`，其它的都返回了 object 字符串）。
2. `instanceof:` instanceof 运算符用来测试一个对象在其原型链中是否存在一个构造函数的 prototype 属性。即判断对象是否是某一数据类型（如Array）的实例。`只有引用数据类型（Array，Function，Object）被精准判断，其他（数值Number，布尔值Boolean，字符串String）等基本数据类型不能被instanceof精准判断`。

2.1 typeof

```javascript
console.log(typeof 7); // number
console.log(typeof '7'); // string
console.log(typeof false); // boolean
console.log(typeof [false]); // object
console.log(typeof function () {}); // function
console.log(typeof {}); // object
console.log(typeof undefined); // undefined
console.log(typeof null); // object
```

2.2 instanceof

```javascript
    console.log(7 instanceof Number); // false
    console.log('7' instanceof String); // false
    console.log(false instanceof Boolean); // false
    console.log([] instanceof Array); //true
    console.log(function () {} instanceof Function); // true
    console.log({} instanceof Object); // true
    // undefined is not a constructor
    // null is not a constructor
```

2.3 constructor

```javascript
    console.log((7).constructor === Number); // 全为true
    console.log(('7').constructor === String); //
    console.log(false.constructor === Boolean); //
    console.log((function () {}).constructor === Function); //
    console.log(({}).constructor === Object); //
    console.log(([]).constructor === Array); //

    function Test() {}
    Test.prototype = new Array();
    let f = new Test();
    console.log(f.constructor === Function) // false
    console.log(f.constructor === Test)  // false
    console.log(f.constructor === Array)  // true
```

2.4 Object.prototype.toString.call()

```javascript
    let too = Object.prototype.toString;
    console.log(too.call(7)); // [object Number]
    console.log(too.call('7')); // [object String]
    console.log(too.call(false)); // [object Boolean]
    console.log(too.call([])); // [object Array]
    console.log(too.call({})); // [object Object]
    console.log(too.call(function () {})); // [object Function]
    console.log(too.call(undefined)); // [object Undefined]
    console.log(too.call(null)); // [object Null]
```

# 二十四、判断数组的方法

## 1.通过instanceof判断

instanceof运算符用于检验构造函数的prototype属性是否出现在对象的原型链中的任何位置，返回一个布尔值

```javascript
let a = [];
a instanceof Array; //true
let b = {};
b instanceof Array; //false

//instanceof 运算符检测Array.prototype属性是否存在于变量a的原型链上
//显然a是一个数组，拥有Array.prototype属性，所以为true
```

## 2.通过constructor判断

实例的构造函数属性constructor指向构造函数，通过constructor属性可以判断是否为一个数组

```javascript
let a = [7,8,9];
a.constructor === Array;  //true
```

## 3.通过Object.prototype.toString.call()判断

Object.prototype.toString.call()可以获取到对象的不同类型

```javascript
let a = [7,8,9];
Object.prototype.toString.call(a) === '[Object Array]';  //true
```

## 4.通过Array.isArray()判断

Array.isArray()用于确定传递的值是否是一个数组，返回一个布尔值

```javascript
let a = [7,8,9];
Array.isArray(a);  //true
```

有个问题是Array.isArray()是ES5新增的方法，目的就是提供一个稳定可用的数组判断方法，对于ES5之前不支持此方法的问题，我们其实可以做好兼容进行自行封装，如下：

```javascript
if(!Array.isArray){
  Array.isArray = function(argument){
    return Object.prototype.toString.call(argument)  === '[object Array]';
  }
};
```

5.补充：typeof
typeof 只能检测 基本数据类型，包括boolean、undefined、string、number、symbol，而null ,Array、Object ,使用typeof出来都是Object，函数的typeof 是function 无法检测具体是哪种引用类型。

```javascript
console.log(typeof(100),1); 	      result:  number  1			 
console.log(typeof("name"),2); 	      result:  string  2 
console.log(typeof(false),3); 		result:  boolean  3
console.log(typeof(null),4); 		result:  object 4
console.log(typeof(undefined),5); 	result:  undefined 5
console.log(typeof([]),6); 		        result:  object  6
console.log(typeof(Function),7); 	result:  function  7
```

# 二十五、伪数组

### 1、伪数组的特点

1. 伪数组拥有数组的属性，
   -具有 length 属性 但length属性不是动态的，不会随着成员的变化而变化
   -按索引方式储存数据
   -不具有数组的push()， forEach()等方法
2. 伪数组本质是一个 Object，而真实的数组是一个 Array。
   伪数组的原型 `Object.__prototype__` 通过改变原型指向可以将伪数组转为真数组

### 2、常见伪数组

1. 函数内部的 arguments，扩展操作符可以将 arguments 展开成独立的参数
2. DOM 对象列表 如 通过 document.getElementByTags 获取的 dom元素
3. jQuery对象 如 $(‘div’)

```css
// 伪数组
var arrLike = {
    0: 'a',
    1: 'b',
    2: 'c',
    length: 3,
};
```

### 3、伪数组转为真数组

1. 遍历添加入一个空数组

```css
var arr = [];
for(var i = 0; i < arrLike.length; i++){
   arr.push(arrLike[i]);
}
```

1. 利用数组的slice()方法

```css
;[].slice.call(arrLike);
//slice() 方法以新的数组对象，返回数组中被选中的元素。
```

或者

```css
Array.prototype.slice.apply(arrLike);
```

> 使用slice()返回一个新的数组,用call()或apply()把他的作用环境指向伪数组。slice 返回的数组中，**不会保留索引值以外的其他额外属性。**

模拟 slice() 内部实现

```javascript
Array.prtotype.slice = function(start, end){
        var result = new Array();
        var start = start | 0;
        var end = end | this.length;

        for(var i = start; i < end; i++){
            result.push(this[i]);
        }
        return result;
    }
```

1. 改变原型指向

```javascript
arrLike.__proto__ = Array.prototype;
```

通过改变原型指向，arrLike就继承了Array.prototype中的方法，可以使用push()，unshift()等方法了，length值也会随之动态改变。

> 这种直接修改原型链的方法，还会保留下伪数组中的所有属性，**包括不是索引值的属性**。

1. Array.from()
   Array.from() 方法从一个类似数组或可迭代对象中创建一个新的数组实例。

```javascript
 var arr = Array.from(arrLike);
```

**只保留索引值内的属性**。

# 二十六、遍历数组的方法

## 1. some()

[遍历](https://so.csdn.net/so/search?q=%E9%81%8D%E5%8E%86&spm=1001.2101.3001.7020)数组，只要有一个以上的元素满足条件就返回 true，否则返回 false ，退出循环

对[数组](https://so.csdn.net/so/search?q=%E6%95%B0%E7%BB%84&spm=1001.2101.3001.7020)中每个元素执行一次ok函数，知道某个元素返回true，则直接返回true。如果都返回false,则返回false

检查整个数组中是否有满足元素。

​    private some(id: number) {
      const arr = [
        { cityId: 195, cityName: '深圳'},
        { cityId: 196, cityName: '北京'},
        { cityId: 198, cityName: '上海'}
      ]
      let result = arr.some((item: any) => {
        return item.cityId === id
      })
      console.log(`传入:${id},结果:${result}`)
    }

## 2. every()

遍历数组，每一个元素都满足条件 则返回 true，否则返回 false

​    private every() {
      const arr = [1,2,3,4,5]
      let result = arr.every((item: any) => {
        return item > 0
      })
      console.log(`结果:${result}`)
    }

​    private every() {
      const arr = [1,2,3,4,5]
      let result = arr.every((item: any) => {
        return item > 10
      })
      console.log(`结果:${result}`)
    }

## 3. forEach() 

数组里的元素个数有几个，该方法里的回调就会执行几次

第一个参数是数组里的当前元素，第二个参数为数组里当前元素的索引值，第三个参数则是它自己
没有返回值，本质上等同于 for 循环，对每一项执行 function 函数。即map是返回一个新数组，原数组不变，forEach 是改变原数组。
不支持 continue，用 return false 或 return true 代替。
不支持 break，用 try catch/every/some 代替
数组自带的遍历方法，虽然使用频率略高，但是性能仍然比普通循环略低
    private forEach() {
      type itemType = {
        cityId: number,
        cityName: string
      }
      const arr = [
        { cityId: 195, cityName: '深圳'},
        { cityId: 196, cityName: '北京'},
        { cityId: 197, cityName: '上海'}
      ]
      arr.forEach((item: itemType, index: number, arr: any) => {
        console.log(`index:${index}，item:${JSON.stringify(item)}，arr:${JSON.stringify(arr)}`)
      })
    }

##  4. map()

map() 方法返回一个新数组，数组中的元素为原始数组元素调用函数处理后的值。map() 方法按照原始数组元素顺序依次处理元素。

使用比较广泛，但其性能还不如 forEach
不会改变原始数组。
      let arr = [1, 2, 3, 4, 5, 6]
      let newArr = arr.map((item: any) => {
        return item * item
      })
      console.log(newArr)

## 5. filter()方法

创建一个新的数组，新数组中的元素是通过检查指定数组中符合条件的所有元素。不会改变原始数组。

​    private filter(id: number): string {
      const arr = [
        { cityId: 195, cityName: '深圳'},
        { cityId: 196, cityName: '北京'},
        { cityId: 197, cityName: '上海'}
      ]
      let name: string = ''
      arr.filter((item: any) => {
        if(item.cityId === id) {
          name = item.cityName
        }
      })
      console.log(`传入:${id}，结果:${name}`)
      return name
    }

## 6. find()

遍历数组，返回符合条件的第一个元素，如果没有符合条件的元素则返回 undefined

​      let arr = [1,2,2,3,3,3,3,4,4,5,6]
      let num = arr.find((item:any) => {
        return item === 3
      })
      console.log(num)

​      let arr = [1,2,2,3,3,3,3,4,4,5,6]
      let num = arr.find((item:any) => {
        return item === 10
      })
      console.log(num)

##  7. findIndex()

遍历数组，返回符合条件的第一个元素的索引，如果没有符合条件的元素则返回 -1

​      let arr = [1,2,2,3,3,3,3,4,4,5,6]
      let num = arr.findIndex((item:any) => {
        return item === 2
      })
      console.log(num)

​      let arr = [1,2,2,3,3,3,3,4,4,5,6]
      let num = arr.findIndex((item:any) => {
        return item === 10
      })
      console.log(num)

## 8. for…of…（ES6）自动解构

for of不能对象用

​      const arr = [
        { cityId: 195, cityName: '深圳'},
        { cityId: 196, cityName: '北京'},
        { cityId: 197, cityName: '上海'}
      ]
      for(const {cityId, cityName} of arr) {
        console.log(cityId, cityName)
      }

## 9. for…in…

for...in 语句用于遍历数组或者对象的属性（对数组或者对象的属性进行循环操作）。for in得到对对象的key或数组,字符串的下标

​      const arr = [
        { cityId: 195, cityName: '深圳'},
        { cityId: 196, cityName: '北京'},
        { cityId: 197, cityName: '上海'}
      ]
      const obj = { cityId: 195, cityName: '深圳'}
      for(const key in arr) {
        console.log(`数组key-${key}`)
      }
      for(const key in obj) {
        console.log(`对象key-${key}`)
      }

## 10. for

最简单的一种循环遍历方法，也是使用频率最高的一种，可优化

​      const arr = [
        { cityId: 195, cityName: '深圳'},
        { cityId: 196, cityName: '北京'},
        { cityId: 197, cityName: '上海'}
      ]
      for(let i = 0; i < arr.length; i++) {
        console.log(arr[i])
      }

**四种遍历方法对于100万的循环时间**

**for最快，但可读性比较差**

**forEach比较快，能够控制内容**

**for....of比较慢，香**

**for...in比较慢，不方便**

# 二十七、null和undefined区别

### 1.深层定义

- null 指空对象，但它是被定义过的
- undefined 指声明未赋值的对象或者是不存在的对象属性值

### 2.逻辑上

你可以定义一个值为null，证明它是空的，但如果你定义它是undefined（未被定义的），逻辑上不合理，尽管你可以这样做

### 3.典型用法

null：

（1）作为函数的参数，来表示该函数的参数不是对象

（2）作为对象原型链的终点

```javascript
Object.getPrototypeOf(Object.prototype)
// null
```

undefined：

（1）变量被声明了，但没有赋值时，就等于undefined。

（2) 调用函数时，应该提供的参数没有提供，该参数等于undefined。

（3）对象没有赋值的属性，该属性的值为undefined。

（4）函数没有返回值时，默认返回undefined。

# 二十八、为什么0.1+0.2 != 0.3?

要解决这个问题，首先要明白计算机底层的编码原理，计算机是采用[二进制](https://so.csdn.net/so/search?q=%E4%BA%8C%E8%BF%9B%E5%88%B6&spm=1001.2101.3001.7020)方式存储数据的，也就是我们常说的01代码

0.1的二进制是`0.0001100110011001100...`（1100循环），0.2的二进制是：`0.00110011001100...`（1100循环），这两个数的二进制都是无限循环的数

再回到JavaScript的数据类型，关于数字的只有一种类型，Number，它使用64位固定长度来表示，也就是标准的double双精度浮点数，在二进制中记住一个原则，**遵循0舍1入**

所以，0.1+0.2 = 0.30000000000000004

那么如何让其相等呢？

在ES6中【推荐阮一峰的ES6入门】，新增了一个**Number.EPSILON**方法，它可以用来**设置“能够接受的误差范围"**

例子：只要判断0.1+0.2-0.3是否小于Number.EPSILON，如果小于，就可以判断为0.1+0.2===0.3

```javascript
function withinErrorMargin (left, right) {
  return Math.abs(left - right) < Number.EPSILON * Math.pow(2, 2);
}

0.1 + 0.2 === 0.3 // false
withinErrorMargin(0.1 + 0.2, 0.3) // true
```

# 二十九、值转换规则

## 1、其他值到Boolean值的转化规则

~~~javascript
在js中存在的假值为:
undefined, null, +0, -0, NaN, false, ""(空串)

console.log(Boolean(undefined))   //false
console.log(Boolean(null))        //false
console.log(Boolean(+0))          //false
console.log(Boolean(-0))          //false
console.log(Boolean(NaN))         //false
console.log(Boolean(false))       //false
console.log(Boolean(""))          //false
除此之外,其他值均为Boolean类型。
~~~

## 2、其他值到字符串的转换规则

**1、null和undefined转换为字符串**

```javascript
String(null)    //‘null’
String(undefined)  //‘undefined’
```

**2、Boolean转化为字符串**

```javascript
String(true)    //'true'
String(false)   //‘false’
```

**3、Number类型数据转换为字符串**

```javascript
console.log(String(10))     //“10”
console.log(String(0.000000000000000000001))   //“1e-21”
console.log(String(10000000000000000000000))   //“1e+22”
```

**4、Symbol类型转换为字符串**

```javascript
//Symbol类型的数据显示转化为字符串不报错，但是隐式转换就报错
console.log(String(Symbol(11)))   //“Symbol(11)”
console.log(Symbol(11) + "")      //报错
```

**5、对象类型转化为字符串类型**

```javascript
如果是普通对象，调用toString方法，则显示[object object],Object.prototype上存在一个方法，为toString方法，例如像数组这样的可以调用该方法，则会打印出tag。
Object.prototype.toString.call([])    //[object array]
```

## 3、其他值转化为数字类型的规则

**1、undefined类型转化为数字类型**

```javascript
Number(undefined)    //NaN
```

**2、null类型转化为数字类型**

```javascript
Number(null)       //0
```

**3、Boolean值类型转化为数字类型**

```javascript
Number(true)   //1
Number(false)   //0
```

**4、字符串类型转换为数字类型**

```javascript
Number("123s")  //NaN
Number("123")   //123
如果传入的只含有数字的字符串，则直接转化为数字，如果包含其他非数字的字符串，则返回NaN.
```

**5、Symbol类型转化为数字类型**

```javascript
Number("Symbol(12)")    //报错
```

**6、对象类型转化为数字类型**

```javascript
对象类型的数据首先先转化为基本数据类型，转化之后，再按照上述几点进行转换。
对象内部使用toPrimitive(input)来解决问题，
具体的解决方案：如果input为基本数据类型则直接返回，如果不是，则调用
valueOf方法，如果是基本数据类型，则返回。否则再调用toString()方法，如果
是基本数据类型则返回，否则报错。
例子：
console.log([1,2,3] == '1,2,3')   //true
这个是因为右边是基本数据类型，左边使用[1,2,3].toString()转换为基本数据类
型，
console.log("play" == true)  //这里左边执行toPrimity()转化为NaN,右边
转换为1  
```

# 三十、&& 和 || 的区别

**一、概念**

与其他语言不同，在js中，逻辑运算符可以返回任何类型的数据，不仅仅是true和false。

&&和||的返回值是两个操作数的其中一个。即a&&b或者a||b返回的是要么是a，要么是b，而其他语言中返回的是true or false。

在js逻辑运算中，需要隐式的转换为boolean类型再来运算，**转换规则**为：

\1. 对象、非零number、非空string——>true

2. 0、""、null、false、undefined、NaN——>false

具体见下表：

| 数据类型     | 转换为boolean后的值 |
| ------------ | ------------------- |
| NAN          | FALSE               |
| null         | FALSE               |
| undefined    | FALSE               |
| Object       | TRUE                |
| Function     | TRUE                |
| 0            | FALSE               |
| 非零的数字   | TRUE                |
| ""(空字符串) | FALSE               |
| 非空字符串   | TRUE                |

因此：

a && b : 将a, b转换为Boolean类型, 再执行逻辑与, 如果结果是true返回b, false返回a
a || b : 将a, b转换为Boolean类型, 再执行逻辑或, 如果结果是false返回b, true返回第一个为true的值。

**逻辑&&和逻辑||还有一个短路原则：知道了前面第一个的结果就知道最后的输出**

**a&&b：左操作数为假值时，返回左操作数，否则返回右操作数。a||b：左操作数为假值时，返回右操作数，否则返回左操作数。**

只要“||”前面为false,不管“||”后面是true还是false，都返回“||”后面的值。

只要“||”前面为true,不管“||”后面是true还是false，都返回“||”前面的值。

只要“&&”前面是false，无论“&&”后面是true还是false，结果都将返“&&”前面的值;

只要“&&”前面是true，无论“&&”后面是true还是false，结果都将返“&&”后面的值;

同样对于多个操作数的情况：

a||b||c||d：若结果为true则返回第一个true值，若结果为false则返回最后一个操作数。eg：var a = “” || null || 3 || 2 -> var a = fasel || false || true || true 结果为true 则返回第一个true,即是3

a&&b&&c&&d：若结果为false则返回第一个false，若结果为true则返回最后一个操作数。eg：var b = 2&&null&&1&&0 -> var b = true&&false&&true&&false结果是false 则返回第一个false 即是null

# 三十一、比较操作符== 和 === 的区别

两者都是判断等式两边是否相等，最大的区别就是==会进行类型的转换之后再判断两者是否相等，而===不会进行数据类型的转换，先判断两边的数据类型是否相等，如果数据类型相等的话才会进行接下来的判断，再进行等式两边值得判断，可以理解为只有等式两边是全等（数据类型相同，值相同）的时候结果才会是true，否则全为false。

==判断等式两边是否相等的情况：

（1）null、undefined和不同类型比较，都是false（null和undefined结果为true）

（2）NaN和任何数据进行比较，都是false（包括NaN和NaN相比较也为false）

（3）布尔值是转换为数字1或0再和其他数据进行比较

​             拓展：   不同数据转换成布尔值的结果：              

```javascript
        console.log(Boolean(''));       //false
        console.log(Boolean({}));       //true
        console.log(Boolean([]));       //true
        console.log(Boolean(null));     //false
        console.log(Boolean(undefined)); //false
        console.log(Boolean(NaN));      //false
        console.log(Boolean(Object));   //true
```

（4）数字和其他简单数据类型进行比较时，会尝试将其他数据类型转换成数值型再进行比较

​                **其他数据类型默认转数字使用的是Number()  

```javascript
        console.log(""==false);     //true
        console.log(parseInt(""));   //NaN
        console.log(Number(""));   //0
        console.log(""==0);         //true
```

（5）对象和其他简单数据类型进行比较的时候，会尝试使用对象的valueOf()和toString()方法将对象转换为原始值进行比较：

​        ①对象.toString()返回值只有[ object Object ]                

```javascript
        let obj = {
            name:'leon',
            age:18
        };
        console.log(obj.toString());    //[object Object]
        console.log(obj.valueOf());     //{name: 'leon', age: 18}
```

```javascript
        let obj = {};
        console.log(obj.toString());    //[object Object]
        console.log(obj.valueOf());     //{}
```

​        ②数组  [ ].toString()返回值是空  其他数组.toString()返回值是字符 ，一个成员一个字符逗号分隔   

```javascript
        let arr1=[1,2,3];
        console.log(arr1.toString());    //1,2,3
        console.log(arr1.valueOf());     //[1, 2, 3]
        let arr=[];       
        console.log(arr.toString());    //空
        console.log(arr.valueOf());     //[]
```

​        ③其他的对象function  reg  返回字符串        

```javascript
        function fn(){
            console.log("你是最棒的！");
        }
        console.log(fn.toString());    
        console.log(fn.valueOf());   
        let reg = /^[^_$]\w{5,}@(163|126|qq|sina)\.(com|cn|net)$/;
        console.log(reg.toString());    
        console.log(reg.valueOf()); 
```

（6）两者同为引用类型时，必须是指向同一个引用地址才相等，否则不相等

（7）-0 == +0   结果为：true

全等比较（===）不转换数据类型，数据类型和内容必须完全一致才是相等

全等比较（===）两边是否相等的情况：

（1）类型不同，一定不相等

（2）两个同为数值，并且相等，则相等；若其中一个为NaN，一定不相等

（3）两个都为字符串，每个位置的字符都一样，则相等

（4）两个同为true,或是false，则相等

（5）两个值都引用同一个对象或函数，则相等，否则不相等（引用类型地址空间可能不一样）

（6）两个值都为null，或undefined，则相等

（7*）两者同为引用类型时，必须是指向同一个引用地址才相等，否则不相等（5的补充）

（8）-0 === +0   结果为：true

# 三十二、判断NAN

NaN与自己都不相等，这个时候就不能用‘===’来判断，那我们用全局函数isNaN()，但是这个函数存在一个问题，当函数里面是[字符串](https://so.csdn.net/so/search?q=%E5%AD%97%E7%AC%A6%E4%B8%B2&spm=1001.2101.3001.7020)的时候，就会返回true，因为isNaN()的实现原理是先用Number()把里面内容转换成数字类型，当里面的内容转出来是数字的，那么isNaN()的结果就是false，不是数字是其他的话，返回值就是true，但是Number已经把里面的东西转换成数字类型了，所以出来的只要不是数字那么都会是NaN。

为解决这个问题我们可以这样做：
1：在使用isNaN()之前先检查一下这个值是不是数字类型，这样就避免了隐式转换的问题：

```javascript
 function f1(value) {

        if (typeof value==='number'&&isNaN(value)) {
           alert('这是NaN');
        }else{
            alert('这不是NaN');
        }
    }
    f1('abc'-1);123456789
```

2:用自身特性，与自己不相等来判断

```javascript
 function f1(value) {

        if (value!=value) {
           alert('这是NaN');
        }else{
            alert('这不是NaN');
        }
    }
    f1('abc');
```

# 三十三、获取dom元素节点的方法

DOM 是一个树形结构，操作一个DOM节点，实际上就是这几个操作：更新、删除、添加、遍历

在操作DOM节点之前，需要通过各种方式先拿到这个DOM节点，常用的方法有：

## 1、通过元素类型的方法来操作：

1. document.getElementById();//id名，在实际开发中较少使用，选择器中多用class  id一般只用在顶级层存在 不能太过依赖id
2. document.getElementsByTagName();//标签名
3. document.getElementsByClassName();//类名
4. document.getElementsByName();//name属性值，一般不用
5. document.querySelector();//css选择符模式，返回与该模式匹配的第一个元素，结果为一个元素；如果没找到匹配的元素，则返回null
6. document.querySelectorAll()//css选择符模式，返回与该模式匹配的所有元素，结果为一个类数组

## 2、根据关系树来选择（遍历节点树）：

**【**先简单介绍一下节点：

DOM（文档对象模型）可以将任何HTML、XML文档描绘成一个多层次的节点树。所有的页面都表现为以一个特定节点为根节点的树形结构。html文档中根节点为document节点。

所有节点都有nodeType属性，代表节点的不同类型，通过nodeType属性可以来判断节点的类型。经常使用的节点主要有以下几种类型：

1. Element类型（元素节点）：nodeType值为 1

2. Text类型（文本节点）：nodeType值为 3

3. Comment类型（注释节点）：nodeType值为 8

4. Document类型（document节点）：nodeType值为 9；其规定的一些常用的属性有

   document.body    document.head  分别为HTML中的 <body><head>

   document.documentElement为<html>标签

所有的节点都有   hasChildNodes()方法    判断有无子节点  有一个或多个子节点时返回true**】**

通过一些属性可以来遍历节点树：

1. parentNode//获取所选节点的父节点，最顶层的节点为#document
2. childNodes //获取所选节点的子节点们 
3. firstChild //获取所选节点的第一个子节点
4. lastChild //获取所选节点的最后一个子节点
5. nextSibling //获取所选节点的后一个兄弟节点  列表中最后一个节点的nextSibling属性值为null
6. previousSibling //获取所选节点的前一兄弟节点   列表中第一个节点的previousSibling属性值为null

## 3、基于元素节点树的遍历（遍历元素节点树）：

1. parentElement　//返回当前元素的父元素节点（IE9以下不兼容）
2. children  // 返回当前元素的元素子节点
3. firstElementChild //返回的是第一个元素子节点（IE9以下不兼容）
4. lastElementChild  //返回的是最后一个元素子节点（IE9以下不兼容）
5. nextElementSibling  //返回的是后一个兄弟元素节点（IE9以下不兼容）
6. previousElementSibling  //返回的是前一个兄弟元素节点（IE9以下不兼容）

# 三十四、变量提升与函数提升

## 1、变量提升

  变量提升即将变量声明提升到它所在[作用域](https://so.csdn.net/so/search?q=%E4%BD%9C%E7%94%A8%E5%9F%9F&spm=1001.2101.3001.7020)的最开始的部分。

- **通过var定义（声明）的变量，在定义语句之前就可以访问到；**
- **值：undefined；**

```javascript
	console.log(a); //undefined
	var a = 1;
```

  因为有变量提升的缘故，上面代码实际的执行顺序为：

```javascript
	var a;
	console.log(a);
	a = 1;
```

## 2、函数提升

  js中创建函数有两种方式：[函数声明](https://so.csdn.net/so/search?q=%E5%87%BD%E6%95%B0%E5%A3%B0%E6%98%8E&spm=1001.2101.3001.7020)式和函数表达式
  **1、函数声明提升**

```javascript
	function fun() {
	    console.log('函数声明式');
	}
```

  **js在执行之前，会把foo函数提升到最前面**，所以我们在fun函数定义之前就可以使用fun函数。
  举个栗子来说明下：

```javascript
	fun();
	function fun(){
		console.log("aa");
	}
```

  打印结果为aa；说明以函数声明来定义函数时，可以在定义函数之前访问到定义的函数。

  **2、函数表达式提升**

```javascript
	var fun = function() {
	    console.log('函数表达式');
	};
```

  此种声明方式我们可以理解为**一个普通变量的提升**，在js代码执行之前会把fun提升带最前面，**在函数赋值之前，fun是undefined，如果调用fun(),将会报错**。

  再举个栗子来理解下：

```javascript
	fun();
	var fun = function (){
	    console.log("aa");
	}
```

  此时打印的结果为报错`Uncaught TypeError: fun is not a function`，因为在js代码执行之前，会把fun提升到最前面，值为undefined，不是一个函数，以函数的形式来进行调用时将会报错。

**函数提升优先级高于变量提升，且不会被同名变量声明时覆盖，但是会被同名变量赋值后覆盖。**

# 三十五、css如何做三角形

**第一步**

首先，先来一个div，然后给这个div加一层border，并且给上下左右border分别加上不同颜色，以便观察，代码和效果如下：

~~~css
.trangle{

　　width: 100px;

　　height: 100px;

　　border: 100px solid #000;

　　border-top-color: red;

　　border-bottom-color: yellow;

　　border-left-color: blue;

　　border-right-color: green;

}
<div class="trangle"></div>
~~~

![img](https://img.php.cn/upload/article/000/000/024/b68147dd7f1055b2b2dd935be0d0bbf7-0.png)

**第二步**

接着，将这个div的width变为0，我们再来看看效果。可以看到，由于div的宽度变成了0，左右两边的border“吸”在了一起，同时上下的border变成了三角形，好像快要完成了，别急，再看看第三步。

~~~css
.trangle{

　　width: 0px;

　　height: 100px;

　　border: 100px solid #000;

　　border-top-color: red;

　　border-bottom-color: yellow;

　　border-left-color: blue;

　　border-right-color: green;

}

<div class="trangle"></div>
~~~



![img](https://img.php.cn/upload/article/000/000/024/b68147dd7f1055b2b2dd935be0d0bbf7-1.png)

**第三步**

然后，再将这个div的height变为0，效果如下。我们可以看到，由于div的高度也变成了0，上下两个border也“吸”在了一起，同时上下的border也变成了三角形，到现在为止，四个三角形已经出来了。

~~~css
.trangle{

　　width: 0px;

　　height: 0px;

　　border: 100px solid #000;

　　border-top-color: red;

　　border-bottom-color: yellow;

　　border-left-color: blue;

　　border-right-color: green;

}

<div class="trangle"></div>
~~~

![img](https://img.php.cn/upload/article/000/000/024/b68147dd7f1055b2b2dd935be0d0bbf7-2.png)

**第四步**

最后，就看你想要哪个角啦，想要哪个角就把其余三个border设为透明即可。例如，我想要最上面的三角形，那就把下、左、右设为透明，代码和效果如下：

~~~css
.trangle{

　　width: 0px;

　　height: 0px;

　　border: 100px solid #000;

　　border-top-color: red;

　　border-bottom-color: transparent;

　　border-left-color: transparent;

　　border-right-color: transparent;

}
<div class="trangle"></div>
~~~

![img](https://img.php.cn/upload/article/000/000/024/aa194d34faf0196417150483f4dd9a7f-3.png)

**简化代码**

其实，我们不需要把四个border都设置一遍，只需设置你想要画的三角形所涉及到的三条边的border即可。以上步的画最上面的三角形为例，只需设置上、左、右三条边即可，并且要上三角形，就把左右border设为透明，代码和效果如下：

~~~css
.trangle{

　　width: 0px;

　　height: 0px;

　　border-top: 100px solid red;

　　border-left: 100px solid transparent;

　　border-right: 100px solid transparent;

}

<div class="trangle"></div>
~~~

# 三十六、对象的拷贝

**一、预备知识**

1、对象拷贝是什么

对象拷贝就是将一个对象的属性拷贝到另一个有着相同属性类类型的对象中去。
主要是为了在新的上下文环境中复用对象的部分或全部数据。

![img](https://pic2.zhimg.com/80/v2-3f991e9428426a315f2f61079ce56f1d_720w.webp)

从上面的图中可以看到：

基础类型：是按照**值** 存放在**栈中，**占用的内存空间的大小是确定的，并由系统自动分配和自动释放。
引用类型： 是按照**地址** 存在堆中，将存放在栈内存中的地址赋值给接收的变量。当我们想要访问引用类型的值的时候，需要先从栈中获得对象的地址指针，然后，在通过地址指针找到堆中的所需要的数据。

**1.1、JS数据类型**

基本数据类型：Boolean、String、Number、null、undefined
引用数据类型：Object、Array、Function、RegExp、Date等

**1.2、数据类型的复制**

基本数据类型的复制，是按值传递的

引用数据类型的复制，是按引用传值

**1.3、深拷贝与浅拷贝**

**深拷贝:**主要是将另一个对象的属性值拷贝过来之后，另一个对象的属性值并不受到影响，因为此时它自己在堆中开辟了自己的内存区域，不受外界干扰。
**浅拷贝:**主要拷贝的是对象的引用值，当改变对象的值，另一个对象的值也会发生变化。

因此，如果在对对象进行赋值时，如果不希望共享对象，那么就要进行深拷贝。

深拷贝和浅拷贝都只针对引用数据类型，浅拷贝会对对象逐个成员依次拷贝，但只复制内存地址，而不复制对象本身，新旧对象成员还是共享同一内存；深拷贝会另外创建一个一模一样的对象，新对象跟原对象不共享内存，修改新对象不会改到原对象。

区别：浅拷贝只复制对象的第一层属性，而深拷贝会对对象的属性进行递归复制。

**二、JS浅拷贝**

**2.1、赋值与浅拷贝**

当把一个对象赋值给一个新的变量时，赋的对象是该对象在栈中的地址，而不是堆中的数据。也就是新旧两个对象指的是同一个存储空间，无论哪个对象发生改变，其实都是改变的存储空间的内容，两个对象联动的会一起改变。

~~~javascript
var obj1 = {
  'name' : 'zhangsan',
  'language' : [1,[2,3],[4,5]],
};
var obj2 = obj1;
obj2.name = "lisi";
obj2.language[1] = ["二","三"];
console.log('obj1',obj1)
console.log('obj2',obj2)
~~~

![202084111528863.png](https://img.jbzj.com/file_images/article/202008/202084111528863.png?202074111535)

浅拷贝是按位拷贝对象，它会创建一个新对象，对原有对象的成员进行依次拷贝。如果属性是基本类型，拷贝的就是基本类型的值；如果属性是引用类型，拷贝的就是内存地址。因此如果新对象中的某个对象成员改变了地址，就会影响到原有的对象。

~~~javascript
//手写浅拷贝
function shallowCopy(obj1) {
 let obj2 = Array.isArray(obj1) ? [] : {}
 for (let i in obj1) {
  obj2[i] = obj1[i]
 }
 return obj2
}
var obj1 = {
  'name' : 'zhangsan',
  'language' : [1,[2,3],[4,5]],
};
var obj2 = shallowCopy(obj1);
obj2.name = "lisi";
obj2.language[1] = ["二","三"];
console.log('obj1',obj1)
console.log('obj2',obj2)
~~~

![202084111612040.png](https://img.jbzj.com/file_images/article/202008/202084111612040.png?202074111619)

**2.2、浅拷贝的实现**

（1）Object.assign()

Object.assign()方法可以把源对象自身的任意多个的可枚举属性拷贝给目标对象，然后返回目标对象，但是Object.assign()进行的是浅拷贝，拷贝的是对象的属性的引用，而不是对象本身。此方法对于Array和Object均可适用。

~~~javascript
var obj1 = {
  'name' : 'zhangsan',
  'language' : [1,[2,3],[4,5]],
};
var obj2 = Object.assign({}, obj1);
obj2.name = "lisi";
obj2.language[1] = ["二","三"];
console.log('obj1',obj1)
console.log('obj2',obj2)
~~~

![img](https://img.jbzj.com/file_images/article/202008/202084111701179.png?20207411178)

2）Array.prototype.concat()和Array.prototype.slice()

Array.prototype.concat()和Array.prototype.slice()均为Array原型上的方法，只适用于Array。

~~~javascript
var arr1 = [1,3,{
 user: 'aaa'
}]
var arr2 = arr1.concat();
arr2[0] = '一';
arr2[2].user = 'AAA';
console.log('arr1',arr1)
console.log('arr2',arr2)


var arr1 = [1,3,{
 user: 'aaa'
}]
var arr2 = arr1.slice();
arr2[0] = '一';
arr2[2].user = 'AAA';
console.log('arr1',arr1)
console.log('arr2',arr2)
~~~

![202084111802761.png](https://img.jbzj.com/file_images/article/202008/202084111802761.png?20207411188)

补充说明：Array的slice和contact方法都不会修改原数组，而是会返回一个对原数组进行浅拷贝的新数组。这两种方法同Object.assign()一样，都是对第一层属性依次拷贝，如果第一层的属性是基本数据类型，就拷贝值；如果是引用数据类型，就拷贝内存地址。

**三、JS深拷贝**

对对象的属性中所有引用类型的值，遍历到是基本类型的值为止。

**3.1、深拷贝实现方式**

(1)JSON.parse(JSON.stringify())

原理：用JSON.stringify()将对象转成字符串，再用JSON.parse()把字符串解析成对象。

~~~javascript
var obj1 = {
  'name' : 'zhangsan',
  'language' : [1,[2,3],[4,5]],
};
var obj2 = JSON.parse(JSON.stringify(obj1));
obj2.name = "lisi";
obj2.language[1] = ["二","三"];
console.log('obj1',obj1)
console.log('obj2',obj2)
~~~

![img](https://img.jbzj.com/file_images/article/202008/202084111855907.png?20207411192)

缺点：这种方法可以实现数组和对象和基本数据类型的深拷贝，但不能处理函数。因为JSON.stringify()方法是将一个javascript值转换我一个JSON字符串，不能接受函数。其他影响如下：

- 如果对象中有时间对象，那么用该方法拷贝之后的对象中，时间是字符串形式而不是时间对象
- 如果对象中有RegExp、Error对象，那么序列化的结果是空
- 如果对象中有函数或者undefined，那么序列化的结果会把函数或undefined丢失
- 如果对象中有NAN、infinity、-infinity，那么序列化的结果会变成null
- JSON.stringfy（）只能序列化对象的可枚举自有属性，如果对象中有是构造函数生成的，那么拷贝后会丢弃对象的constructor
- 如果对象中存在循环引用也无法正确实现深拷贝

（2）手写深拷贝函数

通过递归实现深拷贝

~~~javascript
function deepCopy(obj){
 var result= Array.isArray(obj) ? [] : {}
 if (obj && typeof(obj) === 'object') {
  for (let i in obj) {
   if (obj.hasOwnProperty(i)){ // 思考：这句是否有必要？
    if (obj[i] && typeof(obj[i]) === 'object') {
     result[i] = deepCopy(obj[i])
    } else {
     result[i] = obj[i]
    }
   }
  }
 }
 return result
}
var obj1 = {
 a: 1,
 b: {
  c: 2
 }
};
var obj2 = deepCopy(obj1);
obj2.a = '一';
obj2.b.c = '二'
console.log('obj1', obj1)
console.log('obj2', obj2)
~~~

> obj.hasOwnProperty(prop)用来判断obj这个对象中是否含有prop这个属性，返回布尔值，有则true，没有则false

以上有个缺陷：当遇到两个互相引用的对象时，会出现死循环的情况，从而导致爆栈。为了避免相互引用的对象导致死循环的情况，则应该在遍历的时候判断是否互相引用。

深拷贝函数改进（防止循环递归爆栈）

~~~javascript
function deepCopy(obj, parent = null) {
 let result = Array.isArray(obj) ? [] : {}
 let _parent = parent
 // 该字段有父级则需要追溯该字段的父级
 while(_parent) {
  // 如果该字段引用了它的父级，则为循环引用
  if (_parent.originalParent === obj) {
   // 循环引用返回同级的新对象
   return _parent.currentParent 
  }
  _parent = _parent.parent
 }
 if (obj && typeof(obj) === 'object') {
  for (let i in obj) {
   // 如果字段的值也是一个对象
   if (obj[i] && typeof(obj[i]) === 'object') {
    // 递归执行深拷，将同级的待拷贝对象传递给parent，方便追溯循环引用
    result[i] = deepCopy(obj[i], {
     originalParent: obj,
     currentParent: result,
     parent: parent
    })
   } else {
    result[i] = obj[i]
   }
  }
 }
 return result
}
var obj1 = {
 x: 1,
 y: 2
};
obj1.z = obj1
var obj2 = deepCopy(obj1)
console.log('obj1', obj1)
console.log('obj2', obj2)
~~~

深拷贝函数最终版（支持基本数据类型、Array、Object、原型链、RegExp、Date类型）

~~~javascript
function deepCopy(obj, parent = null) {
 let result
 let _parent = parent
 while(_parent) {
  if (_parent.originalParent === obj) {
   return _parent.currentParent
  }
  _parent = _parent.parent
 }
 if (obj && typeof(obj) === 'object') {
  if (obj instanceof RegExp) {
   result = new RegExp(obj.source, obj.flags)
  } else if (obj instanceof Date) {
   result = new Date(obj.getTime())
  } else {
   if (obj instanceof Array) {
    result = []
   } else {
    let proto = Object.getPrototypeOf(obj)
    result = Object.create(proto)
   }
   for (let i in obj) {
    if(obj[i] && typeof(obj[i]) === 'object') {
     result[i] = deepCopy(obj[i], {
      originalParent: obj,
      currentParent: result,
      parent: parent
     })
    } else {
     result[i] = obj[i]
    }
   }
  }
 } else {
  return obj
 }
 return result
}
var obj1 = {
 x: 1 
}

//试调用
function construct(){
  this.a = 1,
  this.b = {
    x:2,
    y:3,
    z:[4,5,[6]]
  },
  this.c = [7,8,[9,10]],
  this.d = new Date(),
  this.e = /abc/ig,
  this.f = function(a,b){
    return a+b
  },
  this.g = null,
  this.h = undefined,
  this.i = "hello",
  this.j = Symbol("foo")
}
construct.prototype.str = "I'm prototype"
var obj1 = new construct()
obj1.k = obj1
obj2 = deepCopy(obj1)

obj2.b.x = 999
obj2.c[0] = 666

console.log('obj1', obj1)
console.log('obj2', obj2)
~~~

（3）函数库

也可以使用一些函数库，比如函数库lodash，也有提供_.cloneDeep用来做深拷贝；

~~~javascript
var _ = require('lodash');
var obj1 = {
  a: 1,
  b: { f: { g: 1 } },
  c: [1, 2, 3]
};
var obj2 = _.cloneDeep(obj1);
console.log(obj1.b.f === obj2.b.f);
// false
~~~

# 三十七、css3新增特性

## 一、css是什么

`css`，即层叠[样式表](https://so.csdn.net/so/search?q=%E6%A0%B7%E5%BC%8F%E8%A1%A8&spm=1001.2101.3001.7020)（Cascading Style Sheets）的简称，是一种标记语言，由浏览器解释执行用来使页面变得更美观

`css3`是`css`的最新标准，是向后兼容的，`CSS1/2`的特性在`CSS3` 里都是可以使用的

而`CSS3` 也增加了很多新特性，为开发带来了更佳的开发体验

## 二、[选择器](https://so.csdn.net/so/search?q=%E9%80%89%E6%8B%A9%E5%99%A8&spm=1001.2101.3001.7020)

`css3`中新增了一些选择器，主要为如下图所示：

![img](https://img-blog.csdnimg.cn/img_convert/13342844d128e9eb2908cee958349048.png)

## 三、新样式

### 边框

`css3`新增了三个边框属性，分别是：

- border-radius：创建圆角边框
- box-[shadow](https://so.csdn.net/so/search?q=shadow&spm=1001.2101.3001.7020)：为元素添加阴影
- border-image：使用图片来绘制边框

box-shadow

设置元素阴影，设置属性如下：

- 水平阴影
- 垂直阴影
- 模糊距离(虚实)
- 阴影尺寸(影子大小)
- 阴影颜色
- 内/外阴影

其中水平阴影和垂直阴影是必须设置的

### 背景

新增了几个关于背景的属性，分别是`background-clip`、`background-origin`、`background-size`和`background-break`

background-clip

用于确定背景画区，有以下几种可能的属性：

- background-clip: border-box; 背景从border开始显示
- background-clip: padding-box; 背景从padding开始显示
- background-clip: content-box; 背景显content区域开始显示
- background-clip: no-clip; 默认属性，等同于border-box

通常情况，背景都是覆盖整个元素的，利用这个属性可以设定背景颜色或图片的覆盖范围

background-origin

当我们设置背景图片时，图片是会以左上角对齐，但是是以`border`的左上角对齐还是以`padding`的左上角或者`content`的左上角对齐? `border-origin`正是用来设置这个的

- background-origin: border-box; 从border开始计算background-position
- background-origin: padding-box; 从padding开始计算background-position
- background-origin: content-box; 从content开始计算background-position

默认情况是`padding-box`，即以`padding`的左上角为原点

background-size

background-size属性常用来调整背景图片的大小，主要用于设定图片本身。有以下可能的属性：

- background-size: contain; 缩小图片以适合元素（维持像素长宽比）
- background-size: cover; 扩展元素以填补元素（维持像素长宽比）
- background-size: 100px 100px; 缩小图片至指定的大小
- background-size: 50% 100%; 缩小图片至指定的大小，百分比是相对包 含元素的尺寸

background-break

元素可以被分成几个独立的盒子（如使内联元素span跨越多行），`background-break` 属性用来控制背景怎样在这些不同的盒子中显示

- background-break: continuous; 默认值。忽略盒之间的距离（也就是像元素没有分成多个盒子，依然是一个整体一样）
- background-break: bounding-box; 把盒之间的距离计算在内；
- background-break: each-box; 为每个盒子单独重绘背景

### 文字

word-wrap

语法：`word-wrap: normal|break-word`

- normal：使用浏览器默认的换行
- break-all：允许在单词内换行

text-overflow

`text-overflow`设置或检索当当前行超过指定容器的边界时如何显示，属性有两个值选择：

- clip：修剪文本
- ellipsis：显示省略符号来代表被修剪的文本

text-shadow

`text-shadow`可向文本应用阴影。能够规定水平阴影、垂直阴影、模糊距离，以及阴影的颜色

text-decoration

CSS3里面开始支持对文字的更深层次的渲染，具体有三个属性可供设置：

- text-fill-color: 设置文字内部填充颜色
- text-stroke-color: 设置文字边界填充颜色
- text-stroke-width: 设置文字边界宽度

### 颜色

`css3`新增了新的颜色表示方式`rgba`与`hsla`

- rgba分为两部分，rgb为颜色值，a为透明度
- hala分为四部分，h为色相，s为饱和度，l为亮度，a为透明度

## 四、transition 过渡

`transition`属性可以被指定为一个或多个`CSS`属性的过渡效果，多个属性之间用逗号进行分隔，必须规定两项内容：

- 过度效果
- 持续时间

语法如下：

```
transition： CSS属性，花费时间，效果曲线(默认ease)，延迟时间(默认0)
1
```

上面为简写模式，也可以分开写各个属性

```
transition-property: width; 
transition-duration: 1s;
transition-timing-function: linear;
transition-delay: 2s;
1234
```

## 五、transform 转换

`transform`属性允许你旋转，缩放，倾斜或平移给定元素

`transform-origin`：转换元素的位置（围绕那个点进行转换），默认值为`(x,y,z):(50%,50%,0)`

使用方式：

- transform: translate(120px, 50%)：位移
- transform: scale(2, 0.5)：缩放
- transform: rotate(0.5turn)：旋转
- transform: skew(30deg, 20deg)：倾斜

## 六、animation 动画

动画这个平常用的也很多，主要是做一个预设的动画。和一些页面交互的动画效果，结果和过渡应该一样，让页面不会那么生硬

animation也有很多的属性

- animation-name：动画名称
- animation-duration：动画持续时间
- animation-timing-function：动画时间函数
- animation-delay：动画延迟时间
- animation-iteration-count：动画执行次数，可以设置为一个整数，也可以设置为infinite，意思是无限循环
- animation-direction：动画执行方向
- animation-paly-state：动画播放状态
- animation-fill-mode：动画填充模式

## 七、渐变

颜色渐变是指在两个颜色之间平稳的过渡，`css3`渐变包括

- linear-gradient：线性渐变

> background-image: linear-gradient(direction, color-stop1, color-stop2, …);

- radial-gradient：径向渐变

> linear-gradient(0deg, red, green);

## 八、其他

关于`css3`其他的新特性还包括`flex`弹性布局、`Grid`栅格布局，这两个布局在以前就已经讲过，这里就不再展示

除此之外，还包括多列布局、媒体查询、混合模式等等…

# 三十八、怎么理解闭包

在讲解[闭包](https://so.csdn.net/so/search?q=%E9%97%AD%E5%8C%85&spm=1001.2101.3001.7020)之前，我们先来了解一下闭包是用来干嘛的，和闭包的由来：

**由来：**

> 我们都知道，js的[作用域](https://so.csdn.net/so/search?q=%E4%BD%9C%E7%94%A8%E5%9F%9F&spm=1001.2101.3001.7020)分两种，全局和局部，基于我们所熟悉的作用域链相关知识，我们知道在js作用域环境中访问变量的权利是由内向外的，内部作用域可以获得当前作用域下的变量并且可以获得当前包含当前作用域的外层作用域下的变量，反之则不能，也就是说在外层作用域下无法获取内层作用域下的变量，同样在不同的函数作用域中也是不能相互访问彼此变量的，而我们想在一个函数内部也有限权访问另一个函数内部的变量，这就产生了闭包

**作用：**

> 可以访问其所在的外部函数中声明的参数和变量，即使在其外部函数被返回（寿命终结）了之后

接下来我们就来看看闭包是什么？

## 一、闭包的概念

**闭包函数：**声明在一个函数中的函数叫做闭包函数。

**闭包：**内部函数总是可以访问其所在的外部函数中声明的参数和变量，即使在其外部函数被返回（寿命终结）了之后。

**闭包的特点：**

-   让外部访问函数内部变量成为可能；
-   局部变量会常驻在内存中；
-   可以避免使用全局变量，防止全局变量污染；
-   会造成内存泄漏（有一块内存空间被长期占用不被释放，参数和变量不参与垃圾回收机制）

## 二、闭包的创建

闭包就是可以创建一个独立的环境，每个闭包里面的环境都是独立的，互不干扰。闭包会发生内存泄漏，**每次外部函数执行的时 候，外部函数的引用地址不同，都会重新创建一个新的地址。**但凡是当前活动对象中有被内部子集引用的数据，那么这个时候，这个数据不删除，保留一根指针给内部活动对象。

**例子1**

~~~javascript
function funA(){
  var a = 10;  // 外部函数的参数;
  return function(){   //闭包函数;
        alert(a);
  }
}
var b = funA();
b();
~~~

这就是一个简单的闭包，可以访问其所在的外部函数中声明的参数和变量。

**例子2** 

~~~javascript
function outerFn(){
  var i = 0; 
  function innerFn(){
      i++;
      console.log(i);
  }
  return innerFn;
}
//每次外部函数执行的时候,都会开辟一块内存空间,外部函数的地址不同，都会重新创建一个新的地址
//开辟新空间1
var inner = outerFn();  
inner();
inner();
inner();
//输出 1 2 3
 
//开辟新空间2
var inner2 = outerFn();
inner2();
inner2();
inner2();   
//输出 1 2 3
~~~

每次外部函数执行的时候，外部函数的引用地址不同，都会重新创建一个新的地址。

**例子3**

~~~javascript
var i = 0;
function outerFn(){
  var j=0;
  function innnerFn(){
       i++;
       j++;
       console.log(i,j);
  }
  return innnerFn;
}
var inner1 = outerFn();
var inner2 = outerFn();
inner1();//1 1
inner2();//2 1
inner1();//3 2
inner2();//4 2
~~~

虽然外部函数的引用地址不同，会重新创建一个新的地址，但是引用了全局变量，全局变量的引用没有改变。

**例子4**

~~~javascript
function fn(){
	var a = 3;
	return function(){
		return  ++a;                                     
	}
}
alert(fn()());  //4
alert(fn()());  //4 
~~~

这是常见的返回闭包函数，每次引用都赋予了新的地址。

**例子5** 

~~~javascript
function outerFn(){
var i = 0;
  function innnerFn(){
      i++;
      console.log(i);
  }
  return innnerFn;
}
var inner1 = outerFn();
var inner2 = outerFn();
inner1();//1
inner2();//1
inner1();//2
inner2();//2
~~~

外部函数被返回（寿命终结）了之后，可以访问其所在的外部函数中声明的参数和变量。

**例子6**

~~~javascript
(function() { 
  var m = 0; 
  function getM() { return m; } 
  function seta(val) { m = val; } 
  window.g = getM; 
  window.f = seta; 
})(); 
f(100);
console.info(g()); //100
~~~

闭包找到的是同一地址中父级函数中对应变量最终的值，前提是已经得出了最终变量和值。

# 三十九、回调函数

## 1.什么是[回调](https://so.csdn.net/so/search?q=%E5%9B%9E%E8%B0%83&spm=1001.2101.3001.7020)函数（callback）呢？

把函数当作一个参数传到另外一个函数中，当需要用这个函数是，再回调运行()这个函数.

回调函数是一段可执行的代码段，它**作为一个参数**传递给其他的代码，其作用是**在需要的时候方便调用**这段（回调函数）代码。（作为[参数传递](https://so.csdn.net/so/search?q=%E5%8F%82%E6%95%B0%E4%BC%A0%E9%80%92&spm=1001.2101.3001.7020)到另外一个函数中，这个作为参数的函数就是回调函数）

理解：函数可以作为一个参数传递到另外一个函数中。

```javascript
    <script>
        function add(num1, num2, callback) {
            var sum = num1 + num2;
            callback(sum);
        }
 
        function print(num) {
            console.log(num);
        }
 
        add(1, 2, print); //3
    </script>
```

分析：add(1, 2, print);中，函数print作为一个参数传入到add函数中，但并不是马上起作用，而是var sum = num1 + num2;运行完之后需要打印输出sum的时候才会调用这个函数。(这个作为参数传递到另外一个函数中，这个作为参数的函数就是回调函数.

匿名回调函数：

```javascript
    <script>
        function add(num1, num2, callback) {
            var sum = num1 + num2;
            callback(sum);
        }
 
        add(1, 2, function (sum) {
            console.log(sum); //=>3
        });
    </script>
```

## 2.回调函数有哪些特点？

1.不会立即执行

回调函数作为参数传递给一个函数的时候，**传递的只是函数的定义并不会立即执行**。和普通的函数一样，**回调函数在调用函数数中也要通过()运算符调用才会执行**。

2.回调函数是一个闭包

回调函数是一个闭包，也就是说它能访问到其外层定义的变量。

3.执行前类型判断

在执行回调函数前最好确认其是一个函数。

```javascript
    <script>
        function add(num1, num2, callback) {
            var sum = num1 + num2;
            //判定callback接收到的数据是一个函数
            if (typeof callback === 'function') {
                //callback是一个函数，才能当回调函数使用
                callback(sum);
            }
        }
    </script>
```

## 3.回调函数中this的指向问题

注意在**回调函数调用时this的执行上下文并不是回调函数定义时的那个上下文，而是调用它的函数所在的上下文。**

举例：

```javascript
    <script>
        function createData(callback){
            callback();
        }
        var obj ={
            data:100,
            tool:function(){
                createData(function(n){
                    console.log(this,1111);  //window 1111
                })   
            }
        }
        obj.tool();
    </script>
```

分析：this指向是 **离它最近的或者嵌套级别的 function/方法的调用者**，这里离它最近的function是

function(n)，会回到上面的callback()中，这时候调用者就不是obj而是window。

 解决回调函数this指向的方法1：箭头函数

> 回调函数（**若回调函数是普通函数时**）当参数传入另外的函数时，若不知道这个函数内部怎么调用回调函数，就会出现回调函数中的this指向不明确的问题（就比如上面例子中this指向的不是obj而是window）。所以 把**箭头函数当回调函数，然后作为参数传入另外的函数中就不会出现this指向不明的问题**。

```javascript
    <script>
        function createData(callback){
            callback();
        }
        var obj ={
            data:100,
            tool:function(){
                createData((n)=>{
                    this.data = n;
                })   
            }
        }
        obj.tool();
        console.log(obj.data); 
    </script>
```

 分析:回调函数用箭头函数写之后，this指向很明确，就是 离它最近的或者嵌套级别的 function/方法的调用者，所以这里是 obj 。

解决回调函数this指向的方法2：var self = this;

```javascript
    <script>
        function createData(callback){
            callback(999);
        }
        var obj ={
            data:100,
            tool:function(){
                var self = this;   //这里的this指向obj，然后当一个变量取用
                createData(function(n){
                    self.data = n;
                })   
            }
        }
        obj.tool();
        console.log(obj.data);
    </script>
```

## 4.为什么要用到回调函数？

有一个非常重要的原因 —— **JavaScript 是事件驱动的语言**。这意味着，**JavaScript 不会因为要等待一个响应而停止当前运行，而是在监听其他事件时继续执行**。来看一个基本的例子：

```javascript
    <script>
        function first() {
            console.log(1);
        }
 
        function second() {
            console.log(2);
        }
 
        first();
        second();
    </script>
```

 分析:正如你所料，`first` 函数首先被执行，随后 `second` 被执行 —— 控制台输出:1  2

但如果**函数 first 包含某种不能立即执行的代码**会如何呢？例如我们必须发送请求然后等待响应的 API 请求？为了模拟这种状况，我们将使用 `setTimeout`，它是一个在一段时间之后调用函数的 JavaScript 函数。我们将函数延迟 500 毫秒来模拟一个 API 请求，新代码长这样：

```javascript
    <script>
        function first() {
            // 模拟代码延迟
            setTimeout(function () {  //所以function(){console.log(1)}是回调函数
                console.log(1);
            }, 500);
        }
 
        function second() {
            console.log(2);
        }
 
        first();
        second();
    </script>
```

分析:这里 function(){console.log(1)}函数当作一个参数传入setTimeout函数中，因为setTimeout是官方提供得一个函数，里面有很多复杂的业务程序，所以函数 function(){console.log(1)}传入后，不一定马上运行，要setTimeout里面要运行到function(){console.log(1)}时才会运行该函数参数，那是不是整个程序就一直等setTimeout运行？不是的！！！

整个程序运行结果为: 2  1 ,并不是原先的1 2 .**即使我们首先调用了 first() 函数，我们记录的输出结果却在 second() 函数之后。**

这不是 JavaScript 没有按照我们想要的顺序执行函数的问题，而是 **JavaScript 在继续向下执行 second() 之前没有等待 first() 响应**的问题。**回调正是确保一段代码执行完毕之后再执行另一段代码的方式**。

## 5.回调函数和异步操作的关系是什么？回调函数是异步么？

> **定义：**[回调](https://so.csdn.net/so/search?q=%E5%9B%9E%E8%B0%83&spm=1001.2101.3001.7020)函数被认为是一种**高级函数**，一种被作为参数**传递**给另一个函数的高级函数。回调函数的**本质是一种模式**(一种解决常见问题的模式)，因此回调函数也被称为**回调模式**。 
>
> **简而言之：一个函数在另一个函数中被调用。而且可以当参数传给其他函数。**

所以： **回调函数和异步操作的关系是没有关系**！！！ 

那为什么很多的异步操作都有回填函数啊？？

问：你所知道的异步操作，是回调的作用么？？？  并不是。

回调：更多的可以理解为一种业务逻辑把           异步编程：JS代码的执行顺序       

简单理解：**callback 顾名思义  打电话回来的意思**

eg1：你点外卖，刚好你要吃的食物没有了，于是你在店老板那里留下了你的电话，过了几天店里有了，店员就打了你的电话，然后你接到电话后就跑到店里买了。在这个例子里，你的电话号码就叫回调函数，你把电话留给店员就叫登记回调函数，店里后来有货了叫做触发了回调关联的事件，店员给你打电话叫做调用回调函数，你到店里去取货叫做响应回调事件。

eg2：再比如，你发送一个axios 请求，请求成功之后，触发成功的回调函数，请求失败触发失败的回调函数。这里面的回调函数更像是一个工具，后台通过这个工具告诉你，你成功了抑或是失败了。**这里面的所有异步操作都和回调没关系，真正的异步是then方法。**

## 6、常见的回调函数

1、setTimeout 定时函数

~~~javascript
setTimeout(function() {
    let a = 0;
    a = 1 + 1;
}, 1000);
~~~

2、点击事件

~~~javascript
<div id="demo">点击</div>
<script>
var aDiv=document.getElementById("demo")
aDiv.addEventListener('click', function(){
	alert(111)
})
~~~

3、Promise

~~~javascript
    function greet(){
    var promise = new Promise(function(resolve,reject){
        var greet = "hello  world";
        resolve(greet);
    });
    return promise;
    }
    greet().then(v=>{
    console.log(v);//*
    })

~~~

4、异步请求

# 四十、原型与原型链

## 一、前言

在js中，原型和[原型链](https://so.csdn.net/so/search?q=%E5%8E%9F%E5%9E%8B%E9%93%BE&spm=1001.2101.3001.7020)是一个很重要的知识点，只有理解了它，我们才能更深刻的理解js，在这里，我们将分成几个部分来逐步讲解。

## 二、[构造函数](https://so.csdn.net/so/search?q=%E6%9E%84%E9%80%A0%E5%87%BD%E6%95%B0&spm=1001.2101.3001.7020)

构造函数和普通函数本质上没什么区别，只不过使用了new关键字创建对象的函数，被叫做了构造函数。构造函数的首字母一般是大写，用以区分普通函数，当然不大写也不会有什么错误。

```javascript
function Person(name, age) {
   	this.name = name;
   	this.age = age;
    this.species = '人类';
    this.say = function () {
        console.log("Hello");
    }
}

let per1 = new Person('xiaoming', 20);
```

## 三、原型对象

在js中，每一个函数类型的数据，都有一个叫做prototype的属性，这个属性指向的是一个对象，就是所谓的原型对象。

![在这里插入图片描述](https://img-blog.csdnimg.cn/57b4ee4d42b744e2b65190e50f5320dc.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl81NjUwNTg0NQ==,size_16,color_FFFFFF,t_70#pic_center)

对于原型对象来说，它有个constructor属性，指向它的构造函数。

![在这里插入图片描述](https://img-blog.csdnimg.cn/9a73b10ce4dc4f21bf809b82239b0e59.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl81NjUwNTg0NQ==,size_16,color_FFFFFF,t_70#pic_center)

那么这个原型对象有什么用呢？最主要的作用就是用来存放实例对象的公有属性和公有方法。

在上面那个例子里species属性和say方法对于所有实例来说都一样，放在构造函数里，那每创建一个实例，就会重复创建一次相同的属性和方法，显得有些浪费。这时候，如果把这些公有的属性和方法放在原型对象里共享，就会好很多。

```javascript
function Person(name, age) {
    this.name = name;
    this.age = age;
}

Person.prototype.species = '人类';
Person.prototype.say = function () {
    console.log("Hello");
}

let per1 = new Person('xiaoming', 20);
let per2 = new Person('xiaohong', 19);

console.log(per1.species); // 人类 
console.log(per2.species); // 人类

per1.say(); // Hello
per2.say(); // Hello
```

可是这里的species属性和say方法不是实例对象自己的，为什么可以直接用点运算符访问？这是因为在js中，对象如果在自己的这里找不到对应的属性或者方法，就会查看构造函数的原型对象，如果上面有这个属性或方法，就会返回属性值或调用方法。所以有时候，我们会用per1.constructor查看对象的构造函数：

```javascript
console.log(per1.constructor); // Person()
```

这个constructor是原型对象的属性，在这里能被实例对象使用，原因就是上面所说的。那如果原型对象上也没有找到想要的属性呢？这就要说到原型链了。

## 四、原型链

说原型链之前，先来了解两个概念：

#### 1. 显示原型

显示原型就是利用**prototype**属性查找原型，只是这个是函数类型数据的属性。

#### 2. 隐式原型

隐式原型是利用__**proto**__属性查找原型，这个属性指向当前对象的构造函数的原型对象，这个属性是对象类型数据的属性，所以可以在实例对象上面使用：

```javascript
console.log(per1.__proto__ === Person.prototype); // true
console.log(per2.__proto__ === Person.prototype); // true
```

根据上面，就可以得出constructor、prototype和__proto__之间的关系了：

![在这里插入图片描述](https://img-blog.csdnimg.cn/e5bdab96716f42d9990a54f4e398dbe2.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl81NjUwNTg0NQ==,size_16,color_FFFFFF,t_70#pic_center)

#### 3. 原型链

既然这个是对象类型的属性，而原型对象也是对象，那么原型对象就也有这个属性，但是原型对象的__proto__又是指向哪呢？

我们来分析一下，既然原型对象也是对象，那我们只要找到对象的构造函数就能知道__proto__的指向了。而js中，对象的构造函数就是**Object()**，所以对象的原型对象，就是Object.prototype。既然原型对象也是对象，那原型对象的原型对象，就也是Object.prototype。不过Object.prototype这个比较特殊，它没有上一层的原型对象，或者说是它的__proto__指向的是**null**。

所以上面的关系图可以拓展成下面这种：

![在这里插入图片描述](https://img-blog.csdnimg.cn/1ccbdee4f468444dae832fb574ec733d.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl81NjUwNTg0NQ==,size_16,color_FFFFFF,t_70#pic_center)

到这里，就可以回答前面那个问题了，如果某个对象查找属性，自己和原型对象上都没有，那就会继续往原型对象的原型对象上去找，这个例子里就是Object.prototype，这里就是查找的终点站了，在这里找不到，就没有更上一层了（null里面啥也没有），直接返回undefined。

可以看出，整个查找过程都是顺着__**proto**__属性，一步一步往上查找，形成了像链条一样的结构，这个结构，就是**原型链**。所以，**\*原型链也叫作隐式原型链***。

正是因为这个原因，我们在创建对象、数组、函数等等数据的时候，都自带一些属性和方法，这些属性和方法是在它们的原型上面保存着，所以它们自创建起就可以直接使用那些属性和方法。

## 五、函数也是一种对象

函数在js中，也算是一种特殊的对象，所以，可以想到的是，函数是不是也有一个__proto__属性？答案是肯定的，既然如此，那就按上面的思路，先来找找函数对象的构造函数。

在js中，所有函数都可以看做是Function()的实例，而Person()和Object()都是函数，所以它们的构造函数就是Function()。Function()本身也是函数，所以Function()也是自己的实例，听起来既怪异又合理，但是就是这么回事。

```javascript
console.log(Person.constructor === Function); // true
console.log(Object.constructor === Function); // true
console.log(Function.constructor === Function); // true
```

既然知道了函数的构造函数，那么函数的__proto__指向我们也就知道了，就是Function.prototype。

```javascript
console.log(Person.__proto__ === Function.prototype); // true
console.log(Object.__proto__ === Function.prototype); // true
console.log(Function.__proto__ === Function.prototype); // true
```

根据这几个结论，我们就能拓展出一张更大的关系图了：

![在这里插入图片描述](https://img-blog.csdnimg.cn/ff422e52ff0f49df80984d36ee01c719.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl81NjUwNTg0NQ==,size_16,color_FFFFFF,t_70#pic_center)

## 六、总结

1. 构造函数是使用了new关键字的函数，用来创建对象，所有函数都是Function()的实例
2. 原型对象是用来存放实例对象的公有属性和公有方法的一个公共对象，所有原型对象都是Object()的实例
3. 原型链又叫隐式原型链，是由__proto__属性串联起来，原型链的尽头是Object.prototype

# 四十一、作用域和作用域链

## 一、什么是[作用域](https://so.csdn.net/so/search?q=%E4%BD%9C%E7%94%A8%E5%9F%9F&spm=1001.2101.3001.7020)？

作用域就是变量的可用性的代码范围，就叫做这个变量的作用域。简单理解，就是在这个范围内，变量是可以使用的，超过这个范围，变量就无法使用，这个范围就是作用域。

作用域分为三种：全局作用域、局部作用域、块级作用域。

- 全局作用域
  顾名思义，全局作用域就是能够在全局使用，可以在代码的任何地方被调用。示例：创建一个拥有全局作用域的变量a

```javascript
var a=0;
function fun(){
	conslie.log(a);//在函数内部访问变量a
}
console.log(a);//在最外层访问变量a
```

- 局部作用域
  局部作用域只能作用于局部的代码片段，常见于函数内部，即函数内创建的变量，只能作用于函数内部，函数外部无法使用函数内部创建的变量。示例：创建一个拥有局部作用域的变量b

```javascript
function fun(){
	var b=1;
	console.log(b);//1
}
console.log(b);//b is not defined
```

- 块级作用域
  块级作用域是es6新增的，使用let关键字创建变量、const关键字创建常量（当然let、const也会有自己的语法规范，这里不过多展开），作用域只存在于{}花括号内。示例：创建一个拥有局部作用域的变量c

```javascript
function fun(){
	let c=1;
	const d=2;
	console.log(c);//1
	console.log(d);//2
}
console.log(c);//c is not defined
```

## 二、什么是作用域链？

当你要访问一个变量时，首先会在当前作用域下查找，如果当前作用域下没有查找到，则返回上一级作用域进行查找，直到找到全局作用域，这个查找过程形成的链条叫做作用域链。

```javascript
var a = 0;
var b = 0;

function fun1() {
	var b = 1;
	function fun2() {
		console.log(b);//1 在当前作用域下没有找到，到上一级作用域中查找
	}
    fun2();
	console.log(b);//1
}
fun1();
console.log(b);//0
```

# 四十二、执行上下文和执行上下文栈

## 1. 变量提升与函数提升

①  变量声明提升：通过var 定义（声明）的变量，在定义语句之前就可以访问到，值为undefined;
②  函数声明提升：通过function声明的函数，在之前就可以直接调用，值：函数定义（对象）

### 1.1 代码体验

> ```javascript
> <script>
>     /* 经典面试题 */
>     var a = 3;
>     function fn() {
>         console.log(a);
>         var a = 4
>     };
>     fn();
>     // 问：输出结果是什么？
>     // 答：输出 undefined
>     /* 分析：上述代码实际运行顺序如下： */
>     var a;
>     a = 3;
>     function fn() {
>         var a;
>         console.log(a);  // 此时根据就近原则输出a的值，而a只声明未赋值，所以为undefined
>         a = 4;
>     };
>     fn();
>  
>     /* 体验变量声明提升和函数声明提升的作用 */
>     console.log(b);   // undefined，未定义前可访问到，变量提升
>     fn2() // 可调用， 存在函数提升
>     fn3()  // 不可调用，只是存在变量提升，没有函数提升
>     var b=3;
>     function fn2(){
>         console.log('fn2()');
>     };
>     var fn3=function(){
>         console.log('fn3()');
>     };
> </script>
> ```
>
> **注意**：只有通过function声明的函数才具有提升功能，通过赋值操作设置的函数表达式并不具有，只能在声明函数后，才可进行调用，如上述代码中的函数fn3，不可在前调用。

那么问题来了：**变量提升和函数提升是如何产生的呢**？这就涉及到执行上下文的相关知识了...

## 2. 执行上下文

JS代码根据位置可以分为：全局代码 和 函数(局部)代码。从而执行上下文也就分为全局执行上下文和函数执行上下文。

### 2.1 全局执行上下文

① 在执行全局代码前，将window确定为全局执行上下文
② 对全局数据进行[预处理](https://so.csdn.net/so/search?q=%E9%A2%84%E5%A4%84%E7%90%86&spm=1001.2101.3001.7020)（预解析）：

  1）var定义的全局变量==> undefined，添加为window的属性
  2）function声明的全局函数==>赋值(fun)，添加为window的方法
  3）this==>赋值（window）

③ 开始执行全局代码

### 2.2 函数执行上下文

① 在调用函数，准备执行函数体之前，创建对应的函数执行上下文对象（虚拟的，存在于栈中）
② 对局部数据进行预处理（预解析）：

  1）形参变量==>赋值（实参）==>添加为执行上下文的属性
  2）arguments==>赋值（实参列表），添加为执行上下文的属性
  3）var定义的局部变量==> undefined，添加为执行上下文的属性
  2）function声明的函数==>赋值(fun)，添加为执行上下文的方法
  3）this==>赋值（调用函数的对象）

③ 开始执行函数体代码

### 2.3 代码体验

> ```javascript
> <script>
>     // 1. 全局执行上下文--window
>     console.log(a1); // undefined
>     console.log(window.a1); // // undefined
>     console.log(a1 === window.a1); // true，说明全局执行上下文window对var定义的变量a1进行了预处理，将其添加为它的属性
>     a2(); // a2()调用成功
>     console.log(a2() === window.a2()); //true，说明把function声明的函数a2添加为window的方法
>     console.log(this); // window对象，对this赋值
>  
>     var a1 = 3;
>     function a2() {
>         console.log('a2()调用成功');
>     };
>     console.log(a1); // 3， 开始执行全局代码之后，此时的a1被赋值为3，当然其依旧为window的属性
>  
>     // 2. 函数执行上下文
>     function fn(a1) {
>         // 预处理阶段是在调用函数后，执行函数体前进行
>         console.log(a1); // 2，把实参的值赋给形参
>         console.log(a2);  // undefined，var定义的局部变量a2添加为执行上下文的属性
>         a3(); // a3()调用成功
>         console.log(this);  // window，因为此函数是直接调用的，所以调用者为window
>         console.log(arguments);  // 伪数组[2,3]
>         
>         var a2 = 4;
>         function a3() {
>             console.log('a3()调用成功');
>         };
>     };
>     fn(2, 3);
> </script>
> ```

## 3. 执行上下文栈

① 在全局代码执行前，**JS引擎**就会**创建一个栈**来存储管理所有的执行上下文对象；
② 在全局执行上下文（window）确定后，将其添加到栈中（压栈），window永远放在栈的最底层
③ 在函数执行上下文创建后，将其添加到栈中（压栈）
④ 在当前函数执行完后，将栈顶的对象移除（出栈）
③ 当所有的代码执行完后，栈中只剩下window

![img](https://img-blog.csdnimg.cn/6ab8acd58c10489c96093a682f81a0eb.jpeg)

###  3.1 代码体验

> ```javascript
> <script>
>                             // 1. 进入全局执行上下文
>     var a = 10;
>     var bar = function(x) {
>         var b = 5;
>         foo(x + b);       // 3. 进入foo函数执行上下文
>     };
>     var foo = function(y) {
>         var c = 5;
>         console.log(a + c + y);
>     };
>     bar(10);              // 2. 进入bar函数执行上下文
> </script>
> ```
>
> 执行上下文栈中的执行顺序图：
>
> ![img](https://img-blog.csdnimg.cn/915bdae00d0e4028a50e46040cc17567.png)
>
> **注意：**
>
> ① 每调用一次函数，就会对应产生这个函数的执行上下文对象；
>
> ② 函数执行完函数体代码后，就会被销毁，即从内存中消失，也就不再存在于上下文执行栈中，即出栈。

# 四十三、对象的创建模式

## 方式一：Object[构造函数](https://so.csdn.net/so/search?q=%E6%9E%84%E9%80%A0%E5%87%BD%E6%95%B0&spm=1001.2101.3001.7020)模式

概括：先创建空的Object对象，再动态添加属性和方法

适用场景：起始时对象的内部数据是不确定的

缺点：语句过多

```javascript
var p =new Object();
p.name ='javascript';
p.age = 12;
p.setName = function(){
 //代码块
}
```

## 方式二：对象字面量创建模式

概括：使用括号{}创建对象，同时指定属性和方法。

适用场景：起始时对象的内部函数是确定的。

缺点：如果创建多个对象，会有重复代码。

```javascript
var p = {
     name:"javascript",
     age:12;
     setName:function(){
     //代码块
    }
}
```

## 方式三：工厂模式

概括：通过工厂函数动态创建对象并返回。(所谓工厂函数，就是返回一个对象的函数，函数名自定义)

适用场景：需要创建多个对象

缺点：对象都是Object类型

```javascript
function CreatPerson(name,age){
  var obj = {
   name:name,
   age:age,
   setName:function(name){
     this.name=name;
   } 
  }
  return obj;
}
//创建两个人
var p1 = CreatPerson('Tom',12);
var p2 = CreatPerson('Jack',13);
 
 
function CreatStudent(name,mark){
  var obj = {
    name:mame,
    mark:mark
 }
 return obj;
}
//创建一个学生
var s =CreatStudent('jerry',14);
```

创建的这些对象都是Object类型的，有时候我们需要区分类型

## 方式四：自定义构造函数

概括：通过new 创建对象

适用场景：需要创建多个不同类型的对象

缺点：每个对象都有相同的数据，浪费内存

```javascript
function CreatPerson(name,age){
  var obj = {
   this.name:name,
   this.age:age,
   this.setName:function(name){
     this.name=name;
   } 
 }
var p1 = new Person('tom',12);
p1.setName =('jack');
console.log(p1 instanceof Person);
//true
```

## 方式五：构造函数加原型的组合模式

概括：自定义构造函数，属性在函数中初始化，方法添加到原型上

适用场景：需要创建多个类型确定的对象

```javascript
function CreatPerson(name,age){
  var obj = {
   this.name:name,
   this.age:age,
 }
Person.prototype.setName = function(name){
     this.name=name;
} 
//写在原型对象中的方法，还是谁调用就指向谁，如果是调用者是实例对象，这个this就会指向实例对象
var p1 = new Person('tom',12);
p1.setName=('jack');
```

 最后声明：

并不是说最后一种方式一定是最好的，

每一种对象创建模式都有优缺点，选择合适的方式才能够最大化的省内存。

# 四十三、继承模式

### **1、原型链继承：**

构造函数A通过new生成a对象，使得A.prototype指向对象b，而对象b由构造函数B生成，这样就形成了原型链的继承关系

单一，所以实例都会继承到父类实例的属性

a.__proto__ --> A.prototype === b b.__proto__ --> B.prototype

```javascript
    Grand.prototype.lastName = 'Cheng';
    function Grand() {
 
    }
 
    var grand = new Grand();
 
    Father.prototype = grand;
    function Father() {
      this.name = 'ming';
    }
 
    var father = new Father();
 
    Son.prototype = father;
    function Son() {
 
    }
 
    var son = new Son();
 
    console.log(son.lastName);   // 'Cheng'
    console.log(son.name);     // 'ming'
```

 

### **2、借用构造函数：**

通过call或者apply，在A的构造函数中执行调用B构造函数

执行了两次方法（缺点）

同原型链继承，过多的继承了无用的属性（缺点）

```javascript
    function Person(name, age, sex) {
      this.name = name;
      this.age = age;
      this.sex = sex;
    }
 
    function Student (name, age, sex, grade) {
      Person.call(this, name, age, sex);
      this.grade = grade;
    }
 
    var student = new Student();
```

 

### **3、共享原型：**

使得A.prototype = B.prototype

缺少个性化，如若想给A.prototype上面加自己的属性或方法，B.prototype也会加上

```javascript
    Father.prototype.lastName = 'cheng';
    function Father() {
 
    }
    function son() {
 
    }
    // son.prototype = Father.prototype;
    function inherit(Target, Origin) {
      Target.prototype = Origin.prototype;
    }
    
    inherit(Son, Father);
 
    var son = new Son();
    console.log(son.lastName);  // 'cheng'
```

 

### **4、圣杯模式：（继承模式集大成者，较完美解决方案）**

共享原型和原型链组合的方式

参数接收的分别是要继承的构造函数和被继承的构造函数，之所以参数设定构造函数，是因为这样之后由改构造函数产生的对象都会被继承

```javascript
    // 接着共享原型改造 inherit
    function inherit(Target, Origin) {
      function F() {};
      F.prototype = Origin.prototype;
      Target.prototype = new F(); 
    // 至此功能已经实现，下面是便利使用
      Target.prototype.constuctor = Target;     //由于继承了Origin，target的结构体变成了Origin的，所以要重新赋值
      Target.prototype.uber = Origin.prototype;   //设置uber  当想知道继承自谁时，直接调用即可
    }
 
    //雅虎精简版
    var inherit = (function() {
      var F = function() {};
      return function(Target, Origin) {
        F.prototype = Origin.prototype;
        Target.prototype = new F();
        Target.prototype.constuctor = Target;
        Target.prototype.uber = Origin.prototype;
      }
    }());
```

# 四十四、事件机制

### 1、定义

event loop翻译出来就是事件循环，可以理解为实现异步的一种方式，我们来看看event loop在HTML Standard中的定义章节：
**第一句话：**

> 为了协调事件，用户交互，脚本，渲染，网络等，用户代理必须使用本节所述的event loop。

------

**事件，用户交互，脚本，渲染，网络这些都是我们所熟悉的东西，他们都是由event loop协调的。触发一个click事件，进行一次ajax请求，背后都有event loop在运作。**

------

### 2、基础知识

#### 执行栈

javaScript是单线程，也就是说只有一个主线程，主线程有一个栈，每一个函数执行的时候，都会生成新的execution context（执行上下文），执行上下文会包含一些当前函数的参数、局部变量之类的信息，它会被推入栈中， running execution context（正在执行的上下文）始终处于栈的顶部。当函数执行完后，它的执行上下文会从栈弹出。

#### 宏任务与微任务

**宏任务**，macrotask,也叫tasks，一些异步任务的回调会依次进入macrotask queue

等待后续被调用，这些异步任务包括:

- setTimeout
- setInterval
- setImmediate（Node独有）
- requestAnimationFrame（浏览器独有）
- I/O 文件读取 网络请求
- UI rendering(浏览器独有)
- script（整体）

**微任务**，microtask，也叫jobs。另一些异步任务的回调会依次进入macrotask queue，等待后续被调用，这些异步任务包括:

- process.nextTick（Node独有）
- Promise.then()
- Object.observe()
- MutationObserver (注：只针对浏览器和Nodejs)

**注意：Promise构造函数里的代码是同步执行的**

------

以上就是需要记忆的内容。

### 3、从图开始讲起

![在这里插入图片描述](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMxLnpoaW1nLmNvbS84MC92Mi01MzljZmIzNjVmMjY0NmJkNzI0ZGEzOTJkNzc5NDc2Y183MjB3LmpwZw?x-oss-process=image/format,png)
**导图要表达的内容用文字来表述的话：**

- 一开始执行栈空,我们可以把执行栈认为是一个存储函数调用的栈结构，遵循先进后出的原则。micro 队列空，macro 队列里有且只有一个 script 脚本（整体代码）。
- 全局上下文（script 标签）被推入执行栈，同步代码执行。在执行的过程中，会判断是同步任务还是异步任务，通过对一些接口的调用，可以产生新的 macro-task 与 micro-task，它们会分别被推入各自的任务队列里。同步代码执行完了，script 脚本会被移出 macro 队列，这个过程本质上是队列的 macro-task 的执行和出队的过程。
- 上一步我们出队的是一个 macro-task，这一步我们处理的是 micro-task。但需要注意的是：当 macro-task 出队时，任务是一个一个执行的；而 micro-task 出队时，任务是一队一队执行的。因此，我们处理 micro 队列这一步，会逐个执行队列中的任务并把它出队，直到队列被清空。
- 执行渲染操作，更新界面
- 检查是否存在 Web worker 任务，如果有，则对其进行处理
- 上述过程循环往复，直到两个队列都清空

**我们总结一下，每一次循环都是一个这样的过程：**

![在这里插入图片描述](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWM0LnpoaW1nLmNvbS92Mi04YzE3ZTJiOTVlMDM3NDE4NmM2NzJkNGQ4NGIyZGFiM19yLmpwZw?x-oss-process=image/format,png#pic_center)
**当某个宏任务执行完后,会查看是否有微任务队列。如果有，先执行微任务队列中的所有任务，如果没有，会读取宏任务队列中排在最前的任务，执行宏任务的过程中，遇到微任务，依次加入微任务队列。栈空后，再次读取微任务队列里的任务，依次类推。**

> 我们不禁要问了，那怎么知道主线程执行栈为空啊？js引擎存在monitoring process进程，会持续不断的检查主线程执行栈是否为空，一旦为空，就会去Event Queue那里检查是否有等待被调用的函数。

我们从代码开始：

```javascript
console.log('start')

setTimeout( function () {
  console.log('setTimeout')
}, 0 )

Promise.resolve().then(function() {
  console.log('promise1');
}).then(function() {
  console.log('promise2');
});

console.log('end')

// start
// end
// promise1
// promise2
// setTimeout
```

**分析:**

- 全局上下文（script标签）被推入执行栈，先执行所有的同步任务，也就是打印start，end，通过setTimeout1被推入宏任务（macrotask Queue），Promise.then()被推入微任务（microtask Queue）队列
- 执行栈为空，先去微任务（microtask Queue）队列取任务，依次放入执行栈中，先输出promise1，放回值是undefined，紧接着又将Promise.then()推入微任务（microtask Queue）队列，此时执行栈为空，再去微任务队列中找，找到还有一个微任务，将它放进执行栈中，输出promise2，接着所有的微任务执行完。
- 宏任务队列中存在任务为执行，所以就取其中一个任务，放进执行栈中，输出setTimeout，接着栈为空。
- 接着再去微任务队列中找是否有未执行的任务，依次全部推入执行栈。
- 然后再去宏任务队列中取，只取一个，如此反复循环，直到最后执行栈为空。

#### Event Loop 处理模型

前面简单介绍了 JavaScript Runtime 的整个运行流程，而 Event Loop 作为其中的重要一环，它的每一次循环过程也相当复杂，因此将它单独拿出来介绍。下面我会尽量保持 HTML 标准中对处理模型（Processing Model）的定义，并尽量简化，步骤如下（3 步）：

1. 执行 Task：从 Task Queue 中取出最老的一个 Task 并执行；如果没有 Task，直接跳过。
2. 执行 Microtasks：遍历 Microtask Queue 并执行所有 Microtask（参考 Perform a microtask checkpoint）。
3. 进入 Update the rendering（更新渲染）阶段：

> 1. 设置 Performance API 中 now() 的返回值。Performance API 属于 W3C High Resolution Time API 的一部分，用于前端性能测量，能够细粒度的测量首次渲染、首次渲染内容等的各项绘制指标，是前端性能追踪的重要技术手段，感兴趣的同学可关注。
> 2. 遍历本次 Event Loop 相关的 Documents，执行更新渲染。在迭代执行过程中，浏览器会根据各种因素判断是否要跳过本次更新。
> 3. 当浏览器确认继续本次更新后，处理更新渲染相关工作：
>    3.1 触发各种事件：Resize、Scroll、Media Queries、CSS Animations、Fullscreen API。
>    3.2 执行 animation frame callbacks，window.requestAnimationFrame 就在这里。
>    3.3 更新 intersection observations，也就是 Intersection Observer API（可用于图片懒加载）。更新渲染和 UI，将最终结果提交到界面上。

至此，Event Loop 的一次循环结束。。。还是用一张简图来描述吧（process.nextTick 被特意标注出来以示区别）。

![在这里插入图片描述](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMyLnpoaW1nLmNvbS92Mi0zOGU1M2I5ZGYyZDEzZTk0NzBjMzExMDFiYjgyZGJiMV9yLmpwZw?x-oss-process=image/format,png#pic_center)

### 4、Node 中的 Event Loop

node简介

Node 中的 Event Loop 和浏览器中的是完全不相同的东西。Node.js 采用 V8 作为 js 的解析引擎，而 I/O 处理方面使用了自己设计的 libuv，libuv 是一个基于事件驱动的跨平台抽象层，封装了不同操作系统一些底层特性，对外提供统一的 API，事件循环机制也是它里面的实现（下文会详细介绍）。

**Node.js 的运行机制如下:**

- V8 引擎解析 JavaScript 脚本。
- 解析后的代码，调用 Node API。
- libuv 库负责 Node API 的执行。它将不同的任务分配给不同的线程，形成一个 Event Loop（事件循环），以异步的方式将任务的执行结果返回给 V8 引擎。
- V8 引擎再将结果返回给用户。

6个阶段

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020061021514474.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMTI3OTIx,size_16,color_FFFFFF,t_70)

> 上述的五个阶段都是按照先进先出的规则执行回调函数。按顺序执行每个阶段的回调函数队列，直至队列为空或是该阶段执行的回调函数达到该阶段所允许一次执行回调函数的最大限制后，才会将操作权移交给下一阶段。

**每个阶段的简单概要：**

- timers: 执行setTimeout() 和 setInterval() 预先设定的回调函数。
- I/O callbacks: 大部分执行都是timers 阶段或是setImmediate() 预先设定的并且出现异常的回调函数事件。
- idle, prepare: nodejs 内部函数调用。
- poll: 搜寻I/O事件，nodejs进程在这个阶段会选择在该阶段适当的阻塞一段时间。
- check: setImmediate() 函数会在这个阶段执行。
- close callbacks: 执行一些诸如关闭事件的回调函数，如socket.on(‘close’, …)

**Node.js的Event Loop过程：**

- 执行全局的Script代码
- 执行microtask微任务，先执行所有Next Tick Queue中所有任务，再执行Other Microtask Queue中所有的任务
- 开始实行macrotask宏任务，共6个阶段，**从第1个阶段开始执行相应的每一个阶段macrotask中所有任务**，（注意：这里是所有每个阶段宏任务的所有任务，在浏览器的Event Loop中只取宏任务的第一个任务执行） 每一阶段的macrotask任务执行完成后，开始执行微任务，也就是步骤二
- Timers Queue -> 步骤2 -> I/O Queue -> 步骤2 -> Check Queue -> 步骤2 -> Close Callback Queue -> 步骤2 -> Timers Queue

### 5、浏览器和Node中Event Loop有什么不同呢

1. 浏览器和Node.js的Event Loop是不同的
2. Node.js可以理解成4个宏任务队列和2个微任务队列，但是执行宏任务有6个阶段。
3. Nodejs中，先执行全局的Script代码，执行完同步代码调用栈清空后，先从Next Tick Queue中依次取出所有的任务放入调用栈中执行，再Other Microtask Queue中依次取出所有的任务放入调用栈中所有的任务。然后开始宏任务的6个阶段，每个阶段将取出宏任务队列中所有任务来执行（浏览器每次只取一个），每个宏任务阶段执行完毕后，开始执行微任务，再开始执行下一个阶段宏任务，以此构成事件循环。

接下我们通过一个例子来说明两者区别：

```javascript
setTimeout(()=>{
    console.log('timer1')
    Promise.resolve().then(function() {
        console.log('promise1')
    })
}, 0)
setTimeout(()=>{
    console.log('timer2')
    Promise.resolve().then(function() {
        console.log('promise2')
    })
}, 0)
```

> 浏览器端运行结果：timer1=>promise1=>timer2=>promise2

**浏览器端的处理过程如下：**

![在这里插入图片描述](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMyLnpoaW1nLmNvbS92Mi1kMWNhMGQ2YjEzNTAxMDQ0YTVmNzRjOTliZWNiY2QzZF9iLndlYnA?x-oss-process=image/format,png#pic_center)

> Node 端运行结果：timer1=>timer2=>promise1=>promise2

- 全局脚本（main()）执行，将 2 个 timer 依次放入 timer 队列，main()执行完毕，调用栈空闲，任务队列开始执行；
- 首先进入 timers 阶段，执行 timer1 的回调函数，打印 timer1，并将 promise1.then 回调放入 microtask 队列，同样的步骤执行 timer2，打印 timer2；
- 至此，timer 阶段执行结束，event loop 进入下一个阶段之前，执行 microtask 队列的所有任务，依次打印 promise1、promise2

**Node 端的处理过程如下：**
![在这里插入图片描述](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMxLnpoaW1nLmNvbS92Mi05NjMwOTBiZDNiNjgxZGUzMzEzYjQ0NjZiMjM0ZjRmMF9iLndlYnA?x-oss-process=image/format,png#pic_center)

# 四十四、定时器的执行

JS的定时器目前有三个：setTimeout、setInterval和setImmediate。

**定时器也是一种异步任务，通常浏览器都有一个独立的定时器模块，定时器的延迟时间由定时器模块来管理, 当某个定时器到了可执行状态，就会被加入到主线程之中。**　　

### **setTimeout**

　　setTimeout(fn, x)表示延迟x毫秒之后执行fn，**但是使用的时候，千万不要太相信预期，延迟的时间严格来说总是大于x毫秒的,至于大多少，就要看当时JavaScript的执行情况了。**

　　另外，如果多个定时器如果没有及时清除，就会存在干扰，总之，及时清除已经不需要的定时器是一个好的习惯。

> **HTML5规范规定了最小延迟时间不得小于4ms，即如果x小于4，会被当做4来处理。**

　  **setTimeout注册的函数fn会交给浏览器的定时模块来处理，延迟时间到了就会添加fn这个回调函数到主进程队列当中，但是如果主进程队列前面刚好还有正在执行的没有执行完的代码，则又要花费一定的时间去等待主进程，然后再执行fn，所以实际的时间往往是更长的。**

　　 如果fn之前在主进程中刚好有一个超级大的循环，那么延迟就不是一点了： 

```javascript
(function testSetTimeout() {
    const label = 'setTimeout';
    console.time(label);
    setTimeout(() => {
        console.timeEnd(label);
    }, 10);
    for(let i = 0; i < 10000000000; i++) {}
})();
```

　　最后执行结果如下：

```javascript
setTimeout: 12131.85986328125ms
```

　　**即在函数中**，**虽然我们设置了在10ms之后执行函数，但是实际上却是 12131ms，近千倍的差距就是因为主进程上还有没有执行完的任务。**下面我们进行相应的解析：

- 首先在**主进程上同步执行 第一句、第二句代码**。
-  接着，**遇到了setTimeout函数，异步执行。**即首先将异步执行的回调函数和这个事件放在任务队列里，然后将时间告诉给浏览器的定时模块。 
- 然后迅速开始执行下面的for循环，由于这个循环很大，所以执行很久。**在这个过程中， 浏览器的定时模块在10ms之后就开始把这个回调函数放在了主线程的执行队列中。**
- 但是主线程上的for还没有执行完毕，所以，回调函数就需要一直等着，知道for执行完毕，主线程队列上的回调函数开始执行。 所以时间有了一个很大的延迟。

```javascript
      function fda() {
          for (var i = 0; i < 999; i++) {
              console.log(4);
              setTimeout(function () {
                console.log(5);
              }, 10);
          }
      }
      fda();
```

　　比如上面这段代码，就是先输出所有的4，然后再输出所有的5， 因为主线程的任务没有执行完，放在任务队列中的回调函数也就不会立即执行。

### setInterval

　　setInterval的实现机制跟setTimeout类似，只不过setInterval是重复执行的。

　　对于setInterval(fn, 100)容易**产生一个误区： 执行完fn之后的100ms立即再次执行fn。** 

　　**事实上，setInterval交给了浏览器的定时模块，定时模块并不会顾及fn的上一次的执行结果，而是每隔100ms就把fn放在主线程上，但是主线程上是否有任务在执行而不让fn执行呢 ?这个浏览器的定时模块就不管了，我们也无法确定。**　　　

### setImmediate

　　这算一个比较新的定时器，目前IE11/Edge支持、Nodejs支持，Chrome不支持，其他浏览器未测试。

　　这个api的支持性并不是很好。

　   从API名字来看很容易联想到setTimeout(0)，不过setImmediate应该算是setTimeout(0)的替代版。

　　在IE11/Edge中，setImmediate延迟可以在1ms以内，而setTimeout有最低4ms的延迟，所以setImmediate比setTimeout(0)更早执行回调函数。不过在Nodejs中，两者谁先执行都有可能，原因是Nodejs的事件循环和浏览器的略有差异。

　　很明显，setImmediate设计来是为保证让代码在下一次事件循环执行，以前setTimeout(0)这种不可靠的方式可以丢掉了

　　总之，记住setImmediate会比setTimeout(fn, 0)更快、更及时一点就么有错了。

# 四十五、Web Workers

以前我们总说，JS是单线程没有多线程，当JS在页面中运行长耗时同步任务的时候就会导致页面假死影响用户体验，从而需要设置把任务放在任务队列中；执行任务队列中的任务也并非多线程进行的，然而现在HTML5提供了我们前端开发这样的能力 - [Web Workers API](https://link.zhihu.com/?target=https%3A//developer.mozilla.org/zh-CN/docs/Web/API/Web_Workers_API)，我们一起来看一看 Web Worker 是什么，怎么去使用它，在实际生产中如何去用它来进行产出。

**1. 概述**

Web Workers 使得一个Web应用程序可以在与主执行线程分离的后台线程中运行一个脚本操作。这样做的好处是可以在一个单独的线程中执行费时的处理任务，从而允许主（通常是UI）线程运行而不被阻塞。

它的作用就是给JS创造多线程运行环境，允许主线程创建worker线程，分配任务给后者，主线程运行的同时worker线程也在运行，相互不干扰，在worker线程运行结束后把结果返回给主线程。这样做的好处是主线程可以把计算密集型或高延迟的任务交给worker线程执行，这样主线程就会变得轻松，不会被阻塞或拖慢。这并不意味着JS语言本身支持了多线程能力，而是浏览器作为宿主环境提供了JS一个多线程运行的环境。

不过因为worker一旦新建，就会一直运行，不会被主线程的活动打断，这样有利于随时响应主线程的通性，但是也会造成资源的浪费，所以不应过度使用，用完注意关闭。或者说：如果worker无实例引用，该worker空闲后立即会被关闭；如果worker实列引用不为0，该worker空闲也不会被关闭。

**2. 使用**

**2.1 限制**

worker线程的使用有一些注意点

1. 同源限制
   worker线程执行的脚本文件必须和主线程的脚本文件同源，这是当然的了，总不能允许worker线程到别人电脑上到处读文件吧
2. 文件限制
   为了安全，worker线程无法读取本地文件，它所加载的脚本必须来自网络，且需要与主线程的脚本同源
3. DOM操作限制
   worker线程在与主线程的window不同的另一个全局上下文中运行，其中无法读取主线程所在网页的DOM对象，也不能获取 `document`、`window`等对象，但是可以获取`navigator`、`location(只读)`、`XMLHttpRequest`、`setTimeout族`等浏览器API。
4. 通信限制
   worker线程与主线程不在同一个上下文，不能直接通信，需要通过`postMessage`方法来通信。
5. 脚本限制
   worker线程不能执行`alert`、`confirm`，但可以使用 `XMLHttpRequest` 对象发出ajax请求。

**2.2 例子**

在主线程中生成 Worker 线程很容易：

```javascript
var myWorker = new Worker(jsUrl, options)
```

Worker()构造函数，第一个参数是脚本的网址（必须遵守同源政策），该参数是必需的，且只能加载 JS 脚本，否则报错。第二个参数是配置对象，该对象可选。它的一个作用就是指定 Worker 的名称，用来区分多个 Worker 线程。

```javascript
// 主线程

var myWorker = new Worker('worker.js', { name : 'myWorker' });

// Worker 线程
self.name // myWorker
```

关于api什么的，直接上例子大概就能明白了，首先是worker线程的js文件：

```javascript
// workerThread1.js

let i = 1

function simpleCount() {
  i++
  self.postMessage(i)
  setTimeout(simpleCount, 1000)
}

simpleCount()

self.onmessage = ev => {
  postMessage(ev.data + ' 呵呵~')
}
```

在HTML文件中的body中：

```javascript
<!--主线程，HTML文件的body标签中-->

<div>
  Worker 输出内容：<span id='app'></span>
  <input type='text' title='' id='msg'>
  <button onclick='sendMessage()'>发送</button>
  <button onclick='stopWorker()'>stop!</button>
</div>

<script type='text/javascript'>
  if (typeof(Worker) === 'undefined')	// 使用Worker前检查一下浏览器是否支持
    document.writeln(' Sorry! No Web Worker support.. ')
  else {
    window.w = new Worker('workerThread1.js')
    window.w.onmessage = ev => {
      document.getElementById('app').innerHTML = ev.data
    }
    
    window.w.onerror = err => {
      w.terminate()
      console.log(error.filename, error.lineno, error.message) // 发生错误的文件名、行号、错误内容
    }
    
    function sendMessage() {
      const msg = document.getElementById('msg')
      window.w.postMessage(msg.value)
    }
    
    function stopWorker() {
      window.w.terminate()
    }
  }
</script>
```

可以自己运行一下看看效果，上面用到了一些常用的api

主线程中的api，`worker`表示是 Worker 的实例：

- `worker.postMessage`: 主线程往worker线程发消息，消息可以是任意类型数据，包括二进制数据
- `worker.terminate`: 主线程关闭worker线程
- `worker.onmessage`: 指定worker线程发消息时的回调，也可以通过`worker.addEventListener('message',cb)`的方式
- `worker.onerror`: 指定worker线程发生错误时的回调，也可以 `worker.addEventListener('error',cb)`

Worker线程中全局对象为 `self`，代表子线程自身，这时 `this`指向`self`，其上有一些api：

- `self.postMessage`: worker线程往主线程发消息，消息可以是任意类型数据，包括二进制数据
- `self.close`: worker线程关闭自己
- `self.onmessage`: 指定主线程发worker线程消息时的回调，也可以`self.addEventListener('message',cb)`
- `self.onerror`: 指定worker线程发生错误时的回调，也可以 `self.addEventListener('error',cb)`

注意，`w.postMessage(aMessage, transferList)` 方法接受两个参数，`aMessage` 是可以传递任何类型数据的，包括对象，这种通信是拷贝关系，即是传值而不是传址，Worker 对通信内容的修改，不会影响到主线程。事实上，浏览器内部的运行机制是，先将通信内容串行化，然后把串行化后的字符串发给 Worker，后者再将它还原。一个可选的 [Transferable](https://link.zhihu.com/?target=https%3A//developer.mozilla.org/zh-CN/docs/Web/API/Transferable)对象的数组，用于传递所有权。如果一个对象的所有权被转移，在发送它的上下文中将变为不可用（中止），并且只有在它被发送到的worker中可用。可转移对象是如ArrayBuffer，MessagePort或ImageBitmap的实例对象，`transferList`数组中不可传入null。

更详细的API参见 [MDN - WorkerGlobalScope](https://link.zhihu.com/?target=https%3A//developer.mozilla.org/zh-CN/docs/Web/API/WorkerGlobalScope)。

worker线程中加载脚本的api：

```javascript
importScripts('script1.js')	// 加载单个脚本
importScripts('script1.js', 'script2.js')	// 加载多个脚本
```

**3. 实战场景**

个人觉得，Web Worker我们可以当做计算器来用，需要用的时候掏出来摁一摁，不用的时候一定要收起来~

1. 加密数据
   有些加解密的算法比较复杂，或者在加解密很多数据的时候，这会非常耗费计算资源，导致UI线程无响应，因此这是使用Web Worker的好时机，使用Worker线程可以让用户更加无缝的操作UI。
2. 预取数据
   有时候为了提升数据加载速度，可以提前使用Worker线程获取数据，因为Worker线程是可以是用 `XMLHttpRequest` 的。
3. 预渲染
   在某些渲染场景下，比如渲染复杂的canvas的时候需要计算的效果比如反射、折射、光影、材料等，这些计算的逻辑可以使用Worker线程来执行，也可以使用多个Worker线程，这里有个[射线追踪的示例](https://link.zhihu.com/?target=https%3A//nerget.com/rayjs-mt/rayjs.html)。
4. 复杂数据处理场景
   某些检索、排序、过滤、分析会非常耗费时间，这时可以使用Web Worker来进行，不占用主线程。
5. 预加载图片
   有时候一个页面有很多图片，或者有几个很大的图片的时候，如果业务限制不考虑懒加载，也可以使用Web Worker来加载图片，可以参考一下[这篇文章的探索](https://link.zhihu.com/?target=https%3A//juejin.im/post/5a0875fcf265da431f4a8ddc)，这里简单提要一下。

```javascript
// 主线程
let w = new Worker("js/workers.js");
w.onmessage = function (event) {
  var img = document.createElement("img");
  img.src = window.URL.createObjectURL(event.data);
  document.querySelector('#result').appendChild(img)
}

// worker线程
let arr = [...好多图片路径];
for (let i = 0, len = arr.length; i < len; i++) {
    let req = new XMLHttpRequest();
    req.open('GET', arr[i], true);
    req.responseType = "blob";
    req.setRequestHeader("client_type", "DESKTOP_WEB");
    req.onreadystatechange = () => {
      if (req.readyState == 4) {
      postMessage(req.response);
    }
  }
  req.send(null);
}
```

在实战的时候注意

- 虽然使用worker线程不会占用主线程，但是启动worker会比较耗费资源
- 主线程中使用XMLHttpRequest在请求过程中浏览器另开了一个异步http请求线程，但是交互过程中还是要消耗主线程资源

# 四十六、js下载JSON对象

~~~javascript
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
<script src="https://cdn.bootcss.com/FileSaver.js/2014-11-29/FileSaver.js"></script>
<input type="button" id="export" value="保存"/>

<script>
    var button = document.getElementById("export");
    button.addEventListener("click", saveHandler, false);
    function saveHandler(){
        let data = {
            name:"hanmeimei",
            age:88
        };
        var content = JSON.stringify(data);
        var blob = new Blob([content], {type: "text/plain;charset=utf-8"});
        saveAs(blob, "save.json");
    }

</script>
</body>
</html>
~~~

# 四十七、ES6新特性

**ES6**是`ECMA`为`JavaScript`制定的第6个标准版本。

标准委员会最终决定，标准在每年6月正式发布并作为当年的正式版本，接下来的时间里就在此版本的基础上进行改动，直到下一年6月草案就自然变成新一年的版本，这样一来就无需以前的版本号，只要用年份标记即可。`ECMAscript 2015`是在`2015年6月`发布ES6的第一个版本。以此类推，`ECMAscript 2016`是ES6的第二个版本、 `ECMAscript 2017`是ES6的第三个版本。**ES6**既是一个历史名词也是一个泛指，含义是`5.1版本`以后的`JavaScript下一代标准`，目前涵盖了`ES2015`、`ES2016`、`ES2017`、`ES2018`、`ES2019`、`ES2020`。

所以有些文章上提到的`ES7`(实质上是`ES2016`)、`ES8`(实质上是`ES2017`)、`ES9`(实质上是`ES2018`)、`ES10`(实质上是`ES2019`)、`ES11`(实质上是`ES2020`)，实质上都是一些不规范的概念。从ES1到ES6，每个标准都是花了好几年甚至十多年才制定下来，你一个ES6到ES7，ES7到ES8，才用了一年，按照这样的定义下去，那不是很快就ES20了。用正确的概念来说ES6目前涵盖了**ES2015**、**ES2016**、**ES2017**、**ES2018**、**ES2019**、**ES2020**。![ES2015](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f33aa40c8da041b19a6608d4a335f6b4~tplv-k3u1fbpfcp-zoom-in-crop-mark:4536:0:0:0.image)

### 声明

-  **const命令**：声明常量
-  **let命令**：声明变量

> 作用

- 作用域
  - **全局作用域**
  - **函数作用域**：`function() {}`
  - **块级作用域**：`{}`
- 作用范围
  - `var命令`在全局代码中执行
  - `const命令`和`let命令`只能在代码块中执行
- 赋值使用
  - `const命令`声明常量后必须立马赋值
  - `let命令`声明变量后可立马赋值或使用时赋值
- 声明方法：`var`、`const`、`let`、`function`、`class`、`import`

> 重点难点

- 不允许重复声明
- 未定义就使用会报错：`const命令`和`let命令`不存在变量提升
- 暂时性死区：在代码块内使用`const命令`和`let命令`声明变量之前，该变量都不可用

### 解构赋值

-  **字符串解构**：`const [a, b, c, d, e] = "hello"`

-  **数值解构**：`const { toString: s } = 123`

-  **布尔解构**：`const { toString: b } = true`

-  

  对象解构

  - 形式：`const { x, y } = { x: 1, y: 2 }`
  - 默认：`const { x, y = 2 } = { x: 1 }`
  - 改名：`const { x, y: z } = { x: 1, y: 2 }`

-  

  数组解构

  - 规则：数据结构具有`Iterator接口`可采用数组形式的解构赋值
  - 形式：`const [x, y] = [1, 2]`
  - 默认：`const [x, y = 2] = [1]`

-  

  函数参数解构

  - 数组解构：`function Func([x = 0, y = 1]) {}`
  - 对象解构：`function Func({ x = 0, y = 1 } = {}) {}`

> 应用场景

- 交换变量值：`[x, y] = [y, x]`
- 返回函数多个值：`const [x, y, z] = Func()`
- 定义函数参数：`Func([1, 2])`
- 提取JSON数据：`const { name, version } = packageJson`
- 定义函数参数默认值：`function Func({ x = 1, y = 2 } = {}) {}`
- 遍历Map结构：`for (let [k, v] of Map) {}`
- 输入模块指定属性和方法：`const { readFile, writeFile } = require("fs")`

> 重点难点

- 匹配模式：只要等号两边的模式相同，左边的变量就会被赋予对应的值
- 解构赋值规则：只要等号右边的值不是对象或数组，就先将其转为对象
- 解构默认值生效条件：属性值严格等于`undefined`
- 解构遵循匹配模式
- 解构不成功时变量的值等于`undefined`
- `undefined`和`null`无法转为对象，因此无法进行解构

### 字符串扩展

-  **Unicode表示法**：`大括号包含`表示Unicode字符(`\u{0xXX}`或`\u{0XXX}`)
-  **字符串遍历**：可通过`for-of`遍历字符串
-  **字符串模板**：可单行可多行可插入变量的增强版字符串
-  **标签模板**：函数参数的特殊调用
-  **String.raw()**：返回把字符串所有变量替换且对斜杠进行转义的结果
-  **String.fromCodePoint()**：返回码点对应字符
-  **codePointAt()**：返回字符对应码点(`String.fromCodePoint()`的逆操作)
-  **normalize()**：把字符的不同表示方法统一为同样形式，返回`新字符串`(Unicode正规化)
-  **repeat()**：把字符串重复n次，返回`新字符串`
-  **matchAll()**：返回正则表达式在字符串的所有匹配
-  **includes()**：是否存在指定字符串
-  **startsWith()**：是否存在字符串头部指定字符串
-  **endsWith()**：是否存在字符串尾部指定字符串

> 重点难点

- 以上扩展方法均可作用于由`4个字节储存`的`Unicode字符`上

### 数值扩展

-  **二进制表示法**：`0b或0B开头`表示二进制(`0bXX`或`0BXX`)
-  **八进制表示法**：`0o或0O开头`表示二进制(`0oXX`或`0OXX`)
-  **Number.EPSILON**：数值最小精度
-  **Number.MIN_SAFE_INTEGER**：最小安全数值(`-2^53`)
-  **Number.MAX_SAFE_INTEGER**：最大安全数值(`2^53`)
-  **Number.parseInt()**：返回转换值的整数部分
-  **Number.parseFloat()**：返回转换值的浮点数部分
-  **Number.isFinite()**：是否为有限数值
-  **Number.isNaN()**：是否为NaN
-  **Number.isInteger()**：是否为整数
-  **Number.isSafeInteger()**：是否在数值安全范围内
-  **Math.trunc()**：返回数值整数部分
-  **Math.sign()**：返回数值类型(`正数1`、`负数-1`、`零0`)
-  **Math.cbrt()**：返回数值立方根
-  **Math.clz32()**：返回数值的32位无符号整数形式
-  **Math.imul()**：返回两个数值相乘
-  **Math.fround()**：返回数值的32位单精度浮点数形式
-  **Math.hypot()**：返回所有数值平方和的平方根
-  **Math.expm1()**：返回`e^n - 1`
-  **Math.log1p()**：返回`1 + n`的自然对数(`Math.log(1 + n)`)
-  **Math.log10()**：返回以10为底的n的对数
-  **Math.log2()**：返回以2为底的n的对数
-  **Math.sinh()**：返回n的双曲正弦
-  **Math.cosh()**：返回n的双曲余弦
-  **Math.tanh()**：返回n的双曲正切
-  **Math.asinh()**：返回n的反双曲正弦
-  **Math.acosh()**：返回n的反双曲余弦
-  **Math.atanh()**：返回n的反双曲正切

### 对象扩展

-  **简洁表示法**：直接写入变量和函数作为对象的属性和方法(`{ prop, method() {} }`)

-  **属性名表达式**：字面量定义对象时使用`[]`定义键(`[prop]`，不能与上同时使用)

-  

  方法的name属性

  ：返回方法函数名

  - 取值函数(getter)和存值函数(setter)：`get/set 函数名`(属性的描述对象在`get`和`set`上)
  - bind返回的函数：`bound 函数名`
  - Function构造函数返回的函数实例：`anonymous`

-  **属性的可枚举性和遍历**：描述对象的`enumerable`

-  **super关键字**：指向当前对象的原型对象(只能用在对象的简写方法中`method() {}`)

-  **Object.is()**：对比两值是否相等

-  **Object.assign()**：合并对象(浅拷贝)，返回原对象

-  **Object.getPrototypeOf()**：返回对象的原型对象

-  **Object.setPrototypeOf()**：设置对象的原型对象

-  **__proto__**：返回或设置对象的原型对象

> 属性遍历

- 描述：`自身`、`可继承`、`可枚举`、`非枚举`、`Symbol`
- 遍历
  - `for-in`：遍历对象`自身可继承可枚举`属性
  - `Object.keys()`：返回对象`自身可枚举`属性键组成的数组
  - `Object.getOwnPropertyNames()`：返回对象`自身非Symbol`属性键组成的数组
  - `Object.getOwnPropertySymbols()`：返回对象`自身Symbol`属性键组成的数组
  - `Reflect.ownKeys()`：返回对象`自身全部`属性键组成的数组
- 规则
  - 首先遍历所有数值键，按照数值升序排列
  - 其次遍历所有字符串键，按照加入时间升序排列
  - 最后遍历所有Symbol键，按照加入时间升序排列

### 数组扩展

-  **扩展运算符(...)**：转换数组为用逗号分隔的参数序列(`[...arr]`，相当于`rest/spread参数`的逆运算)

-  

  Array.from()

  ：转换具有

  ```javascript
  Iterator接口
  ```

  的数据结构为真正数组，返回新数组

  - 类数组对象：`包含length的对象`、`Arguments对象`、`NodeList对象`
  - 可遍历对象：`String`、`Set结构`、`Map结构`、`Generator函数`

-  **Array.of()**：转换一组值为真正数组，返回新数组

-  **copyWithin()**：把指定位置的成员复制到其他位置，返回原数组

-  **find()**：返回第一个符合条件的成员

-  **findIndex()**：返回第一个符合条件的成员索引值

-  **fill()**：根据指定值填充整个数组，返回原数组

-  **keys()**：返回以索引值为遍历器的对象

-  **values()**：返回以属性值为遍历器的对象

-  **entries()**：返回以索引值和属性值为遍历器的对象

-  **数组空位**：ES6明确将数组空位转为`undefined`(空位处理规不一，建议避免出现)

> 扩展应用

- 克隆数组：`const arr = [...arr1]`
- 合并数组：`const arr = [...arr1, ...arr2]`
- 拼接数组：`arr.push(...arr1)`
- 代替apply：`Math.max.apply(null, [x, y])` => `Math.max(...[x, y])`
- 转换字符串为数组：`[..."hello"]`
- 转换类数组对象为数组：`[...Arguments, ...NodeList]`
- 转换可遍历对象为数组：`[...String, ...Set, ...Map, ...Generator]`
- 与数组解构赋值结合：`const [x, ...rest/spread] = [1, 2, 3]`
- 计算Unicode字符长度：`Array.from("hello").length` => `[..."hello"].length`

> 重点难点

- 使用`keys()`、`values()`、`entries()`返回的遍历器对象，可用`for-of`自动遍历或`next()`手动遍历

### 函数扩展

-  

  参数默认值

  ：为函数参数指定默认值

  - 形式：`function Func(x = 1, y = 2) {}`
  - 参数赋值：惰性求值(函数调用后才求值)
  - 参数位置：尾参数
  - 参数作用域：函数作用域
  - 声明方式：默认声明，不能用`const`或`let`再次声明
  - length：返回没有指定默认值的参数个数
  - 与解构赋值默认值结合：`function Func({ x = 1, y = 2 } = {}) {}`
  - 应用
    - 指定某个参数不得省略，省略即抛出错误：`function Func(x = throwMissing()) {}`
    - 将参数默认值设为`undefined`，表明此参数可省略：`Func(undefined, 1)`

-  

  rest/spread参数(...)

  ：返回函数多余参数

  - 形式：以数组的形式存在，之后不能再有其他参数
  - 作用：代替`Arguments对象`
  - length：返回没有指定默认值的参数个数但不包括`rest/spread参数`

-  

  严格模式

  ：在严格条件下运行JS

  - 应用：只要函数参数使用默认值、解构赋值、扩展运算符，那么函数内部就不能显式设定为严格模式

-  

  name属性

  ：返回函数的函数名

  - 将匿名函数赋值给变量：`空字符串`(**ES5**)、`变量名`(**ES6**)
  - 将具名函数赋值给变量：`函数名`(**ES5和ES6**)
  - bind返回的函数：`bound 函数名`(**ES5和ES6**)
  - Function构造函数返回的函数实例：`anonymous`(**ES5和ES6**)

-  

  箭头函数(=>)

  ：函数简写

  - 无参数：`() => {}`
  - 单个参数：`x => {}`
  - 多个参数：`(x, y) => {}`
  - 解构参数：`({x, y}) => {}`
  - 嵌套使用：部署管道机制
  - this指向固定化
    - 并非因为内部有绑定`this`的机制，而是根本没有自己的`this`，导致内部的`this`就是外层代码块的`this`
    - 因为没有`this`，因此不能用作构造函数

-  

  尾调用优化

  ：只保留内层函数的调用帧

  - 尾调用
    - 定义：某个函数的最后一步是调用另一个函数
    - 形式：`function f(x) { return g(x); }`
  - 尾递归
    - 定义：函数尾调用自身
    - 作用：只要使用尾递归就不会发生栈溢出，相对节省内存
    - 实现：把所有用到的内部变量改写成函数的参数并使用参数默认值

> 箭头函数误区

- 函数体内的`this`是`定义时所在的对象`而不是`使用时所在的对象`
- 可让`this`指向固定化，这种特性很有利于封装回调函数
- 不可当作`构造函数`，因此箭头函数不可使用`new命令`
- 不可使用`yield命令`，因此箭头函数不能用作`Generator函数`
- 不可使用`Arguments对象`，此对象在函数体内不存在(可用`rest/spread参数`代替)
- 返回对象时必须在对象外面加上括号

### 正则扩展

-  **变更RegExp构造函数入参**：允许首参数为`正则对象`，尾参数为`正则修饰符`(返回的正则表达式会忽略原正则表达式的修饰符)

-  **正则方法调用变更**：字符串对象的`match()`、`replace()`、`search()`、`split()`内部调用转为调用`RegExp`实例对应的`RegExp.prototype[Symbol.方法]`

-  

  u修饰符

  ：Unicode模式修饰符，正确处理大于

  ```javascript
  \uFFFF
  ```

  的

  ```javascript
  Unicode字符
  ```

  - `点字符`(.)
  - `Unicode表示法`
  - `量词`
  - `预定义模式`
  - `i修饰符`
  - `转义`

-  **y修饰符**：粘连修饰符，确保匹配必须从剩余的第一个位置开始全局匹配(与`g修饰符`作用类似)

-  **unicode**：是否设置`u修饰符`

-  **sticky**：是否设置`y修饰符`

-  **flags**：返回正则表达式的修饰符

> 重点难点

- `y修饰符`隐含头部匹配标志`^`
- 单单一个`y修饰符`对`match()`只能返回第一个匹配，必须与`g修饰符`联用才能返回所有匹配

### Symbol

- 定义：独一无二的值
- 声明：`const set = Symbol(str)`
- 入参：字符串(可选)
- 方法
  - **Symbol()**：创建以参数作为描述的`Symbol值`(不登记在全局环境)
  - **Symbol.for()**：创建以参数作为描述的`Symbol值`，如存在此参数则返回原有的`Symbol值`(先搜索后创建，登记在全局环境)
  - **Symbol.keyFor()**：返回已登记的`Symbol值`的描述(只能返回`Symbol.for()`的`key`)
  - **Object.getOwnPropertySymbols()**：返回对象中所有用作属性名的`Symbol值`的数组
- 内置
  - **Symbol.hasInstance**：指向一个内部方法，当其他对象使用`instanceof运算符`判断是否为此对象的实例时会调用此方法
  - **Symbol.isConcatSpreadable**：指向一个布尔，定义对象用于`Array.prototype.concat()`时是否可展开
  - **Symbol.species**：指向一个构造函数，当实例对象使用自身构造函数时会调用指定的构造函数
  - **Symbol.match**：指向一个函数，当实例对象被`String.prototype.match()`调用时会重新定义`match()`的行为
  - **Symbol.replace**：指向一个函数，当实例对象被`String.prototype.replace()`调用时会重新定义`replace()`的行为
  - **Symbol.search**：指向一个函数，当实例对象被`String.prototype.search()`调用时会重新定义`search()`的行为
  - **Symbol.split**：指向一个函数，当实例对象被`String.prototype.split()`调用时会重新定义`split()`的行为
  - **Symbol.iterator**：指向一个默认遍历器方法，当实例对象执行`for-of`时会调用指定的默认遍历器
  - **Symbol.toPrimitive**：指向一个函数，当实例对象被转为原始类型的值时会返回此对象对应的原始类型值
  - **Symbol.toStringTag**：指向一个函数，当实例对象被`Object.prototype.toString()`调用时其返回值会出现在`toString()`返回的字符串之中表示对象的类型
  - **Symbol.unscopables**：指向一个对象，指定使用`with`时哪些属性会被`with环境`排除

> 数据类型

- **Undefined**
- **Null**
- **String**
- **Number**
- **Boolean**
- **Object**(包含`Array`、`Function`、`Date`、`RegExp`、`Error`)
- **Symbol**

> 应用场景

- 唯一化对象属性名：属性名属于Symbol类型，就都是独一无二的，可保证不会与其他属性名产生冲突
- 消除魔术字符串：在代码中多次出现且与代码形成强耦合的某一个具体的字符串或数值
- 遍历属性名：无法通过`for-in`、`for-of`、`Object.keys()`、`Object.getOwnPropertyNames()`、`JSON.stringify()`返回，只能通过`Object.getOwnPropertySymbols`返回
- 启用模块的Singleton模式：调用一个类在任何时候返回同一个实例(`window`和`global`)，使用`Symbol.for()`来模拟全局的`Singleton模式`

> 重点难点

- `Symbol()`生成一个原始类型的值不是对象，因此`Symbol()`前不能使用`new命令`
- `Symbol()`参数表示对当前`Symbol值`的描述，相同参数的`Symbol()`返回值不相等
- `Symbol值`不能与其他类型的值进行运算
- `Symbol值`可通过`String()`或`toString()`显式转为字符串
- `Symbol值`作为对象属性名时，此属性是公开属性，但不是私有属性
- `Symbol值`作为对象属性名时，只能用方括号运算符(`[]`)读取，不能用点运算符(`.`)读取
- `Symbol值`作为对象属性名时，不会被常规方法遍历得到，可利用此特性为对象定义`非私有但又只用于内部的方法`

### Set

##### Set

- 定义：类似于数组的数据结构，成员值都是唯一且没有重复的值
- 声明：`const set = new Set(arr)`
- 入参：具有`Iterator接口`的数据结构
- 属性
  - **constructor**：构造函数，返回Set
  - **size**：返回实例成员总数
- 方法
  - **add()**：添加值，返回实例
  - **delete()**：删除值，返回布尔
  - **has()**：检查值，返回布尔
  - **clear()**：清除所有成员
  - **keys()**：返回以属性值为遍历器的对象
  - **values()**：返回以属性值为遍历器的对象
  - **entries()**：返回以属性值和属性值为遍历器的对象
  - **forEach()**：使用回调函数遍历每个成员

> 应用场景

- 去重字符串：`[...new Set(str)].join("")`
- 去重数组：`[...new Set(arr)]`或`Array.from(new Set(arr))`
- 集合数组
  - 声明：`const a = new Set(arr1)`、`const b = new Set(arr2)`
  - 并集：`new Set([...a, ...b])`
  - 交集：`new Set([...a].filter(v => b.has(v)))`
  - 差集：`new Set([...a].filter(v => !b.has(v)))`
- 映射集合
  - 声明：`let set = new Set(arr)`
  - 映射：`set = new Set([...set].map(v => v * 2))`或`set = new Set(Array.from(set, v => v * 2))`

> 重点难点

- 遍历顺序：插入顺序
- 没有键只有值，可认为键和值两值相等
- 添加多个`NaN`时，只会存在一个`NaN`
- 添加相同的对象时，会认为是不同的对象
- 添加值时不会发生类型转换(`5 !== "5"`)
- `keys()`和`values()`的行为完全一致，`entries()`返回的遍历器同时包括键和值且两值相等

##### WeakSet

- 定义：和Set结构类似，成员值只能是对象
- 声明：`const set = new WeakSet(arr)`
- 入参：具有`Iterator接口`的数据结构
- 属性
  - **constructor**：构造函数，返回WeakSet
- 方法
  - **add()**：添加值，返回实例
  - **delete()**：删除值，返回布尔
  - **has()**：检查值，返回布尔

> 应用场景

- 储存DOM节点：DOM节点被移除时自动释放此成员，不用担心这些节点从文档移除时会引发内存泄漏
- 临时存放一组对象或存放跟对象绑定的信息：只要这些对象在外部消失，它在`WeakSet结构`中的引用就会自动消

> 重点难点

- 成员都是`弱引用`，垃圾回收机制不考虑`WeakSet结构`对此成员的引用
- 成员不适合引用，它会随时消失，因此ES6规定`WeakSet结构不可遍历`
- 其他对象不再引用成员时，垃圾回收机制会自动回收此成员所占用的内存，不考虑此成员是否还存在于`WeakSet结构`中

### Map

##### Map

- 定义：类似于对象的数据结构，成员键是任何类型的值
- 声明：`const set = new Map(arr)`
- 入参：具有`Iterator接口`且每个成员都是一个双元素数组的数据结构
- 属性
  - **constructor**：构造函数，返回Map
  - **size**：返回实例成员总数
- 方法
  - **get()**：返回键值对
  - **set()**：添加键值对，返回实例
  - **delete()**：删除键值对，返回布尔
  - **has()**：检查键值对，返回布尔
  - **clear()**：清除所有成员
  - **keys()**：返回以键为遍历器的对象
  - **values()**：返回以值为遍历器的对象
  - **entries()**：返回以键和值为遍历器的对象
  - **forEach()**：使用回调函数遍历每个成员

> 重点难点

- 遍历顺序：插入顺序
- 对同一个键多次赋值，后面的值将覆盖前面的值
- 对同一个对象的引用，被视为一个键
- 对同样值的两个实例，被视为两个键
- 键跟内存地址绑定，只要内存地址不一样就视为两个键
- 添加多个以`NaN`作为键时，只会存在一个以`NaN`作为键的值
- `Object结构`提供`字符串—值`的对应，`Map结构`提供`值—值`的对应

##### WeakMap

- 定义：和Map结构类似，成员键只能是对象
- 声明：`const set = new WeakMap(arr)`
- 入参：具有`Iterator接口`且每个成员都是一个双元素数组的数据结构
- 属性
  - **constructor**：构造函数，返回WeakMap
- 方法
  - **get()**：返回键值对
  - **set()**：添加键值对，返回实例
  - **delete()**：删除键值对，返回布尔
  - **has()**：检查键值对，返回布尔

> 应用场景

- 储存DOM节点：DOM节点被移除时自动释放此成员键，不用担心这些节点从文档移除时会引发内存泄漏
- 部署私有属性：内部属性是实例的弱引用，删除实例时它们也随之消失，不会造成内存泄漏

> 重点难点

- 成员键都是`弱引用`，垃圾回收机制不考虑`WeakMap结构`对此成员键的引用
- 成员键不适合引用，它会随时消失，因此ES6规定`WeakMap结构不可遍历`
- 其他对象不再引用成员键时，垃圾回收机制会自动回收此成员所占用的内存，不考虑此成员是否还存在于`WeakMap结构`中
- 一旦不再需要，成员会自动消失，不用手动删除引用
- 弱引用的`只是键而不是值`，值依然是正常引用
- 即使在外部消除了成员键的引用，内部的成员值依然存在

### Proxy(代理)

- 定义：修改某些操作的默认行为
- 声明：`const proxy = new Proxy(target, handler)`
- 入参
  - **target**：拦截的目标对象
  - **handler**：定制拦截行为
- 方法
  - **Proxy.revocable()**：返回可取消的Proxy实例(返回`{ proxy, revoke }`，通过revoke()取消代理)
- 拦截方式
  - **get()**：拦截对象属性读取
  - **set()**：拦截对象属性设置，返回布尔
  - **has()**：拦截对象属性检查`k in obj`，返回布尔
  - **deleteProperty()**：拦截对象属性删除`delete obj[k]`，返回布尔
  - **defineProperty()**：拦截对象属性定义`Object.defineProperty()`、`Object.defineProperties()`，返回布尔
  - **ownKeys()**：拦截对象属性遍历`for-in`、`Object.keys()`、`Object.getOwnPropertyNames()`、`Object.getOwnPropertySymbols()`，返回数组
  - **getOwnPropertyDescriptor()**：拦截对象属性描述读取`Object.getOwnPropertyDescriptor()`，返回对象
  - **getPrototypeOf()**：拦截对象原型读取`instanceof`、`Object.getPrototypeOf()`、`Object.prototype.__proto__`、`Object.prototype.isPrototypeOf()`、`Reflect.getPrototypeOf()`，返回对象
  - **setPrototypeOf()**：拦截对象原型设置`Object.setPrototypeOf()`，返回布尔
  - **isExtensible()**：拦截对象是否可扩展读取`Object.isExtensible()`，返回布尔
  - **preventExtensions()**：拦截对象不可扩展设置`Object.preventExtensions()`，返回布尔
  - **apply()**：拦截Proxy实例作为函数调用`proxy()`、`proxy.apply()`、`proxy.call()`
  - **construct()**：拦截Proxy实例作为构造函数调用`new proxy()`

> 应用场景

- `Proxy.revocable()`：不允许直接访问对象，必须通过代理访问，一旦访问结束就收回代理权不允许再次访问
- `get()`：读取未知属性报错、读取数组负数索引的值、封装链式操作、生成DOM嵌套节点
- `set()`：数据绑定(Vue数据绑定实现原理)、确保属性值设置符合要求、防止内部属性被外部读写
- `has()`：隐藏内部属性不被发现、排除不符合属性条件的对象
- `deleteProperty()`：保护内部属性不被删除
- `defineProperty()`：阻止属性被外部定义
- `ownKeys()`：保护内部属性不被遍历

> 重点难点

- 要使`Proxy`起作用，必须针对`实例`进行操作，而不是针对`目标对象`进行操作
- 没有设置任何拦截时，等同于`直接通向原对象`
- 属性被定义为`不可读写/扩展/配置/枚举`时，使用拦截方法会报错
- 代理下的目标对象，内部`this`指向`Proxy代理`

### Reflect(反射)

- 定义：保持`Object方法`的默认行为
- 方法
  - **get()**：返回对象属性
  - **set()**：设置对象属性，返回布尔
  - **has()**：检查对象属性，返回布尔
  - **deleteProperty()**：删除对象属性，返回布尔
  - **defineProperty()**：定义对象属性，返回布尔
  - **ownKeys()**：遍历对象属性，返回数组(`Object.getOwnPropertyNames()`+`Object.getOwnPropertySymbols()`)
  - **getOwnPropertyDescriptor()**：返回对象属性描述，返回对象
  - **getPrototypeOf()**：返回对象原型，返回对象
  - **setPrototypeOf()**：设置对象原型，返回布尔
  - **isExtensible()**：返回对象是否可扩展，返回布尔
  - **preventExtensions()**：设置对象不可扩展，返回布尔
  - **apply()**：绑定this后执行指定函数
  - **construct()**：调用构造函数创建实例

> 设计目的

- 将`Object`属于`语言内部的方法`放到`Reflect`上
- 将某些Object方法报错情况改成返回`false`
- 让`Object操作`变成`函数行为`
- `Proxy`与`Reflect`相辅相成

> 废弃方法

- `Object.defineProperty()` => `Reflect.defineProperty()`
- `Object.getOwnPropertyDescriptor()` => `Reflect.getOwnPropertyDescriptor()`

> 重点难点

- `Proxy方法`和`Reflect方法`一一对应
- `Proxy`和`Reflect`联合使用，前者负责`拦截赋值操作`，后者负责`完成赋值操作`

> 数据绑定：观察者模式

```javascript
const observerQueue = new Set();
const observe = fn => observerQueue.add(fn);
const observable = obj => new Proxy(obj, {
    set(tgt, key, val, receiver) {
        const result = Reflect.set(tgt, key, val, receiver);
        observerQueue.forEach(v => v());
        return result;
    }
});

const person = observable({ age: 25, name: "Yajun" });
const print = () => console.log(`${person.name} is ${person.age} years old`);
observe(print);
person.name = "Joway";
复制代码
```

### Class(类)

- 定义：对一类具有共同特征的事物的抽象(构造函数语法糖)

- 原理：类本身指向构造函数，所有方法定义在`prototype`上，可看作构造函数的另一种写法(`Class === Class.prototype.constructor`)

- 方法和关键字

  - **constructor()**：构造函数，`new命令`生成实例时自动调用
  - **extends**：继承父类
  - **super**：新建父类的`this`
  - **static**：定义静态属性方法
  - **get**：取值函数，拦截属性的取值行为
  - **set**：存值函数，拦截属性的存值行为

- 属性

  - **__proto__**：`构造函数的继承`(总是指向`父类`)
  - **__proto__.__proto__**：子类的原型的原型，即父类的原型(总是指向父类的`__proto__`)
  - **prototype.__proto__**：`属性方法的继承`(总是指向父类的`prototype`)

- 静态属性：定义类完成后赋值属性，该属性`不会被实例继承`，只能通过类来调用

- 静态方法：使用`static`定义方法，该方法`不会被实例继承`，只能通过类来调用(方法中的`this`指向类，而不是实例)

- 继承

  - 实质

    - ES5实质：先创造子类实例的`this`，再将父类的属性方法添加到`this`上(`Parent.apply(this)`)
    - ES6实质：先将父类实例的属性方法加到`this`上(调用`super()`)，再用子类构造函数修改`this`

  - super

    - 作为函数调用：只能在构造函数中调用`super()`，内部`this`指向继承的`当前子类`(`super()`调用后才可在构造函数中使用`this`)
    - 作为对象调用：在`普通方法`中指向`父类的原型对象`，在`静态方法`中指向`父类`

  - 显示定义：使用`constructor() { super(); }`定义继承父类，没有书写则`显示定义`

  - 子类继承父类：子类使用父类的属性方法时，必须在构造函数中调用

    ```javascript
    super()
    ```

    ，否则得不到父类的

    ```javascript
    this
    ```

    - 父类静态属性方法可被子类继承
    - 子类继承父类后，可从`super`上调用父类静态属性方法

- 实例：类相当于

  ```javascript
  实例的原型
  ```

  ，所有在类中定义的属性方法都会被实例继承

  - 显式指定属性方法：使用`this`指定到自身上(使用`Class.hasOwnProperty()`可检测到)
  - 隐式指定属性方法：直接声明定义在对象原型上(使用`Class.__proto__.hasOwnProperty()`可检测到)

- 表达式

  - 类表达式：`const Class = class {}`
  - name属性：返回紧跟`class`后的类名
  - 属性表达式：`[prop]`
  - Generator方法：`* mothod() {}`
  - Async方法：`async mothod() {}`

- this指向：解构实例属性或方法时会报错

  - 绑定this：`this.mothod = this.mothod.bind(this)`
  - 箭头函数：`this.mothod = () => this.mothod()`

- 属性定义位置

  - 定义在构造函数中并使用`this`指向
  - 定义在`类最顶层`

- **new.target**：确定构造函数是如何调用

> 原生构造函数

- **String()**
- **Number()**
- **Boolean()**
- **Array()**
- **Object()**
- **Function()**
- **Date()**
- **RegExp()**
- **Error()**

> 重点难点

- 在实例上调用方法，实质是调用原型上的方法
- `Object.assign()`可方便地一次向类添加多个方法(`Object.assign(Class.prototype, { ... })`)
- 类内部所有定义的方法是不可枚举的(`non-enumerable`)
- 构造函数默认返回实例对象(`this`)，可指定返回另一个对象
- 取值函数和存值函数设置在属性的`Descriptor对象`上
- 类不存在变量提升
- 利用`new.target === Class`写出不能独立使用必须继承后才能使用的类
- 子类继承父类后，`this`指向子类实例，通过`super`对某个属性赋值，赋值的属性会变成子类实例的属性
- 使用`super`时，必须显式指定是作为函数还是作为对象使用
- `extends`不仅可继承类还可继承原生的构造函数

> 私有属性方法

```javascript
const name = Symbol("name");
const print = Symbol("print");
class Person {
    constructor(age) {
        this[name] = "Bruce";
        this.age = age;
    }
    [print]() {
        console.log(`${this[name]} is ${this.age} years old`);
    }
}
```

> 继承混合类

```javascript
function CopyProperties(target, source) {
    for (const key of Reflect.ownKeys(source)) {
        if (key !== "constructor" && key !== "prototype" && key !== "name") {
            const desc = Object.getOwnPropertyDescriptor(source, key);
            Object.defineProperty(target, key, desc);
        }
    }
}
function MixClass(...mixins) {
    class Mix {
        constructor() {
            for (const mixin of mixins) {
                CopyProperties(this, new mixin());
            }
        }
    }
    for (const mixin of mixins) {
        CopyProperties(Mix, mixin);
        CopyProperties(Mix.prototype, mixin.prototype);
    }
    return Mix;
}
class Student extends MixClass(Person, Kid) {}
```

### Module(模块化)

- 命令

  - export

    ：规定模块对外接口

    - **默认导出**：`export default Person`(导入时可指定模块任意名称，无需知晓内部真实名称)
    - **单独导出**：`export const name = "Bruce"`
    - **按需导出**：`export { age, name, sex }`(推荐)
    - **改名导出**：`export { name as newName }`

  - import

    ：导入模块内部功能

    - **默认导入**：`import Person from "person"`
    - **整体导入**：`import * as Person from "person"`
    - **按需导入**：`import { age, name, sex } from "person"`
    - **改名导入**：`import { name as newName } from "person"`
    - **自执导入**：`import "person"`
    - **复合导入**：`import Person, { name } from "person"`

  - 复合模式

    ：

    ```javascript
    export命令
    ```

    和

    ```javascript
    import命令
    ```

    结合在一起写成一行，变量实质没有被导入当前模块，相当于对外转发接口，导致当前模块无法直接使用其导入变量

    - **默认导入导出**：`export { default } from "person"`
    - **整体导入导出**：`export * from "person"`
    - **按需导入导出**：`export { age, name, sex } from "person"`
    - **改名导入导出**：`export { name as newName } from "person"`
    - **具名改默认导入导出**：`export { name as default } from "person"`
    - **默认改具名导入导出**：`export { default as name } from "person"`

- 继承：`默认导出`和`改名导出`结合使用可使模块具备继承性

- 设计思想：尽量地静态化，使得编译时就能确定模块的依赖关系，以及输入和输出的变量

- 严格模式：ES6模块自动采用严格模式(不管模块头部是否添加`use strict`)

> 模块方案

- **CommonJS**：用于服务器(动态化依赖)
- **AMD**：用于浏览器(动态化依赖)
- **CMD**：用于浏览器(动态化依赖)
- **UMD**：用于浏览器和服务器(动态化依赖)
- **ESM**：用于浏览器和服务器(静态化依赖)

> 加载方式

- 运行时加载
  - 定义：整体加载模块生成一个对象，再从对象上获取需要的属性和方法进行加载(全部加载)
  - 影响：只有运行时才能得到这个对象，导致无法在编译时做静态优化
- 编译时加载
  - 定义：直接从模块中获取需要的属性和方法进行加载(按需加载)
  - 影响：在编译时就完成模块加载，效率比其他方案高，但无法引用模块本身(**本身不是对象**)，可拓展JS高级语法(**宏和类型校验**)

> 加载实现

- 传统加载

  ：通过

  ```javascript
  <script>
  ```

  进行同步或异步加载脚本

  - 同步加载：`<script src=""></script>`
  - Defer异步加载：`<script src="" defer></script>`(顺序加载，渲染完再执行)
  - Async异步加载：`<script src="" async></script>`(乱序加载，下载完就执行)

- **模块加载**：`<script type="module" src=""></script>`(默认是Defer异步加载)

> CommonJS和ESM的区别

- ```javascript
  CommonJS
  ```

  输出

  ```javascript
  值的拷贝
  ```

  ，

  ```javascript
  ESM
  ```

  输出

  ```javascript
  值的引用
  ```

  - `CommonJS`一旦输出一个值，模块内部的变化就影响不到这个值
  - `ESM`是动态引用且不会缓存值，模块里的变量绑定其所在的模块，等到脚本真正执行时，再根据这个只读引用到被加载的那个模块里去取值

- ```
  CommonJS
  ```

  是运行时加载，

  ```
  ESM
  ```

  是编译时加载

  - `CommonJS`加载模块是对象(即`module.exports`)，该对象只有在脚本运行完才会生成
  - `ESM`加载模块不是对象，它的对外接口只是一种静态定义，在代码静态解析阶段就会生成

> Node加载

- 背景：`CommonJS`和`ESM`互不兼容，目前解决方案是将两者分开，采用各自的加载方案

- 区分：要求

  ```
  ESM
  ```

  采用

  ```
  .mjs
  ```

  后缀文件名

  - `require()`不能加载`.mjs文件`，只有`import命令`才可加载`.mjs文件`
  - `.mjs文件`里不能使用`require()`，必须使用`import命令`加载文件

- 驱动：`node --experimental-modules file.mjs`

- 限制：Node的`import命令`目前只支持加载本地模块(`file:协议`)，不支持加载远程模块

- 加载优先级

  - 脚本文件省略后缀名：依次尝试加载四个后缀名文件(`.mjs`、`.js`、`.json`、`node`)
  - 以上不存在：尝试加载`package.json`的`main字段`指定的脚本
  - 以上不存在：依次尝试加载名称为`index`四个后缀名文件(`.mjs`、`.js`、`.json`、`node`)
  - 以上不存在：报错

- 不存在的内部变量：`arguments`、`exports`、`module`、`require`、`this`、`__dirname`、`__filename`

- CommonJS加载ESM

  - 不能使用`require()`，只能使用`import()`

- ESM加载CommonJS

  - 自动将`module.exports`转化成`export default`
  - `CommonJS`输出缓存机制在`ESM`加载方式下依然有效
  - 采用`import命令`加载`CommonJS模块`时，不允许采用`按需导入`，应使用`默认导入`或`整体导入`

> 循环加载

- 定义：`脚本A`的执行依赖`脚本B`，而`脚本A`的执行又依赖`脚本B`
- 加载原理
  - CommonJS：`require()`首次加载脚本就会执行整个脚本，在内存里生成一个对象缓存下来，二次加载脚本时直接从缓存中获取
  - ESM：`import命令`加载变量不会被缓存，而是成为一个指向被加载模块的引用
- 循环加载
  - CommonJS：只输出已经执行的部分，还未执行的部分不会输出
  - ESM：需开发者自己保证真正取值时能够取到值(可把变量写成函数形式，函数具有提升作用)

> 重点难点

- ES6模块中，顶层`this`指向`undefined`，不应该在顶层代码使用`this`
- 一个模块就是一个独立的文件，该文件内部的所有变量，外部无法获取
- `export命令`输出的接口与其对应的值是`动态绑定关系`，即通过该接口可获取模块内部实时的值
- `import命令`大括号里的变量名必须与被导入模块对外接口的名称相同
- `import命令`输入的变量只读(本质是输入接口)，不允许在加载模块的脚本里改写接口
- `import命令`命令具有提升效果，会提升到整个模块的头部，首先执行
- 重复执行同一句`import语句`，只会执行一次
- `export default`命令只能使用一次
- `export default命令`导出的整体模块，在执行`import命令`时其后不能跟`大括号`
- `export default命令`本质是输出一个名为`default`的变量，后面不能跟`变量声明语句`
- `export default命令`本质是将后面的值赋给名为`default`的变量，可直接将值写在其后
- `export default命令`和`export {}命令`可同时存在，对应`复合导入`
- `export命令`和`import命令`可出现在模块任何位置，只要处于模块顶层即可，不能处于块级作用域
- `import()`加载模块成功后，此模块会作为一个对象，当作`then()`的参数，可使用`对象解构赋值`来获取输出接口
- 同时动态加载多个模块时，可使用`Promise.all()`和`import()`相结合来实现
- `import()`和结合`async/await`来书写同步操作的代码

> 单例模式：跨模块常量

```javascript
// 常量跨文件共享
// person.js
const NAME = "Bruce";
const AGE = 25;
const SEX = "male";
export { AGE, NAME, SEX };
```

```javascript
// file1.js
import { AGE } from "person";
console.log(AGE);
```

```javascript
// file2.js
import { AGE, NAME, SEX } from "person";
console.log(AGE, NAME, SEX);
```

> 默认导入互换整体导入

```javascript
import Person from "person";
console.log(Person.AGE);
```

```javascript
import * as Person from "person";
console.log(Person.default.AGE);
```

### Iterator(迭代器)

- 定义：为各种不同的数据结构提供统一的访问机制
- 原理：创建一个指针指向首个成员，按照次序使用`next()`指向下一个成员，直接到结束位置(数据结构只要部署`Iterator接口`就可完成遍历操作)
- 作用
  - 为各种数据结构提供一个统一的简便的访问接口
  - 使得数据结构成员能够按某种次序排列
  - ES6创造了新的遍历命令`for-of`，`Iterator接口`主要供`for-of`消费
- 形式：`for-of`(自动去寻找Iterator接口)
- 数据结构
  - 集合：`Array`、`Object`、`Set`、`Map`
  - 原生具备接口的数据结构：`String`、`Array`、`Set`、`Map`、`TypedArray`、`Arguments`、`NodeList`
- 部署：默认部署在`Symbol.iterator`(具备此属性被认为`可遍历的iterable`)
- 遍历器对象
  - **next()**：下一步操作，返回`{ done, value }`(必须部署)
  - **return()**：`for-of`提前退出调用，返回`{ done: true }`
  - **throw()**：不使用，配合`Generator函数`使用

> ForOf循环

- 定义：调用`Iterator接口`产生遍历器对象(`for-of`内部调用数据结构的`Symbol.iterator()`)

- 遍历字符串：`for-in`获取`索引`，`for-of`获取`值`(可识别32位UTF-16字符)

- 遍历数组：`for-in`获取`索引`，`for-of`获取`值`

- 遍历对象：`for-in`获取`键`，`for-of`需自行部署

- 遍历Set：`for-of`获取`值` => `for (const v of set)`

- 遍历Map：`for-of`获取`键值对` => `for (const [k, v] of map)`

- 遍历类数组：`包含length的对象`、`Arguments对象`、`NodeList对象`(无`Iterator接口的类数组`可用`Array.from()`转换)

- 计算生成数据结构：

  ```
  Array
  ```

  、

  ```
  Set
  ```

  、

  ```
  Map
  ```

  - **keys()**：返回遍历器对象，遍历所有的键
  - **values()**：返回遍历器对象，遍历所有的值
  - **entries()**：返回遍历器对象，遍历所有的键值对

- 与

  ```
  for-in
  ```

  区别

  - 有着同`for-in`一样的简洁语法，但没有`for-in`那些缺点、
  - 不同于`forEach()`，它可与`break`、`continue`和`return`配合使用
  - 提供遍历所有数据结构的统一操作接口

> 应用场景

- 改写具有`Iterator接口`的数据结构的`Symbol.iterator`
- 解构赋值：对Set进行结构
- 扩展运算符：将部署`Iterator接口`的数据结构转为数组
- yield*：`yield*`后跟一个可遍历的数据结构，会调用其遍历器接口
- 接受数组作为参数的函数：`for-of`、`Array.from()`、`new Set()`、`new WeakSet()`、`new Map()`、`new WeakMap()`、`Promise.all()`、`Promise.race()`

### Promise

- 定义：包含异步操作结果的对象

- 状态

  - **进行中**：`pending`
  - **已成功**：`resolved`
  - **已失败**：`rejected`

- 特点

  - 对象的状态不受外界影响
  - 一旦状态改变就不会再变，任何时候都可得到这个结果

- 声明：`new Promise((resolve, reject) => {})`

- 出参

  - **resolve**：将状态从`未完成`变为`成功`，在异步操作成功时调用，并将异步操作的结果作为参数传递出去
  - **reject**：将状态从`未完成`变为`失败`，在异步操作失败时调用，并将异步操作的错误作为参数传递出去

- 方法

  - then()

    ：分别指定

    ```
    resolved状态
    ```

    和

    ```
    rejected状态
    ```

    的回调函数

    - **第一参数**：状态变为`resolved`时调用
    - **第二参数**：状态变为`rejected`时调用(可选)

  - **catch()**：指定发生错误时的回调函数

  - Promise.all()

    ：将多个实例包装成一个新实例，返回全部实例状态变更后的结果数组(齐变更再返回)

    - 入参：具有`Iterator接口`的数据结构
    - 成功：只有全部实例状态变成`fulfilled`，最终状态才会变成`fulfilled`
    - 失败：其中一个实例状态变成`rejected`，最终状态就会变成`rejected`

  - Promise.race()

    ：将多个实例包装成一个新实例，返回全部实例状态优先变更后的结果(先变更先返回)

    - 入参：具有`Iterator接口`的数据结构
    - 成功失败：哪个实例率先改变状态就返回哪个实例的状态

  - Promise.resolve()

    ：将对象转为Promise对象(等价于

    ```javascript
    new Promise(resolve => resolve())
    ```

    )

    - **Promise实例**：原封不动地返回入参
    - **Thenable对象**：将此对象转为Promise对象并返回(Thenable为包含`then()`的对象，执行`then()`相当于执行此对象的`then()`)
    - **不具有then()的对象**：将此对象转为Promise对象并返回，状态为`resolved`
    - **不带参数**：返回Promise对象，状态为`resolved`

  - **Promise.reject()**：将对象转为状态为`rejected`的Promise对象(等价于`new Promise((resolve, reject) => reject())`)

> 应用场景

- 加载图片
- AJAX转Promise对象

> 重点难点

- 只有异步操作的结果可决定当前状态是哪一种，其他操作都无法改变这个状态
- 状态改变只有两种可能：从`pending`变为`resolved`、从`pending`变为`rejected`
- 一旦新建`Promise对象`就会立即执行，无法中途取消
- 不设置回调函数，内部抛错不会反应到外部
- 当处于`pending`时，无法得知目前进展到哪一个阶段
- 实例状态变为`resolved`或`rejected`时，会触发`then()`绑定的回调函数
- `resolve()`和`reject()`的执行总是晚于本轮循环的同步任务
- `then()`返回新实例，其后可再调用另一个`then()`
- `then()`运行中抛出错误会被`catch()`捕获
- `reject()`的作用等同于抛出错误
- 实例状态已变成`resolved`时，再抛出错误是无效的，不会被捕获，等于没有抛出
- 实例状态的错误具有`冒泡`性质，会一直向后传递直到被捕获为止，错误总是会被下一个`catch()`捕获
- 不要在`then()`里定义`rejected`状态的回调函数(不使用其第二参数)
- 建议使用`catch()`捕获错误，不要使用`then()`第二个参数捕获
- 没有使用`catch()`捕获错误，实例抛错不会传递到外层代码，即`不会有任何反应`
- 作为参数的实例定义了`catch()`，一旦被`rejected`并不会触发`Promise.all()`的`catch()`
- `Promise.reject()`的参数会原封不动地作为`rejected`的理由，变成后续方法的参数

### Generator(生成器)

- 定义：封装多个内部状态的异步编程解决方案

- 形式：调用`Generator函数`(该函数不执行)返回指向内部状态的指针对象(不是运行结果)

- 声明：`function* Func() {}`

- 方法

  - **next()**：使指针移向下一个状态，返回`{ done, value }`(入参会被当作上一个`yield命令表达式`的返回值)
  - **return()**：返回指定值且终结遍历`Generator函数`，返回`{ done: true, value: 入参 }`
  - **throw()**：在`Generator函数`体外抛出错误，在`Generator函数`体内捕获错误，返回自定义的`new Errow()`

- yield命令：声明内部状态的值(

  ```
  return
  ```

  声明结束返回的值)

  - 遇到`yield命令`就暂停执行后面的操作，并将其后表达式的值作为返回对象的`value`
  - 下次调用`next()`时，再继续往下执行直到遇到下一个`yield命令`
  - 没有再遇到`yield命令`就一直运行到`Generator函数`结束，直到遇到`return语句`为止并将其后表达式的值作为返回对象的`value`
  - `Generator函数`没有`return语句`则返回对象的`value`为`undefined`

- yield*命令：在一个`Generator函数`里执行另一个`Generator函数`(后随具有`Iterator接口`的数据结构)

- 遍历：通过`for-of`自动调用`next()`

- 作为对象属性

  - 全写：`const obj = { method: function*() {} }`
  - 简写：`const obj = { * method() {} }`

- 上下文：执行产生的`上下文环境`一旦遇到`yield命令`就会暂时退出堆栈(但并不消失)，所有变量和对象会冻结在`当前状态`，等到对它执行`next()`时，这个`上下文环境`又会重新加入调用栈，冻结的变量和对象恢复执行

> 方法异同

- 相同点：`next()`、`throw()`、`return()`本质上是同一件事，作用都是让函数恢复执行且使用不同的语句替换`yield命令`
- 不同点
  - **next()**：将`yield命令`替换成一个`值`
  - **return()**：将`yield命令`替换成一个`return语句`
  - **throw()**：将`yield命令`替换成一个`throw语句`

> 应用场景

- 异步操作同步化表达
- 控制流管理
- 为对象部署Iterator接口：把`Generator函数`赋值给对象的`Symbol.iterator`，从而使该对象具有`Iterator接口`
- 作为具有Iterator接口的数据结构

> 重点难点

- 每次调用`next()`，指针就从`函数头部`或`上次停下的位置`开始执行，直到遇到下一个`yield命令`或`return语句`为止
- 函数内部可不用`yield命令`，但会变成单纯的`暂缓执行函数`(还是需要`next()`触发)
- `yield命令`是暂停执行的标记，`next()`是恢复执行的操作
- `yield命令`用在另一个表达式中必须放在`圆括号`里
- `yield命令`用作函数参数或放在赋值表达式的右边，可不加`圆括号`
- `yield命令`本身没有返回值，可认为是返回`undefined`
- `yield命令表达式`为惰性求值，等`next()`执行到此才求值
- 函数调用后生成遍历器对象，此对象的`Symbol.iterator`是此对象本身
- 在函数运行的不同阶段，通过`next()`从外部向内部注入不同的值，从而调整函数行为
- 首个`next()`用来启动遍历器对象，后续才可传递参数
- 想首次调用`next()`时就能输入值，可在函数外面再包一层
- 一旦`next()`返回对象的`done`为`true`，`for-of`遍历会中止且不包含该返回对象
- 函数内部部署`try-finally`且正在执行`try`，那么`return()`会导致立刻进入`finally`，执行完`finally`以后整个函数才会结束
- 函数内部没有部署`try-catch`，`throw()`抛错将被外部`try-catch`捕获
- `throw()`抛错要被内部捕获，前提是必须`至少执行过一次next()`
- `throw()`被捕获以后，会附带执行下一条`yield命令`
- 函数还未开始执行，这时`throw()`抛错只可能抛出在函数外部

> 首次next()可传值

```javascript
function Wrapper(func) {
    return function(...args) {
        const generator = func(...args);
        generator.next();
        return generator;
    }
}
const print = Wrapper(function*() {
    console.log(`First Input: ${yield}`);
    return "done";
});
print().next("hello");
```

## ES2016

![ES2016](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/a8b6131b43a2415e8deb82c53a054432~tplv-k3u1fbpfcp-zoom-in-crop-mark:4536:0:0:0.image)

### 数值扩展

-  **指数运算符(\**)**：数值求幂(相当于`Math.pow()`)

### 数组扩展

-  **includes()**：是否存在指定成员

# 四十八、var、let、const的区别

- var 语句的作用域是函数作用域或者全局作用域；它没有块作用域，故不存在暂时死区；它可分配，也可重复性声明。
- let 语句属于块作用域，受到暂时死区的约束；它可分配，但不可重新声明。
- const 语句也属于块作用域，同样受到暂时死区的约束；它既不可重新分配，也不可重新声明。

# 四十九、箭头函数和普通函数的区别

## 1：写法不一样

![img](https://upload-images.jianshu.io/upload_images/16021827-39c9fca447ea83b3.png?imageMogr2/auto-orient/strip|imageView2/2/w/452/format/webp)

## 2：普通函数存在变量提升的现象

![img](https://upload-images.jianshu.io/upload_images/16021827-57d393402892a458.jpg?imageMogr2/auto-orient/strip|imageView2/2/w/400/format/webp)

## 3：箭头函数不能作为构造函数使用

![img](https://upload-images.jianshu.io/upload_images/16021827-f861d69b3ebe9233.png?imageMogr2/auto-orient/strip|imageView2/2/w/774/format/webp)

## 4：两者的this指向不同

> 普通函数的this指向的是谁调用该函数就指向谁
>
> 箭头函数的this指向的是在你书写代码时候的上下文环境对象的this，如果没有上下文环境对象，那么就指向最外层对象window。

![img](https://upload-images.jianshu.io/upload_images/16021827-bbd21fc63a929fe7.png?imageMogr2/auto-orient/strip|imageView2/2/w/736/format/webp)

## 5：箭头函数的arguments指向其父级函数作用域的arguments

![img](https://upload-images.jianshu.io/upload_images/16021827-808506906716ac37.jpg?imageMogr2/auto-orient/strip|imageView2/2/w/960/format/webp)

## 6：箭头函数没有new.target

> 先说明下new.target是干嘛的，这家伙是用来检测函数是否被当做构造函数使用，他会返回一个指向构造函数的引用。
>
> 因为箭头函数不能当做构造函数使用，自然是没有new.target的。

![img](https://upload-images.jianshu.io/upload_images/16021827-c5b6b745bb9eec63.png?imageMogr2/auto-orient/strip|imageView2/2/w/452/format/webp)

# 五十、Set和Map的区别

## 1、简述

Set 和 Map 主要的应用场景在于 **数据重组** 和 **数据储存**。
Set 是一种叫做 集合 的[数据结构](https://so.csdn.net/so/search?q=%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84&spm=1001.2101.3001.7020)，Map 是一种叫做 字典 的数据结构。
[集合](https://so.csdn.net/so/search?q=%E9%9B%86%E5%90%88&spm=1001.2101.3001.7020)（Set）：
[ES6](https://so.csdn.net/so/search?q=ES6&spm=1001.2101.3001.7020) 新增的一种新的数据结构，类似于数组，成员唯一（内部元素没有重复的值）。且使用键对数据排序即顺序存储。

Set 本身是一种[构造函数](https://so.csdn.net/so/search?q=%E6%9E%84%E9%80%A0%E5%87%BD%E6%95%B0&spm=1001.2101.3001.7020)，用来生成 Set 数据结构。

Set 对象允许你储存任何类型的唯一值，无论是原始值或者是对象引用。

## 2、Map

**Map**是一组键值对的结构，用于解决以往不能用对象做为键的问题，具有极快的查找速度。(注：函数、对象、基本类型都可以作为键或值。)

例如下面代码，在n中有很长的数据，但是利用Map则查找十分迅速：

```javascript
const m=new map(['Kris',21],['Bob',19],['Lily',25],['Jack',27]);
m.get('Kris');   //  21
m.get('Lily');   //  25
```

初始化Map需要一个二维[数组](https://so.csdn.net/so/search?q=%E6%95%B0%E7%BB%84&spm=1001.2101.3001.7020)，或者直接初始化一个空Map，

```javascript
var m=new Map();
```

Map方法还有：

| Map方法        | 说明                                                       |
| -------------- | ---------------------------------------------------------- |
| set(key, val): | 向Map中添加新元素                                          |
| get(key):      | 通过键值查找特定的数值并返回                               |
| has(key):      | 判断Map对象中是否有Key所对应的值，有返回true,否则返回false |
| delete(key):   | 通过键值从Map中移除对应的数据                              |
| clear():       | 将这个Map中的所有元素删除                                  |

```javascript
var m=new Map( );	//初始化一个空的 map
m.set('Pluto',23);	//添加新的key-value 值
m.has('Pluto');   //true	是否存在key ‘Pluto’
m.get('Pluto');   	//23
m.delete('Pluto');	//删除key   ‘Pluto ’
```

**一个key只能对应一个value**，所以多次对一个key放入value，后面的值会把前面的值冲掉

```javascript
const m=new Map([['Lily',100],['Bob',97]]);
m.get('Bob');  //97
m.set('Bob',88);  //对key放入新的value
m.get('Bob');  //88
```

## 3、Set 

Set和Map类似，也是一组key的集合，但不存储value。由于key不能重复，所以，在Set中，**没有重复的key。**

这也就是为什么可以用set（）来进行去重。

要创建一个Set，需要提供一个Array作为输入，或者直接创建一个空Set：

```javascript
var s1=new Set();
var s2=new Set([1,2,3]);
```

重复元素在Set中会自动过滤（即重复元素不会被保留）

```javascript
var s=new Set([1,2,3,3,3,2,4]);
s;// set{1,2,3,4}
```

**add方法：**

| add 方法          | 说明                                              |
| ----------------- | ------------------------------------------------- |
| `add(value)`：    | 添加某个值，返回 Set 结构本身(可以链式调用)。     |
| `delete(value)`： | 删除某个值，删除成功返回`true`，否则返回`false`。 |
| `has(value)`：    | 返回一个布尔值，表示该值是否为Set的成员。         |
| `clear()`：       | 清除所有成员，没有返回值。                        |

通过add(key) 可以添加元素到Set中，可以重复添加，但不会有效果

通过delete(key) 可以删除元素

```javascript
var s=new Set([1,2,3,3]);
s.add(4);  // set{1,2,3,4}
s.add(3); //set{1,2,3,4}
s.size();   //4
s.has(3);  //true
```

## 4、Set和Map区别

1. Map是键值对，Set是值的集合，当然键和值可以是任何的值；
2. Map可以通过get方法获取值，而set不能因为它只有值；
3. 都能通过迭代器进行for...of遍历；
4. Set的值是唯一的可以做数组去重，Map由于没有格式限制，可以做数据存储
5. map和set都是stl中的关联容器，map以键值对的形式存储，key=value组成pair，是一组映射关系。set只有值，可以认为只有一个数据，并且set中元素不可以重复且自动排序。

# 五十一、Map和Object的区别

## 1、概念

Object

- 在ECMAScript中，Object是一个特殊的对象。它本身是一个顶级对象，同时还是一个构造函数，可以通过它（如：new Object()）来创建一个对象。我们可以认为JavaScript中所有的对象都是Object的一个实例，对象可以用字面量的方法const obj = {}即可声明。

Map

- Map是Object的一个子类，可以有序保存任意类型的数据，使用键值对去存储，其中键可以存储任意类型，通过const m = new Map();即可得到一个map实例。

## 2、相同点

```
二者都是以key-value的形式对数据进行存储;
```

## 3、不同点

**1.key的数据类型范围不同**

```javascript
Object：可以作为key的有:number,string,以及es6里面的symbol;
Map：js目前存在的数据类型均可以作为key;
```

**2.key的顺序**

```javascript
Object: 如果对象的key中同时存在number string symbol 三种类型的时候,通过Object.keys得到的顺序是数字(升序) -> string(symbol)以创建的顺序;
Map: key以声明的顺序进行排序;
```

**3.创建方式不同**

```javascript
Object：创建方式
const obj1 = new Object()
const obj2 = {}
const obj3 = Object.create({})
Map：创建方式:
const map = new Map();
```

**4.key的调用方式不同**

```javascript
通过key取值:
Object：可通过 . 或 []
Map：只能用原生的get方法进行调用;
判断是否有某个属性
Object:'a' in obj;判断obj中是否有a这个属性;
Map:map.has('a');判断map中是否有a这个属性;
```

**5.设置属性的方式不同**

```javascript
Object：
1.obj.a = 1;
2.obj['a'] = 1;
Map：js目前存在的数据类型均可以作为key;
1.map.set('a',1)
```

**6.删除key的方式**

```javascript
Object: 自身没有删除属性的方法;一般删除对象属性的方式: delete obj.a
Map: map.delete('a') ----删除a属性;
	 map.clear() ----删除所有的属性;
```

**7.获取size**

```javascript
Object: 通过Object.keys(obj) 返回一个数组,通过获取数组的长度来获取size;
Map: 自身带有size属性;map.size,size属性无法修改;
```

**8.Iterating(迭代)**

```javascript
Object: 不可以
Map: 可以;

如何判断一个数据是否可以迭代的方式
typeof [][Symbol.iterator] //function
typeof new Map()[Symbol.iterator] //function
typeof {}[Symbol.iterator]  //undefined
typeof 1[Symbol.iterator] //undefined
```

**9.JSON操作**

```javascript
Object: 支持JSON.stringify和JSON.parse的操作;
Map: 不支持;
```

**10.this不同**

```javascript
const f = function(){ console.log(this) }
Object: 
		const obj = {fn:f}
Map: 
		const map = new Map()
		map.set('fn',f)
		
obj.fn() //指向obj
map.get('fn')() //取决于函数的调用者;
```

# 五十二、扩展运算符

## 对象的扩展运算符

理解对象的扩展运算符其实很简单，只要记住一句话就可以：

> **对象中的扩展运算符(...)用于取出参数对象中的所有可遍历属性，拷贝到当前对象之中**

```javascript
let bar = { a: 1, b: 2 };
let baz = { ...bar }; // { a: 1, b: 2 }
```

上述方法实际上等价于:

```javascript
let bar = { a: 1, b: 2 };
let baz = Object.assign({}, bar); // { a: 1, b: 2 }
```

`Object.assign`方法用于对象的合并，将源对象`（source）`的所有可枚举属性，复制到目标对象`（target）`。

`Object.assign`方法的第一个参数是目标对象，后面的参数都是源对象。(**如果目标对象与源对象有同名属性，或多个源对象有同名属性，则后面的属性会覆盖前面的属性**)。

同样，如果用户自定义的属性，放在扩展运算符后面，则扩展运算符内部的同名属性会被覆盖掉。

```javascript
let bar = {a: 1, b: 2};
let baz = {...bar, ...{a:2, b: 4}};  // {a: 2, b: 4}
```

利用上述特性就可以很方便的修改对象的部分属性。在`redux`中的`reducer`函数规定必须是**一个纯函数**（如果不是很清楚什么是纯函数的可以参考[这里](http://huziketang.mangojuice.top/books/react/lesson32)），`reducer`中的`state`对象要求不能直接修改，可以通过扩展运算符把修改路径的对象都复制一遍，然后产生一个新的对象返回。

这里有点需要注意的是扩展运算符对对象实例的拷贝属于一种浅拷贝。肯定有人要问什么是浅拷贝？我们知道`javascript`中有两种数据类型，分别是*基础数据类型*和*引用数据类型*。*基础数据类型*是按值访问的，常见的*基础数据类型*有`Number`、`String`、`Boolean`、`Null`、`Undefined`，这类变量的拷贝的时候会完整的复制一份；*引用数据类型*比如`Array`，在拷贝的时候拷贝的是对象的引用，当原对象发生变化的时候，拷贝对象也跟着变化，比如：

```javascript
let obj1 = { a: 1, b: 2};
let obj2 = { ...obj1, b: '2-edited'};
console.log(obj1); // {a: 1, b: 2}
console.log(obj2); //  {a: 1, b: "2-edited"}
```

上面这个例子扩展运算符拷贝的对象是*基础数据类型*，因此对`obj2`的修改并不会影响`obj1`，如果改成这样：

```javascript
let obj1 = { a: 1, b: 2, c: {nickName: 'd'}};
let obj2 = { ...obj1};
obj2.c.nickName = 'd-edited';
console.log(obj1); // {a: 1, b: 2, c: {nickName: 'd-edited'}}
console.log(obj2); // {a: 1, b: 2, c: {nickName: 'd-edited'}}
```

这里可以看到，对`obj2`的修改影响到了被拷贝对象`obj1`，原因上面已经说了，因为`obj1`中的对象`c`是一个引用数据类型，拷贝的时候拷贝的是对象的引用。

## [数组](https://so.csdn.net/so/search?q=%E6%95%B0%E7%BB%84&spm=1001.2101.3001.7020)的扩展运算符

扩展运算符同样可以运用在对数组的操作中。

- 可以将数组转换为参数序列

```javascript
function add(x, y) {
  return x + y;
}

const numbers = [4, 38];
add(...numbers) // 42
```

- 可以复制数组

如果直接通过下列的方式进行数组复制是不可取的：

```javascript
const arr1 = [1, 2];
const arr2 = arr1;
arr2[0] = 2;
arr1 // [2, 2]
```

原因上面已经介绍过，用扩展运算符就很方便：

```javascript
const arr1 = [1, 2];
const arr2 = [...arr1];
```

还是记住那句话：**扩展运算符(…)用于取出参数对象中的所有可遍历属性，拷贝到当前对象之中**，这里参数对象是个数组，数组里面的所有对象都是基础数据类型，将所有基础数据类型重新拷贝到新的数组中。

- 扩展运算符可以与解构赋值结合起来，用于生成数组

```javascript
const [first, ...rest] = [1, 2, 3, 4, 5];
first // 1
rest  // [2, 3, 4, 5]
```

需要注意的一点是：

> **如果将扩展运算符用于数组赋值，只能放在参数的最后一位，否则会报错。**

```javascript
const [...rest, last] = [1, 2, 3, 4, 5];
// 报错
const [first, ...rest, last] = [1, 2, 3, 4, 5];
// 报错
```

- 扩展运算符还可以将字符串转为真正的数组

```javascript
[...'hello']
// [ "h", "e", "l", "l", "o" ]
```

- 任何 Iterator 接口的对象（参阅 Iterator 一章），都可以用扩展运算符转为真正的数组

这点说的比较官方，大家具体可以参考阮一峰老师的[ECMAScript 6入门教程](http://es6.ruanyifeng.com/?search=map&x=0&y=0#docs/array)。

比较常见的应用是可以将某些数据结构转为数组,比如：

```javascript
// arguments对象
function foo() {
  const args = [...arguments];
}
```

用于替换`es5`中的`Array.prototype.slice.call(arguments)`写法。

# 五十三、解构赋值

## [数组](https://so.csdn.net/so/search?q=%E6%95%B0%E7%BB%84&spm=1001.2101.3001.7020)的解构赋值

### 基本用法

[ES6](https://so.csdn.net/so/search?q=ES6&spm=1001.2101.3001.7020) 允许按照一定模式，从数组和对象中提取值，对变量进行赋值，这被称为解构（Destructuring）。

以前，为变量赋值，只能直接指定值。

```javascript
let a = 1;
let b = 2;
let c = 3;
```

ES6 允许写成下面这样。

```javascript
let [a, b, c] = [1, 2, 3];
```

上面代码表示，可以从数组中提取值，按照对应位置，对变量赋值。

本质上，这种写法属于“模式匹配”，只要等号两边的模式相同，左边的变量就会被赋予对应的值。下面是一些使用嵌套数组进行解构的例子。

```javascript
let [foo, [[bar], baz]] = [1, [[2], 3]];
foo // 1
bar // 2
baz // 3
 
let [ , , third] = ["foo", "bar", "baz"];
third // "baz"
 
let [x, , y] = [1, 2, 3];
x // 1
y // 3
 
let [head, ...tail] = [1, 2, 3, 4];
head // 1
tail // [2, 3, 4]
 
let [x, y, ...z] = ['a'];
x // "a"
y // undefined
z // []
```

如果解构不成功，变量的值就等于`undefined`。

```javascript
let [foo] = [];
let [bar, foo] = [1];
```

以上两种情况都属于解构不成功，`foo`的值都会等于`undefined`。

另一种情况是不完全解构，即等号左边的模式，只匹配一部分的等号右边的数组。这种情况下，解构依然可以成功。

```javascript
let [x, y] = [1, 2, 3];
x // 1
y // 2
 
let [a, [b], d] = [1, [2, 3], 4];
a // 1
b // 2
d // 4
```

上面两个例子，都属于不完全解构，但是可以成功。

如果等号的右边不是数组（或者严格地说，不是可遍历的结构，参见《Iterator》一章），那么将会报错。

```javascript
// 报错
let [foo] = 1;
let [foo] = false;
let [foo] = NaN;
let [foo] = undefined;
let [foo] = null;
let [foo] = {};
```

上面的语句都会报错，因为等号右边的值，要么转为对象以后不具备 Iterator 接口（前五个表达式），要么本身就不具备 Iterator 接口（最后一个表达式）。

对于 Set 结构，也可以使用数组的解构赋值。

```javascript
let [x, y, z] = new Set(['a', 'b', 'c']);
x // "a"
```

事实上，只要某种数据结构具有 Iterator 接口，都可以采用数组形式的解构赋值。

```javascript
function* fibs() {
  let a = 0;
  let b = 1;
  while (true) {
    yield a;
    [a, b] = [b, a + b];
  }
}
 
let [first, second, third, fourth, fifth, sixth] = fibs();
sixth // 5
```

上面代码中，`fibs`是一个 Generator 函数（参见《Generator 函数》一章），原生具有 Iterator 接口。解构赋值会依次从这个接口获取值。

### 默认值

解构赋值允许指定默认值。

```javascript
let [foo = true] = [];
foo // true
let [x, y = 'b'] = ['a']; // x='a', y='b'
let [x, y = 'b'] = ['a', undefined]; // x='a', y='b'
```

注意，ES6 内部使用严格相等运算符（`===`），判断一个位置是否有值。所以，只有当一个数组成员严格等于`undefined`，默认值才会生效。

```javascript
let [x = 1] = [undefined];
x // 1
let [x = 1] = [null];
x // null
```

上面代码中，如果一个数组成员是`null`，默认值就不会生效，因为`null`不严格等于`undefined`。

如果默认值是一个表达式，那么这个表达式是惰性求值的，即只有在用到的时候，才会求值。

```javascript
function f() {
console.log('aaa');
}
let [x = f()] = [1];
```

上面代码中，因为`x`能取到值，所以函数`f`根本不会执行。上面的代码其实等价于下面的代码。

```javascript
let x;
if ([1][0] === undefined) {
  x = f();
} else {
  x = [1][0];
}
```

默认值可以引用解构赋值的其他变量，但该变量必须已经声明。

```javascript
let [x = 1, y = x] = [];     // x=1; y=1
let [x = 1, y = x] = [2];    // x=2; y=2
let [x = 1, y = x] = [1, 2]; // x=1; y=2
let [x = y, y = 1] = [];     // ReferenceError: y is not defined
```

上面最后一个表达式之所以会报错，是因为`x`用`y`做默认值时，`y`还没有声明。

## 对象的解构赋值

### 简介

解构不仅可以用于数组，还可以用于对象。

```javascript
let { foo, bar } = { foo: 'aaa', bar: 'bbb' };
foo // "aaa"
bar // "bbb"
```

对象的解构与数组有一个重要的不同。数组的元素是按次序排列的，变量的取值由它的位置决定；而对象的属性没有次序，变量必须与属性同名，才能取到正确的值。

```javascript
let { bar, foo } = { foo: 'aaa', bar: 'bbb' };
foo // "aaa"
bar // "bbb"
let { baz } = { foo: 'aaa', bar: 'bbb' };
baz // undefined
```

上面代码的第一个例子，等号左边的两个变量的次序，与等号右边两个同名属性的次序不一致，但是对取值完全没有影响。第二个例子的变量没有对应的同名属性，导致取不到值，最后等于`undefined`。

如果解构失败，变量的值等于`undefined`。

```javascript
let {foo} = {bar: 'baz'};
foo // undefined
```

上面代码中，等号右边的对象没有`foo`属性，所以变量`foo`取不到值，所以等于`undefined`。

对象的解构赋值，可以很方便地将现有对象的方法，赋值到某个变量。

```javascript
// 例一
let { log, sin, cos } = Math;
// 例二
const { log } = console;
log('hello') // hello
```

上面代码的例一将`Math`对象的对数、正弦、余弦三个方法，赋值到对应的变量上，使用起来就会方便很多。例二将`console.log`赋值到`log`变量。

如果变量名与属性名不一致，必须写成下面这样。

```javascript
let { foo: baz } = { foo: 'aaa', bar: 'bbb' };
baz // "aaa"
 
let obj = { first: 'hello', last: 'world' };
let { first: f, last: l } = obj;
f // 'hello'
l // 'world'
```

这实际上说明，对象的解构赋值是下面形式的简写（参见《对象的扩展》一章）。

```javascript
let { foo: foo, bar: bar } = { foo: 'aaa', bar: 'bbb' };
```

也就是说，对象的解构赋值的内部机制，是先找到同名属性，然后再赋给对应的变量。真正被赋值的是后者，而不是前者。

```javascript
let { foo: baz } = { foo: 'aaa', bar: 'bbb' };
baz // "aaa"
foo // error: foo is not defined
```

上面代码中，`foo`是匹配的模式，`baz`才是变量。真正被赋值的是变量`baz`，而不是模式`foo`。

与数组一样，解构也可以用于嵌套结构的对象。

```javascript
let obj = {
  p: [
    'Hello',
    { y: 'World' }
  ]
};
 
let { p: [x, { y }] } = obj;
x // "Hello"
y // "World"
```

注意，这时`p`是模式，不是变量，因此不会被赋值。如果`p`也要作为变量赋值，可以写成下面这样。

```javascript
let obj = {
  p: [
    'Hello',
    { y: 'World' }
  ]
};
 
let { p, p: [x, { y }] } = obj;
x // "Hello"
y // "World"
p // ["Hello", {y: "World"}]
```

下面是另一个例子。

```javascript
const node = {
  loc: {
    start: {
      line: 1,
      column: 5
    }
  }
};
 
let { loc, loc: { start }, loc: { start: { line }} } = node;
line // 1
loc  // Object {start: Object}
start // Object {line: 1, column: 5}
```

上面代码有三次解构赋值，分别是对`loc`、`start`、`line`三个属性的解构赋值。注意，最后一次对`line`属性的解构赋值之中，只有`line`是变量，`loc`和`start`都是模式，不是变量。

下面是嵌套赋值的例子。

```javascript
let obj = {};
let arr = [];
 
({ foo: obj.prop, bar: arr[0] } = { foo: 123, bar: true });
 
obj // {prop:123}
arr // [true]
```

如果解构模式是嵌套的对象，而且子对象所在的父属性不存在，那么将会报错。

```javascript
// 报错
let {foo: {bar}} = {baz: 'baz'};
```

上面代码中，等号左边对象的`foo`属性，对应一个子对象。该子对象的`bar`属性，解构时会报错。原因很简单，因为`foo`这时等于`undefined`，再取子属性就会报错。

注意，对象的解构赋值可以取到继承的属性。

```javascript
const obj1 = {};
const obj2 = { foo: 'bar' };
Object.setPrototypeOf(obj1, obj2);
const { foo } = obj1;
foo // "bar"
```

上面代码中，对象`obj1`的原型对象是`obj2`。`foo`属性不是`obj1`自身的属性，而是继承自`obj2`的属性，解构赋值可以取到这个属性。

### 默认值

对象的解构也可以指定默认值。

```javascript
var {x = 3} = {};
x // 3
 
var {x, y = 5} = {x: 1};
x // 1
y // 5
 
var {x: y = 3} = {};
y // 3
 
var {x: y = 3} = {x: 5};
y // 5
 
var { message: msg = 'Something went wrong' } = {};
msg // "Something went wrong"
```

默认值生效的条件是，对象的属性值严格等于`undefined`。

```javascript
var {x = 3} = {x: undefined};
x // 3
var {x = 3} = {x: null};
x // null
```

上面代码中，属性`x`等于`null`，因为`null`与`undefined`不严格相等，所以是个有效的赋值，导致默认值`3`不会生效。

### 注意点

（1）如果要将一个已经声明的变量用于解构赋值，必须非常小心。

```javascript
// 错误的写法
let x;
{x} = {x: 1};
// SyntaxError: syntax error
```

上面代码的写法会报错，因为 JavaScript 引擎会将`{x}`理解成一个代码块，从而发生语法错误。只有不将大括号写在行首，避免 JavaScript 将其解释为代码块，才能解决这个问题。

```javascript
// 正确的写法
let x;
({x} = {x: 1});
```

上面代码将整个解构赋值语句，放在一个圆括号里面，就可以正确执行。关于圆括号与解构赋值的关系，参见下文。

（2）解构赋值允许等号左边的模式之中，不放置任何变量名。因此，可以写出非常古怪的赋值表达式。

```javascript
({} = [true, false]);
({} = 'abc');
({} = []);
```

上面的表达式虽然毫无意义，但是语法是合法的，可以执行。

（3）由于数组本质是特殊的对象，因此可以对数组进行对象属性的解构。

```javascript
let arr = [1, 2, 3];
let {0 : first, [arr.length - 1] : last} = arr;
first // 1
last // 3
```

上面代码对数组进行对象解构。数组`arr`的`0`键对应的值是`1`，`[arr.length - 1]`就是`2`键，对应的值是`3`。方括号这种写法，属于“属性名表达式”（参见《对象的扩展》一章）。

## 字符串的解构赋值

字符串也可以解构赋值。这是因为此时，字符串被转换成了一个类似数组的对象。

```javascript
const [a, b, c, d, e] = 'hello';
a // "h"
b // "e"
c // "l"
d // "l"
e // "o"
```

类似数组的对象都有一个`length`属性，因此还可以对这个属性解构赋值。

```javascript
let {length : len} = 'hello';
len // 5
```

## 数值和布尔值的解构赋值

解构赋值时，如果等号右边是数值和布尔值，则会先转为对象。

```javascript
let {toString: s} = 123;
s === Number.prototype.toString // true
let {toString: s} = true;
s === Boolean.prototype.toString // true
```

上面代码中，数值和布尔值的包装对象都有`toString`属性，因此变量`s`都能取到值。

解构赋值的规则是，只要等号右边的值不是对象或数组，就先将其转为对象。由于`undefined`和`null`无法转为对象，所以对它们进行解构赋值，都会报错。

```javascript
let { prop: x } = undefined; // TypeError
let { prop: y } = null; // TypeError
```

## 函数参数的解构赋值

函数的参数也可以使用解构赋值。

```javascript
function add([x, y]){
  return x + y;
}
add([1, 2]); // 3
```

上面代码中，函数`add`的参数表面上是一个数组，但在传入参数的那一刻，数组参数就被解构成变量`x`和`y`。对于函数内部的代码来说，它们能感受到的参数就是`x`和`y`。

下面是另一个例子。

```javascript
[[1, 2], [3, 4]].map(([a, b]) => a + b);
// [ 3, 7 ]
```

函数参数的解构也可以使用默认值。

```javascript
function move({x = 0, y = 0} = {}) {
  return [x, y];
}
 
move({x: 3, y: 8}); // [3, 8]
move({x: 3}); // [3, 0]
move({}); // [0, 0]
move(); // [0, 0]
```

上面代码中，函数`move`的参数是一个对象，通过对这个对象进行解构，得到变量`x`和`y`的值。如果解构失败，`x`和`y`等于默认值。

注意，下面的写法会得到不一样的结果。

```javascript
function move({x, y} = { x: 0, y: 0 }) {
  return [x, y];
}
 
move({x: 3, y: 8}); // [3, 8]
move({x: 3}); // [3, undefined]
move({}); // [undefined, undefined]
move(); // [0, 0]
```

上面代码是为函数`move`的参数指定默认值，而不是为变量`x`和`y`指定默认值，所以会得到与前一种写法不同的结果。

`undefined`就会触发函数参数的默认值。

```javascript
[1, undefined, 3].map((x = 'yes') => x);
// [ 1, 'yes', 3 ]
```

## 圆括号问题

解构赋值虽然很方便，但是解析起来并不容易。对于编译器来说，一个式子到底是模式，还是表达式，没有办法从一开始就知道，必须解析到（或解析不到）等号才能知道。

由此带来的问题是，如果模式中出现圆括号怎么处理。ES6 的规则是，只要有可能导致解构的歧义，就不得使用圆括号。

但是，这条规则实际上不那么容易辨别，处理起来相当麻烦。因此，建议只要有可能，就不要在模式中放置圆括号。

### 不能使用圆括号的情况

以下三种解构赋值不得使用圆括号。

（1）变量声明语句

```javascript
// 全部报错
let [(a)] = [1];
 
let {x: (c)} = {};
let ({x: c}) = {};
let {(x: c)} = {};
let {(x): c} = {};
 
let { o: ({ p: p }) } = { o: { p: 2 } };
```

上面 6 个语句都会报错，因为它们都是变量声明语句，模式不能使用圆括号。

（2）函数参数

函数参数也属于变量声明，因此不能带有圆括号。

```javascript
// 报错
function f([(z)]) { return z; }
// 报错
function f([z,(x)]) { return x; }
```

（3）赋值语句的模式

```javascript
// 全部报错
({ p: a }) = { p: 42 };
([a]) = [5];
```

上面代码将整个模式放在圆括号之中，导致报错。

```javascript
// 报错
[({ p: a }), { x: c }] = [{}, {}];
```

上面代码将一部分模式放在圆括号之中，导致报错。

### 可以使用圆括号的情况

可以使用圆括号的情况只有一种：赋值语句的非模式部分，可以使用圆括号。

```javascript
[(b)] = [3]; // 正确
({ p: (d) } = {}); // 正确
[(parseInt.prop)] = [3]; // 正确
```

上面三行语句都可以正确执行，因为首先它们都是赋值语句，而不是声明语句；其次它们的圆括号都不属于模式的一部分。第一行语句中，模式是取数组的第一个成员，跟圆括号无关；第二行语句中，模式是`p`，而不是`d`；第三行语句与第一行语句的性质一致。

## 用途

变量的解构赋值用途很多。

**（1）交换变量的值**

```javascript
let x = 1;
let y = 2;
[x, y] = [y, x];
```

上面代码交换变量`x`和`y`的值，这样的写法不仅简洁，而且易读，语义非常清晰。

**（2）从函数返回多个值**

函数只能返回一个值，如果要返回多个值，只能将它们放在数组或对象里返回。有了解构赋值，取出这些值就非常方便。

```javascript
// 返回一个数组
 
function example() {
  return [1, 2, 3];
}
let [a, b, c] = example();
 
// 返回一个对象
 
function example() {
  return {
    foo: 1,
    bar: 2
  };
}
let { foo, bar } = example();
```

**（3）函数参数的定义**

解构赋值可以方便地将一组参数与变量名对应起来。

```javascript
// 参数是一组有次序的值
function f([x, y, z]) { ... }
f([1, 2, 3]);
 
// 参数是一组无次序的值
function f({x, y, z}) { ... }
f({z: 3, y: 2, x: 1});
```

**（4）提取 JSON 数据**

解构赋值对提取 JSON 对象中的数据，尤其有用。

```javascript
let jsonData = {
  id: 42,
  status: "OK",
  data: [867, 5309]
};
 
let { id, status, data: number } = jsonData;
 
console.log(id, status, number);
// 42, "OK", [867, 5309]
```

上面代码可以快速提取 JSON 数据的值。

**（5）函数参数的默认值**

```javascript
jQuery.ajax = function (url, {
  async = true,
  beforeSend = function () {},
  cache = true,
  complete = function () {},
  crossDomain = false,
  global = true,
  // ... more config
} = {}) {
  // ... do stuff
};
```

指定参数的默认值，就避免了在函数体内部再写`var foo = config.foo || 'default foo';`这样的语句。

**（6）遍历 Map 结构**

任何部署了 Iterator 接口的对象，都可以用`for...of`循环遍历。Map 结构原生支持 Iterator 接口，配合变量的解构赋值，获取键名和键值就非常方便。

```javascript
const map = new Map();
map.set('first', 'hello');
map.set('second', 'world');
 
for (let [key, value] of map) {
  console.log(key + " is " + value);
}
// first is hello
// second is world
```

如果只想获取键名，或者只想获取键值，可以写成下面这样。

```javascript
// 获取键名
for (let [key] of map) {
  // ...
}
 
// 获取键值
for (let [,value] of map) {
  // ...
}
```

**（7）输入模块的指定方法**

加载模块时，往往需要指定输入哪些方法。解构赋值使得输入语句非常清晰。

```javascript
const { SourceMapConsumer, SourceNode } = require("source-map");
```

# 五十四、Promise的理解

1、概念：**Promise** 对象用于表示一个异步操作的最终完成 (或失败)及其结果值。

2、状态：大致分为三种状态。

①：pending：未决定的

②、resolved / fullfilled：成功

③、rejected：失败

状态的改变：pending -》 resolved

pending -》 rejected

3、解决了什么问题？

①、支持链式调用，解决了回掉地狱的问题。

实例对象中的一个属性 【PromiseState】。

`promise.then()`，`promise.catch()`和`promise.finally()`等方法可以实现。

什么是回调地狱？：回调函数嵌套调用，外部回调函数异步执行的结果是嵌套的回执行的条件。

回调地狱的缺点：

不便于阅读

不便于异常处理

解决方案：Promise链式调用

例如：

const myPromise =
(new Promise(myExecutorFunc))
.then(handleFulfilledA)
.then(handleFulfilledB)
.then(handleFulfilledC)
.catch(handleRejectedAny);

②、启动异步任务 =》 返回Promise对象 =》给Promise对象绑定回调函数。

4、Promise 对象的值

实例对象中的另一个属性值：【PromiseResult】

保存着异步任务 【成功/失败】的结果

以上是两个方法

resolve

reject

5、Promise的基本流程

![img](https://pic2.zhimg.com/80/v2-62e1272b4106d0f66a2f0adeae24e795_720w.webp)

pending：初始状态，既没有被兑现，也没有被拒绝。

fullfiled：待定状态的 Promise 对象要么会通过一个值*被兑现*

*rejected：*通过某个原因（错误）*被拒绝*

then：将*fullfilled或rejected的两种情况被执行调用，返回的是promise，所以会被链式的调用。*

链式实现：

~~~javascript
// 在上面代码中 是实现了new出一个对象 定义了个常量来接收了 不用常量接收直接使用时
 
const num = 2;
 
new Promise((r,e) => {  // r(resolve)  e(reject)
    // 异步逻辑代码
    num === 1 ? r(num) : e(num) // 同一个逻辑中只能执行一种状态方式
}).then(res => {
    console.log(`num为1时被调用，num为：${res}`)
}).catch(err => {
    console.log(`num为2时被调用，num为：${err}`)
})
~~~

then方法解释：

~~~javascript
// then方法是new时返回对象里的方法 也就是Promise里内置的一些方法
// then可以有第二个回调参数 这个回调参数就是catch
const num = 1;
 
new Promise((r,e) => {
    // 异步逻辑代码
    num === 1 ? r(num) : e(num)
}).then(res => {  // 为r(resolve)调用时执行的方法
    console.log(`num为1时被调用，num为：${res}`)
}, err => {       // 为e(reject)调用时执行的方法
    console.log(`num为2时被调用，num为：${err}`)
})
 
// 在then方法里 会返回一个新的Promise 这就是Promise链式调用的本质 
 
// 在then里如果返回的是一个普通值(数字/字符串/普通对象/undefined) 那么这个返回值就会作为这个新返回对象里的resolve调用时传参的值 此时再链式调用then方法调用的就是新Promise对象的方法
// 如果返回的是一个Promise，当前状态就会变成返回Promise里的状态 同理返回一个对象 里面包含then方法时 也会改变状态
~~~

catch方法解释：

~~~javascript
// catch方法在new的Promise中的回调函数里调用第二个参数(reject)时，就会回调catch方法里的回调参数 (也可是then中的第二个回调参数)。
// 在在new的Promise中的回调函数抛出异常时也会回调这个回调参数
 
const num = 1;
 
new Promise((resolve,reject) => {
    if(num === 2) {
        resolve(num);
    }else {
        // reject(num);  // 此时就会回调catch里的会调参数
        throw new Error('num不为2',num); // 此时也会回调catch里的会调参数
    } 
}).then(res => {
    console.log(`num等于2时:${res}`)
}).catch(err => {
    console.log(`num不等于2时:${err}`)
})
 
~~~

finally方法解释：

~~~javascript
// finally 无论什么状态都会执行
 
const num = 1;
 
new Promise((resolve,reject) => {
    num === 1 ? resolve(num) : reject(num);
}).then(res => {
    console.log(`num等于1时:${res}`)
}).catch(err => {
    console.log(`num不等于1时:${err}`)
}).finally(() => {
    console.log(`都会执行`)
})
 
~~~

Promise类上的方法 all / allSettled

~~~javascript
// all方法可以多个Promise一起使用 统一返回所有结果
 
const num = 1;
    
const p1 = new Promise((r,t) => {
    num === 1 ? r(num) : t(num);
})
 
const p2 = new Promise((r,t) => {
    num === 1 ? r(num) : t(num);
})
 
const p3 = new Promise((r,t) => {
    num === 1 ? r(num) : t(num);
})
 
Promise.all([p1,p2,p3]).then((res) => {
    console.log(res);  // [1,1,1] 以数组的方式返回所有结果
})
 
// 当其中一个抛出异常 或者执行t(reject)方法时会在执行处阻断Promise，下面的Promise执行就会被阻断
// 如若不乡阻断，可以用类allSettled方法
 
Promise.allSettled([p1,p2,p3]).then((res) => {
    console.log(res);  // 以数组的方式返回所有结果
})
~~~

# 五十五、async和await

**async和await 概念**

​     先从字面意思来理解。[async](https://so.csdn.net/so/search?q=async&spm=1001.2101.3001.7020) 是“异步”的简写，而 await 可以认为是 async wait 的简写。所以应该很好理解 async 用于申明一个 function 是异步的，而 await 用于等待一个异步方法执行完成。

​    另外还有一个很有意思的语法规定，await 只能出现在 async 函数中。然后细心的朋友会产生一个疑问，如果 await 只能出现在 async 函数中，那这个 async 函数应该怎么调用？

​     如果需要通过 await 来调用一个 async 函数，那这个调用的外面必须得再包一个 async 函数，然后……进入死循环，永无出头之日……

  再来说说async有什么作用。

**async的作用**

​       这个问题的关键在于，async 函数是怎么处理它的返回值的！

用return吗？那await做什么呢？试一下。

![img](https://img-blog.csdnimg.cn/0964180cbadd431f95495ebdc8d5ce59.PNG) 

看结果，我们知道返回的是一个promise对象。

![img](https://img-blog.csdnimg.cn/6093d81657e1462fa634a8dc0fd95a09.PNG)

​      所以我们从中知道，async 函数返回的是一个 Promise 对象。async 函数（包含函数语句、函数表达式）会返回一个 Promise 对象，如果在函数中 `return` 一个直接量，async 会把这个直接量通过 `Promise.resolve()` 封装成 Promise 对象。

​      async 函数返回的是一个 Promise 对象，所以在最外层不能用 await 获取其返回值的情况下，我们当然应该用原来的方式：`then()` 链来处理这个 Promise 对象，试一下

![img](https://img-blog.csdnimg.cn/6b19c418438745faa40f7c143c6cb5d4.PNG)

输出结果 ⬇

![img](https://img-blog.csdnimg.cn/72c42c1d90b94a5fbc8322ef8fd56b55.PNG) 

 如果async函数没有返回值会报错吗？该返回什么？

 ![img](https://img-blog.csdnimg.cn/b8001c651cb64737b926b542d5c18dd1.PNG)

![img](https://img-blog.csdnimg.cn/b49b09dbbb304d87b98a037e56643fbd.PNG) 

  不会报错，直接返回undefined。

​    在没有 `await` 的情况下执行 async 函数，它会立即执行，返回一个 Promise 对象，并且，绝不会阻塞后面的语句。这和普通返回 Promise 对象的函数并无二致。

**那await是做什么用的：**

​    可以认为 await 是在等待一个 async 函数完成。await 等待的是一个表达式，这个表达式的计算结果是 Promise 对象或者其它值（换句话说，就是没有特殊限定）。

​    因为 async 函数返回一个 Promise 对象，所以 await 可以用于等待一个 async 函数的返回值——这也可以说是 await 在等 async 函数，但要清楚，它等的实际是一个返回值。注意到 await 不仅仅用于等 Promise 对象，它可以等任意表达式的结果，所以，await 后面实际是可以接普通函数调用或者直接量的。找一个例子试试看。

 ![img](https://img-blog.csdnimg.cn/6e9c75d8adc14457b02cc69e5398692a.PNG?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5ZGG55Oc55Oc55Oc,size_17,color_FFFFFF,t_70,g_se,x_16)

返回结果

![img](https://img-blog.csdnimg.cn/0f94879765434f9a9210d14a5f614cae.PNG) 

**await等到结果之后呢？**

​     await 等到了它要等的东西，一个 Promise 对象，或者其它值，然后呢？我不得不先说，`await` 是个运算符，用于组成表达式，await 表达式的运算结果取决于它等的东西。

​    如果它等到的不是一个 Promise 对象，那 await 表达式的运算结果就是它等到的东西。

​    如果它等到的是一个 Promise 对象，await 就忙起来了，它会阻塞后面的代码，等着 Promise 对象 resolve，然后得到 resolve 的值，作为 await 表达式的运算结果。

​    其实这就是 await 必须用在 async 函数中的原因。async 函数调用不会造成阻塞，它内部所有的阻塞都被封装在一个 Promise 对象中异步执行。

**async/await帮我们做了啥？**

先做个简单的比较吧 ⬇

​    之前已经说明了 async 会将其后的函数的返回值封装成一个 Promise 对象，而 await 会等待这个 Promise 完成，并将其 resolve 的结果返回出来。

举个例子，用 `setTimeout` 模拟耗时的异步操作，先来看看不用 async/await 会怎么写

![img](https://img-blog.csdnimg.cn/2e5f1abd34114be98ebd76c9c202fdc4.PNG?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5ZGG55Oc55Oc55Oc,size_19,color_FFFFFF,t_70,g_se,x_16)

 再试试async/await

![img](https://img-blog.csdnimg.cn/52dbf1ed79ba48819379787f5dbcb54a.PNG?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5ZGG55Oc55Oc55Oc,size_19,color_FFFFFF,t_70,g_se,x_16)

 

​    我们看到 `takeLongTime()` 没有申明为 `async`。实际上，`takeLongTime()` 本身就是返回的 Promise 对象，加不加 `async` 结果都一样。

​    又一个疑问产生了，这两段代码，两种方式对异步调用的处理（实际就是对 Promise 对象的处理）差别并不明显，甚至使用 async/await 还需要多写一些代码，那它的优势到底在哪？

**async/await的优势在于处理 then：**

​    单一的 Promise 链并不能发现 async/await 的优势，但是，如果需要处理由多个 Promise 组成的 then 链的时候，优势就能体现出来了（Promise 通过 then 链来解决多层回调的问题，现在又用 async/await 来进一步优化它）。

​    假设一个业务，分多个步骤完成，每个步骤都是异步的，而且依赖于上一个步骤的结果。我们仍然用 `setTimeout` 来模拟异步操作：

![img](https://img-blog.csdnimg.cn/390b043765724e90b6b122d8c9b71b12.PNG?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5ZGG55Oc55Oc55Oc,size_16,color_FFFFFF,t_70,g_se,x_16)

 现在用promise实现这三个步骤的处理![img](https://img-blog.csdnimg.cn/36bfbd84f6854894a2fe1de54d150e49.PNG?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5ZGG55Oc55Oc55Oc,size_17,color_FFFFFF,t_70,g_se,x_16)

输出结果

![img](https://img-blog.csdnimg.cn/527510e2cef84b0a806542ad182f3d30.PNG?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5ZGG55Oc55Oc55Oc,size_19,color_FFFFFF,t_70,g_se,x_16)

 结果和之前的 Promise 实现是一样的，但是这个代码看起来是不是清晰得多，几乎跟同步代码一样

# 五十六、JS模块化

## 1、什么是模块化

在js刚刚出现的时候，是为了实现一些简单的功能，但随着浏览器的不断发展，js越来越被重视起来，可以实现较为复杂的功能。这个时候开发者为了维护方便，会把不同功能的模块抽离出来写入单独的js文件，但是当项目更为复杂的时候，html可能会引入很多个js文件，而这个时候就会出现命名冲突，污染作用域等一系列问题，这个时候模块化的概念及实现方法应运而生。

模块化开发是一种管理方式，一种生产方式，一种解决问题的方案。一个模块就是实现某个特定功能的文件，我们可以很方便的使用别人的代码，想要什么模块，就引入那个模块。但是模块开发要遵循一定的规范，后面就出现了我们所熟悉的AMD和[CMD](https://so.csdn.net/so/search?q=CMD&spm=1001.2101.3001.7020)规范。

**（以下只讲各模块化的基本知识与开发中的使用方法，不讲实现原理及内部处理机制。）**

## 2、立即执行函数

在早期，使用立即执行函数实现模块化是最常见的手段，通过函数作用域解决了命名冲突、污染全局的问题，那么立即执行函数也是一种模块化的实现方式，但并非是一种解决方案。举个例子：

```javascript
(function (a) {
    // 在这里面声明各种变量、函数都不会污染全局作用域
})(a)
```

## 3、AMD

AMD即是“异步模块定义”，它采用异步方式加载模块，模块的加载不影响后面语句的运行，所有依赖整个模块的语句，都定义在一个回调函数中，等到加载完成后，整个回调函数才会运行。

在AMD规范中，我们使用define定义模块，使用require加载模块。

### **1、定义模块**

```javascript
define(id?, dependencies?, factory);
```

- id是定义的模块名，这个参数是可选的，如果没有定义该参数，模块名字应该默认为模块加载器请求的指定脚本的名字，如果有该参数，模块名必须是顶级的绝对的。
- dependencies是定义的模块中所依赖的模块数组，依赖模块优先级执行，并且执行结果按照数组中的排序依次以参数的形式传入factory。
- factory是模块初始化要执行的函数或对象，只被执行依次，如果是对象，则为该模块的输出值。

下面来看一个例子：

```javascript
define("OrderModel", ["Header", "Pay"], function (Header, Pay) {   
    var OrderModel = function () {
        this.headerData = Header.getHeaderData();
        this.payData = Pay.getPayData();
    }
    return OrderModel;
})
```

### **2、加载模块**

```javascript
require([module], callback); 
```

require要传入两个参数，第一个是[module]，是一个数组，就是要加载的模块，第二个callback是加载成功之后的回调函数。

下面举个例子：

```javascript
// 在定义模块中已经定义过OrderModel模块了，下面只需要加载并使用它
require(["OrderModel"], function (OrderModel) {
    console.log(OrderModel.headerData);    
    console.log(OrderModel.payData);
})
```

## 4、CMD

CMD即是“通用模块定义”，CMD规范是国内发展出来的，CMD和AMD都是要解决同一个问题，只不过两者在模块定义方式和模块加载时机上有所不同罢了。

### **1、定义模块**

在CMD中一个模块就是一个文件，通过define()进行定义。

define接收factory参数，它可以使一个函数，也可以是一个对象一个字符串。

- 当factory是一个对象或者一个字符串时，表示该模块的接口就是这个对象或者字符串。
- 当factory是一个函数时，表示是该模块的构造方法。执行该构造方法，可以得到模块向外提供的接口，factory在执行时，默认传入三个参数：require、exports、module。
  - 其中require用来加载其它模块。exports用来实现向外提供的模块接口。
  - module是一个对象，存储着与当前模块相关联的一些属性和方法，传给factory构造方法的exports是module.exports对象的一个引用，至通过exports参数来提供对外的接口，有时无法满足所有需求，比如当模块的接口是某个类的实例时，这个时候就需要通过module.exports来实现。

下面举个例子：

```javascript
// 定义模块OrderModel.js
define(function (require, exports, module) {
    
    var Header = require('./Header'); // require用来加载其它模块    
    exports.headerData = Header.getHeaderData(); // 对外提供headerData属性    
    // exports是module.exports的一个引用
    console.log(exports === modele.exports); // true
 
    var Pay = require('./Pay'); // 依赖可以就近加载
    exports.payData = Pay.getPayData(); // 对外提供payData属性    
    exports.payFun = function() {
        console.log('payFun log something');
    }; // 对外提供payFun方法
 
})
```

### **2、加载模块**

通过SeaJs的use方法我们可以加载模块

举个例子：

```javascript
// 上面我们已经定义了OrderModel模块了，直接加载即可
seajs.use(["OrderModel.js"], function (orderModel) {
    var headerData = orderModel.headerData;
    var payData = orderModel.payData;
    orderModel.payFun(); // 可以直接使用，输出 payFun log something
})
```

### **3、AMD与CMD的不同**

- 对于依赖模块，AMD是提前执行，CMD是延迟执行
- 对于依赖模块，AMD是依赖前置，CMD是依赖就近

## 5、CommonJS

CommonJS规范主要应用于Node，每个文件就是一个模块，有自己的作用域，即在一个文件中定义的变量、函数、类都是私有的，对其他文件不可见。

### **1、定义模块**

（上面说了每个文件就是一个模块，所以不存在定义的概念，只是为了承接上下文，更好理解罢了，文章后面不再说明。）

CommonJs规范规定，每个模块内部有两个变量可以使用：require和module。

- require用来加载某个需要的模块。
- module代表的是当前模块，是一个对象，存储着当前模块的相关联的属性和方法。exports是module上的一个属性。该属性表示当前模块对外输出的接口，其它文件加载该模块，实际上就是读取module.exports变量。（在实际开发中如果区分不了exports和module.exports的话，那就直接使用module.exports即可，那个exports就别管、别用了。）

举个例子：

```javascript
// orderModel.js
var Header = require('./Header'); // require用来加载其它模块
var Pay = require('./Pay');
 
var payFun = function () {
    console.log('payFun log something');
}
 
module.exports = { // 对外提供以下三个属性
    headerData: Header.getHeaderData(),
    payData: Pay.getPayData(),
    payFun: payFun
}
```

### **2、加载模块**

其实在上面的代码中，即orderModel.js中已经写出了加载模块的方法了。

下面是加载并使用orderModel.js的例子：

```javascript
var orderModel = require('./orderModel');
var headerData = orderModel.headerData;
var payData = orderModel.payData;
orderModel.payFun(); // 输出 payFun log something
```

需要注意的是，CommonJS规范规定，模块可以多次加载，但是只会在第一次加载时运行一次，运行结果就会被缓存下来，以后再加载就直接读取缓存结果，如果想让模块再次运行，必须清除缓存。

举个例子：

```javascript
require('./orderModel');
require('./orderModel').message = 'hello world';
require('./orderModel').message;
// hello world
```

清除缓存例子：

```javascript
// 删除指定模块的缓存，这里删除orderModel.js，也可以写多个进行批量删除。
delete require.cache[require.resolve('./orderModel')];
// 删除所有模块的缓存，大范围攻击
Object.keys(require.cache).forEach(function (key) {
    delete require.cache[key];
})
```

## 6、ES Module

在[ES6](https://so.csdn.net/so/search?q=ES6&spm=1001.2101.3001.7020)没出来之前，模块加载方案主要使用CommonJS和AMD两种，前者用于服务器，后者用于浏览器。ES6在语言标准层面上实现了模块功能，而且使用起来相当简单。

### **1、定义模块**

模块功能主要由两个命令构成：export和import，export命令用于规定模块的对外接口，import用于引入其它模块提供的功能。

一般来说，一个模块对应的就是一个文件，该文件内部的变量外部无法获取，如果你希望外部能够读取到某个变量，就需要使用export关键字输出该变量。

举个例子：

```javascript

```

**2、加载模块**

上面已经使用export命令定义了模块对外的接口后，其它的JS文件就可以通过import命令加载这个模块。

举个例子：

```javascript
// main.js
import {name, age, getSex} from './user';
console.log(name); // 张三
console.log(age); // 20
console.log(getSex(1)); // 男
```

import接受一对大括号，里面指定的是要从其它模块导入的变量名。大括号内的变量名，必须与导入模块对外接口的名称相同。

我们经常需要对加载模块进行重命名，如下写法：

```javascript
// main.js
import {name as otherName} from './user'; // 使用as进行重命名
console.log(otherName); // 张三
```

我们也经常使用到对模块的整体加载，如下写法：

```javascript
// main.js
import * as user from './user'; // 使用 * 号指定一个对象，所有输出值都加载在这个对象上面
 
console.log(user.name); // 张三
console.log(user.age); // 20
console.log(user.getSex(1)); // 男
 
// 需要注意的是 user是静态分析的，不允许运行时改变
// 下面的写法是不允许的
user.height = 180;
user.setOld = function () {};
```

**3、和CommonJS的区别**

1. ES Module不支持动态导入，但已提案，指日可待。
2. ES Module是异步导入，因为用于浏览器，需要下载文件，如果采用同步导入对渲染有很大影响。CommonJS是同步导入，因为用于服务端，文件都在本地，同步导入即使卡主主线程影响也不大。
3. ES Module导出的是值的引用，导入导出值都指向同一个内存地址，所以导入值会跟随导出值变化。而CommonJS在导出时都是值的拷贝，就算导出的值变了，导入的值也不会改变，所以想要更新值，必须重新导入一次。

# 五十七、生成器和迭代器

## 1、迭代器

迭代器是一个对象，是确使用户可在容器对象（[container](https://so.csdn.net/so/search?q=container&spm=1001.2101.3001.7020)，例如链表或数组）上遍访的对象，使用该接口无需关心对象的内部实现细节。
迭代器有next属性，其对应的方法有如下的要求：
一个无参数或者一个参数的函数，返回一个应当拥有以下两个属性的对象：

- done（boolean） ü 如果迭代器可以产生序列中的下一个值，则为 false。（这等价于没有指定 done 这个属性。）如果迭代器已将序列迭代完毕，则为 true。这种情况下，value 是可选的，如果它依然存在，即为迭代结束之后的默认返回值。
- value
  迭代器返回的任何 JavaScript 值。done 为 true 时可省略。

```javascript
	const friends = ['lilei', 'kobe', 'james'];
    let index = 0
    const friendsIterator = {
       next: function() {
       if (index < friends.length)
           return { done: false, value: friends[index++] }
       } else {
       	   return { done: true, value: friends[index++] }
       }
    }
    console.log(friendsIterator.next().value);
    console.log(friendsIterator.next().value);
    console.log(friendsIterator.next().value);
```

可迭代对象：

当一个对象实现了iterable protocol协议时，它就是一个可迭代对象；它和迭代器是不一样的。这个对象的要求是必须实现 @@[iterator](https://so.csdn.net/so/search?q=iterator&spm=1001.2101.3001.7020) 方法，在代码中我们使用 Symbol.iterator 访问该属性；

```javascript
	// 可迭代对象
    const iteratorObj = {
        names: ['leilei', 'tom', 'mark'],
        index: 0,
        [Symbol.iterator]: function() {
            return {
                // 这边使用箭头函数，以使this指向iteratorObj
                next: () => {
                    if (this.index < this.names.length) {
                        return { done: false, value: this.names[this.index++] }
                    } else {
                        return { done: true, value: 'no name' }
                    }
                }
            }
        }
    }
    // 获取迭代器
    const iterator1 = iteratorObj[Symbol.iterator]()
    console.log(iterator1.next());
    console.log(iterator1.next());
    console.log(iterator1.next());
    console.log(iterator1.next());	
```

事实上我们平时创建的很多原生对象已经实现了可迭代协议，会生成一个迭代器对象的：String、Array、Map、Set、arguments对象、NodeList集合；

## 2、生成器

生成器是ES6中新增的一种函数控制、使用的方案，它可以让我们更加灵活的控制函数什么时候继续执行、暂停执行等。
生成器函数也是一个函数，但是和普通的函数有一些区别：

- 首先，生成器函数需要在function的后面加一个符号*：
- 其次，生成器函数可以通过yield关键字来控制函数的执行流程：
- 最后，生成器函数的返回值是一个Generator（生成器）：
  生成器事实上是一种特殊的迭代器；
  MDN的解释：Instead, they return a special type of iterator, called a Generator

```javascript
 function* getName() {
  console.log('函数开始执行');
      const value1 = 'tom'
      console.log(value1)
      yield value1

      const value2 = 'mary'
      console.log(value2);
      yield value2
	  console.log('函数执行结束')
  }
  // 返回生成器
  const iterator = getName()
  console.log(iterator.next()); 
  console.log(iterator.next());
  console.log(iterator.next());
  console.log(iterator.next());
  // 函数开始执行
  // tom
  // { value: 'tom', done: false }
  // { value: 'mary', done: false }
  // { value: 'tony', done: false }
  // '函数执行结束'
  // { value: undefined, done: true }
```

注意：直接调用生成器函数是不会执行的，它会返回生成器。yield表示每次会在这儿停止。
其中，yield可以返回值。

next(传递参数)

生成器的next可以传递参数，而且这个参数会作为上一个yield语句的返回值；

```javascript
function* sum() {
    const value1 = 10;
     const n1 = yield value1; // 这个n1的值为5

     const value2 = 20 * n1
     /** 
     * 注意此处的n接收的是next()传来的值，和上面的value2的值没有必然关联，当然我们也可以把第一
     * 次的结果当作参数传入，视实际情况而定
     */ 
     const n2 = yield value2 // 这个n2的值为10

     const value3 = 30 * n2
     yield value3
 }
 const iterator = sum()
 console.log('第一次的值：', iterator.next());
 console.log('第二次的值：', iterator.next(5)); // 传给第一次yield的返回值
 console.log('第三次的值：', iterator.next(10)); // 传给第二次yield的返回值
 // 第一次的值： {value: 10, done: false}
 // 第二次的值： {value: 100, done: false}
 // 第三次的值： {value: 300, done: false}
```

生成器提前结束 - return函数

return传值后这个生成器函数就会结束，之后调用next不会继续生成值了；

```javascript
	function* sum() {
    	const value1 = 10;
        const n1 = yield value1;

        // 相当与在这执行了以下代码
        // return 5
        const value2 = 20 * n1
        const n2 = yield value2

        const value3 = 30 * n2
        yield value3
    }
    const iterator = sum()
    console.log('第一次的值：', iterator.next());
    console.log('第二次的值：', iterator.return(5)); 
    // 第一次的值： {value: 10, done: false}
    // 第二次的值： {value: 5, done: true}
```

生成器抛出异常 - throw函数

抛出异常后我们可以在生成器函数中捕获异常；
但是在catch语句中不能继续yield新的值了，但是可以在catch语句外使用yield继续中断函数的执行；

```javascript
function* sum() {
    const value1 = 10;
    yield value1;
    
    try {
        const value2 = 20
        yield 20
    } catch (error) {
        console.log(error);
        // yield '哈哈，错了'
    }

    const value3 = 30
    yield value3
}
const iterator2 = sum()
console.log('第一次的值：', iterator2.next());
console.log('第二次的值：', iterator2.next());
// 注意：throw紧跟着上个next()执行异常处理，所以要看好应该进行异常处理的位置
console.log('第三次的值：', iterator2.throw('有错误')); 
console.log('第四次的值：', iterator2.next());

// 结果：
// 第一次的值： {value: 10, done: false}
// 第二次的值： {value: 20, done: false}
// 有错误
// 第三次的值： {value: 30, done: false}
// 第四次的值： {value: undefined, done: true}
```