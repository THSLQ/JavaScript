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
* PS:当您声明新变量时，可以使用关键词 "new" 来声明其类型:[JavaScript 变量均为对象。当您声明一个变量时，就创建了一个新的对象。]，但是不推荐使用new创建一些基础变量对象，这种操作会拖慢执行速度，而且可能产生其他副作用。
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



##### 11. JavaScript 错误 - throw try 和 catch  
1. try 语句测试代码块的错误  
    try 语句允许我们定义在执行时进行错误测试代码块
2. catch 语句处理错误  
    catch 语句允许我们定义当try代码块发生错误时，所要执行的代码块。
3. throw 语句创建自定义错误  创建或抛出异常（exception）
4. finally 语句在try 和 catch 语句之后，无论是否出发异常，都会执行。 
  
*实例*  
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
也就是说，var x = 7;    var x 是变量声明，会提升，但 x = 7 是初始化，不会提升。所以，如果在输出后面 var x = 7; 输出x是undefined的变量。  

***PS：*** 关于 函数提升 和 变量提升  
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



### JS 函数  
---  



### JS 类  


### JS HTML DOM  


### JS 高级教程  


### JS 浏览器 BOM  


### JS 库  
