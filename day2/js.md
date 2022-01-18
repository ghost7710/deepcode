# JavaScript

1. JavaScript程序不需要我们程序员手动编译，编写完源代码之后，浏览器直接打开执行

JavaScript的目标程序以普通文本形式保存，这种语言叫做脚本语言

Java的目标程序以.class形式存在，不能使用文本编辑器打开，不是脚本语言

2. 在HTML中嵌入JavaScript代码

要实现的功能：用户点击一下按钮，弹出信息框。

```html
<!doctype html>
<html>
    <head>
        <title>html中嵌入js代码的第一种方式</title>
    </head>
    <body>
        <!--要实现的功能：
            1.用户点击一下按钮，弹出信息框。
            2.JS是一门事件驱动型的语言；在js中有很多事件，其中有一个事件叫做鼠标单击，单词click，并且在任何事件都会对应一个事件句柄
            叫做onclick,而事件句柄是以HTML标签的属性存在的。
            3.onclick="js代码",页面打开时js代码不会执行，只会之策在按钮上，等待click后js代码会被调用
            4.怎么淡出消息框？
            在JS中有一个内置对象叫做window，全部小写，可以拿来直接使用，window表示的是浏览器对象
            window对象有一个函数叫做alert，用法:window.alert("消息")，就可以弹窗
            5.字符串单双引号皆可，语句末分号皆可
        -->
        <!--window.可以省略不写-->
        <input type="button" value="hello" onclick="window.alert('hello js')
                                                    window.alert('hello js code')
                                                    alert('hello js')"/>

    </body>
</html>
```

