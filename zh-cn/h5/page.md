# 第一节 页面布局相关

## No.1 常见div居中布局方法有哪些?

* 首先制定页面结构

```js
<div class="wrapper">
    <div class="inner"></div>
</div>
```

* 其次就是设定CSS样式
  
1. 使用Flex布局实现

```
.wrapper {
    display: flex;
    width: 500px;
    height: 500px;
    -webkit-box-pack: center;
    -ms-flex-pack: center;
    -webkit-box-align: center;
    -ms-flex-align: center;
    justify-content: center;
    align-items: center;
    background-color: #000;
}
.wrapper .inner {
    width: 300px;
    height: 300px;
    background-color: #666;
}
```

2. 流体布局

```
.wrapper {
    position: relative;
    width: 500px;
    height: 500px;
    background-color: #000;
}
.wrapper .inner {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    margin: auto;
    width: 300px;
    height: 300px;
    background-color: #666;
}
```

3. transform平移

```
.wrapper {
    position: relative;
    width: 500px;
    height: 500px;
    background-color: #000;
}
.wrapper .inner {
    position: absolute;
    top: 50%;
    left: 50%;
    -webkit-transform: translate(-50%, -50%);
    transform: translate(-50%, -50%);
    width: 300px;
    height: 300px;
    background-color: #666;
}
```

4. 已知宽高绝对定位

```
.wrapper {
    position: relative;
    width: 500px;
    height: 500px;
    background-color: #000;
}
.wrapper .inner {
    position: absolute;
    margin-top: 50%;
    margin-left: 50%;
    top: -150px;
    left: -150px;
    width: 300px;
    height: 300px;
    background-color: #666;
}
```

## No.2 H5有哪些比较实用的新功能?

* File API支持本地文件操作;
* Canvas/SVG支持绘图;
* 拖拽功能支持;
* 本地存储支持;
* 表单多属性验证支持,如(pattern, maxlength等)
* 原生音频视频支持等;

## No.3 Sass与Less的区别?

1. 处理方式不同

Sass是基于ruby的,是在服务端处理的;
Less是需要引入less.js来处理less代码;

2. 变量符不同

Sass采用$符号,less是@符号

3. 输出设置

Sass提供4种输出选项:nested(嵌套),compact(紧凑),compressed(压缩),expanded(扩展)
Less没有

4. 逻辑语法

Sass支持条件或流程控制语句,可以使用if else, for循环,而less没有.

## No.4 如何进行响应式布局

1. 使用css3 media screen

* 宽度匹配内联写法:

```js
@media screen and (max-width:400px) {...}
```

* 宽度匹配外链写法:

```js
<link rel="stylesheet" media="screen and (max-width:400px)" href="xxx.css" />
```

2. 支持移动端的viewport

```js
<media name="viewport" content="width-device-width, initial-scale=1.0" />
```

3. 宽度使用百分比,字号大小使用rem

* 响应式布局需要注意的事项

  * 布局结构不要使用绝对宽度,而要使用百分比;
  * 字体使用em或rem,不要使用px或pt;

4. 图片的响应式处理

```js
img {max-width: 100%; max-height: 100%}
```

## No.4 浮动布局的优缺点是什么?

* 优点:采用float布局,如果宽度太小,后面的元素会自动滚动到下方,不会出现滚动条
* 缺点:浮动元素是脱离文档流,处理不好,会出现高度塌陷等问题.

目前很多时候采用混搭:很多结构可以用display:inline-block或者position:absolute替代.

## No.5 什么是BFC?

BFC中文就是块级作用域,一个HTML元素要创建BFC,需要满足下列任意一个或多个条件即可:

* float的值不是none;
* position的值不是static或者relative;
* display的值为inline-block、table-cell、flex、table-caption或者inline-flex;
* overflow的值不是visible

常见创建BFC的方法如下:

* display: table; // 可能引发响应性问题
* overflow: scroll; // 可能产生多余滚动条
* float: left; // 将把元素移至左侧,并被其他元素环绕
* overflow: hidden; // 将裁切溢出的元素

## No.6 多个html页面如何共享数据?

* 使用jsonp;
* 同域下可以使用cookie, 可以记录用户访问网站的喜好等;
* 同域下也可以也可以使用localStorage或sessionStorage;
* 在范围域内也可以是用Service Worker
* 使用postMessage;
* 使用中转页面传递;
* 使用隐藏的表单post方式.



