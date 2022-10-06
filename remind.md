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

## 1.单行超出隐藏

~~~css
div {
  overflow:hidden; //超出的文本隐藏
  text-overflow:ellipsis; //用省略号显示
  white-space:nowrap; //不换行
}
~~~

2、多行超出隐藏

```css
div{
  overflow:hidden; 
  text-overflow:ellipsis;
  display:-webkit-box;    //将对象作为弹性伸缩盒子模型显示。
  -webkit-box-orient:vertical;  // 从上到下垂直排列子元素
  -webkit-line-clamp:2; //显示的行数
}
```

3、表格中单行超出隐藏

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

