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