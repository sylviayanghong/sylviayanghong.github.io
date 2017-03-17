####3-6笔记

###前端课程基础

* html--（内容）超文本标记（标签）语言
* css--样式
* js--动作
#####快捷键
* ctrl+n: 新建
* ctrl+[: 减少一个缩进
* ctrl+]: 增加一个缩进
* ctrl+/：注释
* ctrl+w: 关闭
* ctrl+shift+D: 复制当行（光标）
* 按住ctrl可以多选
* alt+f3: 选中相同的文字
#####网页大致布局
######标签的属性：<名_属性=值></名>
* 标题：h1-h6标签
* 段落：p标签
* 图片：img标签
* 列表：ul{li}标签---无序列表
* 链接：a标签
#####树状结构
######节点分为三类
* 元素节点
* 属性节点
* 文本节点
######同一个父级才是同级节点，不然就不是
####css选择器
```html
选择器名{
    css属性名：属性值；
}
//注：属性值不能数字开头；要有语义
```
######元素分为三类
* 独立成行，可设宽高：块元素--h标签，p标签，ul和li标签
* 不独立成行，不可设宽高：行内元素（内联元素）--a标签
* 不独立成行，可设宽高：行内块元素--img标签
######一些常用元素属性
```html
fant-sise;//字体大小
border: 1px solid #red;//边框为一像素的实线，dashed为虚线
text-algin:center;line-height；//水平方向，垂直方向（居中与height一样高）居中
background-color://背景颜色
list-style:none;//消除列表前的点
float:left;//左浮动
属性：hover{
    bgc/其他
}//鼠标光标移动到时变化
```




####3-7笔记

#####选择器
1.元素选择器
```html
<body>
    <h1>元素</h1>
</body>>
<style>
    h1{
    /*元素属性*/
}
</style>

```
2.id选择器
```html
<body>
    <h3 id="hello">id</h3>
</body>
<style>
   #hello{
    /*元素属性*/
} 
</style>
```
3.类别（class）选择器
```html
<body>
    <h3 class="world">id</h3>
</body>
<style>
   .world{
    /*元素属性*/
} 
</style>
```
4.层级选择器
```html
<body>
    <ul class="fruit">
        <li></li>
    </ul>
</body>
<style>
   .fruit li{
    /*元素属性*/
} 
</style>
```
5.伪类选择器（用来指定一些动作）
```html
<body>
    <ul class="fruit">
        <li></li>
    </ul>
</body>
<style>
   .fruit li{
        background-color: #fff;
} 
   .fruit li:hover{
     background-color: #f00;
   } 
</style>
```
6.*选择器可以选到所有
```html
<style>
    *{
        margin: 0px;
        padding: 0px;
    } 
</style>
```
#####浮动
1.浮动就是让块元素不独立成行
浮动元素{
    不占位；
    脱离文档；
}
2.清除浮动
```html
<!-- 在浮动的元素后加一个属性值为clear的元素 -->
<body>
    <div class="clear"></div>
    <!-- 或<br class="clear">/<hr class="clear"> -->
</body>
<style>
    .clear{
        clear: both;
    }
</style>
```
#####布局
```html
margin: 10px;<!-- 上下左右 -->
margin: 10px 20px;<!-- (上下)（左右） -->
margin: 10px 20px 30px;<!-- 上（左右）下 -->
margin: 10px 20px 30px 40px;<!-- 上,右，下，左 -->
```


####3-8笔记

###盒子模型（重要）
```html
    <style>
        *{
            margin: 0px;
            padding: 0px;
            box-sizing: border-box;

        }
        .box1{
            border: 10px solid #000;
            width: 200px;
            height: 200px;
            float: left;
            margin-right: 100px;
        }
        .box2{
            border: 10px solid #000;
            width: 200px;
            height: 200px;
            float: left;
        }
        .box1 h3{
            margin-left: 20px;
            margin-top: 50px;
        }
    </style>
</head>
<body>
    <div class="box1">
        <h3>盒子1</h3>
    </div>
    <div class="box2">
        <h3>盒子2</h3>
    </div>
</body>
```
######盒宽-实宽：wiath+padding+border
```html
*{
    box-sizing: border-box;
}
```
*alt+shift+2：把html和css分屏操作
*link引入css文件
######媒体元素
*audio---音乐标签*
```html
<audio src="" controls autoplay=""></audio>
<video src=""></video>
<!-- controls是控制器面板属性，autoplay是自动播放属性，loop循环播放 -->
<!-- source标签：设置源文件，可省略 -->
```
* 行内元素换行可用br
* 块元素定宽用margin： 0 auto；居中
* 块元素有文字的标签是让文字居中用text-algin：center；
* 行内元素，行内块元素让父级text-algin:center;

####3-9笔记
###定位
#####绝对定位
* 参照距离：屏幕左上角
* 不占位，脱离文档，一般重叠时才用
```html
    <style>
        *{
            margin: 0px;
            padding: 0px;
        }
        .btn{
            position: absolute;//绝对定位
            top: 150px;
            left: 50px;
            font-size: 26px;
        }
    </style>
</head>
<body>
    <img src="homework-menu.jpg" alt="">
    <p class="btn">不想上课</p>
</body>
```

#####相对定位
* 参照自己原来的位置变化，不脱离文档流
```html
    <style>
        *{
            margin: 0px;
            padding: 0px;
        }
        .test{
            width: 200px;
            height: 200px;
            margin-top: 10px;
            background-color: #f00;
        }
        .btn{
            position: relative;
            top: 200px;
            left: 200px;
        }
    </style>
</head>
<body>
    <div class="test test1"></div>
    <p class="test btn"><img src="homework-menu.jpg" alt=""></p>
    <div class="test test2"></div>
</body>
```

#####固定定位
* 参照屏幕变化；随滚动条变化，不占位，脱离文档
```html
    <style>
        *{
            margin: 0px;
            padding: 0px;
        }
        body{
            height: 2000px;
        }
        .test{
            width: 200px;
            height: 200px;
            margin-top: 10px;
            background-color: #f00;
        }
        .btn{
            position: fixed;
            top: 100px;
            left: 50px;
        }
    </style>
</head>
<body>
    <div class="test test1"></div>
    <p class="test btn"><img src="homework-menu.jpg" alt=""></p>
    <div class="test test2"></div>
</body>
```

#####参照物定位（常用）
* 父级设相对定位，子集设绝对定位
```html
<style>
    *{
        margin: 0px;
        padding: 0px;
    }
    .test{
        width: 500px;
        height: 500px;
        /*border: 1px solid red;*/
        background-color: #eee;
        position: relative;
        top: 100px;
        left: 100px;
    }
    .test1{
        position: absolute;
        top: 300px;
        left: 300px;
    }
    </style>
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <link rel="stylesheet" href="6-参照物定位.css">
</head>
<body>
    <div class="test">
        <img class="test1" src="homework-menu.jpg" alt="">
    </div>
</body>
```
######在一个定宽高的盒子里写过多的内容会从下边溢出，解决方法：
* overflow：hidden；--隐藏（多余的部分不会显示）
* overflow：auto；--多余部分生成滚动条显示
* 子集元素的margin-top作用在父级元素上也可用（放在父级里）
 
###表单（form）
```html
<form action="">
    <!-- 文本框 -->
    <input type="text"><!-- placeholder属性在文本框里显示文字 -->
    <!-- 按钮 -->
    <input type="button">
    <button>按钮</button>
    <!-- 下拉选框 -->
    <select name="" id="">
        <option value=""></option>
    </select>
    <!-- 密码框 -->
    <input type="password">
    <!-- 单选框 -->
    <input type="radio" name="sex">男
    <input type="radio" name="sex">女
    <!-- 复选框 -->
    <input type="checkbox">
</form>
<!-- 表单元素去边框 -->
border:none;
outline:none;
<!-- 圆角 -->
border-radius: 30px;<!-- 根据宽度定，50%是一个圆 -->
cursor: pointer;<!-- 鼠标放上去是一个小手 -->
hover:{悬浮}
active:{点击}
```

####before/after
* 可用来清除浮动
```html
    <style>
        *{
            margin: 0px;
            padding: 0px;
        }
        /*清除浮动*/
        .clear:before,.clear:after{
            content: '';
            display: block;
            clear: both;

        }
        .box1{
            width: 200px;
            border: 10px solid red;
        }
        .box2{
            width: 100px;
            height: 100px;
            background-color: #000;
            float: left;
        }
        .box3{
            width: 100px;
            height: 100px;
            float: left;
            background-color: #0f0;
        }
    </style>
</head>
<body>
    <div class="box1 clear">
        <div class="box2"></div>
        <div class="box3"></div>
    </div>
</body>
```


####3-10笔记
###PS
* ctrl+'+'/alt+滚轮:缩放
* F8：信息
* ctrl+r:标尺
* 切片删除用delete
* ctrl+0：显示整个页面/ctrl+1：1：1显示
* 按住空格键拖动图片

#####图片存储
* gif：动图，颜色单一（小）
* jpg：颜色丰富（中）
* png：透明度（大）

* 要一行文字里前后颜色不一样，可加span
```html
<style>
    .h3{
        color: red;
    }
    .span{
        color: #000;
    }
</style>
<body>
    <h3><span>颜色</span>改变</h3>
</body>
```
* font-family；设置字体
* hr:可以设一条分隔线



####3-13笔记

###css3基础

####css3基本属性

1.缩放
例
```html
transform: scale(2);
```
()里为缩放的倍数；
可放初识状态也可在hover状态
2.旋转
```html
transform: rotate(45deg);
<!-- (旋转度数，两个状态都可) -->
transform-origin: left top;
<!-- 旋转的原点设置 -->
```
3.移位
```html
translate()
<!-- 只指定一个值x轴有位移；两个值分别为xy轴 -->
translateY()
<!-- 也可单独指定值 -->
<!-- 值为负数为反方向位移 -->
```
4.过渡效果
在原属性里加，不是在hover里
```html
transition: transform 5s;
<!-- 控制hover里的属性的过渡时间 -->
<!-- 多种属性同时用时，用","分隔 -->
transition: transform 5s,backgound-color: #fff;
```
5.贝塞尔曲线
常用函数：
ease---先快后慢；
linner---匀速；
ease-in---加速，渐显效果；
ease-out---减速，渐隐效果；
ease-in-out---先加速再减速，渐显渐隐效果
```html
<!-- 在这些函数后加秒数有延迟作用 -->
<!-- 用这些函数用空格分隔，不是"，"号 -->
```
6.设置透明度。。
```html
opacity: 0.5;
<!-- 值越小越透明 -->
```

####3-14笔记

###动画
```html
    <style>
        .box{
            width: 1050px;
            height: 200px;
            margin-left: 100px;
            overflow: hidden;
            border: 1px solid #eee;
        }
        .box1{
            width: 2200px;
            animation: turnaround 10s linear infinite;
            /*用在多个元素上，就都可以用动画*/
            /*infinite属性不用刷新，动画不会终止*/
        }
        img{
            display: block;
            width: 200px;
            height: 200px;
            margin-left: 10px;
            float: left;


        }
        /*turanaround为属性名，可以自己起*/
        @keyframes turnaround{
            0%{
                transform: translateX(0px);
            }
            20%{
                transform: translateX(-210px);
            }
            40%{
                transform: translateX(-410px);
            }
            60%{
                transform: translateX(-610px);
            }
            80%{
                transform: translateX(-810px);
            }
            100%{
                transform: translateX(-100px);
            }
        }
            /*停止动画*/
        .box1:hover{
                animation-play-state: paused;
            }
    </style>
</head>
<body>
    <div class="box">
        <div class="box1">
            <img  src="1.jpg" alt="">
            <img  src="2.jpg" alt="">
            <img  src="3.jpg" alt="">
            <img  src="2.jpg" alt="">
            <img  src="3.jpg" alt="">
            <img  src="1.jpg" alt="">
            <img  src="2.jpg" alt="">
            <img  src="3.jpg" alt="">
            <img  src="2.jpg" alt="">
            <img  src="3.jpg" alt="">
        </div>      
    </div>
</body>
```
* 一个keyframes可以作用在多个元素上；一个网页也可以有多个keyframes

####3-15笔记
###github命令
cd ..      返回上级目录
cd 目录名  进入目录
ls 查看当前目录下的文件
cd ../..
cd e:   进入盘符

git init 初始化一个git仓库

git status  查看文件状态

git add . 将编辑区文件添加到暂存区

git commit -m "备注信息"  将暂存区文件提交到分支

！！！ tell me who you are.

git config --

git remote + 自己项目的地址（本行复制就可以了）

git push origin master  将本地分支同步到远程分支

看提示信息！！！

* 按↑返回上一条指令代码
* 粘贴：shift+insert

