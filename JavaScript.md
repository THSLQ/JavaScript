### JavaScript 基础教程  2022-03-17  
##### 1. JavaScript 用法  
HTML 中的脚本必须位于 \<script> 与 \</script> 标签之间。
脚本可被放置在 HTML 页面的 \<body> 和 \<head> 部分中。  
###### 1.1 \<script> 标签  
如需在 HTML 页面中插入 JavaScript，请使用 \<script> 标签。
\<script> 和 \</script> 会告诉 JavaScript 在何处开始和结束。
\<script> 和 \</script> 之间的代码行包含了 JavaScript  
如需使用外部文件，请在 \<script> 标签的 "src" 属性中设置该 .js 文件  
\<script src="myScript.js">\</script>

###### 1.2 \<body> 中的 \<script> 标签  
可以直接写入body中的文本:  
```javascript  
    <script> document.write("写入"); </script>  
```   

###### 1.3 Javascript 输出  
* JavaScript 可以通过不同的方式来输出数据：  
> 1. 使用 window.alert() 弹出警告框。
> 2. 使用 document.write() 方法将内容写到 HTML 文档中。
> 3. 使用 innerHTML 写入到 HTML 元素。
> 4. 使用 console.log() 写入到浏览器的控制台。  
PS： 如果在文档已完成加载后执行 document.write，整个 HTML 页面将被覆盖。
  
###### 1.4 操作 HTML 元素  
 JavaScript 访问某个 HTML 元素，您可以使用 document.getElementById(id) 方法。需要为元素提前设置id属性。  
 使用 "id" 属性来标识 HTML 元素，并 innerHTML 来获取或插入元素内容。  

##### 2. JavaScript 语法  
 JavaScript 是一个程序语言。语法规则定义了语言结构。  
###### 2.1 变量 variable  
 - 变量必须以字母开头
 - 变量也能以 $ 和 _ 符号开头（不过我们不推荐这么做）
 - 变量名称对大小写敏感（y 和 Y 是不同的变量）

  
##### 3. JavaScript 数据类型  
- 值类型[基本类型]：数字Number、字符串String、布尔Boolean、对空Null、未定义Undefined、Symbol（ES6，引入的新原始类型，表示独一无二的值）  
- 引用类型：数组Array、对象Object、函数Function  
###### 3.1 JavaScript 拥有动态类型  
表示，相同的变量名，可以用作不同的类型。  
var x;  // undefined
var x = 7; // number
var x = 'abc'; // string  
* PS: 当您声明新变量时，可以使用关键词 "new" 来声明其类型:[JavaScript 变量均为对象。当您声明一个变量时，就创建了一个新的对象。]，但是不推荐使用new创建一些基础变量对象，这种操作会拖慢执行速度，而且可能产生其他副作用。
    > var name = new String;
    > var x=      new Number;
    > var y=      new Boolean;
    > var cars=   new Array;
    > var person= new Object;  
* PS02: 对于Array类型，typeof(Array)返回值是object。所以，判断Array类型，使用下列方式  
    1. isArray():   if(Array.isArray){if(Array.isArray(cars)) console.log("cars是Array");}  
    2. instanceof:  if(cars instanceof Array) {console.log("cars是Array");}  
      
##### 4. JavaScript 函数  
函数是由事件驱动的或者当它被调用时执行的可重复使用的代码块。  
###### 4.1 JavaScript 函数语法
    function functionName()
    {
        // 执行代码
    }

##### 5. JavaScript 作用域  
在 JavaScript 中, 对象和函数同样也是变量。  
**在 JavaScript 中, 作用域为可访问变量，对象，函数的集合。**  
JavaScript 函数作用域: 作用域在函数内修改。  
###### 5.1 JavaScript 局部作用域  
变量在函数内声明，变量为局部作用域。  
局部变量：只能在函数内部访问。  
因为局部变量只作用于函数内，所以不同的函数可以使用相同名称的变量。  
局部变量在函数开始执行时创建，函数执行完后局部变量会自动销毁。  
函数参数只在函数内部其作用，是局部变量。
###### 5.2 JavaScript 全局作用域  
变量在函数外定义，即为全局变量。 全局变量有 全局作用域: 网页中所有脚本和函数均可使用。   
*PS：* 在 HTML 中, 全局变量是 window 对象: 所有数据变量都属于 window 对象。
###### 5.3 JavaScript 变量生命周期  
JavaScript 变量生命周期在它声明时初始化。
局部变量在函数执行完毕后销毁。
全局变量在页面关闭后销毁。  
###### 5.4 ES6 let 关键字  
let 允许你声明一个作用域被限制在块级中的变量、语句或者表达式（对于使用for循环，中的循环变量，使用 let 声明）。与var关键字不同的是，它声明的变量只能是全局或者整个函数块的。  

##### 6. JavaScript 事件  
当HTML中发生事件是，称为HTML事件。在HTML中使用JavaScript来相应HTML事件，称为JavaScript事件。  
###### 6.1 HTML 事件  
HTML 事件可以是浏览器行为，也可以是用户行为：
* HTML 页面完成加载
* HTML input 字段改变时
* HTML 按钮被点击  
* 等等  

当HTML事件触发时，你可以做一些事情，比如执行一些 JavaScript 代码。  
|   常用HTML事件    |   描述    |
| :-----    |  :----- |
| onchange  | HTML 元素改变  |
| onclick   | 用户点击 HTML 元素  |
| onmouseover  | 鼠标指针移动到指定的元素上时发生  |
| onmouseout   | 用户从一个 HTML 元素上移开鼠标时发生  |
| onkeydown    | 用户按下键盘按键  |
| onload       | 浏览器已完成页面的加载  |  

##### 7. JavaScript 字符串  
JavaScript 字符串用于存储和处理文本。  
###### 7.1 字符串的 属性 和 方法  
1. 属性：  
    constructor：返回创建字符串属性的函数；  
    length：返回字符串的长度；  
    prototype：	允许您向对象添加属性和方法；  
2. 方法：  
    charAt(index): 返回指定索引位置的字符  
    charCodeAt(): 返回指定索引位置字符的 Unicode 值  
    concat(): 连接两个或多个字符串，返回连接后的字符串  
    indexOf()	返回字符串中检索指定字符第一次出现的位置  
    lastIndexOf()	返回字符串中检索指定字符最后一次出现的位置  
    match()	找到一个或多个正则表达式的匹配  
    replace()	替换与正则表达式匹配的子串  
    search()	检索与正则表达式相匹配的值  
    slice(start,end): 提取字符串的片断，并在新的字符串中返回被提取的部分(区间[start,end))  
    split(splitter, ?limit)	把字符串分割为子字符串数组(splitter分割字符，可选参数limit保留多少数组元素)  
    substr(start,length): 从起始索引号提取字符串中指定数目的字符(包含start)  
    substring(start,end)	提取字符串中两个指定的索引号之间的字符(区间[start,end))  
    toLocaleLowerCase()	根据主机的语言环境把字符串转换为小写，只有几种语言（如土耳其语）具有地方特有的大小写映射  
    toLocaleUpperCase()	根据主机的语言环境把字符串转换为大写，只有几种语言（如土耳其语）具有地方特有的大小写映射  
    toLowerCase()	把字符串转换为小写  
    toUpperCase()	把字符串转换为大写  
    trim()	移除字符串首尾空白(JS中"A "空格也有长度 "A "长度为2)  
    valueOf()	返回某个字符串对象的原始值  

##### 7. JavaScript 运算符  
###### 7.1 对字符串和数字进行加法运算  
两个数字相加，返回数字相加的和，如果数字与字符串相加，返回字符串。  
###### 7.2 JavaScript == 与 === 区别
1. 对于 string、number 等基础类型，== 和 === 是有区别的  
* 不同类型间比较，== 之比较 "转化成同一类型后的值" 看 "值" 是否相等，=== 如果类型不同，其结果就是不等。  
* 同类型比较，直接进行 "值" 比较，两者结果一样。  
2. 对于 Array,Object 等高级类型，== 和 === 是没有区别的  
    进行 "指针地址" 比较  
3. 基础类型与高级类型，== 和 === 是有区别的  
* 对于 ==，将高级转化为基础类型，进行 "值" 比较  
* 因为类型不同，=== 结果为 false  

*PS010*: bool 类型在与数字类型进行相加时，视为 0 或者 1 处理。  
*PS020*: null 类型与数字类型进行累加时，视为 0 处理。  
*PS030*: undefined 除了与字符串进行累加时有效（undefined 视为字符串"undefined"处理），其他情况皆返回 NaN。

##### 8. JavaScript 比较 和 逻辑运算符  
###### 8.1 比较运算符  
==  等于  
=== 绝对等于（值和类型均相等）  
!=	 不等于  
!==	 不绝对等于（值和类型有一个不相等，或两个都不相等）  
###### 8.2 逻辑运算符  
给定 x=6 以及 y=3，下表解释了逻辑运算符：
&&	and	    (x < 10 && y > 1) 为 true  
||	or	    (x==5 || y==5) 为 false  
!	not     not	!(x==y) 为 true  
*PS010*: 其他数据类型转换为布尔类型的规则: null、 undefined、 0、 NaN、 空字符串 转换为false，其他转化为 true。  

##### 9. 条件语句  
。。。

###### 9.1 break 和 continue 语句  
break 语句用于跳出当前循环。  
continue 用于跳过循环中的一个迭代。  
###### 9.2 操作符 typeof 或 方法 typeof()  
typeof "John"                // 返回 string  
typeof 3.14                  // 返回 number  
typeof false                 // 返回 boolean  
typeof [1,2,3,4]             // 返回 object  
typeof {name:'John', age:34} // 返回 object  

###### 9.3 null  
在 JavaScript 中 null 表示 "什么都没有"。  
null是一个只有一个值的特殊类型。表示一个空对象引用。  
用 typeof 检测 null 返回是object。  
*PS:* 当使用完一个比较大的对象时，需要对其进行释放内存时，设置为 null。
###### 9.4 undefined
在 JavaScript 中, undefined 是一个没有设置值的变量。  
typeof 一个没有值的变量会返回 undefined。  

> **undefined 和 null 的区别**  
> null 和 undefined 的值相等，但类型不等：  
> typeof undefined             // undefined
> typeof null                  // object
> null === undefined           // false
> null == undefined            // true
  
##### 10. 类型转换  
> NaN 的数据类型是 number
> 数组(Array)的数据类型是 object
> 日期(Date)的数据类型为 object
> null 的数据类型是 object
> undefined 未定义变量的数据类型为 undefined，Number(undefined)  显示NaN

1. constructor 属性  
> constructor 属性返回所有 JavaScript 变量的构造函数。  
> "John".constructor                 // 返回函数 String()  { [native code] }  
> (3.14).constructor                 // 返回函数 Number()  { [native code] }  
> false.constructor                  // 返回函数 Boolean() { [native code] }  
> [1,2,3,4].constructor              // 返回函数 Array()   { [native code] }  
> {name:'John', age:34}.constructor  // 返回函数 Object()  { [native code] }  
> new Date().constructor             // 返回函数 Date()    { [native code] }  
> function () {}.constructor         // 返回函数 Function(){ [native code] }  

2. 可以使用 constructor 属性来查看对象是否为数组 (包含字符串 "Array"):  
> function isArray(myArray) {
>   return myArray.constructor.toString().indexOf("Array") > -1;
> }

3. 可以使用 constructor 属性来查看对象是否为日期 (包含字符串 "Date"):
> function isDate(myDate) {
>   return myDate.constructor.toString().indexOf("Date") > -1;
> }  
  
###### 10.1 日期  
var myDate = new Date();  
*一些方法*  
getDate()   从 Date 对象返回一个月中的某一天 (1 ~ 31)。  
getDay()	从 Date 对象返回一周中的某一天 (0 ~ 6)。  
getFullYear()	从 Date 对象以四位数字返回年份。  
getHours()	返回 Date 对象的小时 (0 ~ 23)。  
getMilliseconds()	返回 Date 对象的毫秒(0 ~ 999)。  
getMinutes()	返回 Date 对象的分钟 (0 ~ 59)。  
getMonth()	从 Date 对象返回月份 (0 ~ 11)。  
getSeconds()	返回 Date 对象的秒数 (0 ~ 59)。  
getTime()	返回 1970 年 1 月 1 日至今的毫秒数。  
  
###### 10.2 Number 数字  
***字符串转成数字***
1. Number()  
2. 一元运算符 +  可用于将变量转换为数字：
    var y = "5"; // string  
    var x = + y; // number  
    如果变量不能转换，它仍然会是一个数字，但值为 NaN (不是一个数字):  
    var y = "John";   // y 是一个字符串 string
    var x = + y;      // x 是一个数字 (NaN) number  

---  
***布尔值转换为数字***  
Number(false)     // 返回 0
Number(true)      // 返回 1  

---   
***日期转换为数字***  
d = new Date();
Number(d)          // 返回 1404568027739  
日期方法 getTime() 也有相同的效果。
d = new Date();
d.getTime()        // 返回 1404568027739  

---  
***自动转换类型***  
当 JavaScript 尝试操作一个 "错误" 的数据类型时，会自动转换为 "正确" 的数据类型。  
5 + null    // 返回 5         null 转换为 0  
"5" + null  // 返回"5null"   null 转换为 "null"  
"5" + 1     // 返回 "51"      1 转换为 "1"   
"5" - 1     // 返回 4         "5" 转换为 5  

---  
***自动转换为字符串***
当你尝试输出一个对象或一个变量时 JavaScript 会自动调用变量的 toString() 方法。  

___  


##### 11. JavaScript 错误 - throw try 和 catch  
1. try 语句测试代码块的错误  
    try 语句允许我们定义在执行时进行错误测试代码块
2. catch 语句处理错误  
    catch 语句允许我们定义当try代码块发生错误时，所要执行的代码块。
3. throw 语句创建自定义错误  创建或抛出异常（exception）
4. finally 语句在try 和 catch 语句之后，无论是否出发异常，都会执行。 
  
*实例*  
```javascript
function myFunction() {
    var message, x;
    message = document.getElementById("message");
    message.innerHTML = "";
    x = document.getElementById("demo").value;
    try { 
        if(x == "")  throw "值为空";
        if(isNaN(x)) throw "不是数字";
        x = Number(x);
        if(x < 5)    throw "太小";
        if(x > 10)   throw "太大";
    }
    catch(err) {
        message.innerHTML = "错误: " + err;
    } 
    finally {
        document.getElementById("..").value = "";
    }
}  
```

##### 12. JavaScript 调试  
1. 浏览器控制台调试   console.log() 方法
2. 设置断点  
3. debugger 关键字  这个关键字与在调试工具中设置断点的效果是一样的。
    var x = 15 * 5;
    debugger;
    document.getElementbyId("demo").innerHTML = x;  

##### 13. JavaScript 声明提升   
JavaScript 中，函数及变量的声明都将被提升到函数的最顶部。  
JavaScript 中，变量可以在使用后声明，也就是变量可以先使用再声明。  
*PS：* 声明提升：函数声明和变量声明总是会被解释器悄悄地被"提升"到方法体的最顶部。  
1. JavaScript 初始化不会提升  
JavaScript 只有声明的变量会提升，初始化（赋值...）不会提升。  
也就是说，var x = 7;    var x 是变量声明，会提升，但 x = 7 是初始化，不会提升。所以，如果var x = 7;写在输出后面console.log(x)  输出x是undefined的变量。  

***PS： 关于 函数提升 和 变量提升  ***
在JS解析机制中，函数提升，优先于变量提升。  
*实例*  
> var getName = function() {console.log(2);}  
> function getName(){console.log(1);}  
> getName();
> 结果： 2  
  
解析机制如下：  
> // 函数、变量声明提升  
> function getName() {console.log(1);}  
> // 但是变量在后  
> var getName;  
> getName = function() {console.log(2);} // 变量赋值并不提升，还在原来的位置  
> getName(); // 最后输出2  
  
*PS:* 使用匿名函数不存在函数提升，因为函数名称使用变量表示，只存在变量提升。  
  
2. JavaScript 严格模式(user strict)  
使用 "use strict" 指令，它不是一条语句，但是是一个字面量表达式。  
"use strict" 的目的是指定代码在严格条件下执行。严格模式下你不能使用未声明的变量。  
  
**严格模式通过在脚本或函数的头部添加 use strict; 表达式来声明。**  
在函数内部声明是局部作用域 (只在函数内使用严格模式)  

> 严格模式的限制  
> *1.不允许 使用 未声明的 变量*  
> "use strict"; x = 3.14; // 报错  
> *2.不允许 删除 变量 或 对象*  
> "use strict"; var x = 3.14; delete x; // 报错  
> *3.不允许 删除 函数*  
> "use strict"; function myF() {}; delete myF; // 报错  
> *4.不允许 变量 重名*  
> *5.不允许 使用 八进制*   
> "use strict"; var x = 010; // 报错  
> *6.不允许 对 只读属性 赋值:*  
> ...; var obj = {};Object.defineProperty(obj, "x", {value:0, writable:false});obj.x = 3.14; // 报错  
> *7.不允许 对 一个使用 getter方法 读取的属性 进行赋值*  
> ...; var obj = {get x() {return 0} }; obj.x = 1; // 报错  
> *8.不允许删除一个不允许删除的属性*  
> ...; delete Object.prototype; // 报错  
> *9.变量名不能使用 "eval" 、 "arguments"  字符串:*  
> ...; var eval = 3.14;         // 报错
> *10. 禁止 this关键字 指向全局对象。*  
```JavaScript
    function f(){
    return !this;
} 
// 返回false，因为"this"指向全局对象，"!this"就是false

function f(){ 
    "use strict";
    return !this;
} 
// 返回true，因为严格模式下，this的值为undefined，所以"!this"为true。
```

##### 14. JavaScript 表单  
* 14.1 JavaScript 表单验证  
HTML 表单验证可以通过 JavaScript 来完成。  
JavaScript 可用来在数据被送往服务器前对 HTML 表单中的这些输入数据进行验证。  
* 14.2 JavaScript 验证API


##### 15. JavaScript 关键字  
* 15.1 this 关键字  
面向对象语言中 this 表示当前对象的一个引用。  
但是在 JavaScript 中 this 不是固定不变的，它会随着执行环境的改变而改变。  
    * 在方法中 this 表示当前方法所属的对象  
    * 如果单独使用，this 表示全局对象    
    * 在函数中 this 表示全局对象  
    * 在函数中 严格模式 "use strict" 下，this 是未定义的（undefined）  
    * 在事件中，this 表示接受事件的元素  
    * 类似 call() 和 apply() 方法可以将 this 引用到任何对象  

*实例1：*  在方法中 this 表示当前方法所属的对象  
``` javascript
var person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};  
console.log(person.fullName());  
// 输出 John Doe  
// 解释：符合第一条，在方法中 this 表示当前方法所属的对象，即当前 this 属于 person对象
```
*实例2：*  如果单独使用，this 表示全局对象    
单独使用 this，则它指向全局(Global)对象。
在浏览器中，window 就是该全局对象为 [object Window]；  
严格模式下，如果单独使用，this 也是指向全局(Global)对象。
```javascript
    // "use strict";
    console.log(this);
    // 输出：[object Window]
```
*实例3：* 在函数中，使用 this 表示全局变量(默认)  
在函数中，函数的所属者默认绑定到 this 上。
在浏览器中，window 就是该全局对象为 [object Window]:
```javascript
function myFunction() {
  return this;
}
myFunction();
// 输出：[object Window]
```
*实例4：* 函数中使用 this（严格模式）
严格模式下函数是没有绑定到 this 上，这时候 this 是 undefined。
```javascript
function myFunction() {
  return this;
}
myFunction();
// 输出：undefined
```  
*实例5：*  在事件中，this 表示接受事件的元素  
在 HTML 事件句柄中，this 指向了接收事件的 HTML 元素  
``` html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>

<h2>JavaScript <b>this</b> 关键字</h2>

<button onclick="this.style.display='none'">点我后我就消失了</button>

</body>
</html>
```  
*实例6：* 类似 call() 和 apply() 方法可以将 this 引用到任何对象  
*显式函数绑定：*  
在 JavaScript 中函数也是对象，对象则由方法，call() 和 apply() 就是对象的方法。  
这两个方法异常强大，他们允许切换函数执行的上下文环境(context)，即 this 绑定的对象。  
PS： 在下面实例中，当我们使用 person2 作为参数来调用 person1.fullName 方法时, this 将指向 person2, 即便它是 person1 的方法：  
```javascript 
var person1 = {
    firstName:"John1",
    lastName: "Doe1",
    fullName: function() {
    return this.firstName + " " + this.lastName;
  }
}
var person2 = {
  firstName:"John",
  lastName: "Doe",
}
person1.fullName.call(person2);  // 返回 "John Doe"
```  

* 15.2 let 和 const 关键字[ES6]  
let 声明的变量只在 let 命令所在的代码块内有效  
const 声明一个只读的变量，一旦声明，常量的值就不能再被修改  
*PS：*在ES6之前，JavaScript 中只有两种作用域：全区变量作用域 和 函数内的局部变量作用局。  

    ##### I 全局变量  
    在函数在声明的变量是全局的，全局变量在JavaScript 程序的任何位置都可以访问。  
    ##### II 局部变量  
    在函数内部声明的变量，其作用域是局部的（函数内部）。  
    在函数内部使用var 声明的变量只能在函数内部访问，如果不适应var 则是全局变量。  
    ##### III JavaScript 块级作用域  
    使用 var 关键字声明的变量不具备块级作用域的特性，它在{}外部依然能够被访问。  
    {var x = 2;} // 外部任然可以使用x  
    * 在ES6 之前，是没有块级作用域的概念的。  
    ES6可以使用 let 关键字来实现 块级作用域 (Block Scope)。  
    let 声明的变量只在 let 命令所在的代码块{}内有效，在{}之外不能被访问。  
    {let x = 2;}} // 外部访问不到x  
    
* 1. 重新定义变量  
使用 var 关键字重新声明变量可能会带来问题。在块中重新声明变量也会重新声明块外的变量：  
```javascript
        var x = 10;
        // 这里输出 x 为 10
        { 
            var x = 2;
            // 这里输出 x 为 2
        }
        // 这里输出 x 为 2
```  
let 关键字就可以解决这个问题，因为它只在 let 命令所在的代码块 {} 内有效。  
```javascript
        var x = 10;
        // 这里输出 x 为 10
        { 
            let x = 2;
            // 这里输出 x 为 2
        }
        // 这里输出 x 为 10
```  
* 2. 循环作用域  
例如 for 循环  
使用 var 关键字：  
```javascript
        var i = 5;
        for (var i = 0; i < 10; i++) {
            // 一些代码...
        }
        // 这里输出 i 为 10
```  
使用 let 关键字：  
```javascript
        let i = 5;
        for (let i = 0; i < 10; i++) {
            // 一些代码...
        }
        // 这里输出 i 为 5
```  
*PS01:*在第一个实例中，使用了 var 关键字，它声明的变量是全局的，包括循环体内与循环体外。  
*PS02:*在第二个实例中，使用 let 关键字， 它声明的变量作用域只在循环体内，循环体外的变量不受影响。  

* 3. HTML 代码中使用全局变量  
在 JavaScript 中, 全局作用域是针对 JavaScript 环境。  
在 HTML 中, 全局作用域是针对 window 对象。  
使用 var 关键字声明的全局作用域变量属于 window 对象:  
```html
        <!DOCTYPE html>
        <html>
        <head> 
        <meta charset="utf-8"> 
        <title>菜鸟教程(runoob.com)</title> 
        </head>
        <body>
        <h2>JavaScript 全局变量</h2>
        <p>使用 var 关键字声明的全局作用域变量属于 window 对象。</p>
        <p id="demo"></p>
        <script>
            var carName = "Volvo";
            // 可以使用 window.carName 访问变量
            document.getElementById("demo").innerHTML = "I can display " + window.carName;
        </script>
```  
使用 let 关键字声明的全局作用域变量不属于 window 对象: 不能使用window.name   

* 3. 重置变量  
使用 var 关键字声明的变量在任何地方都可以修改：   
```javascript
        var x = 2;
        // x 为 2
        var x = 3;
        // 现在 x 为 3
```  
在相同的作用域或块级作用域中，不能使用 let 关键字来重置 var 关键字声明的变量:  
```javascript
        var x = 2;       // 合法
        let x = 3;       // 不合法 
        {
            var x = 4;   // 合法
            let x = 5   // 不合法
        }
```  
在相同的作用域或块级作用域中，不能使用 let 关键字来重置 let 关键字声明的变量:  
```javascript
        let x = 2;       // 合法
        let x = 3;       // 不合法
        {
            let x = 4;   // 合法
            let x = 5;   // 不合法
        } 
```  
在相同的作用域或块级作用域中，不能使用 var 关键字来重置 let 关键字声明的变量;  
let 关键字在不同作用域，或不同块级作用域中是可以重新声明赋值的;  

* 4. 变量提升  
JavaScript 中，var 关键字定义的变量可以在使用后声明，也就是变量可以先使用再声明。  
let 关键字定义的变量则不可以在使用后声明，也就是变量需要先声明再使用。

* 5. const 关键字  
const 用于声明一个或多个常量，声明时必须进行初始化，且初始化后值不可再修改。  

    * const定义常量与使用let 定义的变量相似：  
        > * 二者都是块级作用域    
        > * 都不能和它所在作用域内的其他变量或函数拥有相同的名称  
    * 两者还有以下两点区别：  
        > * const声明的常量必须初始化，而let声明的变量不用  
        > * const 定义常量的值不能通过再赋值修改，也不能再次声明。而 let 定义的变量值可以修改。  

***PS:*** 在JS中 const *并非真正的常量*  
const 的本质: const 定义的变量并非常量，并非不可变，它定义了一个常量引用一个值。使用 const 定义的对象或者数组，其实是可变的。  
*实例:*  
```javascript 
/ 创建常量对象
const car = {type:"Fiat", model:"500", color:"white"};
// 修改属性:
car.color = "red";
// 添加属性
car.owner = "Johnson";
```  
但是我们不能对常量对象重新赋值： 
```javascript  
const car = {type:"Fiat", model:"500", color:"white"};
car = {type:"Volvo", model:"EX60", color:"red"};    // 错误
```
*实例02：*  
以下实例修改常量数组：
```javascript
// 创建常量数组
const cars = ["Saab", "Volvo", "BMW"]; 
// 修改元素
cars[0] = "Toyota"; 
// 添加元素
cars.push("Audi");
```  
但是我们不能对常量数组重新赋值：  
```javascript
const cars = ["Saab", "Volvo", "BMW"];
cars = ["Toyota", "Volvo", "Audi"];    // 错误
```


##### 16. JavaScript JSON  
JSON 是用于存储和传输数据的格式  
JSON 通常用于服务端向网页传递数据  

###### I 什么是 JSON  
JSON 英文全称 JavaScript Object Notation  
JSON 是一种轻量级的交换格式  
JSON 是独立的语言  
JSON 易于理解  
*PS:JSON 使用 JavaScript 语法，但是 JSON 格式仅仅是一个文本。文本可以被任何编程语言读取及作为数据格式传递。*  

###### II JSON 格式化后为 JavaScript 对象 
JSON 格式在语法上与创建 JavaScript 对象代码是相同的  
由于它们很相似，所以 JavaScript 程序可以很容易的将 JSON 数据转换为 JavaScript 对象。  

##### III JSON 语法规则  
* 数据为 键/值 对  
* 数据由逗号分隔  
* 大括号保存对象  {包含多个键/值 对}
* 方括号保存数组[PS：数组中也可以存在{对象}]  


##### IV JSON 字符串转换成 JavaScript 对象  
通常我们在服务器上读取JSON 数据，然后显示在网页上。  
首先，创建 JavaScript 字符串，字符串为 JSON 格式的数据：
然后，使用 JavaScript 内置函数 JSON.parse() 将字符串转换为 JavaScript 对象:
```javascript
var text = '{ "sites" : [' +
'{ "name":"Runoob" , "url":"www.runoob.com" },' +
'{ "name":"Google" , "url":"www.google.com" },' +
'{ "name":"Taobao" , "url":"www.taobao.com" } ]}';  
var obj = JSON.parse(text);
```  
*PS:相关函数*  
|函数|描述|  
|:---|:---|
|JSON.parse()|用于将一个JSON字符串转换为JavaScript对象|
|JSON.stringify()|用于将JavaScript值转换成JSON字符串|   


##### 17. JavaScript void  
###### I javascript:void(0)  
我们经常使用得到 javascript:void(0) 这样的代码，那么在 JavaScript 中 javascript:void(0) 代表什么意思呢？  
javascript:void(0) 中最关键的是 void 关键字，void 是 JavaScript 中非常重要的关键字,该操作符指定要计算一个表达式但是不返回值。  
语法格式如下：  
```javascript
void func()
javascript:void func()
// 或者：  
void(func())
javascript:void(func())

```  
* 下面的代码创建了一个超级链接，当用户点击以后不会发生任何事。  
```html
<a href="javascript:void(0)">单击此处什么也不会发生</a>  
<!-- 当用户链接时，void(0) 计算为 0，但 Javascript 上没有任何效果。 -->
```  
* 以下实例中，在用户点击链接后显示警告信息：  
```html
<p>点击以下链接查看结果：</p>
<a href="javascript:void(alert('Warning!!!'))">点我!</a>
<!-- void()仅仅是代表不返回任何值，但是括号内的表达式还是要运行 -->
```  
* 以下实例中参数 a 将返回 undefined :  
```html  
<!DOCTYPE html> 
<html> 
<head> 
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<script type="text/javascript">
function getValue(){
   var a,b,c;
   a = void ( b = 5, c = 7 );
   document.write('a = ' + a + ' b = ' + b +' c = ' + c );
}
</script>
</head>
<body>
<p>点击以下按钮查看结果：</p>
<form>
<input type="button" value="点我" onclick="getValue();" />
</form>
</body>
</html>  
<!-- 输出： a = undefined b = 5 c = 7 -->
```   

###### II href="#" 和 href = "javascript:void(0)"  的区别  
\#包含一个位置信息，默认的锚点\#top 也就是网页的上端。  
而 javascript:void(0)，仅表示一个死链接。  
在页面很长的时候会使用 \# 来定位页面的具体位置，格式为：\# + id。  
如果你要定义一个死链接请使用 javascript:void(0)  
*实例：*  
```html  
<a href="javascript:void(0);">点我没有反应的!</a>
<a href="#pos">点我定位到指定位置!</a>
<br>
...
<br>
<p id="pos">尾部定位点</p>
```

##### 18. JavaScript 异步编程  
###### I 异步编程  Asynchronous, async 与 同步编程 Synchronous, sync
###### II 什么时候使用异步编程  
在前端编程中（甚至后端有时也是这样），我们在处理一些简短、快速的操作时，例如计算 1 + 1 的结果，往往在主线程中就可以完成。主线程作为一个线程，不能够同时接受多方面的请求。所以，当一个事件没有结束时，界面将无法处理其他请求。  
现在有一个按钮，如果我们设置它的 onclick 事件为一个死循环，那么当这个按钮按下，整个网页将失去响应。  
为了避免这种情况的发生，我们常常用子线程来完成一些可能消耗时间足够长以至于被用户察觉的事情，比如读取一个大文件或者发出一个网络请求。因为子线程独立于主线程，所以即使出现阻塞也不会影响主线程的运行。  
但是子线程有一个局限：一旦发射了以后就会与主线程失去同步，我们无法确定它的结束，如果结束之后需要处理一些事情，比如处理来自服务器的信息，我们是无法将它合并到主线程中去的。  
为了解决这个问题，JavaScript 中的异步操作函数往往通过回调函数来实现异步任务的结果处理。  
##### III 回调函数  
回调函数就是一个函数，它是在我们启动一个异步任务的时候就告诉它：等你完成了这个任务之后要干什么。这样一来主线程几乎不用关心异步任务的状态了，他自己会善始善终。  
*实例1：*
这段程序中的 setTimeout 就是一个消耗时间较长（3 秒）的过程，它的第一个参数是个回调函数，第二个参数是毫秒数，这个函数执行之后会产生一个子线程，子线程会等待 3 秒，然后执行回调函数 "print"，在命令行输出 "RUNOOB!"。  
```javascript
setTimeout(function () {
    document.getElementById("demo").innerHTML="RUNOOB!";
}, 3000);
```  
*实例2：*  
既然 setTimeout 会在子线程中等待 3 秒，在 setTimeout 函数执行之后主线程并没有停止  
```javascript 
setTimeout(function() {console.log("1")},3000);
console.log("2");
// 执行结果是：
//  2
//  1
```  
###### IV 异步 AJAX  
除了 setTimeout 函数以外，异步回调广泛应用于 AJAX 编程。  
有关于 AJAX 详细请参见：https://www.runoob.com/ajax/ajax-tutorial.html  


##### 19. JavaScript Promise  
Promise 是一个 ECMAScript6 提供的<u>类</u>，目的是更加优雅的书写复杂的异步任务。  
###### I 创建 Promise  
* 语法：
```javascript
new Promise(function(resolve,reject){
    // 函数体
    });
```   
* 应用：
我们之前遇到的异步任务都是一次异步，如果需要多次调用异步函数呢？  
例如，如果我想分三次输出字符串，第一次间隔 1 秒，第二次间隔 4 秒，第三次间隔 3 秒：  
使用setTimeout  
```javascript
setTimeout(function () {
    console.log("First");
    setTimeout(function () {
        console.log("Second");
        setTimeout(function () {
            console.log("Third");
        }, 3000);
    }, 4000);
}, 1000);
```  
这段程序实现了这个功能，但是它是用 "函数瀑布" 来实现的。  
可想而知，在一个复杂的程序当中，用 "函数瀑布" 实现的程序无论是维护还是异常处理都是一件特别繁琐的事情，而且会让缩进格式变得非常冗赘。  
**现在我们用 Promise 来实现同样的功能**   
```javascript
new Promise(function(resolve,reject){
    setTimeout(function(){
        console.log("1");
        resolve();
    },1000);
}).then(function(){
    return new Promise(function(resolve,reject){
        setTimeout(function(){
            console.log("2");
            resolve();
        },4000);
    });
}).then(function(){
    setTimeout(function(){
        console.log("3");
    },3000);
});
// 执行结果： 1 2 3
```  
```javascript
new Promise(function(resolve,reject){
    setTimeout(function(){
        console.log("1");
        resolve();
    },1000);
}).then(function(){
        setTimeout(function(){
            console.log("2");
            resolve();
        },4000);
}).then(function(){
    setTimeout(function(){
        console.log("3");
    },3000);
});
// 执行结果： 1 3 2
```  

Promise 将嵌套格式的代码变成了顺序格式的代码。  

###### II Promise 使用  
Promise 构造函数只有一个参数，是一个函数，这个函数在构造之后会直接被异步运行，所以我们称之为起始函数。  
起始函数包含两个参数 resolve 和 reject。  
resolve 和 reject 都是函数，其中调用 resolve 代表一切正常，reject 是出现异常时所调用的。  
*实例01：*  
```javascript
new Promise(function(resolve,reject){
    var a = 0;
    var b = 1;
    if (b == 0)
        reject("Divide zero!");
    else  
        resolve(a/b);
}).then(function(value){
    console.log("a / b = " + value);
}).catch(function(err){
    console.log("错误：" + err);
}).finally(function(){
    console.log("END");
});
// 执行结果：a / b = 0
//          End
```
*说明01：*  
Promise 类有.then(),.catch(),.finally() 三个方法，这三个方法的参数都是一个函数。  
.then() 可以将参数中的函数添加到当前 Promise 的正常执行序列，.catch() 则是设定 Promise 的异常处理序列，.finally() 是在 Promise 执行的最后一定会执行的序列。  
 .then() 传入的函数会按顺序依次执行，有任何异常都会直接跳到 catch 序列。  
 *实例02：*   
 ```javascript
new Promise(function(resolve,reject){
    console.log(1111);
    resolve(2222); // 传给下一个then
}).then(function(value){
    console.log(value);
    return 3333; // 传给下一个then，并且不会中断
}).then(function(value){
    console.log(value);
    throw "An Error"; // 抛出自定义异常
}).catch(function(err){
    console.log(err); // .catch() 捕获异常
});
// 执行结果：
//1111
//2222
//3333
//An error
 ```  
 *说明02：*  
 resolve() 中可以放置一个参数用于向下一个 then 传递一个值，then 中的函数也可以返回一个值传递给 then。  
 但是，如果 then 中返回的是一个 Promise 对象，那么下一个 then 将相当于对这个返回的 Promise 进行操作，这一点从刚才的计时器的例子中可以看出来。  
 reject() 参数中一般会传递一个异常给之后的 catch 函数用于处理异常。  
 ***注意：*** 
     * resolve 和 reject 的作用域只有起始函数，不包括 then 以及其他序列；
     * resolve 和 reject 并不能够使起始函数停止运行，别忘了 return。

###### III Promise 函数  
上述的 "计时器" 程序看上去比函数瀑布还要长，所以我们可以将它的核心部分写成一个 Promise 函数：  
```javascript
function print(delay,message) {
    return new Promise(function(resolve,reject) {
        setTimeout(function(){
            console.log(message);
            resolve();
        },delay);
    });
}

// 实现功能:  
print(1000,"1").then(function() {
    return print(4000,"2"); // 使用return，返回一个promise，所以后面的then依赖当前2的promise,在2执行4s后执行
}).then(function() {
    print(3000,"3");
});
// 结果: 1 2 3
// 如果取消return 则，2和3的then都是依赖于1的promise，所以执行结果为1 3 2
```  
###### IV 异步函数  
异步函数 (async function) 是 ECMAScript 2017 (ECMA-262) 标准的规范，几乎被所有浏览器所支持，除了 Internet Explorer。  
我们可以使用异步函数，使上面使用Promise 函数写的解决方案更简洁：  
```javascript
async function asyncFun() {
    await print(1000,"1");
    await print(4000,"2");
    await print(3000,"3");
}
asyncFun();
```  
*PS:异步函数 async function 中可以使用 await 指令，await 指令后必须跟着一个 Promise，异步函数会在这个 Promise 运行中暂停，直到其运行结束再继续运行。
异步函数实际上原理与 Promise 原生 API 的机制是一模一样的，只不过更便于程序员阅读。*  
处理异常的机制将用 try-catch 块实现：  
```javascript
async function asyncFunc() {
    try {
        await new Promise(function (resolve, reject) {
            throw "Some error"; // 或者 reject("Some error")
        });
    } catch (err) {
        console.log(err);
        // 会输出 Some error
    }
}
asyncFunc();
```  
如果 Promise 有一个正常的返回值，await 语句也会返回它：  
```javascript
async function asyncFunc() {
    let value = await new Promise( function (resolve, reject) {
            resolve("Return value");
        });
    console.log(value);
}
asyncFunc(); // 输出： Return value
```
###### V Promise 对象  
* Promise 对象有以下两个特点:  
    1. 对象的状态不受外界影响。Promise 对象代表一个异步操作，有三种状态：
        * pending：初始状态，不是成功或失败的状态  
        * fulfilled: 操作成功完成，resolved  
        * rejected：操作失败  
    只有一步操作的结果，可以决定当前是哪一种状态，其他操作都无法改变这个状态。  
    2. 一旦状态改变，就不会再变，任何时候都能得到这个结果。     
        Promise 对象的状态改变，只有两种可能：
        * 从Pending -> fulfilled（即，resolved）
        * 从Pending -> rejected  
    只要这两种情况发生，状态就凝固了，不会再变了，会一直保持这个结果。就算改变已经发生了，你再对 Promise 对象添加回调函数，也会立即得到这个结果。这与事件（Event）完全不同，事件的特点是，如果你错过了它，再去监听，是得不到结果的。  

* Promise 优缺点:  
有了 Promise 对象，就可以将异步操作以同步操作的流程表达出来，避免了层层嵌套的回调函数。此外，Promise 对象提供统一的接口，使得控制异步操作更加容易。  
Promise 也有一些缺点。首先，无法取消 Promise，一旦新建它就会立即执行，无法中途取消。其次，如果不设置回调函数，Promise 内部抛出的错误，不会反应到外部。第三，当处于 Pending 状态时，无法得知目前进展到哪一个阶段（刚刚开始还是即将完成）。  


##### 20. 正则表达式  




























---

### JS 函数  
---  



### JS 类  


### JS HTML DOM  


### JS 高级教程  


### JS 浏览器 BOM  


### JS 库  

### JS ES6
