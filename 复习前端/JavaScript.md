# 介绍

1. 弱类型语言，数据声明后，类型可以转变。

   ```javascript
   <script type="text/javascript">
   	var i;
   	alert(typeof(i)); 	//undefined
   	i = 17;
   	alert(typeof(i));	//number
   	i = 'ihch17';
   	alert(typeof(i));	//string
   </script>
   ```

   

2. 交互

3. 安全（无法访问本地硬盘）

4. 跨平台

# 使用方式

1. <head>或者<body>标签中使用<script>标签

   ```javascript
   <script type="text/javascript">
   	alert('message');
   </script>
   ```

2. 外部引入

   ```javascript
   <script type="text/javascript" src="js/index.js"></script>
   ```

# 变量

## JS中的变量类型

1. 数值类型	number
2. 字符串类型  string
3. 对象类型    object
4. 布尔类型    boolean
5. 函数类型    function

## 特殊值

1. undefined    未定义。JS变量未定义初始值，默认都是undefined
2. null    空
3. nan    not a number，非数字

# 数组

```javascript
var arr1 = [];	//空数组
var arr2 = [1,2,3];
```

1. 自动扩容
2. 元素类型可以不一致

```javascript
// 数组势力
<script type="text/javascript">
	var arr = [];
	arr[0]=0;
	arr[3]='abc';
	for (var i = 0; i < arr.length; i++) {
		alert(arr[i]);
	}
</script>
```



# 函数

## 定义方式

1. 定义方式1

   ```javascript
   <script type="text/javascript">
       // 无参函数
       function func1(){
       	alert("无参函数")
   	}
   	// 函数必须调用才能执行
   	func1();
   
   	// 有参函数
   	function func2(a,b){
       	alert(a);
       	alert(b);
   	}
   	func2(1,'abc');
   </script>
   ```

2. 定义方式2

   ```javascript
   <script type="text/javascript">
       var fun10 = function(){
           alert('函数的第二种定义方式');
       }
   	fun10();
   </script>
   ```

**注：JS中，函数没有重载。若在JS中实现重载，则会覆盖方法.**

## 隐形参数arguments

```javascript
    <script type="text/javascript">
        /*
        *  设计一个函数，用来计算所有传入参数的和
        * */
        var sum = function(){
            var result = 0;
            for (var i = 0; i < arguments.length; i++) {
                result += arguments[i];
            }
            return result;
        }
        alert(sum(1,2,3,4,5,6,7,8,9));
    </script>
```

# 自定义对象

```javascript
    <script type="text/javascript">
        // 方式1
        var obj = new Object();
        obj.name = 'ihch17';
        obj.age = 34;
        obj.dosth = function (){
            alert(this.name+this.age+'dosth');
        }

        alert(obj.name);
        alert(obj.age);
        obj.dosth();

        // 方式2
        var obj1 = {
            name : '张三',
            age:10;
            dosth:function (){
                alert('dosth')
            }
        };
    </script>
```

# 事件

常用事件：

- onload：加载事件

- onclick：单击

- onblur：失去焦点

- onchange：内容发生改变

- onsubmit：表单提交

时间绑定方式

- 静态绑定：通过html标签的动作属性直接赋予事件的响应代码
- 动态绑定：通过js获取dom对象，在同过dom对象的事件名赋予事件的响应代码

## onload事件

动态注册onload事件固定写法

```javascript
    <script type="text/javascript">
        window.onload = function (){
            alert('动态绑定');
        }
    </script>
```

## 其他事件

动态绑定

1. 获取dom对象
2. 绑定时间

**注意:**

```javascript
return false; // 阻止默认行为
```

# DOM模型

> document object model，文档对象模型
>
> 把文档中的标签，属性，文本转化为对象来处理

1. document管理了所有html文档内容
2. document是一种树形结构，有上下层关系
3. 将所有`标签对象化`