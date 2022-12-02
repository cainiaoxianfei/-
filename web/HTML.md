### 1.HTML简介

![image-20221016205839408](E:\学习笔记\assets\image-20221016205839408.png)

![image-20221017151336707](../assets/image-20221017151336707.png)

![image-20221017152629357](../assets/image-20221017152629357.png)

![image-20221017153631421](../assets/image-20221017153631421.png)

![image-20221017192323060](../assets/image-20221017192323060.png)



### 2.Js简介&引入方式

![image-20221017200836986](../assets/image-20221017200836986.png)

![image-20221017200853468](../assets/image-20221017200853468.png)

```javascript
//内
<script>
    alert("js引入");
</script>
//外引入
<script src=""></script>
```



#### 2.1 输出语句

![image-20221017201734778](../assets/image-20221017201734778.png)

#### 2.2 变量

![image-20221017202552420](../assets/image-20221017202552420.png)

let关键字所定义的变量只在当前代码块有效，是一个局部变量。

#### 2.3 类型转换

![image-20221017212320283](../assets/image-20221017212320283.png)

可以利用js中类型转换简化java代码的书写

```javascript
//一般通过parselnt方法将其他类型转换为数字，可以直接调用该方法
var a ;
alert(a);

if (a){
    alert("不为空置转换为true")
}else {
    alert("为null转换为false")
}
```

#### 2.4 函数

![image-20221017213838308](../assets/image-20221017213838308.png)

```javascript
var a = "name";
alert(a);
var b = 1;
//返回值为name1
let add1 = add(a,b);
    alert(add1)  
//如果a为null返回值为1
//如果a为undefined返回值为NaN

```

#### 2.5 对象

##### 2.5.1 Array数组对象

![image-20221017220617930](../assets/image-20221017220617930.png)

注意：js数组类似于Java集合，长度，类型都可变

```javascript
var arr =[1,2,3];
//直接访问数组中的元素
 arr[0] = 10;
// // alert(arr);

//通过length属性获取数组长度，遍历数组，类似于java中的getsize方法
 for (let i =0;i<arr.length;i++){
     alert(arr[i]);
 }

//添加元素的方法
arr.push(0,1);
alert(arr);
//删除元素的方法
arr.splice(0,1);
alert(arr);
```



##### 2.5.2 自定义对象

==自定义对象==

![image-20221018111405054](../assets/image-20221018111405054.png)

```javascript
var person = {
    name: "名字",
    age: 20,

    fangfa: function (a, b) {
        alert(a + b);
    }
}
```

##### 2.5.3 BOM对象

![image-20221018112014478](../assets/image-20221018112014478.png)

###### 2.5.3.1 Window对象

![image-20221018120312880](../assets/image-20221018120312880.png)

注意：confirm确认返回true，取消返回false

```javascript
//定时器,在一定时间后执行一个function,只执行一次
setTimeout(function (){
    alert("yes");
},2000)
//定时器,在一定时间后执行一个function,循环执行
setInterval(function (){
    alert("hello");
},2000);
```

###### 2.5.3.2 History对象

==前进，后退==

![image-20221019193150244](../assets/image-20221019193150244.png)

###### 2.5.3.3 Location对象

==设置跳转到指定地址==

![image-20221019193207372](../assets/image-20221019193207372.png)

##### 2.5.4 DOM对象

![image-20221019194346511](../assets/image-20221019194346511.png)

***将各个标签封装为对象，可以通过获取对应的对象执行对应的方法***

![image-20221019194816613](../assets/image-20221019194816613.png)

***调用方法操作HTML（网页）***



![image-20221019195122954](../assets/image-20221019195122954.png)

###### 1.Element对象

==通过方法获得各标签对象或对象数组==

![image-20221019201028475](../assets/image-20221019201028475.png)

==通过整个文档对象来获取标签的对象调用该标签的方法，标签的具体方法可查看参考手册==

```javascript
<body>
<img id="name" src="1.jpg" height="800" width="1000">
<script>
    let elementById = document.getElementById("name");
     elementById.src="2.jpg"
</script>
</body>
```

```javascript
//对应的方法只能获得数组，需要在循环中调用该标签对象的方法
//所以一般要用到多个相同属性时定义class而不是使用id

<div class="jjb">这是一个script</div>
<div class="jjb"> sire this way</div>
<script>
    let dic = document.getElementsByClassName("jjb");
  for (let i = 0; i < dic.length; i++) {
      dic[i].style.color='blue';
  }
```

###### 2.事件监听

![image-20221020202352494](../assets/image-20221020202352494.png)

![image-20221020202400007](../assets/image-20221020202400007.png)

***通过DOM元素绑定对应的事件完成对应的动态修改***

==常见事件==

![image-20221020204844586](../assets/image-20221020204844586.png)



###### 3.表单验证

```javascript
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
</head>
<body>

<p>本例使用 HTML DOM 将 "onblur" 事件分配给输入元素。</p>

<p>在输入字段中写一些东西，然后在字段外单击以失去焦点（blur）。</p>


<input name="username" type="text" id="username">
<input name="user" type="button" id="user" value="提交">
<span id="userid" class="text" style="display: none">用户名错误</span>

<script>
document.getElementById("username").onblur = function() {myFunction()};

function myFunction() {
  var ggb = document.getElementById("username");
  var s = ggb.value.trim();
  var b = s.length>=6 && s.length<=12
  //script中if会自动判断值是否为true，不为true则执行else 
  if(b){
  }else {
    alert("输入错误");
  }

}
</script>

</body>
</html>
```

###### 4.正则表达式

![image-20221022092353548](../assets/image-20221022092353548.png)


