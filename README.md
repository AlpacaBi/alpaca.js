# alpaca.js

### 一个类（copy）vue的mvvm框架

#### 注意：这个项目只是我学习vue源码的过程中，为了加深自己的理解和增强动手能力，会仿造vue的源码，撸（chao）出来的框架，改动目前也仅仅是换个变量名（例如Vue换成Alpaca,v-on换成alpaca-on等等），只是用于娱乐，请不要用作生产。


目前已经实现的只有**双向绑定**和**事件绑定**

##### 双向绑定
和vue的一样，就是换了个名字而已，示例代码如下
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>alpaca.js</title>
</head>

<body>
    <div id="app">
        <input alpaca-model="msg">
        <span>{{msg}}</span>
    </div>
</body>

<script src="js/alpaca.js"></script>
<script type="text/javascript">
     new Alpaca({
        el: '#app',
        data: {
            msg: 'Alpaca'
        }
    });
</script>
</html>
```

##### 事件绑定
和vue的一样，就是换了个名字而已，示例代码如下
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>alpaca.js</title>
</head>

<body>
    <div id="app">
        <button alpaca-on:click="del">-</button>
        <span>{{num}}</span>
        <button alpaca-on:click="add">+</button>
    </div>
</body>

<script src="js/alpaca.js"></script>
<script type="text/javascript">
     new Alpaca({
        el: '#app',
        data: {
            num: 0,
        },
        methods: {
            add: function () {
                this.num = this.num +1;
            },
            del: function () {
                this.num = this.num -1;
            }
        }
    });
</script>
</html>
```



### 当然我也发布在了npm上
如果你用的是webpack工程化项目，你只需要执行

 `npm install alpacajs`

然后在js
```
var Alpaca = require("alpacajs")

new Alpaca({
    el: '#app',
    data: {
        msg: 'Alpaca',
        num: 0,
    },
    methods: {
        add: function () {
            this.num = this.num +1;
        },
        del: function () {
            this.num = this.num -1;
        }
    }
});
```
也可以生效