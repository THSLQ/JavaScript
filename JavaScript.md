### 一、 JavaScript 基础教程 2022.0317

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

可以直接写入 body 中的文本:

```javascript
<script> document.write("写入"); </script>
```

###### 1.3 Javascript 输出

- JavaScript 可以通过不同的方式来输出数据： 
  > 1. 使用 window.alert() 弹出警告框。
  > 2. 使用 document.write() 方法将内容写到 HTML 文档中。
  > 3. 使用 innerHTML 写入到 HTML 元素。
  > 4. 使用 console.log() 写入到浏览器的控制台。  
  > PS： 如果在文档已完成加载后执行 document.write，整个 HTML 页面将被覆盖。

###### 1.4 操作 HTML 元素

JavaScript 访问某个 HTML 元素，您可以使用 document.getElementById(id) 方法。需要为元素提前设置 id 属性。  
 使用 "id" 属性来标识 HTML 元素，并 innerHTML 来获取或插入元素内容。

##### 2. JavaScript 语法

JavaScript 是一个程序语言。语法规则定义了语言结构。

###### 2.1 变量 variable

- 变量必须以字母开头
- 变量也能以 $ 和 \_ 符号开头（不过我们不推荐这么做）
- 变量名称对大小写敏感（y 和 Y 是不同的变量）

##### 3. JavaScript 数据类型

- 值类型[基本类型]：数字 Number、字符串 String、布尔 Boolean、对空 Null、未定义 Undefined、Symbol（ES6，引入的新原始类型，表示独一无二的值）
- 引用类型：数组 Array、对象 Object、函数 Function

###### 3.1 JavaScript 拥有动态类型

表示，相同的变量名，可以用作不同的类型。  
var x; // undefined
var x = 7; // number
var x = 'abc'; // string

- PS: 当您声明新变量时，可以使用关键词 "new" 来声明其类型:[JavaScript 变量均为对象。当您声明一个变量时，就创建了一个新的对象。]，但是不推荐使用 new 创建一些基础变量对象，这种操作会拖慢执行速度，而且可能产生其他副作用。
  > var name = new String;
  > var x= new Number;
  > var y= new Boolean;
  > var cars= new Array;
  > var person= new Object;
- PS02: 对于 Array 类型，typeof(Array)返回值是 object。所以，判断 Array 类型，使用下列方式
  1. isArray(): if(Array.isArray){if(Array.isArray(cars)) console.log("cars 是 Array");}
  2. instanceof: if(cars instanceof Array) {console.log("cars 是 Array");}

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
_PS：_ 在 HTML 中, 全局变量是 window 对象: 所有数据变量都属于 window 对象。

###### 5.3 JavaScript 变量生命周期

JavaScript 变量生命周期在它声明时初始化。
局部变量在函数执行完毕后销毁。
全局变量在页面关闭后销毁。

###### 5.4 ES6 let 关键字

let 允许你声明一个作用域被限制在块级中的变量、语句或者表达式（对于使用 for 循环中的循环变量，使用 let 声明）。与 var 关键字不同的是，它声明的变量只能是全局或者整个函数块的。

##### 6. JavaScript 事件

当 HTML 中发生事件是，称为 HTML 事件。在 HTML 中使用 JavaScript 来相应 HTML 事件，称为 JavaScript 事件。

###### 6.1 HTML 事件

HTML 事件可以是浏览器行为，也可以是用户行为：

- HTML 页面完成加载
- HTML input 字段改变时
- HTML 按钮被点击
- 等等

当 HTML 事件触发时，你可以做一些事情，比如执行一些 JavaScript 代码。  
| 常用 HTML 事件 | 描述 |
| :----- | :----- |
| onchange | HTML 元素改变 |
| onclick | 用户点击 HTML 元素 |
| onmouseover | 鼠标指针移动到指定的元素上时发生 |
| onmouseout | 用户从一个 HTML 元素上移开鼠标时发生 |
| onkeydown | 用户按下键盘按键 |
| onload | 浏览器已完成页面的加载 |
| onblur| 失去焦点时触发 |

##### 7. JavaScript 字符串

JavaScript 字符串用于存储和处理文本。

###### 7.1 String 字符串的 属性 和 方法

1. 属性：  
   constructor：返回创建字符串属性的函数；  
   length：返回字符串的长度；  
   prototype： 允许您向对象添加属性和方法；
2. 方法：  
   charAt(index): 返回指定索引位置的字符  
   charCodeAt(): 返回指定索引位置字符的 Unicode 值  
   concat(): 连接两个或多个字符串，返回连接后的字符串  
   indexOf() 返回字符串中检索指定字符第一次出现的位置  
   lastIndexOf() 返回字符串中检索指定字符最后一次出现的位置  
   match() 找到一个或多个正则表达式的匹配  
   replace() 替换与正则表达式匹配的子串  
   search() 检索与正则表达式相匹配的值  
   slice(start,end): 提取字符串的片断，并在新的字符串中返回被提取的部分(区间[start,end))  
   split(splitter, ?limit) 把字符串分割为子字符串数组(splitter 分割字符，可选参数 limit 保留多少数组元素)  
   substr(start,length): 从起始索引号提取字符串中指定数目的字符(包含 start)  
   substring(start,end) 提取字符串中两个指定的索引号之间的字符(区间[start,end))  
   toLocaleLowerCase() 根据主机的语言环境把字符串转换为小写，只有几种语言（如土耳其语）具有地方特有的大小写映射  
   toLocaleUpperCase() 根据主机的语言环境把字符串转换为大写，只有几种语言（如土耳其语）具有地方特有的大小写映射  
   toLowerCase() 把字符串转换为小写  
   toUpperCase() 把字符串转换为大写  
   trim() 移除字符串首尾空白(JS 中"A "空格也有长度 "A "长度为 2)  
   valueOf() 返回某个字符串对象的原始值

#### 7. JavaScript 运算符

###### 7.1 对字符串和数字进行加法运算

两个数字相加，返回数字相加的和，如果数字与字符串相加，返回字符串。

###### 7.2 JavaScript == 与 === 区别

1. 对于 string、number 等基础类型，== 和 === 是有区别的

- 不同类型间比较，== 之比较 "转化成同一类型后的值" 看 "值" 是否相等，=== 如果类型不同，其结果就是不等。
- 同类型比较，直接进行 "值" 比较，两者结果一样。

2. 对于 Array,Object 等高级类型，== 和 === 是没有区别的  
   进行 "指针地址" 比较
3. 基础类型与高级类型，== 和 === 是有区别的

- 对于 ==，将高级转化为基础类型，进行 "值" 比较
- 因为类型不同，=== 结果为 false

_PS010_: bool 类型在与数字类型进行相加时，视为 0 或者 1 处理。  
_PS020_: null 类型与数字类型进行累加时，视为 0 处理。  
_PS030_: undefined 除了与字符串进行累加时有效（undefined 视为字符串"undefined"处理），其他情况皆返回 NaN。 1 + undefined = NaN

##### 8. JavaScript 比较 和 逻辑运算符

###### 8.1 比较运算符

== 等于  
=== 绝对等于（值和类型均相等）  
!= 不等于  
!== 不绝对等于（值和类型有一个不相等，或两个都不相等）

###### 8.2 逻辑运算符

给定 x=6 以及 y=3，下表解释了逻辑运算符：
&& and (x < 10 && y > 1) 为 true  
|| or (x == 5 || y == 5) 为 false  
! not not !(x == y) 为 true  
_PS010_: 其他数据类型转换为布尔类型的规则: null、 undefined、 0、 NaN、 空字符串 转换为 false，其他转化为 true。

###### 8.3 常用函数  
isNaN() 函数用于检查其参数是否是非数字值。  
如果参数值为 NaN 或字符串、对象、undefined等非数字值则返回 true, 否则返回 false。

##### 9. 条件语句

。。。

###### 9.1 break 和 continue 语句

break 语句用于跳出当前循环。  
continue 用于跳过循环中的一个迭代。

###### 9.2 操作符 typeof 或 方法 typeof()

typeof "John" // 返回 string  
typeof 3.14 // 返回 number  
typeof false // 返回 boolean  
typeof [1,2,3,4] // 返回 object  
typeof {name:'John', age:34} // 返回 object

###### 9.3 null

在 JavaScript 中 null 表示 "什么都没有"。  
null 是一个只有一个值的特殊类型。表示一个空对象引用。  
用 typeof 检测 null 返回是 object。  
_PS:_ 当使用完一个比较大的对象时，需要对其进行释放内存时，设置为 null。

###### 9.4 undefined

在 JavaScript 中, undefined 是一个没有设置值的变量。  
typeof 一个没有值的变量会返回 undefined。  

```javascript
var x;
console.log(x);// undefined
```

> **undefined 和 null 的区别**  
> null 和 undefined 的值相等，但类型不等：  
> typeof undefined // undefined
> typeof null // object
> null === undefined // false
> null == undefined // true

##### 10. 类型转换

> NaN 的数据类型是 number
> 数组(Array)的数据类型是 object
> 日期(Date)的数据类型为 object
> null 的数据类型是 object
> undefined 未定义变量的数据类型为 undefined，Number(undefined) 显示 NaN

1. constructor 属性

   > constructor 属性返回所有 JavaScript 变量的构造函数。  
   > "John".constructor // 返回函数 String() { [native code] }  
   > (3.14).constructor // 返回函数 Number() { [native code] }  
   > false.constructor // 返回函数 Boolean() { [native code] }  
   > [1,2,3,4].constructor // 返回函数 Array() { [native code] }  
   > {name:'John', age:34}.constructor // 返回函数 Object() { [native code] }  
   > new Date().constructor // 返回函数 Date() { [native code] }  
   > function () {}.constructor // 返回函数 Function(){ [native code] }

2. 可以使用 constructor 属性来查看对象是否为数组 (包含字符串 "Array"):

   > function isArray(myArray) {
   > return myArray.constructor.toString().indexOf("Array") > -1;
   > }
```javascript
// 也可以使用 prototype  
console.log(Object.prototype.toString.call(myArray).indexOf("Array") > -1); //
```

3. 可以使用 constructor 属性来查看对象是否为日期 (包含字符串 "Date"):
   > function isDate(myDate) {
   > return myDate.constructor.toString().indexOf("Date") > -1;
   > }

###### 10.1 日期

var myDate = new Date();  
**一些方法**  
getDate() 从 Date 对象返回一个月中的某一天 (1 ~ 31)。  
getDay() 从 Date 对象返回一周中的某一天 (0 ~ 6)。  
getFullYear() 从 Date 对象以四位数字返回年份。  
getHours() 返回 Date 对象的小时 (0 ~ 23)。  
getMilliseconds() 返回 Date 对象的毫秒(0 ~ 999)。  
getMinutes() 返回 Date 对象的分钟 (0 ~ 59)。  
getMonth() 从 Date 对象返回月份 (0 ~ 11)。  
getSeconds() 返回 Date 对象的秒数 (0 ~ 59)。  
getTime() 返回 1970 年 1 月 1 日至今的毫秒数。

###### 10.2 Number 数字

***字符串转成数字***

1. Number()
2. 一元运算符 + 可用于将变量转换为数字：
   var y = "5"; // string  
   var x = + y; // number  
   如果变量不能转换，它仍然会是一个数字，但值为 NaN (不是一个数字):  
   var y = "John"; // y 是一个字符串 string
   var x = + y; // x 是一个数字 (NaN) number

---

**_布尔值转换为数字_**  
Number(false) // 返回 0
Number(true) // 返回 1

---

**_日期转换为数字_**  
d = new Date();
Number(d) // 返回 1404568027739  
日期方法 getTime() 也有相同的效果。
d = new Date();
d.getTime() // 返回 1404568027739

---

**_自动转换类型_**  
当 JavaScript 尝试操作一个 "错误" 的数据类型时，会自动转换为 "正确" 的数据类型。  
5 + null // 返回 5 null 转换为 0  
"5" + null // 返回"5null" null 转换为 "null"  
"5" + 1 // 返回 "51" 1 转换为 "1"  
"5" - 1 // 返回 4 "5" 转换为 5

---

**_自动转换为字符串_**
当你尝试输出一个对象或一个变量时 JavaScript 会自动调用变量的 toString() 方法。

---

##### 11. JavaScript 错误 - try throw 和 catch finally

1. try 语句测试代码块的错误  
   try 语句允许我们定义在执行时进行错误测试代码块
2. catch 语句处理错误  
   catch 语句允许我们定义当 try 代码块发生错误时，所要执行的代码块。
3. throw 语句创建自定义错误 创建或抛出异常（exception）
4. finally 语句在 try 和 catch 语句之后，无论是否出发异常，都会执行。

_实例_

```javascript
function myFunction() {
  var message, x;
  message = document.getElementById("message");
  message.innerHTML = "";
  x = document.getElementById("demo").value;
  try {
    if (x == "") throw "值为空";
    if (isNaN(x)) throw "不是数字";
    x = Number(x);
    if (x < 5) throw "太小";
    if (x > 10) throw "太大";
  } catch (err) {
    message.innerHTML = "错误: " + err;
  } finally {
    document.getElementById("..").value = "";
  }
}
```

##### 12. JavaScript 调试

1. 浏览器控制台调试 console.log() 方法
2. 设置断点
3. debugger 关键字 这个关键字与在调试工具中设置断点的效果是一样的。
   var x = 15 \* 5;
   debugger;
   document.getElementbyId("demo").innerHTML = x;

##### 13. JavaScript 声明提升

JavaScript 中，函数及变量的声明都将被提升到函数的最顶部。  
JavaScript 中，变量可以在使用后声明，也就是变量可以先使用再声明。  
_PS：_ 声明提升：函数声明和变量声明总是会被解释器悄悄地被"提升"到方法体的最顶部。

1. JavaScript 初始化不会提升  
   JavaScript 只有声明的变量会提升，初始化（赋值...）不会提升。  
   也就是说，var x = 7; var x 是变量声明，会提升，但 x = 7 是初始化，不会提升。所以，如果 var x = 7;写在输出后面 console.log(x) 输出 x 是 undefined 的变量。

**PS： 关于 函数提升 和 变量提升**
在 JS 解析机制中，函数提升，优先于变量提升。  
_实例_

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
> getName(); // 最后输出 2

**PS:** 使用匿名函数不存在函数提升，因为函数名称使用变量表示，只存在变量提升。

2. JavaScript 严格模式(user strict)  
   使用 "use strict" 指令，它不是一条语句，但是是一个字面量表达式。  
   "use strict" 的目的是指定代码在严格条件下执行。严格模式下你不能使用未声明的变量。

**严格模式通过在脚本或函数的头部添加 use strict; 表达式来声明。**  
在函数内部声明是局部作用域 (只在函数内使用严格模式)

> 严格模式的限制  
> _1.不允许 使用 未声明的 变量_  
> "use strict"; x = 3.14; // 报错  
> _2.不允许 删除 变量 或 对象_  
> "use strict"; var x = 3.14; delete x; // 报错  
> _3.不允许 删除 函数_  
> "use strict"; function myF() {}; delete myF; // 报错  
> _4.不允许 变量 重名_  
> _5.不允许 使用 八进制_  
> "use strict"; var x = 010; // 报错  
> _6.不允许 对 只读属性 赋值:_  
> ...; var obj = {};Object.defineProperty(obj, "x", {value:0, writable:false});obj.x = 3.14; // 报错  
> _7.不允许 对 一个使用 getter 方法 读取的属性 进行赋值_  
> ...; var obj = {get x() {return 0} }; obj.x = 1; // 报错  
> _8.不允许删除一个不允许删除的属性_  
> ...; delete Object.prototype; // 报错  
> _9.变量名不能使用 "eval" 、 "arguments" 字符串:_  
> ...; var eval = 3.14; // 报错
> _10. 禁止 this 关键字 指向全局对象。_

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

- 14.1 JavaScript 表单验证  
  HTML 表单验证可以通过 JavaScript 来完成。  
  JavaScript 可用来在数据被送往服务器前对 HTML 表单中的这些输入数据进行验证。
- 14.2 JavaScript 验证 API

##### 15. JavaScript 关键字

- 15.1 this 关键字  
  面向对象语言中 this 表示当前对象的一个引用。  
  但是在 JavaScript 中 this 不是固定不变的，它会随着执行环境的改变而改变。  
   * 在方法中 this 表示当前方法所属的对象  
   * 如果单独使用，this 表示全局对象  
   * 在函数中 this 表示全局对象  
   * 在函数中 严格模式 "use strict" 下，this 是未定义的（undefined）  
   * 在HTML事件中，this 表示接受事件的元素  
   * 类似 call() 和 apply() 方法可以将 this 引用到任何对象  
**PS: this 绑定的优先级** new > bind > call,apply > obj.function() > 默认绑定

**实例 1：** 在方法中 this 表示当前方法所属的对象

```javascript
var person = {
  firstName: "John",
  lastName: "Doe",
  id: 5566,
  fullName: function () {
    return this.firstName + " " + this.lastName;
  },
};
console.log(person.fullName());
// 输出 John Doe
// 解释：符合第一条，在方法中 this 表示当前方法所属的对象，即当前 this 属于 person对象
```

_实例 2：_ 如果单独使用，this 表示全局对象  
单独使用 this，则它指向全局(Global)对象。
在浏览器中，window 就是该全局对象为 [object Window]；  
严格模式下，如果单独使用，this 也是指向全局(Global)对象。

```javascript
// "use strict";
console.log(this);
// 输出：[object Window]
```

_实例 3：_ 在函数中，使用 this 表示全局变量(默认)  
在函数中，函数的所属者默认绑定到 this 上。
在浏览器中，window 就是该全局对象为 [object Window]:

```javascript
function myFunction() {
  return this;
}
myFunction();
// 输出：[object Window]
```

_实例 4：_ 函数中使用 this（严格模式）
严格模式下函数是没有绑定到 this 上，这时候 this 是 undefined。

```javascript
function myFunction() {
  return this;
}
myFunction();
// 输出：undefined
```

_实例 5：_ 在事件中，this 表示接受事件的元素  
在 HTML 事件句柄中，this 指向了接收事件的 HTML 元素

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>菜鸟教程(runoob.com)</title>
  </head>
  <body>
    <h2>JavaScript <b>this</b> 关键字</h2>

    <button onclick="this.style.display='none'">点我后我就消失了</button>
  </body>
</html>
```

**实例 6:** 类似 call() 和 apply() 方法可以将 this 引用到任何对象  
**显式函数绑定:**  
在 JavaScript 中函数也是对象，对象则由方法，call() 和 apply() 就是对象的方法。  
这两个方法异常强大，他们允许切换函数执行的上下文环境(context)，即 this 绑定的对象。  
在下面实例中，当我们使用 person2 作为参数来调用 person1.fullName 方法时, this 将指向 person2, 即便它是 person1 的方法：

```javascript
var person1 = {
  firstName: "John1",
  lastName: "Doe1",
  fullName: function () {
    return this.firstName + " " + this.lastName;
  },
};
var person2 = {
  firstName: "John",
  lastName: "Doe",
};
person1.fullName.call(person2); // 返回 "John Doe"
```

- 15.2 let 和 const 关键字[ES6]  
  let 声明的变量只在 let 命令所在的代码块内有效  
  const 声明一个只读的变量，一旦声明，常量的值就不能再被修改  
  **PS:** 在 ES6 之前，JavaScript 中只有两种作用域：全区变量作用域 和 函数内的局部变量作用局。

##### I 全局变量
在函数在声明的变量是全局的，全局变量在JavaScript 程序的任何位置都可以访问。
##### II 局部变量
在函数内部声明的变量，其作用域是局部的（函数内部）。
在函数内部使用var 声明的变量只能在函数内部访问，如果不适应var 则是全局变量。
**实例：**

```javascript
function fn() {
  var a = (b = 1);
} // 等价于 var a = b, b = 1; 因为b没有使用var声明，是全局变量，a是局部变量
fn();
console.log(b); // 输出 1
console.log(a); // 报错:Uncaught ReferenceError: a is not defined at ...
```

##### III JavaScript 块级作用域
使用 var 关键字声明的变量不具备块级作用域的特性，它在{}外部依然能够被访问。
{var x = 2;} // 外部任然可以使用x
* 在ES6 之前，是没有块级作用域的概念的。
    ES6可以使用 let 关键字来实现 块级作用域 (Block Scope)。
    let 声明的变量只在 let 命令所在的代码块{}内有效，在{}之外不能被访问。
    {let x = 2;}} // 外部访问不到x

- 1. 重新定义变量  
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

- 2. 循环作用域  
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

**PS01:** 在第一个实例中，使用了 var 关键字，它声明的变量是全局的，包括循环体内与循环体外。  
**PS02:** 在第二个实例中，使用 let 关键字， 它声明的变量作用域只在循环体内，循环体外的变量不受影响。

- 3. HTML 代码中使用全局变量  
     在 JavaScript 中, 全局作用域是针对 JavaScript 环境。  
     在 HTML 中, 全局作用域是针对 window 对象。  
     使用 var 关键字声明的全局作用域变量属于 window 对象:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>菜鸟教程(runoob.com)</title>
  </head>
  <body>
    <h2>JavaScript 全局变量</h2>
    <p>使用 var 关键字声明的全局作用域变量属于 window 对象。</p>
    <p id="demo"></p>
    <script>
      var carName = "Volvo";
      // 可以使用 window.carName 访问变量
      document.getElementById("demo").innerHTML =
        "I can display " + window.carName;
    </script>
  </body>
</html>
```

使用 let 关键字声明的全局作用域变量不属于 window 对象: 不能使用 window.name

- 3. 重置变量  
     使用 var 关键字声明的变量在任何地方都可以修改：

```javascript
var x = 2;
// x 为 2
var x = 3;
// 现在 x 为 3
```

在相同的作用域或块级作用域中，不能使用 let 关键字来重置 var 关键字声明的变量:

```javascript
var x = 2; // 合法
let x = 3; // 不合法
{
  var x = 4; // 合法
  let x = 5; // 不合法
}
```

在相同的作用域或块级作用域中，不能使用 let 关键字来重置 let 关键字声明的变量:

```javascript
let x = 2; // 合法
let x = 3; // 不合法
{
  let x = 4; // 合法
  let x = 5; // 不合法
}
```

在相同的作用域或块级作用域中，不能使用 var 关键字来重置 let 关键字声明的变量;  
let 关键字在不同作用域，或不同块级作用域中是可以重新声明赋值的;

- 4. 变量提升  
     JavaScript 中，var 关键字定义的变量可以在使用后声明，也就是变量可以先使用再声明。  
     let 关键字定义的变量则不可以在使用后声明，也就是变量需要先声明再使用。

- 5.  const 关键字  
      const 用于声明一个或多个常量，声明时必须进行初始化，且初始化后值不可再修改。

      * const定义常量与使用let 定义的变量相似：
          > * 二者都是块级作用域
          > * 都不能和它所在作用域内的其他变量或函数拥有相同的名称
      * 两者还有以下两点区别：
          > * const声明的常量必须初始化，而let声明的变量不用
          > * const 定义常量的值不能通过再赋值修改，也不能再次声明。而 let 定义的变量值可以修改。

**_PS:_** 在 JS 中 const **并非真正的常量**  
const 的本质: const 定义的变量并非常量，并非不可变，它定义了一个常量引用一个值。使用 const 定义的对象或者数组，其实是可变的。  
**实例:**

```javascript
// 创建常量对象
const car = {type:"Fiat", model:"500", color:"white"};
// 修改属性:
car.color = "red";
// 添加属性
car.owner = "Johnson";
```

但是我们不能对常量对象重新赋值：

```javascript
const car = { type: "Fiat", model: "500", color: "white" };
car = { type: "Volvo", model: "EX60", color: "red" }; // 错误
```

**实例 02：** 
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
cars = ["Toyota", "Volvo", "Audi"]; // 错误
```

##### 16. JavaScript JSON

JSON 是用于存储和传输数据的格式  
JSON 通常用于服务端向网页传递数据

###### I 什么是 JSON

JSON 英文全称 JavaScript Object Notation  
JSON 是一种轻量级的交换格式  
JSON 是独立的语言  
JSON 易于理解  
**PS:** JSON 使用 JavaScript 语法，但是 JSON 格式仅仅是一个文本。文本可以被任何编程语言读取及作为数据格式传递。

###### II JSON 格式化后为 JavaScript 对象

JSON 格式在语法上与创建 JavaScript 对象代码是相同的  
由于它们很相似，所以 JavaScript 程序可以很容易的将 JSON 数据转换为 JavaScript 对象。

##### III JSON 语法规则

- 数据为 键/值 对
- 数据由逗号分隔
- 大括号保存对象 {包含多个键/值 对}
- 方括号保存数组[PS：数组中也可以存在{对象}]

##### IV JSON 字符串转换成 JavaScript 对象

通常我们在服务器上读取 JSON 数据，然后显示在网页上。  
首先，创建 JavaScript 字符串，字符串为 JSON 格式的数据：
然后，使用 JavaScript 内置函数 JSON.parse() 将字符串转换为 JavaScript 对象:

```javascript
var text =
  '{ "sites" : [' +
  '{ "name":"Runoob" , "url":"www.runoob.com" },' +
  '{ "name":"Google" , "url":"www.google.com" },' +
  '{ "name":"Taobao" , "url":"www.taobao.com" } ]}';
var obj = JSON.parse(text);
```

**PS:相关函数**  
|函数|描述|
|:---|:---|
|JSON.parse()|用于将一个 JSON 字符串转换为 JavaScript 对象|
|JSON.stringify()|用于将 JavaScript 值转换成 JSON 字符串|

#### 17. JavaScript void

###### I javascript:void(0)

我们经常使用得到 javascript:void(0) 这样的代码，那么在 JavaScript 中 javascript:void(0) 代表什么意思呢？  
javascript:void(0) 中最关键的是 void 关键字，void 是 JavaScript 中非常重要的关键字，该操作符指定要计算一个表达式但是不返回值。  
语法格式如下：

```javascript
void func();
javascript: void func();
// 或者：
void func();
javascript: void func();
```

- 下面的代码创建了一个超级链接，当用户点击以后不会发生任何事。

```html
<a href="javascript:void(0)">单击此处什么也不会发生</a>
<!-- 当用户链接时，void(0) 计算为 0，但 Javascript 上没有任何效果。 -->
```

- 以下实例中，在用户点击链接后显示警告信息：

```html
<p>点击以下链接查看结果：</p>
<a href="javascript:void(alert('Warning!!!'))">点我!</a>
<!-- void()仅仅是代表不返回任何值，但是括号内的表达式还是要运行 -->
```

- 以下实例中，参数 a 将返回 undefined :

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>菜鸟教程(runoob.com)</title>
    <script type="text/javascript">
      function getValue() {
        var a, b, c;
        a = void ((b = 5), (c = 7));
        document.write("a = " + a + " b = " + b + " c = " + c);
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

###### II href="#" 和 href = "javascript:void(0)" 的区别

\# 包含一个位置信息，默认的锚点 \#top 也就是网页的上端。  
而 javascript:void(0)，仅表示一个死链接。  
在页面很长的时候会使用 \# 来定位页面的具体位置，格式为：\# + id。  
如果你要定义一个死链接请使用 javascript:void(0)  
**实例：**
```html
<a href="javascript:void(0);">点我没有反应的!</a>
<a href="#pos">点我定位到指定位置!</a>
<br />
...
<br />
<p id="pos">尾部定位点</p>
```

##### 18. JavaScript 异步编程
可以用于 JavaScript 异步模式的编程的方式：  
1. 回调函数 setTimeout
2. 事件监听
3. 发布 publish / 订阅 subscribe
4. Promise 对象
###### I 异步编程 Asynchronous, async 与 同步编程 Synchronous, sync

###### II 什么时候使用异步编程

在前端编程中（甚至后端有时也是这样），我们在处理一些简短、快速的操作时，例如计算 1 + 1 的结果，往往在主线程中就可以完成。主线程作为一个线程，不能够同时接受多方面的请求。所以，当一个事件没有结束时，界面将无法处理其他请求。  
现在有一个按钮，如果我们设置它的 onclick 事件为一个死循环，那么当这个按钮按下，整个网页将失去响应。  
为了避免这种情况的发生，我们常常用子线程来完成一些可能消耗时间足够长以至于被用户察觉的事情，比如读取一个大文件或者发出一个网络请求。因为子线程独立于主线程，所以即使出现阻塞也不会影响主线程的运行。  
但是子线程有一个局限：一旦发射了以后就会与主线程失去同步，我们无法确定它的结束，如果结束之后需要处理一些事情，比如处理来自服务器的信息，我们是无法将它合并到主线程中去的。  
为了解决这个问题，JavaScript 中的异步操作函数往往通过回调函数来实现异步任务的结果处理。

##### III 回调函数

回调函数就是一个函数，它是在我们启动一个异步任务的时候就告诉它：等你完成了这个任务之后要干什么。这样一来主线程几乎不用关心异步任务的状态了，他自己会善始善终。  
**实例 1：**
这段程序中的 setTimeout 就是一个消耗时间较长（3 秒）的过程，它的第一个参数是个回调函数，第二个参数是毫秒数，这个函数执行之后会产生一个子线程，子线程会等待 3 秒，然后执行回调函数 "print"，在命令行输出 "RUNOOB!"。

```javascript
setTimeout(function () {
  document.getElementById("demo").innerHTML = "RUNOOB!";
}, 3000);
```

**实例 2：** 
既然 setTimeout 会在子线程中等待 3 秒，在 setTimeout 函数执行之后主线程并没有停止

```javascript
setTimeout(function () {
  console.log("1");
}, 3000);
console.log("2");
// 执行结果是：
//  2
//  1
```

###### IV 异步 AJAX

除了 setTimeout 函数以外，异步回调广泛应用于 AJAX 编程。  
有关于 AJAX 详细请参见：https://www.runoob.com/ajax/ajax-tutorial.html

##### 19. JavaScript Promise

Promise 是一个 ECMAScript6 提供的 **类**，目的是更加优雅的书写复杂的异步任务。

###### I 创建 Promise

**语法：**
```javascript
new Promise(function (resolve, reject) {
  // 函数体
});
```

* 应用：
  我们之前遇到的异步任务都是一次异步，如果需要多次调用异步函数呢？  
  例如，如果我想分三次输出字符串，第一次间隔 1 秒，第二次间隔 4 秒，第三次间隔 3 秒：  
  使用 setTimeout

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
new Promise(function (resolve, reject) {
  setTimeout(function () {
    console.log("1");
    resolve();
  }, 1000);
})
  .then(function () {
    return new Promise(function (resolve, reject) {
      setTimeout(function () {
        console.log("2");
        resolve();
      }, 4000);
    });
  })
  .then(function () {
    setTimeout(function () {
      console.log("3");
    }, 3000);
  });
// 执行结果： 1 2 3
```

```javascript
new Promise(function (resolve, reject) {
  setTimeout(function () {
    console.log("1");
    resolve();
  }, 1000);
})
  .then(function () {
    setTimeout(function () {
      console.log("2");
      resolve();
    }, 4000);
  })
  .then(function () {
    setTimeout(function () {
      console.log("3");
    }, 3000);
  });
// 执行结果： 1 3 2
// 这里，第二次没有返回一个新的Promise，所以第三层还是依赖于第一层的，所以3s后执行，比第二层4s快。
```
**Promise 将嵌套格式的代码变成了顺序格式的代码。**

###### II Promise 使用
Promise 构造函数只有一个参数，是一个函数，这个函数在构造之后会直接被异步运行，所以我们称之为起始函数。  
起始函数包含两个参数 resolve 和 reject。  
resolve 和 reject 都是函数，其中调用 resolve 代表一切正常，reject 是出现异常时所调用的。  
**实例 01**
```javascript
new Promise(function (resolve, reject) {
  var a = 0;
  var b = 1;
  if (b == 0) reject("Divide zero!");
  else resolve(a / b);
})
  .then(function (value) {
    console.log("a / b = " + value);
  })
  .catch(function (err) {
    console.log("错误：" + err);
  })
  .finally(function () {
    console.log("END");
  });
// 执行结果：a / b = 0
//          End
```

**说明 01：** 
Promise 类有.then(),.catch(),.finally() 三个方法，这三个方法的参数都是一个函数。  
.then() 可以将参数中的函数添加到当前 Promise 的正常执行序列，.catch() 则是设定 Promise 的异常处理序列，.finally() 是在 Promise 执行的最后一定会执行的序列。  
.then() 传入的函数会按顺序依次执行，有任何异常都会直接跳到 catch 序列。  
**实例 02**
```javascript
new Promise(function (resolve, reject) {
  console.log(1111);
  resolve(2222); // 传给下一个then
})
  .then(function (value) {
    console.log(value);
    return 3333; // 传给下一个then，并且不会中断
  })
  .then(function (value) {
    console.log(value);
    throw "An Error"; // 抛出自定义异常
  })
  .catch(function (err) {
    console.log(err); // .catch() 捕获异常
  });
// 执行结果：
//1111
//2222
//3333
//An error
```

**说明 02**
 resolve() 中可以放置一个参数用于向下一个 then 传递一个值，then 中的函数也可以返回一个值传递给 then。  
 但是，如果 then 中返回的是一个 Promise 对象，那么下一个 then 将相当于对这个返回的 Promise 进行操作，这一点从刚才的计时器的例子中可以看出来。  
 reject() 参数中一般会传递一个异常给之后的 catch 函数用于处理异常。  
 **_注意：_**
resolve 和 reject 的作用域只有起始函数，不包括 then 以及其他序列；
resolve 和 reject 并不能够使起始函数停止运行，别忘了 return。

###### III Promise 函数
上述的 "计时器" 程序看上去比函数瀑布还要长，所以我们可以将它的核心部分写成一个 Promise 函数：
```javascript
function print(delay, message) {
  return new Promise(function (resolve, reject) {
    setTimeout(function () {
      console.log(message);
      resolve();
    }, delay);
  });
}

// 实现功能:
print(1000, "1")
  .then(function () {
    return print(4000, "2"); // 使用return，返回一个promise，所以后面的then依赖当前2的promise,在2执行4s后执行
  })
  .then(function () {
    print(3000, "3");
  });
// 结果: 1 2 3
// 如果取消return 则，2和3的then都是依赖于1的promise，所以执行结果为1 3 2
```
###### IV 其他 Promise 方法  
* Promise.all() 方法用于将多个 Promise 实例，包装成一个新的 Promise 实例。  
```javascript
var p = Promise.all([p1,p2,p3]);
```
Promise.all 方法的参数不一定是数组，但是必须具有 iterator 接口，且返回的每个成员都是 Promise 实例。  
> p 的状态由 p1、p2、p3 决定，分成两种情况。
> * 只有p1、p2、p3的状态都变成fulfilled，p的状态才会变成fulfilled，此时p1、p2、p3的返回值组成一个数组，传递给p的回调函数。
> * 只要p1、p2、p3之中有一个被rejected，p的状态就变成rejected，此时第一个被reject的实例的返回值，会传递给p的回调函数。

* Promise.race() 方法同样是将多个 Promise 实例，包装成一个新的 Promise 实例。

###### IV 异步函数

异步函数 (async function) 是 ECMAScript 2017 (ECMA-262) 标准的规范，几乎被所有浏览器所支持，除了 Internet Explorer。  
我们可以使用异步函数，使上面使用 Promise 函数写的解决方案更简洁：

```javascript
async function asyncFun() {
  await print(1000, "1");
  await print(4000, "2");
  await print(3000, "3");
}
asyncFun();
```

_PS:异步函数 async function 中可以使用 await 指令，await 指令后必须跟着一个 Promise，异步函数会在这个 Promise 运行中暂停，直到其运行结束再继续运行。
异步函数实际上原理与 Promise 原生 API 的机制是一模一样的，只不过更便于程序员阅读。_  
处理异常的机制将用 try-catch 块实现：

```javascript
async function asyncFunc() {
  try {
    await new Promise(function (resolve, reject) {
      throw "Some error"; // 或者 reject("Some error")
    });
  } catch (err) {
    console.log(err); // 会输出 Some error
  }
}
asyncFunc();
```

如果 Promise 有一个正常的返回值，await 语句也会返回它：

```javascript
async function asyncFunc() {
  let value = await new Promise(function (resolve, reject) {
    resolve("Return value");
  });
  console.log(value);
}
asyncFunc(); // 输出： Return value
```

###### V Promise 对象

- Promise 对象有以下两个特点:

  1. 对象的状态不受外界影响。Promise 对象代表一个异步操作，有三种状态：
     * pending：初始状态，不是成功或失败的状态  
     * fulfilled: 操作成功完成，resolved  
      * rejected：操作失败  
     只有异步操作的结果，可以决定当前是哪一种状态，其他操作都无法改变这个状态。
  2. 一旦状态改变，就不会再变，任何时候都能得到这个结果。  
      Promise 对象的状态改变，只有两种可能：
      从 pending -> fulfilled（即，resolved）
      从 pending -> rejected  
     只要这两种情况发生，状态就凝固了，不会再变了，会一直保持这个结果。就算改变已经发生了，你再对 Promise 对象添加回调函数，也会立即得到这个结果。这与事件（Event）完全不同，事件的特点是，如果你错过了它，再去监听，是得不到结果的。

- Promise 优缺点:  
  有了 Promise 对象，就可以将异步操作以同步操作的流程表达出来，避免了层层嵌套的回调函数。此外，Promise 对象提供统一的接口，使得控制异步操作更加容易。  
  Promise 也有一些缺点。首先，无法取消 Promise，一旦新建它就会立即执行，无法中途取消。其次，如果不设置回调函数，Promise 内部抛出的错误，不会反应到外部。第三，当处于 Pending 状态时，无法得知目前进展到哪一个阶段（刚刚开始还是即将完成）。

##### 20. 正则表达式 Regular Expression

正则表达式 Regular Expression（在代码中常用简写，regex，regexp 或 RE）使用单个字符串来描述、匹配一系列符合某个语法规则的字符串搜索模式。  
搜索模式可以用文本搜索和文本替换。

###### I 什么是正则表达式？

正则表达式是由一个字符序列形成的搜索模式。  
当你在文本中搜索数据时，你可以用搜索模式来描述你要查询的内容。  
正则表达式可以是一个简单的字符，或一个更复杂的模式。  
正则表达式可用于所有文本搜索和文本替换的操作。

###### II 语法

/正则表达式主体/修饰符(可选)  
主体： \^[1-9]+abc\$
        \^ 匹配输入字符串的开头
        [1-9]+ 匹配1次或多次数字，[1-9]1-9的单个数字，+匹配一次或多次
        abc\$ 匹配以字母 abc 并以 abc 结尾，\$匹配输入字符串结尾位置。
_实例：_

```javascript
var patt = /food/i;
// /food/i 是一个正则表达式
// food 是主体，用于检索
// i 是修饰符，表示不区分大小写
```

###### III 使用字符串方法

在 JavaScript 中，正则表达式通常用两个字符串方法 search() 和 replace()。

- search() 方法用于检索字符串中指定的字符串，或检索与正则表达式相匹配的子字符串，并返回子串的起始位置，如果不存在，返回-1。
- replace() 方法用于在字符串中用一些字符串替换另一些字符串，或替换一个与正则表达式匹配的子串，并返回替换后的字符串。  
  _实例：_

```javascript
// 使用正则表达式搜索 "Runoob" 字符串，且不区分大小写：
var str = "Visit Runoob!";
var n = str.search(/Runoob/i);
console.log(n); // 6
// search 方法可使用字符串作为参数。字符串参数会转换为正则表达式:
var str = "Visit Runoob!";
var n = str.search("Runoob");
console.log(n); // 6

// 使用正则表达式且不区分大小写将字符串中的 Microsoft 替换为 Runoob :
var str = "Visit Microsoft!";
var n = str.replace(/microsoft/i, "Runoob");
console.log(n); // Visit Runoob!
// replace() 方法将接收字符串作为参数：
var str = "Visit Microsoft!";
var n = str.replace("Microsoft", "Runoob");
console.log(n); // Visit Runoob!
```

###### IV 正则表达式修饰符

| 修饰符 | 描述                                                     |
| :----- | :------------------------------------------------------- |
| i      | 执行对大小写不敏感的匹配                                 |
| g      | 执行全局匹配（查找所有匹配而非在找到第一个匹配后停止）。字符串的match()方法 |
| m      | 执行多行匹配                                             |

###### V 正则表达式模式

- 方括号用于查找某个范围内的字符  
   |表达式|描述|
  |:---|:---|
  |[abc...]|查找方括号之间的任一字符|
  |[^abc]|匹配非[]中字符的所有字符|
  |[0-9]|查找任一 0-9 的数字|
  |(x\|y)|查找任何以\|分隔的选项|
- 元字符是拥有特殊含义的字符  
  |元字符|描述|
  |:---|:---|
  |\d|查找数字|
  |\s|查找空白字符|
  |\b|匹配单词边界|
  |\uxxxx|查找以十六进制 xxxx 规定的 Unicode 字符|
- 量词  
   |量词|描述|
  |:---|:---|
  |n+|匹配任何包含至少一个 n 的字符|
  |n\*|匹配任何包含 0 个或多个 n 的字符串|
  |n?|匹配任何包含 0 个或一个 n 的字符串|
- 通配符
  |通配符|描述|
  |:---|:---|

###### VI 使用 RegExp 对象

在 JavaScript 中，RegExp 对象是一个预定义了属性和方法的正则表达式对象。  
手册地址：https://www.runoob.com/jsref/jsref-obj-regexp.html

###### VII 使用 test()

test() 方法是一个正则表达式方法。  
test() 方法用于匹配一个正则表达式是否匹配某个模式，如果字符串中含有匹配的文本，则返回 true，反之返回 false。  
_实例：_

```javascript
// 以下实例用于搜索字符串中的字符 "e"：
var patt = /e/;
console.log(patt.test("The best things in life are free!")); // true

// 你可以不用设置正则表达式的变量，以上两行代码可以合并为一行：
/e/.test("The best things in life are free!");
```

###### VIII 使用 exec()

exec() 方法是一个正则表达式方法。  
exec() 方法用于检索字符串中的正则表达式的匹配。  
该函数返回一个数组，其中存放匹配的结果。如果未找到匹配，则返回值为 null。  
**实例：**
```javascript
console.log(/e/.exec("The best things in life are free!")[0]); // e
console.log(/e/.exec("The best things in life are free!").input); // The best things in life are free!
// 输出
```

**实例 01：**
```javascript
// 判断输入是否为数字、字母、下划线组成
var pattern = /^\w+$/;
var str = "1234abd__";
var str2 = "$32343#"
console.log(pattern.test(str));

// 判断输入字符串是否为全部都是字母
/^[a-zA-Z]+$/
// 判断输入字符串是否为全部都是数字
/^\d+$/
```

**实例 02：** 正则表达式常用实例
```javascript
// 是否带有小数
var regex01 = /^\d+\.\d+$/;

// 是否中文名称组成  2-4位中文
var regex02 = /^[\u4E00-\u9FA5]{2,4}$/;

// 校验是否全由8位数字组成
var regex03 = /^[0-9]{8}$/;

// 电话
var regex04 = /^((0\d{2,3}-\d{7,8})|(1[3584]\d{9}))$/;

// 邮箱
var regex05 = /^\w+@[a-zA-Z0-9]{2,10}(?:\.[a-z]{2,4}){1,3}$/;
```

###### IX 使用 字符串方法 match() 匹配正则表达式
match() 方法，可以匹配一个正则表达式，并返回一个数组。没有匹配到结果，返回 null
**实例 01：**
```javascript
var str = "google runoob taobao";
var patt = /[abc]/g;
str.match(patt);
// 结果：  [ "b",  "a", "b",  "a"]
```

- 常用字符  
   |字符|描述|
  |:---|:---|
  |[ABC]|匹配 [...] 中的所有字符，例如 [aeiou] 匹配字符串 "google runoob taobao" 中所有的 e o u a 字母。|
  |[^abc]|匹配除了 [...] 中字符的所有字符|
  |[A-Z]|[A-Z] 表示一个区间，匹配所有大写字母，[a-z] 表示所有小写字母。|
  |.|匹配除换行符（\n、\r）之外的任何单个字符，相等于 [^\n\r]|
  |[\s\S]|匹配所有。 说明：\s 是匹配所有空白符，包括换行。\S 非空白符，不包括换行。|
  |\w|匹配字母、数字、下划线。等价于[A-Za-z0-9_]|

- 特殊字符  
  所谓特殊字符，就是一些有特殊含义的字符。如果要匹配这些特殊字符，需要对这些字符进行转义\。  
  下表列出了正则表达式中的特殊字符：
  |特殊字符|描述|
  |:---|:---|
  |$|匹配输入字符串的结尾位置。要匹配 $ 字符本身，请转义。|
  |()|标记一个子表达式的开始和结束位置。子表达式可以获取供以后使用。|
  |\*|匹配一个子表达式 0 次或多次。|
  |+|匹配一个子表达式1次或多次|
  |[|标记一个中括号表达式的开始|
  |?|匹配一个子表达式 0 次或 1 次，或指明一个非贪婪限定符|
  |\\|转义字符|
  |{|标记限定符表达式的开始（限定符看下一张表格）|
  |\||指明两项之间的一个选择|
- 限定符  
  限定字符用来指定正则表达式的一个给定组件必须要出现多少次才能满足匹配要求。有* + ? {n} {n,} {n,m}六种
  |特殊字符|描述|
  |:---|:---|
  |*|匹配前面的子表达式 **0 次或多次**|
  |+|匹配前面的子表达式 **1 次或多次** |
  |?|匹配前面的子表达式 **0 次或 1 次** 。例如，"do(es)?" 可以匹配 "do" 、 "does" 中的 "does" 、 "doxy" 中的 "do" 。 等价于 {0,1}。|
  |{n}|n 是一个非负整数。匹配确定的 n 次。例如，'o{2}' 不能匹配 "Bob" 中的 'o'，但是能匹配 "food" 中的两个 o。|
  |{n,}|n 是一个非负整数。 **至少** 匹配 n 次。|
  |{n,m}|m 和 n 均为非负整数，其中 n <= m。最少匹配 n 次且最多匹配 m 次。|

**PS01:** * 和 + 都是贪婪的，因为它们会尽可能多的匹配文字，只有在它们的后面加上?就可以实现非贪婪或最小匹配。  
**实例：**

```javascript
// 例如，您可能搜索 HTML 文档，以查找在 h1 标签内的内容。
var str = "<h1>RUNOOB-菜鸟教程</h1>";
str.match(/^<.*?>$/); //  <h1>
// . 匹配非\n\r

var str = "<h1>RUNOOB-菜鸟教程</h1>";
str.match(/^<.*>$/); //  <h1>RUNOOB-菜鸟教程</h1>
```

* 定位符  
  定位符 能够将正则表达式固定到行首或行尾。
  使用定位符，能够创建这样的正则表达式，这些正则表达式出现在一个单词内、在一个单词的开头或者一个单词的结尾。  
  定位符用来描述字符串或单词的边界，^ 和 $ 定位符分别指字符串的开始与结束。 \b 描述单词的前或后边界。\B 表示非单词边界。  
  **PS01:** 不能将限定符与定位符一起使用。
  由于在紧靠换行或者单词边界的前面或后面不能有一个以上位置，因此不允许诸如 \^ 之类的表达式。  

  **PS02:** 若要匹配一行文本开始处的文本，请在正则表达式的开始使用 ^ 字符。不要将 ^ 的这种用法与中括号表达式内的用法混淆。

  **PS03:** 若要匹配一行文本的结束处的文本，请在正则表达式的结束处使用 $ 字符。  
  **实例:**

```javascript
// 真正的章节标题不仅出现行的开始处，而且它还是该行中仅有的文本。它既出现在行首又出现在同一行的结尾。
var patt = /^Chapter [1-9][0-9]{0,1}$/;
```

    PS 单词边界是单词和空格之间的位置。非单词边界是任何其他位置。

##### 21 JavaScript 代码规范

---

### 二、 JS 函数  2022.0330

#### I JavaScript 函数定义
JavaScript 使用 function 关键字定义函数  
函数可以通过声明定义，也可以是一个表达式。 

---
##### 1. 函数声明  
```javascript 
function myFunction(a, b) {
    return a * b;
}
```

##### 2. 函数表达式  
JavaScript 函数可以通过一个表达式定义。  
函数表达式可以存储在变量中：  
```javascript
var x = function (a, b) {return a * b};  
// 在函数表达式存储在变量后，变量也可作为一个函数使用：  
var z = x(4, 3);
console.log(z); // 12
```
***PS：*** 以上函数实际上是一个 匿名函数 (函数没有名称)。  
函数存储在变量中，不需要函数名称，通常通过变量名来调用。  
***PS02：*** 上述函数以分号结尾，因为它是一个执行语句。  

##### 3. Function() 构造函数  
JavaScript 函数同样可以通过内置的函数构造器(Function())定义。  
*实例：*  
```JavaScript
var myFunction = new Function("a","b","return a*b");
var z = myFunction(4,3);

// 或则不适用构造函数，	在 JavaScript 中，很多时候，你需要避免使用 new 关键字。  
```

##### 4. 函数提升 Hoisting  
提升（Hoisting）是 JavaScript 默认将当前作用域提升到前面去的行为。  
提升（Hoisting）应用在变量的声明与函数的声明。  
***PS:*** 使用表达式定义函数时无法提升。  

##### 5. 自调用函数  (function(){}) 和 (function(){})()
函数表达式可以'自调用'。  
自调用表达式会自动调用。  
如果表达式后面紧跟()，则会自动调用。  
不能自调用声明的函数。  
***实例：***  
```JavaScript  
(function(){console.log("test")})  // 实际是， 匿名自我调用的函数 (没有函数名)。
// ƒ (){console.log("test!")}

(function(){console.log("test")})();
// test

```
##### 6. 函数是对象  
在 JavaScript 中使用typeof 操作符判断函数类型，返回 "function"  
但是JavaScript 函数描述为一个对象更加准确。  
JavaScript 函数有 属性 和 方法。  
* arguments.length 属性返回函数调用过程接收到的参数个数  
* toString() 方法将函数作为一个字符串返回:
```javascript
function myFunction(a, b) {
    return arguments.length;
}
myFunction(4,3); // 2

function myFunction(a, b) {
    return arguments.length;
}
var txt = myFunction.toString();
console.log(txt); // function myFunction(a, b) { return arguments.length; }
```

##### 7. 箭头函数  
ES6 新增了箭头函数。  
箭头函数表达式的语法比普通函数表达式更简洁。  
**语法：** 
> 1. (参数1, 参数2, …, 参数N) => { 函数声明 }  
> 2. (参数1, 参数2, …, 参数N) => 表达式(单一)   
>     // 相当于：(参数1, 参数2, …, 参数N) =>{ return 表达式; }  
> 3. 当只有一个参数时，圆括号是可选的  
>     (单一参数) => {函数声明}  或  
>     单一参数 => {函数声明}  
> 4. 没有参数的函数应该写成一对圆括号  
>     () => {函数声明}  

**实例：** 
```javascript
// ES5  
var x = function(a,b) {return a * b;};

//ES6
var x = (a,b) => a * b; // 或  
var x1 = (a,b) => { return a * b; }
```
* 有的箭头函数都没有自己的 this。 不适合定义一个对象的方法。  
* 当我们使用箭头函数时，箭头函数会默认绑定外层的this 的值，所以在**箭头函数中 this 的值和外层的 this 是一样的** 。
* 箭头函数 是不能提升的，需要在使用之前定义。  
* 使用 const 比 var 安全，因为表达式始终是一个常量。  
* 如果函数部分只有一个语句，则可以省去 return 关键字和 大括号{} 。  
```javascript
// ES6 之前，JavaScript 的 this 对象一直很令人头大，回调函数，经常看到 var self = this 这样的代码，为了将外部 this 传递到回调函数中，那么有了箭头函数，就不需要这样做了，直接使用 this 就行。
var Person = {
    'age': 18,
    'sayHello': function () {
      setTimeout(function () {
        console.log(this.age); // this -> window
      });
    }
};
var age = 20;
Person.sayHello();  // 20
 
var Person1 = {
    'age': 18,
    'sayHello': function () {
      setTimeout(()=>{
        console.log(this.age); // this -> Person1
      });
    }
};
var age = 20;
Person1.sayHello();  // 18
```


#### II JavaScript 函数参数  
JavaScript 函数对参数的值没有进行任何的检查。  
###### 1. 函数显式参数(Parameters) 和 隐式参数(Arguments)  
* 函数显式参数 在函数定义是列出  
* 函数隐式参数 在函数调用时传递给函数真正的值  

###### 2. 参数规则  
JavaScript 函数定义显式参数时没有指定数据类型。  
JavaScript 函数对隐式参数没有进行类型检测。  
JavaScript 函数对隐式参数的个数没有进行检测。  

###### 3. 默认参数  
* ES5 中如果函数在调用时未提供隐式参数，参数会默认设置为： undefined  
有时这是可以接受的，但是建议最好为参数设置一个默认值：  
```javascript
function myFunction(x, y) {
    if (y === undefined) {
          y = 0;
    } 
}
// 或  
function myFunction(x, y) {
    y = y || 0; // 	如果y已经定义 ， y || 返回 y, 因为 y 是 true, 否则返回 0, 因为 undefined 为 false。
}
// 如果函数调用时设置了过多的参数，参数将无法被引用，因为无法找到对应的参数名。 只能使用 arguments 对象来调用。
```
* ES6 函数可以自带参数  
ES6 支持函数带有默认参数，就判断 undefined 和 || 的操作:  
```javascript 
function myFunction(x, y = 10) {
    // y is 10 if not passed or undefined
    return x + y;
}
myFunction(0, 2) // 输出 2
myFunction(5); // 输出 15, y 参数的默认值
```
* arguments 对象  
JavaScript 函数有个内置的对象 arguments 对象。arguments 对象包含了函数调用的参数数组。  
通过这种方式你可以很方便的找到最大的一个参数的值：  
```javascript
x = findMax(1, 123, 500, 115, 44, 88);
function findMax() {
    let i, max = arguments[0];
    
    if(arguments.length < 2) return max;
 
    for (i = 1; i < arguments.length; i++) {
        if (arguments[i] > max) {
            max = arguments[i];
        }
    }
    return max;
}

// 或者创建一个函数用来统计所有数值的和  

x = sumAll(1, 123, 500, 115, 44, 88);
function sumAll() {
    let i, sum = 0;
    for (i = 0; i < arguments.length; i++) {
        sum += arguments[i];
    }
    return sum;
}

```

###### 4. 参数传递  
* 通过值传递参数：  
    在函数中调用的参数是函数的隐式参数。  
    JavaScript 隐式参数通过值来传递：函数仅仅只是获取值。  
    如果函数修改参数的值，不会修改显式参数的初始值（在函数外定义）。  
    隐式参数的改变在函数外是不可见的。  
* 通过对象传递参数：  
    在JavaScript中，可以引用对象的值。因此我们在函数内部修改对象的属性就会修改其初始的值。  
    修改对象属性可作用于函数外部（全局变量）。  
    修改对象属性在函数外是可见的。  

#### III JavaScript 函数调用  
JavaScript 函数有4种调用方式。  
每种方式的不同在 this 的初始化。  

* this 关键字  
一般而言，this 指向函数执行时的当前对象。  

###### 1. 调用 JavaScript 函数  
* 1. 作为一个函数调用 
  ```javascript
  function myFunction(a, b) {
    return a * b;
  }
  myFunction(10, 2);           // myFunction(10, 2) 返回 20
  ```
  以上函数不属于任何对象。但是在 JavaScript 中它始终处于默认的全局对象。  
  在 HTML 中默认的全局对象是 HTML 页面本身，所以函数是属于 HTML 页面。  
  在浏览器中的页面对象是浏览器窗口(window 对象)。以上函数会自动变为 window 对象的函数。  
  所以，myFunction() 和 window.myFunction() 是一样的：
  ```javascript
  function myFunction(a, b) {
    return a * b;
  }
  window.myFunction(10, 2);           // myFunction(10, 2) 返回 20
  ```
  ***PS:这是调用 JavaScript 函数常用的方法， 但不是良好的编程习惯全局变量，方法或函数容易造成命名冲突的bug。***  

* 2. 全局对象  
  当函数没有被自身的对象调用时， this 的值就会变成全局对象。  
  在web浏览器中，全局对象就是 window 对象。  
  函数作为全局对象调用，会使 this 的值成为全局对象。使用 window 对象作为一个变量容易造成程序崩溃。  

* 3. 函数作为方法调用（即将函数定义为对象的方法）  
  在 JavaScript 中你可以将函数定义为对象的方法。  
  **实例：**
  以下实例创建了一个对象 (myObject), 对象有两个属性 (firstName 和 lastName), 及一个方法 (fullName):
  ```javascript
  var myObject = {
    firstName: "John",
    lastName: "Doe",
    fullName: function() {
      return this.firstName + " " + this.lastName;
    }
  }
  myObject.fullName(); // John Doe
  ```
  fullName 方法是一个函数。函数属于对象。 myObject 是函数的所有者。  
  this对象，拥有 JavaScript 代码。实例中 this 的值为 myObject 对象。

* 4. 使用构造函数调用函数  
  如果函数调用前使用了 new 关键字，则是调用了构造函数。  
  这看起来就像创建了新的函数，但实际上 JavaScript 函数是重新创建的对象：  
  ```javascript
  function myFunction(arg1, arg2) {
      this.firstName = arg1;
      this.lastName = arg2;
  }
  // 创建对象  
  var x = new myFunction("John","Doe");
  console.log(x.firstName); // John
  ```
  构造函数的调用会创建一个新的对象。新对象会继承构造函数的属性和方法。  
  构造函数中 this 关键字没有任何的值。this 的值在函数调用实例化对象(new object)时创建。  

* 5. 作为函数方法调用函数  
  在 JavaScript 中函数是对象，JavaScript 函数有它的属性和方法。  
  call() 和 apply() 是预定义的函数方法。两个方法可以调用函数，两个方法的第一个参数必须是对象本身。  
```javascript
function myFunction(a,b) {return a * b;}  
myObject = myFunction.call(myObject,10,2); // 20

myArray = [10,2];
myObject2 = myFunction.apply(myObject2,myArray); // 20
```
***PS:*** 两个方法都使用了对象本身作为第一个参数。 两者的区别在于第二个参数：  
> * apply传入的是一个参数数组，也就是将多个参数组合成为一个数组传入，而call则作为call的参数传入（从第二个参数开始）。  
> * 在 JavaScript 严格模式("use strict")下，在调用函数时第一个参数会会成为 this 的值，即使该参数不是一个对象。  
> * 在 JavaScript 非严格模式下，如果第一个参数的值是null 或 undefined，它将使用全局对象替代。  
> * 通过 call() 或 apply() 方法你可以设置 this 的值, 且作为已存在对象的新方法调用。  

**实例：**  
```javascript
// 在 JavaScript 严格模式("use strict")下，在调用函数时第一个参数会会成为 this 的值，即使该参数不是一个对象。  
var value = "我在这里!";
var obj = {
  fun : function() { console.log(this); }
}
obj.fun.call(value); // 我在这里!

```

#### IV  JavaScript 闭包  
JavaScript 变量可是 局部变量 或 全局变量。  
私有变量可以用到闭包。  

###### 1. 全局变量  
函数可以访问由函数内部定义的变量，如：  
```javascript
function myFunction() {
    var a = 4;
    return a * a;
}
```
函数也可以访问函数外部定义的变量。如：  
```javascript
var a = 4;
function myFunction() {
    return a * a;
}
```

后面一个实例中， a 是一个 全局 变量。在web页面中全局变量属于 window 对象。全局变量可应用于页面上的所有脚本。  
在第一个实例中， a 是一个 局部 变量。局部变量只能用于定义它函数内部。对于其他的函数或脚本代码是不可用的。  
全局和局部变量即便名称相同，它们也是两个不同的变量。修改其中一个，不会影响另一个的值。  
***PS:*** 变量声明时如果不使用 var 关键字，那么它就是一个全局变量，即使在函数中声明。  

###### 2. 变量生命周期  
全局变量的作用域是全局性的，即在整个JavaScript程序中，全局变量处处都在。  
而在函数内部声明的变量，只在函数内部起作用。这些变量是局部变量，作用域是局部性的；函数的参数也是局部性的，只在函数内部起作用。  

### 3. 计数器困境  
设想下如果你想统计一些数值，且该计数器在所有函数中都是可用的。  
你可以使用全局变量，函数设置计数器递增：  
```javascript
var counter = 0; // 计数器
function add() {
   return counter += 1;
}
add();
add();
add();  // 计数器现在为 3
```
计数器数值在执行 add() 函数时发生变化。  
但问题来了，页面上的任何脚本都能改变计数器，即便没有调用 add() 函数。  
如果我在函数内声明计数器，如果没有调用函数将无法修改计数器的值：  
```javascript
function add() {
    var counter = 0;
    return counter += 1;
}
add();
add();
add();
// 本意是想输出 3, 但事与愿违，输出的都是 1 !
```
以上代码将无法正确输出，每次我调用 add() 函数，计数器都会设置为 1。  
***JavaScript 内嵌函数可以解决该问题。*** 

###### 4. JavaScript 内嵌函数  
所有的函数都能访问全局变量。  
实际上，在 JavaScript 中所有的函数都能访问它们上一层的作用域。  
JavaScript 支持嵌套函数。 嵌套函数可以访问上一层的函数变量。  
***实例***
该实例中，内嵌函数 plus() 可以访问父函数的 counter 变量：  
```javascript
function add() {
  var counter = 0;
  function plus() { counter += 1;}
  plus();
  return counter;
}
```
如果我们能在外部访问 plus() 函数，这样就能解决计数器的困境。  
我们同样需要确保 counter = 0 只执行一次。  
***我们需要闭包.***  

###### 5. JavaScript 闭包  
还记得函数自我调用吗？该函数会做什么？  
(function(){})() //返回结果
(function(){}) // 返回函数表达式
***实例：***  
```javascript
var add = (function() {
  var counter = 0;
  return function () { return counter += 1;}
})();
console.log(add); // ƒ () { return counter += 1;}
add();
add();
add(); // 计数器为3

// 可以将以上代码才分成如下实例  
function outFunction() {
  var counter = 0;
  function plus() {
    return counter += 1;
  }
  return plus; // 函数
}
var add = outFunction();   // 赋值给add 是函数plus();

```
**实例解析：**
变量add指定了函数自我调用的返回值。  
自我调用函数执行一次。设置计数器为0，并返回函数表达式。  
add变量可以作为一个函数使用。非常棒的部分是它可以访问函数上一层作用域的计数器。  
这个叫作 JavaScript 闭包。它使得函数拥有私有变量变成可能。  
计数器受匿名函数的作用域保护，只能通过 add 方法修改。  
**PS:** 闭包 是一种保护私有变量的机制，在函数执行时形成私有的作用域，保护里面的私有变量不受外界干扰。直观的说就是形成一个不销毁的栈环境。  



___
### 三、 JS 类  2022.0403
#### I JavaScript 类
**类是用于创建对象的模板**  
使用 class 关键字来创建一个类，类体在一对大括号 {} 中，我们可以在大括号 {} 中定义类成员的位置，如方法或构造函数。  
每个类中包含了一个特殊的方法 constructor()，它是类的构造函数，这种方法用于创建和初始化一个由 class 创建的对象。  
***语法：***
class ClassName {
  constructor() { ... }
}

**实例：**
```javascript
class Runoob {
  constructor(name, url) {
    this.name = name;
    this.url = url;
  }
}
// 以上实例创建了一个类，名为 "Runoob"。类中初始化了两个属性： "name" 和 "url"。

// 定义好类后，我们就可以使用 new 关键字来创建对象：创建对象时会自动调用构造函数方法 constructor()。
let site = new Runoob("菜鸟教程",  "https://www.runoob.com");
```
###### 1. 类表达式  
类表达式是定义类的另一种方式。类表达式可以命名或不命名。命名类表达式的名称是该类体的局部名称。  
```javascript
// 未命名/匿名类
let Runoob = class {
  constructor(name.url) {
    this.name = name;
    this.url = url;
  }
};
console.log(Runoob.name); // Runoob

// 命名类
let Runoob = class Runoob2 {
  constructor(name, url) {
    this.name = name;
    this.url = url;
  }
};
console.log(Runoob.name);
// 输出: "Runoob2"

```
> * 构造方法  
> 构造方法名为 constructor()。
> 构造方法在创建新对象时会自动执行。
> 构造方法用于初始化对象属性。
> 如果不定义构造方法，JavaScript 会自动添加一个空的构造方法。 

###### 2. 类的方法  
使用关键字 class 创建一个类，可以添加一个 constructor() 方法，然后添加任意数量的方法。 
**实例**
```javascript
class Runoob {
  constructor(name, year) {
    this.name = name;
    this.year = year;
  }
  age() {
    let date = new Date();
    return date.getFullYear() - this.year;
  }
}
 
let runoob = new Runoob("菜鸟教程", 2018);
document.getElementById("demo").innerHTML = "菜鸟教程 " + runoob.age() + " 岁了。";
```

###### 3. 严格模式 "use strict"  
类声明 和 类表达式的主体都执行在严格模式下。比如，构造函数，静态方法，原型方法，getter 和 setter 都在严格模式下执行。  
如果你没有遵循严格模式，则会出现错误：
***实例***
```javascript
class Runoob {
  constructor(name, year) {
    this.name = name;
    this.year = year;
  }
  age() {
    // date = new Date();  // 错误
    let date = new Date(); // 正确
    return date.getFullYear() - this.year;
  }
}
```

#### I JavaScript 继承  
JavaScript 类继承使用 extends 关键字。  
继承允许我们依据另一个类来定义一个类。  
super() 方法用于调用父类的构造函数。  
当创建一个类时，不需要重新编写新的数据成员和成员函数，只需指定新建的类继承了一个已有的类的成员即可。  
这个已有的类称为基类（父类），新建的类称为派生类（子类）。  

###### 1.  getter 和 setter 
类中可以使用 getter 和 setter 获取和设置值。 getter 和 setter 都需要在严格模式下执行。
getter 和 setter 可以使得我们对属性的操作变的很灵活。  
类中添加 getter 和 setter 使用的是 get 和 set 关键字。  
***实例：***  
```javascript
class Runoob{
  constructor(name){
    this.siteName = name;
  }
  get s_name(){
    return this.siteName;
  }
  set s_name(x){
    this.siteName = x;
  }
}

let noob = new Runoob("菜鸟教程");
console.log(noob.s_name);
```
***PS:即使 getter 是一个方法，当你想获取属性值时也不要使用括号。***  
getter / setter 方法的名称不能与属性的名称相同，在本例中属名为 siteName。  
很多开发者在属性名称前使用下划线字符 _ 将 getter/setter 与实际属性分开。_siteName
***实例***
要使用 setter，请使用与设置属性值时相同的语法，虽然 set 是一个方法，但需要不带括号：
```javascript
class Runoob {
  constructor(name) {
    this._siteName = name;
  }
  set siteName(x) {
    this._siteName = x;
  }
  get siteName() {
    return this._siteName;
  }
}
let noob = new Runoob("菜鸟教程");
noob.siteName = "RUNOOB";
console.log(noob.siteName);
```
###### 2. 提升  
函数姓名和类声明之间的一个重要区别在于，函数声明会提升，类声明不会。  

#### III JavaScript 静态方法  
静态方法是使用关键字 static 修饰的方法，又叫类方法，属于类，但不属于对象。在实例化对象之前可以通过**类名.方法名**调用静态方法。  
静态方法不能在对象上调用，只能在类中调用。  
***实例：***
```Javascript
class Runoob {
  constructor(name) {
    this.name = name;
  }
  static hello() {
    return "Hello!!";
  }
}
 
let noob = new Runoob("菜鸟教程");
 
// 可以在类中调用 'hello()' 方法
 console.log(Runoob.hello());
 
// 不能通过实例化后的对象调用静态方法
// console.log(noob.hello());
// 以上代码会报错

// 如果你想在实例化对象 noob 中使用静态方法，可以作为一个参数传递给它：
console.log(Runoob.hello(noob););
```
___


## 四、 JS HTML DOM  2022.0405  
通过 HTML DOM，可访问 JavaScript HTML 文档的所有元素。  
#### I HTML DOM(文档对象模型 Document Object Model)  
当网页被加载时，浏览器会创建页面的文档对象模型（DOM）  
**HTML DOM** 模型被构造为对象的树  
<img alt="HTML DOM 树" src="./js_images/pic_htmltree.gif">  
通过可编程的对象模型，JavaScript 获得了足够的能力来创建动态的HTML。  
* JavaScript 能够改变页面中的所有HTML元素、属性。
* JavaScript 能够改变页面中的所有CSS样式。
* JavaScript 能够对页面中的所有事件作出反应。  

###### 1. 查找 HTML 元素  
通过 JavaScript，您需要操作 HTML 元素。为了做到这件事情，您必须首先找到该元素。有三种方法来做这件事：  
 * 1. 通过id找到HTML元素.  
    > var x=document.getElementById("intro");
    > 如果找到该元素，则该方法将以对象（在 x 中）的形式返回该元素。
    > 如果未找到该元素，则 x 将包含 null。
* 2. 通过标签名找到HTML元素.
  > 本例查找 id="main" 的元素，然后查找 id="main" 元素中的所有 \<p> 元素：
  > var x=document.getElementById("main");
  > var y=x.getElementsByTagName("p");
* 3. 通过类名找到HTML元素.  
  > 通过 getElementsByClassName 函数来查找 class="intro" 的元素：
  > var x=document.getElementsByClassName("intro");

***PS:***
getElementsByTagName 和 getElementsByClassName 这两个方法查找**多个**DOM元素，返回值是HtmlCollection类型，是伪数组而不是真正的数组，不是使用数组方法。  
可以使用数组原型配合slice方法，利用call，apply，bind方法将伪数组转为真数组。  
***实例：***
```javascript
var x = document.getElementById("main");
var y = x.getElementByTagName("p");
console.log(y); // 在控制台我们可以看到原型proto为htmlcollection，是伪数组

//伪数组转为真数组方法1
console.log(Array.prototype.slice.call(y)); //在控制台我们可以看到原型proto为Array(0)，是真数组

//伪数组转为真数组方法2
console.log(Array.prototype.slice.apply(y))//在控制台我们可以看到原型proto为Array(0)，是真数组

//伪数组转为真数组方法3
console.log(Array.prototype.slice.bind(y)())//在控制台我们可以看到原型proto为Array(0)，是真数组

```

#### II HTML DOM  改变HTML  
HTML DOM 允许JavaScript 改变 HTML 元素的内容。  
###### 1. 改变 HTML 输出流  
JavaScript 能够创建动态的 HTML 内容：  
```html
<!-- 在 JavaScript 中，document.write() 可用于直接向 HTML 输出流写内容。 -->
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>

<script>
document.write(Date());
</script>

</body>
</html>
```

**PS:** 绝对不要在文档(DOM)加载完成之后使用 document.write()。这会覆盖该文档。 

###### 2. JavaScript  改变 HTML 内容  
修改 HTML 内容的最简单的方法是使用 innerHTML 属性。  
改变 HTML 元素的内容，请使用这个语法：  
> document.getElementById("id").innerHTML = ....
**实例：**
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>

<p id="p1">Hello World!</p>
<script>
document.getElementById("p1").innerHTML="新文本!";
</script>
<p>以上段落通过脚本修改文本。</p>

</body>
</html>
```

###### 3. JavaScript  改变 HTML 属性  
改变 HTML 元素的属性，请使用这个语法：  
> document.getElementById("id").attribute = ...
> attribute 是具体的属性，例如img标签的src属性alt属性

**实例：**
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>

<img id="image" src="smiley.gif" width="160" height="120">
<script>
document.getElementById("image").src="landscape.jpg";
</script>
<p>原图片为 smiley.gif,脚本将图片修改为 landscape.jpg</p>

</body>
</html>
```

###### 4. JavaScript HTML DOM - 改变CSS  
HTML DOM 允许 JavaScript 改变 HTML 元素的样式。  
改变 HTML 元素的样式，请使用这个语法：  
> document.getElementById(id).style.property = ...  
> property 为具体的样式属性 ,color,fontFamily,fontSize等

**实例**
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>
 
<p id="p1">Hello World!</p>
<p id="p2">Hello World!</p>
<script>
document.getElementById("p2").style.color="blue";
document.getElementById("p2").style.fontFamily="Arial";
document.getElementById("p2").style.fontSize="larger";
</script>
<p>以上段落通过脚本修改。</p>
 
</body>
</html>

```

#### III JavaScript HTML DOM 事件
HTML DOM 使 JavaScript 有能力对 HTML 事件做出反应。  
###### 1. 对事件做出反应  
可以在事件发生时执行 JavaScript，比如当用户在 HTML 元素上点击时。  
用户点击某个元素时执行代码，请向一个 HTML 事件属性添加 JavaScript 代码：
> onclick=JavaScript  

###### 2. HTML DOM 事件
HTML DOM 事件允许 Javascript 在HTML文档元素中注册不同事件处理程序。  
事件通常与函数结合使用，函数不会在事件发生前被执行！  

|鼠标事件|描述|  
|:---|:---|
|onclick|用户点击鼠标时|
|oncontextmenu|当用户右键打开上下文菜单时触发|
|ondblclick|当用户双击某个对象时触发|
|onmousedown|鼠标按钮被按下。|
|onmouseup|鼠标按键被松开。|
|onmouseenter|当鼠标指针移动到元素上时触发。|
|onmouseleave|当鼠标指针移出元素时触发|  
|onmousemove|鼠标被移动。|
|onmouseover|鼠标移到某元素之上|
|onmouseout|鼠标从某元素移开|


|键盘事件|描述|  
|:---|:---|
|onkeydown|某个键盘按键被按下。|
|onkeypress|某个键盘按键被按下并松开。|
|onkeyup|某个键盘按键被松开。|

|框架/对象（Frame/Object）事件|描述|  
|:---|:---|
|onabort|图像的加载被中断。 ( \<object>)|
|onerror|在加载文档或图像时发生错误。 (\<object>, \<body>和 \<frameset>)|
|onbeforeunload|在即将离开页面（刷新或关闭）时触发|
|onhashchange|在当前 URL 的锚部分发生修改时触发。|
|onload|一张页面或一幅图像完成加载|
|onpageshow|在用户访问页面时触发。|
|onpagehide|该事件在用户离开当前网页跳转到另外一个页面时触发|
|onresize|窗口或框架被重新调整大小。|
|onscroll|当文档被滚动时发生的事件。|
|onunload|用户退出页面。 ( \<body> 和 \<frameset>)|

|框架/对象（Frame/Object）事件|描述|  
|:---|:---|
|onblur|元素失去焦点时触发|
|onfocus|元素获取焦点时触发|
|onfocusin|	元素即将获取焦点时触发|
|onfocusout|元素即将失去焦点时触发|
|onchange|在表单元素的内容改变时触发( \<input>,\ <keygen>,\ <select>, 和 \<textarea>)|
|oninput|元素获取用户输入时触发|
|onreset|表单重置时触发|
|onsearch|用户向搜索域输入文本时触发 ( \<input="search">)|
|onselect|用户选取文本时触发 ( \<input> 和 \<textarea>)|
|onsubmit|表单提交时触发|
||图像已加载时|
||输入字段被改变时|
||提交 HTML 表单时|

*2.1 onload 和 onunload 事件*  
onload 和 onunload 事件会在用户进入或离开页面是触发。  
onload 事件可以用于检测访问者的浏览器类型和浏览器版本，并基于这些信息来加载网页的正确版本。  
onload 和 onunload 事件可用于处理 cookie。  

**实例：**
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body onload="checkCookies()">

<script>
function checkCookies(){
	if (navigator.cookieEnabled==true){
		alert("Cookies 可用")
	}
	else{
		alert("Cookies 不可用")
	}
}
</script>
<p>弹窗-提示浏览器 cookie 是否可用。</p>
	
</body>
</html>
```

*2.2 onchange 事件*  
onchange 事件常结合对输入字段的验证来使用。  
**实例**
```html
<!-- 当用户改变输入字段的内容时，会调用 upperCase() 函数。 -->
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<head>
<script>
function myFunction(){
	var x=document.getElementById("fname");
	x.value=x.value.toUpperCase();
}
</script>
</head>
<body>

输入你的名字: <input type="text" id="fname" onchange="myFunction()">
<p>当你离开输入框后，函数将被触发，将小写字母转为大写字母。</p>

</body>
</html>
```  
*2.3 onmouseover 和 onmouseout  事件*  
onmouseover 和 onmouseout 事件可用于在用户的鼠标移至 HTML 元素上方或移出元素时触发函数。  
**实例**
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>

<div onmouseover="mOver(this)" onmouseout="mOut(this)" 
  style="background-color:#D94A38;width:120px;height:20px;padding:40px;"
>Mouse Over Me
</div>
<script>
function mOver(obj){
	obj.innerHTML="Thank You"
}
function mOut(obj){
	obj.innerHTML="Mouse Over Me"
}
</script>
</body>
</html>
```

*2.4 onmousedown、onmouseup 以及 onclick 事件*  
onmousedown, onmouseup 以及 onclick 构成了鼠标点击事件的所有部分。  
首先当点击鼠标按钮时，会触发 onmousedown 事件，当释放鼠标按钮时，会触发 onmouseup 事件，最后，当完成鼠标点击时，会触发 onclick 事件。  
**实例**
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<head>
<script>
function lighton(){
	document.getElementById('myimage').src="bulbon.gif";
}
function lightoff(){
	document.getElementById('myimage').src="bulboff.gif";
}
</script>
</head>

<body>
<img id="myimage" onmousedown="lighton()" onmouseup="lightoff()" src="bulboff.gif" width="100" height="180" />
<p>点击不释放鼠标灯将一直亮着!</p>
</body>
</html>
```
###### 3. HTML 事件属性  
**实例1：**
```html
<!-- 向 button 元素分配 onclick 事件： -->
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
</head>
<body>
<p>点击按钮执行 <em>displayDate()</em> 函数.</p>
<button onclick="displayDate()">点这里</button>
<script>
function displayDate(){
	document.getElementById("demo").innerHTML=Date();
}
</script>
<p id="demo"></p>

</body>
</html>
```

**实例2：使用 HTML DOM 来分配事件**
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<head>
</head>
<body>

<p>点击按钮执行 <em>displayDate()</em> 函数.</p>
<button id="myBtn">点这里</button>
<script>
document.getElementById("myBtn").onclick=function(){displayDate()};
function displayDate(){
	document.getElementById("demo").innerHTML=Date();
}
</script>
<p id="demo"></p>

</body>
</html>

```

###### 4. JavaScript HTML DOM EventListener  

1. addEventListener() 方法  
addEventListener() 用于向指定元素添加事件句柄。  
addEventListener() 方法添加的事件句柄不会覆盖已存在的事件句柄。  
可以向一个元素添加多个事件句柄。  
可以向同个元素添加多个同类型的事件句柄，如：两个 "click" 事件。 且不会覆盖已存在的事件：
可以向任何 DOM 对象添加事件监听，不仅仅是 HTML 元素。如： window 对象。  
addEventListener() 方法 可以更简单的控制事件（冒泡与捕获）。  
使用 addEventListener() 方法时, JavaScript 从 HTML 标记中分离开来，可读性更强， 在没有控制HTML标记时也可以添加事件监听。  
可以使用 removeEventListener() 方法来移除事件的监听。  
2. 语法 
element.addEventListener(event, function, useCapture);  
*说明*  
第一个参数是事件的类型 (如 "click" 或 "mousedown").  
第二个参数是事件触发后调用的函数。  
第三个参数是个布尔值用于描述事件是冒泡还是捕获。该参数是可选的。  
**注意:不要使用 "on" 前缀。 例如，使用 "click" ,而不是使用 "onclick"。**  
**实例1：**
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>

<p>该实例使用 addEventListener() 方法在按钮中添加点击事件。 </p>
<button id="myBtn">点我</button>
<p id="demo"></p>
<script>
document.getElementById("myBtn").addEventListener("click", displayDate); // 使用函数名，来引用外部函数:
function displayDate() {
    document.getElementById("demo").innerHTML = Date();
}
</script>

</body>
</html>
```

**实例2：向 Window 对象添加事件句柄**
```html
<!-- addEventListener() 方法允许你在 HTML DOM 对象添加事件监听 -->
<!-- HTML DOM 对象如： HTML 元素, HTML 文档, window 对象。或者其他支持的事件对象如: xmlHttpRequest 对象。 -->

<!-- 当用户重置窗口大小时添加事件监听 -->
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>

<p>实例在 window 对象中使用 addEventListener() 方法。</p>
<p>尝试重置浏览器的窗口触发 "resize" 事件句柄。</p>
<p id="demo"></p>
<script>
window.addEventListener("resize", function(){
    document.getElementById("demo").innerHTML = Math.random();
});
</script>

</body>
</html>

```

4. 传递参数
当传递参数值时，使用"匿名函数"调用带参数的函数：
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>

<p>实例演示了在使用 addEventListener() 方法时如何传递参数。</p>
<p>点击按钮执行计算。</p>
<button id="myBtn">点我</button>
<p id="demo"></p>
<script>
var p1 = 5;
var p2 = 7;
document.getElementById("myBtn").addEventListener("click", function() {
    myFunction(p1, p2);
});
function myFunction(a, b) {
    var result = a * b;
    document.getElementById("demo").innerHTML = result;
}
</script>

</body>
</html>
```  

5. 事件冒泡 或 事件捕获 
事件传递有两种方式：冒泡 与 捕获  
事件传递定义了元素事件触发的顺序。  
如果你将 \<p> 元素插入到 \<div> 元素中，用户点击 \<p> 元素, 哪个元素的 "click" 事件先被触发呢？  
在**冒泡**中，内部元素的事件会先被触发，然后再触发外部元素，即： \<p> 元素的点击事件先触发，然后会触发 \<div> 元素的点击事件。  
在<b>捕获</b>中，外部元素的事件会先被触发，然后才会触发内部元素的事件，即： \<div> 元素的点击事件先触发 ，然后再触发 \<p> 元素的点击事件。  
addEventListener() 方法可以指定 "useCapture" 参数来设置传递类型：  
addEventListener(event, function, useCapture);  
默认值为 false, 即冒泡传递，当值为 true 时, 事件使用捕获传递。  

6. removeEventListener() 方法  
removeEventListener() 方法移除由 addEventListener() 方法添加的事件句柄:  
**语法**
element.removeEventListener(event, function);  

**PS：浏览器支持**
IE 8 及更早 IE 版本，Opera 7.0及其更早版本不支持 addEventListener() 和 removeEventListener() 方法。  
但是，对于这类浏览器版本可以使用attachEvent()添加事件句柄 和  detachEvent() 方法来移除事件句柄。  
element.attachEvent(event, function);  
element.detachEvent(event, function);  

```javascript
// 跨浏览器解决方案
var x = document.getElementById('');
if(x.addEventListener){
  x.addEventListener("click","myFunction");
}
else if(x.attachEvent) {
  x.attachEvent("onclick","myFunction");
}

```

#### IV JavaScript HTML DOM 元素  
如何向文档中添加和移除元素(节点)。  

**4.1 创建新的 HTML 元素 (节点) - appendChild() - 添加新元素到尾部**  
```html
<!-- 要创建新的 HTML 元素 (节点)需要先创建一个元素，然后在已存在的元素中添加它。 -->
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>

<div id="div1">
<p id="p1">这是一个段落。</p>
<p id="p2">这是另外一个段落。</p>
</div>
 
<script>
var para = document.createElement("p"); // 创建 <p> 元素:
var node = document.createTextNode("这是一个新的段落。"); // 为 <p> 元素创建一个新的文本节点
para.appendChild(node); // 文本节点添加到 <p> 元素中
 
var element = document.getElementById("div1");
element.appendChild(para);  // 在一个已存在的元素中添加 p 元素。
</script>

</body>
</html>
```
**4.2 创建新的 HTML 元素 (节点) - insertBefore() - 将新元素添加到指定位置**  
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>

<div id="div1">
<p id="p1">这是一个段落。</p>
<p id="p2">这是另外一个段落。</p>
</div>
 
<script>
var para = document.createElement("p");
var node = document.createTextNode("这是一个新的段落。");
para.appendChild(node);
 
var element = document.getElementById("div1");
var child = document.getElementById("p1");
element.insertBefore(para, child);
</script>

</body>
</html>
```

**4.3 移除已存在的元素**  
要移除一个元素，你需要知道该元素的父元素。  
```html
<!-- DOM 需要清楚您需要删除的元素，以及它的父元素。 -->
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>

<div id="div1">
<p id="p1">这是一个段落。</p>
<p id="p2">这是另外一个段落。</p>
</div>
 
<script>
var parent = document.getElementById("div1");
var child = document.getElementById("p1");
parent.removeChild(child);
</script>

</body>
</html>
```
**注意：** 早期的 Internet Explorer 浏览器不支持 node.remove() 方法。

```javascript
//以下代码是已知要查找的子元素，然后查找其父元素，再删除这个子元素（删除节点必须知道父节点）
var child = document.getElementById("p1");
child.parentNode.removeChild(child);
```

**4.4 替换 HTML 元素 - replaceChild()**  
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>

<div id="div1">
<p id="p1">这是一个段落。</p>
<p id="p2">这是另外一个段落。</p>
</div>
 
<script>
var para = document.createElement("p");
var node = document.createTextNode("这是一个新的段落。");
para.appendChild(node);
 
var parent = document.getElementById("div1");
var oldChild = document.getElementById("p1");
parent.replaceChild(para, oldChild);
</script>

</body>
</html>
```

#### V JavaScript HTML DOM 集合(Collection)  

###### 5.1 HTMLCollection 对象  
getElementsByTagName() 方法返回 HTMLCollection 对象。  
HTMLCollection 对象类似包含 HTML 元素的一个数组。  
###### 5.2 HTMLCollection 对象 length 属性
HTMLCollection 对象的 length 属性定义了集合中元素的数量。  
集合 length 属性常用于遍历集合中的元素  
```javascript
var myCollection = document.getElementsByTagName("p");
let i;
for (i = 0; i < myCollection.length; i++) {
    myCollection[i].style.backgroundColor = "red";
}
```
**PS:** HTMLCollection 不是一个数组！  
HTMLCollection 看起来可能是一个数组，但其实不是。  
可以像数组一样，使用索引来获取元素。HTMLCollection 无法使用数组的方法： valueOf(), pop(), push(), 或 join() 。  

#### VI JavaScript HTML DOM 节点列表（NodeList）  
NodeList 对象是一个从文档中获取的节点列表 (集合) 。  
NodeList 对象类似 HTMLCollection 对象。  
一些旧版本浏览器中的方法（如：getElementsByClassName()）返回的是 NodeList 对象，而不是 HTMLCollection 对象。  
所有浏览器的 childNodes 属性返回的是 NodeList 对象。  
大部分浏览器的 querySelectorAll() 返回 NodeList 对象。  

**6.1 NodeList 对象 length 属性**  
NodeList 对象 length 属性定义了节点列表中元素的数量。  

**6.2 HTMLCollection 与 NodeList 的区别**  
>1. HTMLCollection 是 HTML 元素的集合。
>2. NodeList 是一个文档节点的集合。
>3. HTMLCollection 元素可以通过 name，id 或索引来获取。
>4. NodeList 只能通过索引来获取。
>5. 只有 NodeList 对象有包含属性节点和文本节点。
>6. NodeList 与 HTMLCollection 都与数组对象有点类似，可以使用索引 (0, 1, 2, 3, 4, ...) 来获取元素。
>7. NodeList 与 HTMLCollection 都有 length 属性。
>8. 两者都是动态集合。唯一有区别的是querySelectorAll方法返回的是NodeList，且是**静态的**，不会随着文档节点的增删改变。 querySelectorAll().length 不会随着元素的删除改变，getElementsByTagName().length 会实时变动。  

___


### 五、 JS 高级教程 2022-04-18

#### I JavaScript 对象  
JavaScript 中的所有事物都是对象：字符串、数值、数组、函数...  
此外，JavaScript 允许自定义对象。  
对象只是一种特殊的数据。对象拥有属性和方法。  
**JS内置对象:**
|对象|描述|
|:---|:---|
|Argument|函数参数集合|
|Array|数组|
|Boolean|布尔对象|
|Date|日期|
|Error|异常对象|
|Function|函数构造器|
|Math|数学|
|Number|数值|
|Object|基础对象|
|RegExp|正则|
|String|字符串|
###### 5.1.1 所有事物都是对象  
JavaScript 提供多个内建对象，比如 String、Date、Array 等等。 对象只是带有属性和方法的特殊数据类型。  
###### 5.1.2 创建 JavaScript 对象  
通过 JavaScript，您能够定义并创建自己的对象。  
创建新对象有两种不同的方法：  
  * 使用 Object 定义并创建对象的实例。
  * 使用函数来定义对象，然后创建新的对象实例。  
>1. 使用 Object  
> 在 JavaScript 中，几乎所有的对象都是 Object 类型的实例，它们都会从 Object.prototype 继承属性和方法。  
> Object 构造函数创建一个对象包装器。
> Object 构造函数，会根据给定的参数创建对象，具体有以下情况：
> * 如果给定值是 null 或 undefined，将会创建并返回一个空对象。
> * 如果传进去的是一个基本类型的值，则会构造其包装类型的对象。
> * 如果传进去的是引用类型的值，仍然会返回这个值，经他们复制的变量保有和源对象相同的引用地址。  
> * 当以非构造函数形式被调用时，Object 的行为等同于 new Object()。  
> 语法：new Object([value]) // 以构造函数形式来调用, value 可以是任何值。
> var o = new Object(true); // 等价于 o = new Boolean(true);
```javascript
// 创建了对象的一个新实例，并向其添加了四个属性
person=new Object();
person.firstname="John";
person.lastname="Doe";
person.age=50;
person.eyecolor="blue";
```
也可以使用对象字面量来创建对象，语法格式如下:
* { name1 : value1, name2 : value2,...nameN : valueN }  

> 2. 使用对象构造器  
```javascript
    // 使用函数来构造对象：
    function person(firstname,lastname,age,eyecolor)
    {
        this.firstname=firstname;
        this.lastname=lastname;
        this.age=age;
        this.eyecolor=eyecolor;
    }
    myFather=new person("John","Doe",50,"blue"); // 创建 JavaScript 对象实例

    // 把属性添加到 JavaScript 对象
    // 假设 person 对象已存在 - 您可以为其添加这些新属性：firstname、lastname、age 以及 eyecolor：
    person.firstname="John";
    person.lastname="Doe";
    person.age=30;
    person.eyecolor="blue";

    x=person.firstname;
    console.log(x); // John

    // 把方法添加到 JavaScript 对象
    // 方法只不过是附加在对象上的函数。
    // 在构造器函数内部定义对象的方法：
    function person(firstname,lastname,age,eyecolor)
    {
        this.firstname=firstname;
        this.lastname=lastname;
        this.age=age;
        this.eyecolor=eyecolor;

        this.changeName=changeName;
        function changeName(name) // changeName() 函数 name 的值赋给 person 的 lastname 属性。
        {
            this.lastname=name;
        }
    }
```
###### 5.1.3 JavaScript 类  
JavaScript 是面向对象的语言，但 JavaScript 不使用类。  
在 JavaScript 中，不会创建类，也不会通过类来创建对象（就像在其他面向对象的语言中那样）。  
JavaScript 基于 prototype，而不是基于类的。  
###### 5.1.4 JavaScript for...in 循环
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>
	
<p>点击下面的按钮，循环遍历对象 "person" 的属性。</p>
<button onclick="myFunction()">点击这里</button>
<p id="demo"></p>
<script>
function myFunction(){
	var x;
	var txt="";
	var person={fname:"Bill",lname:"Gates",age:56}; 
	for (x in person){
		txt=txt + person[x];
	}
	document.getElementById("demo").innerHTML=txt; // BillGates56
}
</script>
	
</body>
</html>
```
###### 5.1.4 JavaScript 的对象是可变的  
对象是可变的，它们是通过**引用**来传递的。  
```javascript
var x = person;  // 不会创建 person 的副本，是引用
// 如果修改 x ，person 的属性也会改变：
var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"}
var x = person;
x.age = 10;           //  x.age 和 person.age 都会改变

```

#### II JavaScript prototype(原型对象)  
所有的 JavaScript 对象都会从一个 prototype（原型对象）中继承属性和方法。  
在前面的章节中我们学会了如何使用对象的构造器（constructor）：  
```javascript
function Person(first, last, age, eyecolor) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eyecolor;
}
var myFather = new Person("John", "Doe", 50, "blue");
var myMother = new Person("Sally", "Rally", 48, "green");
```
我们也知道在一个已存在构造器的对象中是不能添加新的属性：
```javascript
Person.nationality = "English"; // 报错
```
要添加一个新的属性需要在在构造器函数中添加：
```javascript
function Person(first, last, age, eyecolor) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eyecolor;
  this.nationality = "English";
}
```
###### 1. prototype 继承  
所有的JavaScript 对象都会从一个prototype（原型对象）中继承属性和方法。  
* Date 对象从 Date.prototype 继承
* Array 对象从 Array.prototype 继承
* Person 对象从 Person.prototype 继承

所有的JavaScript 中的对象都是位于原型链顶端的的Object实例。  
JavaScript 对象有一个指向原型对象的链。当试图访问一个对象的属性时，它不仅仅在该对象上搜寻，还会搜寻该对象的原型，以及该对象的原型的原型，依次层层向上搜寻，直到找到一个名字匹配的属性或达到原型链的末尾。  
Date 对象, Array 对象, 以及 Person 对象从 Object.prototype 继承。  

###### 2. 添加属性和方法  
有时候我们想要在所有已存在的对象添加新的属性或方法。  
另外，有时候我们想在对象的构造函数中添加新的属性或方法。 
**格式：**构造函数.prototype.新属性或方法
使用 prototype 属性就可以给对象的构造函数添加新的属性。  
```javascript
function Person(first, last, age, eyecolor) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eyecolor;
}
// 在不直接修改对象的构造器（constructor）的基础上，使用prototype添加新属性nationality 
Person.prototype.nationality = "English";
// 或则添加新的方法
Person.prototype.name = function() {return this.firstName + " " + this.lastName;};
```

#### III JavaScript Number 对象  
JavaScript 只有一种数字类型。  
可以使用也可以不使用小数点来书写数字。  
```javascript
var pi=3.14;    // 使用小数点
var x=34;       // 不使用小数点
var y=123e5;    // 12300000
var z=123e-5;   // 0.00123
```
**所有 JavaScript 数字均为 64 位**  
* 精度:  
```javascript
// 整数（不使用小数点或指数计数法）最多为 15 位。
var x = 999999999999999;   // x 为 999999999999999
var y = 9999999999999999;  // y 为 10000000000000000
// 小数的最大位数是 17，但是浮点运算并不总是 100% 准确：
var x = 0.2+0.1; // 输出结果为 0.30000000000000004
```
* 八进制和十六进制
```javascript 
// 如果前缀为 0，则 JavaScript 会把数值常量解释为八进制数，如果前缀为 0 和 "x"，则解释为十六进制数。
var y = 0377;
var z = 0xFF;
// 绝不要在数字前面写零，除非您需要进行八进制转换。 

// 默认情况下，JavaScript 数字为十进制显示。
// 你可以使用 toString() 方法 输出16进制、8进制、2进制。
var myNumber=128;
myNumber.toString(16);   // 返回 80
myNumber.toString(8);    // 返回 200
myNumber.toString(2);    // 返回 10000000
```

* 无穷大 Infinity  
当数字运算结果超过了JavaScript所能表示的数字上限（溢出），结果为一个特殊的无穷大（infinity）值，在JavaScript中以Infinity表示。  
当负数的值超过了JavaScript所能表示的负数范围，结果为负无穷大，在JavaScript中以-Infinity表示。  
无穷大值的行为特性和我们所期望的是一致的：基于它们的加、减、乘和除运算结果还是无穷大（当然还保留它们的正负号）。  
```javascript
// 除以0也产生了无限:
var x = 2/0;
var y = -2/0;
var z = 0/0; // NaN
```

* NaN - 非数字值  
NaN 属性是代表非数字值的特殊值。  
该属性用于指示某个值不是数字。可以把 Number 对象设置为该值，来指示其不是数字值。  
可以使用 isNaN() 全局函数来判断一个值是否是 NaN 值。  
```javascript
var x = 1000 / "Apple";
isNaN(x); // 返回 true
var y = 100 / "1000";
isNaN(y); // 返回 false
```
######  1. Number 属性  
|属性|描述|
|:---|:---|
|Number.MAX_VALUE|最大值|
|Number.MIN_VALUE|最小值|  
|Number.NaN|非数字|
|Number.POSITIVE_INFINITY|正无穷，在溢出时返回|
|Number.NEGATIVE_INFINITY|负无穷，在溢出时返回|
|Number.EPSILON|表示 1 和比最接近 1 且大于 1 的最小 Number 之间的差别|
|Number.MAX_SAFE_INTEGER|最大安全整数。|
|Number.MIN_SAFE_INTEGER|最小安全整数。|

###### 2. Number 数字方法
|方法|描述|
|:---|:---|
|Number.parseFloat()|将字符串转换成浮点数，和全局方法 parseFloat() 作用一致。|
|Number.parseInt()|将字符串转换成整型数字，和全局方法 parseInt() 作用一致。|
|Number.isFinite()|判断传递的参数是否为有限数字。|
|Number.isInteger()|判断传递的参数是否为整数。|
|Number.isNaN()|判断传递的参数是否为NaN。|
|Number.isSafeInteger()|判断传递的参数是否为安全整数。|


#### IV JavaScript String 对象  
* 特殊字符  

|代码|输出|
|:---|:---|
|\\'|单引号|
|\\"|双引号|
|\\\\|斜杆|
|\\n|换行|
|\\r|回车|
|\\t|	tab|
|\\b|空格|
|\\f|换页|

#### V JavaScript Date  日期对象  
日期对象用于处理日期和时间。  
<a href = "https://www.runoob.com/jsref/jsref-obj-date.html ">详情链接</a>  

#### VI JavaScript Array 数组对象 
数组对象的作用是：使用单独的变量名来存储一系列的值。  
* 在一个数组中你可以有不同的对象，可以在数组中有不同的变量类型。

###### 1. 创建数组  
① 常规方式：    
```javascript
var myCars=new Array();
myCars[0]="Saab";      
myCars[1]="Volvo";
myCars[2]="BMW";
```
② 简洁方式：
```javascript
var myCars=new Array("Saab","Volvo","BMW");
```
③ 字面：
```javascript
var myCars = ["Saab","Volvo","BMW"];
```
不推荐使用new关键字创建数组，所以一般使用③  

###### 2. 数组方法和属性
***属性***
|属性|描述|
|:---|:---|
|constructor|返回数组对象的原型函数|
|length|设置或返回数组元素的个数|
|prototype|允许向数组对象添加属性或方法|
```javascript
// 创建一个新的方法：用于将数组小写字符转为大写字符。
Array.prototype.myUpperCase = function() {
  for(i = 0; i < this.length; i++){
    this[i] = this[i].toUpperCase();
  }
}
```
**方法**
|方法|描述|
|:---|:---|
|concat()|连接两个或多个数组，并返回结果|
|copyWithin()|从数组指定位置拷贝元素到数组的另一个指定位置中|
|entries()|返回数组的可迭代对象|
|every()| 检测数组的每一个元素是否都符合条件（通过函数提供），every() 方法使用指定函数检测数组中的所有元素，出现false直接返回，剩余不在校验|
|some()|检测数组中元素是否有符合指定条件的，如果有一个元素满足条件，则表达式返回true , 剩余的元素不会再执行检测。如果没有满足条件的元素，则返回false。|
|fill()| 使用一个固定值来填充数组，fill(value必填, start, end)|
|filter()|检测数值元素，并返回符合条所有元素的数组|
|find()|返回符合传入测试（函数）条件的数组元素|
|findIndex()|返回符合传入测试（函数）条件的数组元素索引|
|forEach()|数组的每一个函数都执行一次回调函数|
|map()|通过指定函数处理数组中的元素，并返回处理后的数组|
|from()|通过给定的对象中创建一个数组|
|includes()|判断一个数组中是否包含一个指定的值。|
|indexOf()|搜索数组中元素，并返回它在数组中的位置。返回 item 的第一次出现的位置。没找到指定元素则返回 -1。|
|lastIndexOf()|搜索数组中元素，并返回它在数组中最后出现的位置，后面向前查找。|
|isArray()|判断对象是否是数组。如果对象是数组返回 true，否则返回 false。|
|join()|把数组中的元素组合成一个字符串|
|keys()|返回数组的可迭代对象，包含原始数组的键（key）|
|shift()|删除并返回数组的第一个元素|
|unshift()|向数组的头部添加一个或多个元素，并返回之后的长度|
|pop()|删除数组的最后一个元素，并返回元素值|
|push()| 向数组的尾部添加一个或多个元素，并返回之后的长度|
|reduce()|将数组元素计算成一个值（左->右）|
|reduceRight()|将数组元素计算为一个值（从右到左）。|
|reverse()|反转数组的元素顺序|
|slice()|选取数组的一部分，并返回一个新的数组|
|sort()|对数组元素进行排序，默认升序|
|splice()|从数组中添加或者删除元素|
|toString()|将数组转换成字符串，并返回结果|
|valeOf()|返回数组对象的原始值|
|at(index)|类似于[0...n-1]索引，但是at中允许负值，意味着反向索引|

**部分方法详解**
① copyWithin()  
array.copyWithin(target, start, end)
target  必需。复制到指定目标索引位置。  
start   可选。元素复制的起始位置。  
end     可选。停止复制的索引位置 (默认为 array.length)。如果为负值，表示倒数。  
```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.copyWithin(2, 0);  // Banana,Orange,Banana,Orange
```

② filter() 方法创建一个新的数组，新数组中的元素是通过检查指定数组中符合条件的所有元素。如果没有符合条件的元素则返回空数组。
* filter() 不会对空数组进行检测。
* filter() 不会改变原始数组。
array.filter(function(currentValue,index,arr), thisValue)  
function(currentValue, index,arr)   必须。函数，数组中的每个元素都会执行这个函数。函数参数:currentValue必须。当前元素的值；index可选。当前元素的索引值；arr可选。当前元素属于的数组对象。  
thisValue   可选。对象作为该执行回调时使用，传递给函数，用作 "this" 的值。如果省略了 thisValue ，"this" 的值为 "undefined"。
```javascript
var ages = [32, 33, 16, 40];
function checkAdult(age) {
    return age >= 18;
}
console.log(ages.filter(checkAdult)); // 32,33,40
```

③find()  方法返回通过测试（函数内判断）的数组的第一个元素的值。  
find() 方法为数组中的每个元素都调用一次函数执行：  
* 当数组中的元素在测试条件时返回 true 时, find() 返回符合条件的元素，之后的值不会再调用执行函数。  
* 如果没有符合条件的元素返回 undefined  
array.find(function(currentValue, index, arr),thisValue)  
```javascript
var ages = [3, 10, 18, 20];
 
function checkAdult(age) {
    return age >= 18;
}
console.log(ages.find(checkAdult)); // 18
```

④ findIndex() 方法返回传入一个测试条件（函数）符合条件的数组第一个元素位置（索引）。  

⑤ foreEach() 方法用于调用数组的每个元素，并将元素传递给回调函数。 
* 在forEach中使用 return false 或者 break无法跳出整个循环，并且使用break会直接报错  
* 没有返回值 
* forEach方法无法中断执行，总是会将所有成员遍历完。
* forEach方法不会跳过 undefined 和 null，但会跳过空位。
* forEach方法也可以用于类似数组的对象和字符串。
array.forEach(function(currentValue, index, arr), thisValue)
```javascript
// 数组
var out = [];
[1,2,3].forEach(function(elem){ 
  this.push(elem * elem);
  } , out);
console.log(out); // [1, 4, 9]

// 对象
var obj = {
        0: 1,
        a: 'hello',
        length: 1
      }
Array.prototype.forEach.call(obj,function(elem, index) { console.log(index + ':' + elem);});
// 0:1

// 字符串
var str = 'abc'
Array.prototype.forEach.call(str,function(elem, index) { console.log(index + ':' + elem);});
// 0:a
// 1:b
// 2:c

```

⑥map() 方法返回一个新数组，数组中的元素为原始数组元素调用函数处理后的值。  
* map() 方法按照原始数组元素顺序依次处理元素。 
array.map(function(currentValue,index,arr), thisValue)  
```javascript
var arr = [4,9,16,25];
var x = arr.map(Math.sqrt);
console.log(x); // [2,3,4,5]
```  

⑦ slice() 方法可以从也有数组中返回选定的元素。  
* slice() 方法可提取字符串的某个部分，并以新的字符串返回被提取的部分。
* slice() 方法不会改变原始数组。   
array.slice(start, end) 选取区间 [start , end) 不包含end
start 可选。规定从何处开始选取。如果该参数为负数，则表示从原数组中的倒数第几个元素开始提取，slice(-2) 表示提取原数组中的倒数第二个元素到最后一个元素（包含最后一个元素）。  
end 可选。规定从何处结束选取。该参数是数组片断结束处的数组下标。如果没有指定该参数，那么切分的数组包含从 start 到数组结束的所有元素。如果该参数为负数， 则它表示在原数组中的倒数第几个元素结束抽取。   
* slice(-2,-1) 表示抽取了原数组中的倒数第二个元素到最后一个元素（不包含最后一个元素，也就是只有倒数第二个元素）。
* slice方法的一个重要应用，是将类似数组的对象转为真正的数组。
```javascript
var fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
var citrus = fruits.slice(1,3);
console.log(citrus);  // Orange,Lemon
```

⑧splice() 方法用于删除或添加数组中的元素。  
* splice() 方法会改变原始数组。  
**语法**
array.splice(index,howmany,item1,.....,itemX)  
index 必需。规定从何处添加/删除元素。该参数是开始插入和（或）删除的数组元素的下标，必须是数字。  
howmany 可选。规定应该删除多少元素。必须是数字，但可以是 "0"。如果未规定此参数，则删除从 index 开始到原数组结尾的所有元素。  
item1, ..., itemX	  可选。要添加到数组的新元素  
**返回值**
删除：  Array 如果从 arrayObject 中删除了元素，则返回的是含有被删除的元素的数组。如果未删除任何元素，则返回空数组。
添加：  Array 返回添加元素之后的数组
```javascript
// 删除
var fruits1 = ["Banana", "Orange", "Apple", "Mango"];
fruits1.splice(2,1);
console.log(fruits1.splice(2,1)); // ['Apple']
console.log(fruits1);   // ['Banana', 'Orange', 'Mango']

var fruits2 = ["Banana", "Orange", "Apple", "Mango"];
fruits2.splice(2,0);
console.log(fruits2.splice(2,0)); // []
console.log(fruits2);   // ["Banana", "Orange", "Apple", "Mango"]

// 添加
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(2,0,"Lemon","Kiwi");
console.log(fruits); //  ['Banana', 'Orange', 'Lemon', 'Kiwi', 'Apple', 'Mango']
```  

#### VI JavaScript Boolean 布尔对象  
Boolean（布尔）对象用于将非布尔值转换为布尔值（true 或者 false）。  
> 0 为布尔值 false
> 1 为布尔值 true
> 空字符串是布尔值 false
> null 是布尔值 false
> NaN 是布尔值 false
> 字符串'false' 是布尔值true  

**如果布尔对象无初始值或者其值为:0 -0 null "" false undefined NaN 那么对象的值为 false。否则，其值为 true（即使当变量值为字符串 "false" 时）！**  

#### VII JavaScript Math 算数对象  
Math 算数对象，用于执行常见的算数任务。  
* 该对象没有构造函数 Math()。  
**Math 对象属性**  

|属性|描述|
|:---|:---|
|E|返回算术常量 e，即自然对数的底数（约等于2.718）。|
|LN2|返回 2 的自然对数（约等于0.693）。| 
|LN10|返回 10 的自然对数（约等于2.302）。| 
|LOG2E|	返回以 2 为底的 e 的对数（约等于 1.4426950408889634）。|  
|LOG10E|返回以 10 为底的 e 的对数（约等于0.434）。|  
|PI|返回圆周率（约等于3.14159）。|  
|SQRT1_2|返回 2 的平方根的倒数（约等于 0.707）。|
|SQRT2|返回 2 的平方根（约等于 1.414）。|  

**Math 方法**  
|方法|描述|
|:---|:---|
|abs(x)|返回 x 的绝对值。|
|ceil(x)|对数进行上舍入。向上取整计算，它返回的是大于或等于函数参数，并且与之最接近的整数。|  
|floor(x)|对 x 进行下舍入。返回小于等于x的最大整数。|
|round(x)|四舍五入。把一个数字舍入为最接近的整数。|
|exp(x)|返回 E<sup>x</sup> 的指数。|
|pow(x,y)|返回 x 的 y 次幂。x<sup>y</sup>|
|log(x)|返回数的自然对数（底为e）。|
|sqrt(x)|返回数的平方根。|
|max(x,y,z,...,n)|返回 x,y,z,...,n 中的最高值。如果没有参数，则返回 -Infinity。如果有某个参数为 NaN，或是不能转换成数字的非数字值，则返回 NaN。|
|min(x,y,z,...,n)|返回 x,y,z,...,n中的最低值。|
|random()|介于 0（包含） ~ 1（不包含） 之间的一个随机数。区间[0,1)|  

① round() 方法可把一个数字舍入为最接近的整数。  
```javascript
var a=Math.round(2.60); // 3
var b=Math.round(2.50); // 3
var c=Math.round(2.49); // 2
var d=Math.round(-2.60); // -3
var e=Math.round(-2.50); // -2
var f=Math.round(-2.49); // -2
```
② random
```javascript
// 介于[min.max)
function getRndInteger(min,max)
{
  return (Math.random() * (max - min) + min);
}

// 介于[min.max]
function getRndInteger(min, max) {
  return Math.floor(Math.random() * (max - min + 1) ) + min;
}
```

#### IIX JavaScript RegExp 对象  
RegExp：是正则表达式（regular expression）的简写。  
###### 1. 语法  
> var patt=new RegExp(pattern,modifiers);
> 或更简单的方法
> var patt=/pattern/modifiers;  

 * 模式(pattern)描述了一个表达式模型。
 * 修饰符(modifiers)描述了检索是否是全局，区分大小写等。  

**注意：** 当使用构造函数创造正则对象时，需要常规的字符转义规则（在前面加反斜杠 \）。比如，以下是等价的：  
```javascript
var re = new RegExp("\\w+");
var re = /\w+/;
```  

###### 2. RegExp 修饰符 modifier  
修饰符用于执行不区分大小写和全文的搜索。  
* i - 修饰符是用来执行不区分大小写的匹配。  
* g - 修饰符是用于执行全文的搜索（而不是在找到第一个就停止查找,而是找到所有的匹配）。
* m - 执行多行匹配。

###### 3. RegExp 方法  
* exec() 方法用于检索字符串中的正则表达式的匹配。
RegExpObject.exec(string)
如果字符串中有匹配的值返回该匹配值，否则返回 null。  
* test() 方法用于检测一个字符串是否匹配某个模式。  
如果字符串中有匹配的值返回 true ，否则返回 false。

###### 4. RegExp 对象属性  
|属性|描述|
|:---|:---|
|constructor|返回一个函数，该函数是一个创建 RegExp 对象的原型。|
|lastIndex|用于规定下次匹配的起始位置|
|source|返回正则表达式的匹配模式|
|global|判断是否设置了 "g" 修饰符| 
|ignoreCase|判断是否设置了 "i" 修饰符|
|multiline|判断是否设置了 "m" 修饰符|

#### IX JavaScript Error 对象  
Error 对象在错误发生时提供了错误的提示信息。  
|属性|描述|
|:---|:---|
|name|设置或返回一个错误名|
|message|设置或返回一个错误信息(字符串)|
>  * name 属性  
> name 属性可以返回以下 6 个不同的值。
> 
> |错误名|描述|
> |:---|:---|
> |EvalError|eval() 函数产生的错误。 注意: 新版的 JavaScript 使用 SyntaxError 替代 EvalError。|
> |RangeError|数值超出规定的范围|
> |ReferenceError|非法引用|
> |SyntaxError|语法错误|
> |TypeError|类型错误|
> |URIError|encodeURI() 函数产生的错误|

**实例**
```javascript
try {
    adddlert("Welcome guest!");
}
catch(err) {
    console.log(err.name + ":" + err.message)
}
// ReferenceError:adddlert is not defined
```
__________
### 六、 JS 浏览器(Browser) BOM 2022-04-22

#### I  JavaScript Window - 浏览器对象模型  
浏览器对象模型（Browser Object Module） 使得 JavaScript 有能力和浏览器对话。  

###### 1. window 对象  
所有的浏览器都支持 window 对象，它表示浏览器窗口。  
所有 JavaScript 全局对象、函数以及变量均自动称为 window 对象的成员。  
全局变量是 window 对象的属性。全局函数是 window 对象的方法。  
甚至 HTML DOM 的 document 也是 window 对象的属性之一：  window.document.getElementById("header");  document.getElementById("header");  

###### 2. window 尺寸  
有三种方法可以获取浏览器窗口的尺寸。  
对于Internet Explorer、Chrome、Firefox、Opera 以及 Safari：  
> window.innerHeight - 浏览器窗口的内部高度（包括滚轮条）
> window.innerWidth - 浏览器窗口的内部宽度(包括滚动条)  

对于 Internet Explorer 8、7、6、5：  
> document.documentElement.clientHeight
> document.documentElement.clientWidth  
> document.body.clientHeight
> document.body.clientWidth  

###### 3. 其他window 方法  
window.open() - 打开新的窗口  
window.close() - 关闭当前窗口  
widow.moveTo() - 移动当前窗口  
window.resizeTo() - 调整当前窗口尺寸  


#### II JavaScript Window Screen
window.screen 对象包含有关用户屏幕的信息。  
###### 1. window.screen  
window.screen对象在编写时可以不使用 window 这个前缀。  
|属性|描述|
|:---|:---|
|screen.width|总宽度|
|screen.height|总高度|
|screen.availWidth|可用的屏幕宽度，以像素计，减去界面特性，比如窗口任务栏。|
|screen.availHeight|可用的屏幕高度，以像素计，减去界面特性，比如窗口任务栏。|  
|screen.colorDepth|色彩深度|
|screen.pixelDepth|色彩分辨率|

#### III JavaScript Window Location  
window.location 对象 用于获取当前页面的地址URL，并把浏览器重定向到新的页面。  
###### window.location
window.location 对象在编写时可不使用 window 这个前缀。  
一些例子：  
|属性|描述|
|:---|:---|
|location.hostname|返回 web 主机的域名|
|location.pathname|返回当前页面的路径和文件名|
|location.port|返回 web 主机的端口（80 或 433）|
|location.protocol|返回所使用的 web 协议（http、https）|
|location.href|返回当前页面的URL|  

|方法|描述|
|:---|:---|
|location.assign("url")|加载新的文档|  


#### IV JavaScript Window History  
window.history 对象包含浏览器的历史。  

###### 1. Window History  
window.history对象在编写时可不使用 window 这个前缀。  
为了保护用户隐私，对 JavaScript 访问该对象的方法做出了限制。  
|方法|描述|
|:---|:---|
|history.back()|在浏览器点击后退按钮相同，加载历史列表中的前一个URL|
|history.forward()|与在浏览器中点击向前按钮相同，加载历史列表中的下一个URL|
|history.go(x)|x = 1表示前进一个页面，相当于forwar()；x = -1表示后退一个页面back()；x = 0表示刷新页面|  


#### V JavaScript Window Navigator  
window.navigator 对象包含有关访问者浏览器的信息。  
###### 1. Window Navigator
window.navigator 对象在编写时可不使用 window 这个前缀。
|属性|描述|
|:---|:---|
|navigator.appCodeName|浏览器代号，Mozilla|
|navigator.appName|浏览器名称，Netscape|
|navigator.appVersion|浏览器版本|
|navigator.cookieEnabled|是否启用cookie|
|navigator.platform|硬件平台|
|navigator.userAgent|用户代理|
|navigator.language|用户代理语言|  
**警告**
来自 navigator 对象的信息具有误导性，不应该被用于检测浏览器版本，这是因为：  
* navigator 数据可被浏览器使用者更改  
* 一些浏览器对测试站点会识别错误
* 浏览器无法报告晚于浏览器发布的新操作系统

###### 2. 浏览器检测  
由于 navigator 可误导浏览器检测，使用对象检测可用来嗅探不同的浏览器。  
由于不同的浏览器支持不同的对象，您可以使用对象来检测浏览器。例如，由于只有 Opera 支持属性 "window.opera"，您可以据此识别出 Opera。  
**例子**
```javascript
if(window.opera){console.log("这是opera浏览器！！");}
```

#### VI JavaScript 弹框  
可以在 JavaScript 中创建三种消息框：警告框alert、确认框confirm、提示框prompt。  
* 警告框
警告框经常用于确保用户可以得到某些信息。
当警告框出现后，用户需要点击确定按钮才能继续进行操作。
widow.alert("") 警告框  
* 确认框  
当确认卡弹出时，用户可以点击 "确认" 或者 "取消" 来确定用户操作。
当你点击 "确认", 确认框返回 true， 如果点击 "取消", 确认框返回 false。
window.confirm("")
* 提示框  
提示框经常用于提示用户在进入页面前输入某个值。  
当提示框出现后，用户需要输入某个值，然后点击确认或取消按钮才能继续操纵。
如果用户点击确认，那么返回值为输入的值。如果用户点击取消，那么返回值为 null。
window.prompt("")
**弹窗使用 反斜杠 + "n"(\n) 来设置换行。**  

#### VII JavaScript 计时事件  
###### 1. JavaScript 计时事件  
通过使用 JavaScript，我们有能力做到在一个设定的时间间隔之后来执行代码，而不是在函数被调用后立即执行。我们称之为计时事件。  
> * 两个关键方法是
> 1. setInterval() 间隔指定的毫秒数不停地执行指定的代码。
> 2. setTimeout() 在指定的毫秒数后执行指定代码。  

**PS:** setInterval() 和 setTimeout() 是 HTML DOM Window对象的两个方法。  

① setInterval() 方法 间隔指定的毫秒数不停地执行指定的代码  
**语法**   
window.setInterval("function",milliseconds)  // window 可以省略
```javascript
setInterval(function(){alert("Hello")},3000);
```
② 停止执行 setInterval()  
clearInterval() 方法用于停止 setInterval() 方法执行的函数代码。  
**语法**
window.clearInterval(intervalVariable)  // window 可以省略  
要使用 clearInterval() 方法, 在创建计时方法时你必须使用全局变量：
```javascript
var myVar = setInterval("javascript function",milliseconds);
clearInterval(myVar);
```

③ settimeOut()  
**语法**  
myVar = window.setTimeout("javascript function", milliseconds);
setTimeout() 方法会返回某个值。在上面的语句中，值被储存在名为 myVar 的变量中。假如你希望取消这个 setTimeout()，你可以使用这个变量名来指定它。  
* clearTimeout() 方法用于停止执行setTimeout()方法的函数代码。  

#### IIX JavaScript Cookie  
Cookie 用于存储web 页面的用户信息。  
###### 1. 什么是 Cookie ？  
Cookie 是一些数据，存储于电脑的文本文件中。  
当 web 服务器向浏览器发送 web 页面时，在连接关闭后，服务端不会记录用户的信息。  
Cookie 的作用就是用于解决 "如何记录客户端的用户信息":  
  * 当用户访问浏览器时，他的名字可以记录在cookie中
  * 在用户下一次访问该页面时，可以在 cookie 中读取用户访问记录。

Cookie 以 名/值 对的形式存储： username=John Doe  
当浏览器从服务器上请求 web 页面时， 属于该页面的 cookie 会被添加到该请求中。服务端通过这种方式来获取用户的信息。  

###### 2. 使用 JavaScript 创建 Cookie  
JavaScript 可以使用 document.cookie 属性来创建 、读取、及删除 cookie。  
```javascript
// 1. 创建cookie
document.cookie="username=John Doe";  
// 为 cookie 添加一个过期时间（以 UTC 或 GMT 时间）。默认情况下，cookie 在浏览器关闭时删除：
document.cookie="username=John Doe; expires=Thu, 18 Dec 2043 12:00:00 GMT";
// 可以使用 path 参数告诉浏览器 cookie 的路径。默认情况下，cookie 属于当前页面。
document.cookie="username=John Doe; expires=Thu, 18 Dec 2043 12:00:00 GMT; path=/";

// 2. 读取cookie
// 	document.cookie 将以字符串的方式返回所有的 cookie，类型格式： cookie1=value; cookie2=value; cookie3=value;
var x = document.cookie;

// 3. 修改cookie   修改 cookie 类似于创建 cookie
document.cookie="username=John Smith; expires=Thu, 18 Dec 2043 12:00:00 GMT; path=/";

// 4. 删除 Cookie
// 删除 cookie 非常简单。您只需要设置 expires 参数为以前的时间即可，如下所示，设置为 Thu, 01 Jan 1970 00:00:00 GMT:
// 当您删除时不必指定 cookie 的值。
document.cookie = "username=; expires=Thu, 01 Jan 1970 00:00:00 GMT";

```
###### 3. Cookie 字符串  
document.cookie 属性看起来像一个普通的文本字符串，其实它不是。  
即使您在 document.cookie 中写入一个完整的 cookie 字符串, 当您重新读取该 cookie 信息时，cookie 信息是以名/值对的形式展示的。  
如果您设置了新的 cookie，旧的 cookie 不会被覆盖。  


__________

### 七、 JS 库  JQuery  2022-04-25  
#### I JavaScript 库  
JavaScript 库 - JQuery 、 Prototype 、 MooTools  

###### 1. JavaScript 框架（库）  
JavaScript 高级程序设计（特别是对浏览器差异的复杂处理）。通常很困难也很耗时。  
为了应对这些调整，许多的 **JavaScript (helper)** 库应运而生。  
这些 JavaScript 库常被称为 **JavaScript 框架**。  
一些广受欢迎的 JavaScript 框架：  
* JQuery
* Prototype
* MooTools  
所有这些框架都提供针对常见 JavaScript 任务的函数，包括动画、DOM 操作以及 Ajax 处理。  

* JQuery  
jQuery 是目前最受欢迎的 JavaScript 框架。  
它使用 CSS 选择器来访问和操作网页上的 HTML 元素（DOM 对象）。  
jQuery 同时提供 companion UI（用户界面）和插件。  
许多大公司在网站上使用 jQuery：  Google  Microsoft IBM Netflix  
**教程:** <a href= "https://www.runoob.com/jquery/jquery-tutorial.html">链接</a>  
* Prototype  
Prototype 是一种库，提供用于执行常见 web 任务的简单 API。  
API 是应用程序编程接口（Application Programming Interface）的缩写。它是包含属性和方法的库，用于操作 HTML DOM。  
Prototype 通过提供类和继承，实现了对 JavaScript 的增强。  
* MooTools  
MooTools 也是一个框架，提供了可使常见的 JavaScript 编程更为简单的 API。  
MooTools 也含有一些轻量级的效果和动画函数。  
* 其他框架  
YUI - Yahoo! User Interface Framework，涵盖大量函数的大型库，从简单的 JavaScript 功能到完整的 internet widget。  
Ext JS - 可定制的 widget，用于构建富因特网应用程序（rich Internet applications）。  
Dojo - 用于 DOM 操作、事件、widget 等的工具包。  
script.aculo.us - 开源的 JavaScript 框架，针对可视效果和界面行为。  
UIZE - Widget、AJAX、DOM、模板等等。  

#### I JQuery 教程  
JQuery 是一个JavaScript 库，极大地简化了JavaScript 编程。  
###### 1. JQuery 说明  
|JQuery 选择器|描述|
|:---|:---|
|$(this).hide()|隐藏当前HTML元素|
|$("标签").hide()|隐藏所有的"标签"|
|$(".类名").hide()|隐藏相应类名的元素|
|$("#ID").hide()|隐藏相应ID名的元素|  

|JQuery 事件|描述|
|:---|:---|  
|$().click()|单击事件|  
|$().dbclick()|双击事件|  
|$().mouseenter()|鼠标移动到元素上触发事件|  
|$().mouseleave()|鼠标移动到指定元素，然后在离开触发事件|  
|$().mousedown()|鼠标左键按下触发事件|  
|$().mouseup()|鼠标左键按下，抬起时触发事件|  
|$().hover()|鼠标悬浮在元素上，触发事件|  
|$().focus()|元素获取焦点时触发事件|  
|$().blur()|元素失去焦点时触发事件|  

###### 2. JQuery 安装  
> * 网页中添加 jQuery  
> 1. 从 jquery.com 下载 jQuery 库  
> 2. 从 CDN 中载入 jQuery, 如从 Google 中加载 jQuery  
有两个版本的 jQuery 可供下载：Production version - 用于实际的网站中，已被精简和压缩。Development version - 用于测试和开发（未压缩，是可读的代码）  

```html
<!-- // 引入 -->
<head>
<script src="jquery-1.10.2.min.js"></script>
</head>
<!-- // JavaScript 是 HTML5 以及所有现代浏览器中的默认脚本语言！ -->
```
###### 3. JQuery 语法  
通过 jQuery，您可以选取（查询，query） HTML 元素，并对它们执行"操作"（actions）。  
* 基础语法： $(selector).action()  
* 美元符号定义 jQuery;
* 选择符（selector）"查询"和"查找" HTML 元素  
* jQuery 的 action() 执行对元素的操作  

**文档就绪事件**  
实例中的所有 jQuery 函数位于一个 document ready 函数中：  
```javascript
$(document).ready(function()
{
  // 代码
});
// 简洁语法
$(function()
{
  // 代码
});
```
这是为了防止文档在完全加载（就绪）之前运行JQuery代码，即在DOM加载完成之后才对DOM进行操作。  
如果在文档没有加载完成之前就运行函数，操作可能失败。  

######  4. JQuery 选择器 
jQuery 选择器允许您对 HTML 元素组或单个元素进行操作。  
jQuery 选择器基于元素的 id、类、类型、属性、属性值等"查找"（或选择）HTML 元素。  
它基于已经存在的 CSS 选择器，除此之外，它还有一些自定义的选择器。  
jQuery 中所有选择器都以美元符号开头：$()。  

4.1. 元素选择器  
jQuery 元素选择器基于元素名选取元素。  
在页面中选取所有 \<p> 元素:  $("p")    
```javascript
// 用户点击按钮后，所有 <p> 元素都隐藏：
$(function()
{
  $("button").click(
    function(){
      $("p").hide();
    });
});
```
4.2. #id 选择器  
jQuery #id 选择器通过 HTML 元素的 id 属性选取指定的元素。  
页面中元素的id应该是唯一的，所以您要在页面中选取唯一的元素需要通过 #id 选择器。  
通过 id 选取元素语法如下：  $("#test")
```javascript
// 当用户点击按钮后，有 id="test" 属性的元素将被隐藏：
$(document).ready(function()
{
  $("button").click(
    function(){
      $("#test").hide();
    });
});
```  

4.3. .class 选择器  
jQuery 类选择器可以通过指定的 class 查找元素。  
语法如下： $(".test")  
```javascript
// 用户点击按钮后所有带有 class="test" 属性的元素都隐藏：
$(function()
{
  $("button").click(
    function(){
      $(".test").hide();
    });
});
```  
4.4. 更多实例  

|语法|描述|
|:---|:---|
|\$("*")|选取所有元素|
|\$(this)|选取当前元素|
|\$("p.info")|选取class为info的p元素|  
|\$("ul li:first")|选取第一个ul元素的li元素|
|\$("ul li:first-child")|选取每一个ul元素的第一个li元素|
|\$("[href]")|选取带有href属性的元素|
|\$("a[target='_blank']")|选取target属性等于"_blank"的a元素|
|\$("a[target!='_blank']")|选取target属性不等于"_blank"的元素|
|\$(":button")|选取所有type="button"的input元素和所有的button元素|
|\$("tr:even")|选取偶数位置的tr元素|
|\$("tr:odd")|选取奇数位置的tr元素|  

###### 5. JQuery 事件  
jQuery 是为事件处理特别设计的。  
事件： 页面对不同访问者的响应叫做事件。  
事件处理程序指的是当 HTML 中发生某些事件时所调用的方法。  

#### II JQuery 效果
隐藏、显示、切换，滑动，淡入淡出，以及动画。  

###### 1. 效果

###### 2. JQuery CallBack 方法  
Callback 函数在当前动画 100% 完成之后执行。  
所以，被立即停止的动画不会触发回调，被立即完成的动画会触发回调。  
###### 3. JQuery 链 Chaining  
通过 jQuery，可以把动作/方法链接在一起。  
Chaining 允许我们在一条语句中运行多个 jQuery 方法（在相同的元素上）。  
直到现在，我们都是一次写一条 jQuery 语句（一条接着另一条）。  
不过，有一种名为链接（chaining）的技术，允许我们在相同的元素上运行多条 jQuery 命令，一条接着另一条。  
**提示：** 这样的话，浏览器就不必多次查找相同的元素。  
**实例**
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<script src="https://cdn.staticfile.org/jquery/1.10.2/jquery.min.js">
</script>
<script>
$(document).ready(function()
  {
  $("button").click(function(){
    $("#p1").css("color","red")
            .slideUp(2000)
            .slideDown(2000);
  });
});
</script>
</head>
<body>

<p id="p1">菜鸟教程!!</p>
<button>点我</button>

</body>
</html>
```

#### III JQuery HTML  
jQuery 拥有可操作 HTML 元素和属性的强大方法。  

###### 1. JQuery 捕获内容和属性
jQuery 拥有可操作 HTML 元素和属性的强大方法。  
**jQuery 中非常重要的部分，就是操作 DOM 的能力。**  
jQuery 提供一系列与 DOM 相关的方法，这使访问和操作元素和属性变得很容易。  
|方法|描述|
|:---|:---|
|text()|设置或返回所选元素的文本内容|
|html()|设置或返回所选元素的内容（包含html标签）|
|val()|设置或返回表单字段的值（例如input输入框的输入值）|
|prop|用于获取属性值。|
|attr|用于获取属性值。|

**实例**
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<script src="https://cdn.staticfile.org/jquery/1.10.2/jquery.min.js">
</script>
<script>
$(document).ready(function(){
  $("#btn1").click(function(){
    // 设置文本
    // $("#test1").text("Hello world!");
    console.log("Text: " + $("#test").text());  // Text: 这是段落中的 粗体 文本。
    
  });
  $("#btn2").click(function(){
    // 设置
    // $("#test2").html("<b>Hello world!</b>");
    console.log("HTML: " + $("#test").html()); // HTML: 这是段落中的 <b>粗体</b> 文本。
  });
  // 设置
  $("#btn3").click(function(){
    $("#test3").val("RUNOOB");
  });
  // 设置属性
  $("#runoob").attr({
        "href" : "http://www.runoob.com/jquery",
        "title" : "jQuery 教程"
    });
});
</script>
</head>

<body>
<p id="test">这是段落中的 <b>粗体</b> 文本。</p>
<button id="btn1">显示文本</button>
<button id="btn2">显示 HTML</button>
</body>
</html>
```
> prop() 和 attr() 的区别
> * prop()
> 1.如果有相应的属性，返回指定属性值。
> 2.如果没有相应的属性，返回值是空字符串。
> * attr()
> 1.如果有相应的属性，返回指定属性值。
> 2.如果没有相应的属性，返回值是空字符串。
> * 结论
> 对于HTML元素本身就带有的固有属性，在处理时，使用prop方法。
> 对于HTML元素我们自己自定义的DOM属性，在处理时，使用 attr 方法。
> 具有 true 和 false 两个属性的属性，如 checked, selected 或者 disabled 使用prop()。  

* 回调函数  
text()、html() 以及 val()，同样拥有回调函数。  
回调函数有两个参数：被选元素列表中当前元素的下标，以及原始（旧的）值。然后以函数新值返回您希望使用的字符串。  

**实例**
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<script src="https://cdn.staticfile.org/jquery/1.10.2/jquery.min.js">
</script>
<script>
$(document).ready(function(){
  $("#btn1").click(function(){
    $("#test1").text(function(i,origText){
      return "旧文本: " + origText + " 新文本: Hello world! (index: " + i + ")"; 
      // 旧文本: 这是一个有 粗体 字的段落。 新文本: Hello world! (index: 0)
    });
  });

  $("#btn2").click(function(){
    $("#test2").html(function(i,origText){
      return "旧 html: " + origText + " 新 html: Hello <b>world!</b> (index: " + i + ")"; 
      // 旧 html: 这是另外一个有 粗体 字的段落。 新 html: Hello world! (index: 0)
    });
  });

});
</script>
</head>

<body>
<p id="test1">这是一个有 <b>粗体</b> 字的段落。</p>
<p id="test2">这是另外一个有 <b>粗体</b> 字的段落。</p>
<button id="btn1">显示 新/旧 文本</button>
<button id="btn2">显示 新/旧 HTML</button>
</body>
</html>
```

###### 2. jQuery  设置内容和属性

###### 3. jQuery - 添加元素  
添加新的 HTML 内容

|方法|描述|
|:---|:---|
|append()|在被选元素的结尾插入内容|  
|prepend()|在被选元素的开头插入内容|
|after()|在被选元素的之后插入内容|
|before()|在被选元素的之前插入内容|  

① append() 方法在被选元素的结尾插入内容（仍然**在该元素的内部**）。  
**实例**
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<script src="https://cdn.staticfile.org/jquery/1.10.2/jquery.min.js">
</script>
<script>
  $(document).ready(function(){

    $("#btn1").click(function(){
      $("p").append(" <b>追加文本</b>。"); // 这是一个段落。 追加文本
    });

    $("#btn2").click(function(){
      $("ol").append("<li>追加列表项</li>"); // 4. 追加列表项
    });

  });
</script>
</head>

<body>
  <p>这是一个段落。</p> 。
  <p>这是另外一个段落。</p>
  <ol>
    <li>List item 1</li>
    <li>List item 2</li>
    <li>List item 3</li>
  </ol> 
  <button id="btn1">添加文本</button>
  <button id="btn2">添加列表项</button>
</body>
</html>
```
append() 和 prepend() 方法能够通过参数接收无限数量的新元素。可以通过 jQuery 来生成文本/HTML（就像上面的例子那样），或者通过 JavaScript 代码和 DOM 元素。  
**append() 和 prepend() 方法能够通过参数接收无限数量的新元素。可以通过 jQuery 来生成文本/HTML（就像上面的例子那样），或者通过 JavaScript 代码和 DOM 元素。**
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
<meta charset="utf-8">
<script src="https://cdn.staticfile.org/jquery/1.10.2/jquery.min.js">
</script>
<script>
  function appendText(){
    var txt1="<p>文本-1。</p>";              // 使用 HTML 标签创建文本
    var txt2=$("<p></p>").text("文本-2。");  // 使用 jQuery 创建文本
    var txt3=document.createElement("p");
    txt3.innerHTML="文本-3。";               // 使用 DOM 创建文本 text with DOM
    $("body").append(txt1,txt2,txt3);        // 追加新元素
  }
</script>
</head>
<body>
  <p>这是一个段落。</p>
  <button onclick="appendText()">追加文本</button>
</body>
</html>
``` 
② after() 和 before() 方法  
after() 方法在被选元素之后插入内容。 before() 方法在被选元素之前插入内容。  
**实例**
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <script src="https://cdn.staticfile.org/jquery/1.10.2/jquery.min.js"></script>
  <script>
    $(document).ready(function(){
      $("#btn1").click(function(){
        $("img").before("<b>之前</b>"); // 之前 图片
      });

      $("#btn2").click(function(){
        $("img").after("<i>之后</i>");  // 图片 之后
      });
    });
  </script>
</head>
<body>
  <img src="/images/logo.png" >
  <br><br>
  <button id="btn1">之前插入</button>
  <button id="btn2">之后插入</button>
</body>
</html>
```

###### 4. jQuery - 删除元素  
删除元素/内容  
一般可使用以下两个 jQuery 方法：  
* remove() - 删除被选元素（以及其子元素）  
* empty() - 从被选元素中删除子元素  

① 过滤被删除的元素  
remove() 方法也可接受一个参数，允许您对被删元素进行过滤。  
参数可以是任何 jQuery 选择器的语法。  
**实例**
```javascript
// 删除所有类名为italic的p元素
$(document).ready(function(){
  $("button").click(function(){
    $("p").remove(".italic");
  });
});
```

###### 5. jQuery - 获取并设置 CSS 类  
jQuery 操作CSS  
|方法|描述|
|:---|:---|
|addClass()|向被选中元素中添加一个或者多个类|
|removeClass()|向被选中元素中删除一个或多个类|
|toggleClass|相别选中元素进行添加/删除类的切换操作|
|css()|设置或者返回样式属性|

**实例**
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
  <script src="https://cdn.staticfile.org/jquery/1.10.2/jquery.min.js"></script>
  <script>
    
    $(document).ready(function(){
      // 向不同的元素添加 class 属性。
      $("button").click(function(){
        $("h1,h2,p").addClass("blue");
        $("div").addClass("important");
      });

      // 也可以在 addClass() 方法中规定多个类：
      $("button").click(function(){
        $("body div:first").addClass("important blue");
      });
      // removeClass() 方法 在不同的元素中删除指定的 class 属性
      $("button").click(function(){
        $("h1,h2,p").removeClass("blue");
      });
      // toggleClass() 方法 对被选元素进行添加/删除类的切换操作
      $("button").click(function(){
        $("h1,h2,p").toggleClass("blue");
      });

    });

    //

  </script>
  <style type="text/css">
    .important
    {
      font-weight:bold;
      font-size:xx-large;
    }
    .blue
    {
      color:blue;
    }
  </style>
</head>
<body>
  <h1>标题 1</h1>
  <h2>标题 2</h2>
  <p>这是一个段落。</p>
  <p>这是另外一个段落。</p>
  <div>这是一些重要的文本!</div>
  <br>
  <button>为元素添加 class</button>
</body>
</html>
```

**css() 方法**  
css() 设置或返回被选元素的一个或多个样式属性。  
语法：
css("propertyName")   
```javascript
$(function(){
  $("p").css("background-color");
});

```
设置css属性语法：
css("propertyName","value");  
css({"propertyName1":"value1","propertyName2":"value2",...})
```javascript
$(document).ready(function(){
  $("p").css("background-color":"red");
});
```  

###### 6. jQuery 尺寸  
BOX Module 结合
左外边距 左边框 左内边距 元素(高宽) 右内边距 右边框 右外边距

|处理方法|描述|
|:---|:---|
|width()|设置或返回元素的宽度（不包括内边距、边框或外边距），仅元素宽度|
|height()|设置或返回元素的高度（不包括内边距、边框或外边距），仅元素高度|
|innerWidth()|返回元素的宽度（包括内边距），元素宽度 + 左右内边距|
|interHeight()|返回元素的高度（包括内边距），元素高度 + 上下内边距|
|outerWidth()|返回元素的宽度（包括内边距和边框）。元素宽度 + 左右内边距 + 左右边框|
|outerHeight()|返回元素的高度（包括内边距和边框）。元素高度 + 上下内边距 + 上下边框|

**PS：** 设置box-sizing 属性之后，width()获取的是css设置的width - padding 的值
```html
<style>
  div {
    width:100px;
    height:100px;
    padding:10px;
    border:10px;
    box-sizing:border-box;
  }
</style>
<script>
  $(document).ready(function(){
    $("div").width(); // 80px
    $("div").innerWidth(); // 100px
    $("div").outerWidth(); // 100px
  });
  </script>
```

#### IV jQuery 遍历   
jQuery 遍历，意为"移动"，用于根据其相对于其他元素的关系来"查找"（或选取）HTML 元素。以某项选择开始，并沿着这个选择移动，直到抵达您期望的元素为止。  
可以向上、向下或者同级移动。  

###### 4.1. jQuery 祖先（向上）  
祖先是父、祖父或曾祖父等等。  
通过 jQuery，能够向上遍历 DOM 树，以查找元素的祖先。  

|方法|描述|
|:---|:---|
|parent()|返回被选元素的直接父元素。|
|parents()|返回被选元素的所有祖先元素，它一路向上直到文档的根元素 (<html>)。也可以使用可选参数来过滤对祖先元素的搜索。parents("body")|
|parentUntil()|返回介于两个给定元素之间的所有祖先元素。示例，$("span").parentsUntil("div").css({"color":"red","border":"2px solid red"});|

###### 4.2. jQuery 后代（向下）  
后代是子、孙、曾孙等等。  
通过 jQuery，您能够向下遍历 DOM 树，以查找元素的后代。  

|方法|描述|
|:---|:---|
|children()|返回被选元素的所有直接子元素。只会向下一级对 DOM 树进行遍历。参数可选$("div").children("p.1");|
|find()|返回被选元素的后代元素，一路向下直到最后一个后代。 $("div").find("span");, $("div").find("*");|

###### 4.3. jQuery 同胞（sibling）  
同胞拥有相同的父元素。 

|方法|描述|  
|:---|:---|  
|siblings()|返回被选元素的所有同胞元素。也使用可选参数来过滤对同胞元素的搜索。|
|next()|返回被选元素的下一个同胞元素。也使用可选参数来过滤对同胞元素的搜索。|
|nextAll()|返回被选元素的所有跟随的同胞元素。也使用可选参数来过滤对同胞元素的搜索。|
|nextUntil()|返回介于两个给定参数之间的所有跟随的同胞元素。|
|prev()|返回被选元素的上一个同胞元素。也使用可选参数来过滤对同胞元素的搜索。|
|prevAll()|返回被选元素的所有之上的同胞元素。也使用可选参数来过滤对同胞元素的搜索。|
|prevUntil()|返回介于两个给定参数之间的所有之上的同胞元素。|

###### 4.4. jQuery 遍历 - 过滤  
缩小搜索元素的范围  
三个最基本的过滤方法是：first(), last() 和 eq()，它们允许基于其在一组元素中的位置来选择一个特定的元素。  

① first() 返回被选元素的首个元素。  
```javascript
// 选取首个div内部的首个p元素
$(document).ready(function(){
  $("div p").first();
});
```
② last() 方法返回被选元素的最后一个元素。
```javascript
// 最后一个 <div> 元素中的最后一个 <p> 元素：  
$(document).ready(function(){
  $("div p").last();
});
```  
③ eq() 方法返回被选元素中带有指定索引号的元素。  
```javascript
// 索引号从 0 开始，因此首个元素的索引号是 0 而不是 1。
// 选取第二个 <p> 元素（索引号 1）：
$(document).ready(function(){
  $("p").eq(1);
});
```  
④ filter() 规定一个标准，不匹配这个标准的元素会被从集合中删除，匹配的元素会保留。  
```javascript
// 匹配所有带有类名url的p元素
$(document).ready(function(){
  $("p").filter(".url");
});
```
⑤ not() 不匹配标准的所有元素  
```javascript
// 返回不带有类名url的所有p元素
$(document).ready(function(){
  $("p").not(".url");
});
```

#### V jQuery AJAX 简介  
AJAX 是与服务器交换数据的技术，它在不重载全部页面的情况下，实现了对部分网页的刷新。  
###### 5.1 什么是AJAX？
AJAX = 异步 JavaScript 和 XML (Asynchronous JavaScript and XML)  
即，在不重载整个网页的情况下，AJAX通过后台加载数据，并在页面显示。  
**连接1：** https://www.runoob.com/jquery/ajax-ajax.html  
**连接2：** https://www.runoob.com/ajax/ajax-tutorial.html
jQuery 提供多个与 AJAX 有关的方法。  
通过 jQuery AJAX 方法，您能够使用 HTTP Get 和 HTTP Post 从远程服务器上请求文本、HTML、XML 或 JSON - 同时您能够把这些外部数据直接载入网页的被选元素中。  

###### 5.2 jQuery 中 AJAX 方法  

① load() 方法  
load() 方法从服务器加载数据，并把返回的数据放入被选的元素中。  
语法：
\$(selector).load(URL,data,callback);  
URL： 必须的，规定要加载的URL  
data：可选的，规定与请求一同发送的查询字符键/值对集合  
callback：可选的，load()完成后，所执行的函数  

② post() HTTP GET 请求从服务器请求数据。
语法：
\$(selector).get(URL,callback);
必需的 URL 参数规定请求的 URL。  
可选的 callback 参数是请求成功后所执行的函数名。

③ get() HTTP POST 请求从服务器请求数据。
语法：
\$(selector).post(URL,callback);

> HTTP 请求：GET vs POST
> 两种在客户端和服务器端进行请求-响应的常用方法是：GET 和 POST。
> GET - 从指定的资源请求数据  
> POST - 向指定的资源提交要处理的数据  
> GET 基本上用于从服务器获得（取回）数据。注释：GET 方法可能返回缓存数据。l
> POST 也可用于从服务器获取数据。不过，POST 方法不会缓存数据，并且常用于连同请求一起发送数据。
> 链接： https://www.runoob.com/tags/html-httpmethods.html  
> * 区别  
> 1. 发送的数据数量
> 在 GET 中，只能发送有限数量的数据，因为数据是在 URL 中发送的。
> 在 POST 中，可以发送大量的数据，因为数据是在正文主体中发送的。
> 2. 安全性
> GET 方法发送的数据不受保护，因为数据在 URL 栏中公开，这增加了漏洞和黑客攻击的风险。
> POST 方法发送的数据是安全的，因为数据未在 URL 栏中公开，还可以在其中使用多种编码技术，这使其具有弹性。  
> 3. 加入书签中
> GET 查询的结果可以加入书签中，因为它以 URL 的形式存在；而 POST 查询的结果无法加入书签中。
> 4. 编码
> 在表单中使用 GET 方法时，数据类型中只接受 ASCII 字符。
> 在表单提交时，POST 方法不绑定表单数据类型，并允许二进制和 ASCII 字符。
> 5. 可变大小
> GET 方法中的可变大小约为 2000 个字符。
> POST 方法最多允许 8 Mb 的可变大小。
> 6. 缓存
> GET 方法的数据是可缓存的，而 POST 方法的数据是无法缓存的。
> 7. 主要作用
> GET 方法主要用于获取信息。而 POST 方法主要用于更新数据。

④ noConflict() 方法  
如何在页面上同时使用 jQuery 和其他框架？  
jQuery 使用 $ 符号作为 jQuery 的简写。如果其他 JavaScript 框架也使用 $ 符号作为简写怎么办？  
在用的两种不同的框架正在使用相同的简写符号，有可能导致脚本停止运行。  
```javascript
// noConflict() 方法会释放对 $ 标识符的控制，这样其他脚本就可以使用它了。  
// 可以通过全名替代简写的方式来使用 jQuery
$.noConflict();
jQuery(document).ready(function(){
  jQuery("p").click(function(){
    this.hide();
  });
});

//也可以创建自己的简写。noConflict() 可返回对 jQuery 的引用，您可以把它存入变量，以供稍后使用。
jq = $.noConflict();
jq(function(){
  // ...
});

// 不愿意改变这个快捷方式，那么您可以把 $ 符号作为变量传递给 ready 方法。这样就可以在函数内使用 $ 符号了 - 而在函数外，依旧不得不使用 "jQuery"
$.noConflict();
jQuery(document).ready(function($){
  $("button").click(function(){
    $("p").hide();
  });
});

```  
###### 5.3 JSONP  
JSONP(JSON with Padding) 是JSON的一种使用方式，可以让网页从别的域名（网页）获取数据，即跨域读取数据。  
因为同源策略的存在，需要使用特殊的技术C才能实现跨域读取数据。  

① JSONP 应用  
**服务端JSONP格式数据**  
如客户想访问 : https://www.runoob.com/try/ajax/jsonp.php?jsoncallback=callbackFunction。  
假设客户期望返回数据：["customername1","customername2"]。
真正返回到客户端的数据显示为: callbackFunction(["customername1","customername2"])。

###### 5.4 jQuery 实例
**连接：**  https://www.runoob.com/jquery/jquery-examples.html


---
## 八、 JS ES6
ES6，全程ECMAScript6.0 是JavaScript下的一个标准版本，2015年06月发布。   

#### I ES6 let 与 const  
**暂时性死区**  
ES6 明文规定，代码块内如果存在let 或者 const，代码块会对这些命令声明的变量从块的开始就形成一个封闭作用域。  
```javascript
var PI = "a";
if(true){
  console.log(PI);  // ReferenceError: PI is not defined
  const PI = "3.14";
}
```  
**PS** const 如何做到变量在声明初始化之后不允许改变的？  
其实 const 其实保证的不是变量的值不变，而是保证变量指向的内存地址所保存的数据不允许改动。  
简单类型和复合类型保存值的方式是不同的。  
1. 对于简单类型（数值 number、字符串 string 、布尔值 boolean）,值就保存在变量指向的那个内存地址，因此 const 声明的简单类型变量等同于常量。  
2. 复杂类型（对象 object，数组 array，函数 function），变量指向的内存地址其实是保存了一个指向实际数据的指针，所以 const 只能保证指针是固定的，至于指针指向的数据结构变不变就无法控制了，所以使用 const 声明复杂类型对象时要慎重。  

#### II ES6 解构赋值  
解构赋值是对赋值运算符的一种扩展。    
是一种针对数组和对象进行模式匹配，然后对其中的变量进行赋值。  
在代码书写上简洁且易读，语义更加清晰明了；也方便了复杂对象中数据字段获取。  
###### 2.1 解构模型  
在解构中，有以下两部分参与：  
* 解构的源，解构赋值表达式的右部分。
* 解构的目标，解构赋值表达式的左部分。  

###### 3.2 数组模型的解构  
```javascript
// 1. 基本 
let [a,b,c] = [1,2,3] // a = 1,b = 2,c = 3

// 2. 可嵌套  
let [a, [[b],c]] = [1,[[2],3]];

// 3. 可忽略  
let [a,,c] = [1,2,3]; // a = 1,c = 3

// 4. 不完全解构
let [a = 1, b] = []; // a = 1, b = undefined

// 5. 剩余运算符
let [a,...b] = [1,2,3]; // a = 1,b = [2,3]

// 6. 字符串等等  
// 在数组的解构中，解构的目标若为可遍历对象，皆可进行解构赋值。可遍历对象即实现 Iterator 接口的数据。
let [a, b, c, d, e] = 'hello';
// a = 'h'
// b = 'e'
// c = 'l'
// d = 'l'
// e = 'o'-  

// 7. 解构默认值  
let [a = 2] = [undefined]; // a = 2
// 当解构模式有匹配结果，且匹配结果是 undefined 时，会触发默认值作为返回结果。  
let [a = 3, b = a] = [];     // a = 3, b = 3
let [a = 3, b = a] = [1];    // a = 1, b = 1
let [a = 3, b = a] = [1, 2]; // a = 1, b = 2 都可以正常解构

```  
###### 3.2 对象模型的解构  
```javascript
// 1. 基本  
let { foo, bar } = { foo: 'aaa', bar: 'bbb' };  // foo = 'aaa' bar = 'bbb'
let { baz : foo } = { baz : 'ddd' };  // foo = 'ddd' 

// 2. 嵌套可忽略 
let obj = {p: ['hello', {y: 'world'}] };
let {p: [x, { y }] } = obj;   // x = 'hello' y = 'world'  
let obj = {p: ['hello', {y: 'world'}] };
let {p: [x, {  }] } = obj;    // x = 'hello'

// 3. 不完全解构  
let obj = {p: [{y: 'world'}] };
let {p: [{ y }, x ] } = obj;  // x = undefined  y = 'world'  

// 4. 剩余运算符  
let {a, b, ...rest} = {a: 10, b: 20, c: 30, d: 40};
// a = 10
// b = 20
// rest = {c: 30, d: 40}

// 5. 解构默认值  
let {a = 10, b = 5} = {a: 3};   // a = 3; b = 5;  
let {a: aa = 10, b: bb = 5} = {a: 3};   // aa = 3; bb = 5;  

```

#### III ES6 Symbol 对象  
ES6 引入了一个新的原始对象 Symbol，表示独一无二的值，最大的用法是来定义对象的唯一属性。  
Symbol 函数栈不能使用 new 命令，因为Symbol 是一个原始数据类型，不是对象。  
可以接受一个字符串作为参数，为新创建的 Symbol 提供描述，用来显示在控制台或者作为字符串的时候使用，便于区分。  
```javascript
let sy = Symbol("KK");  
console.log(sy);   // Symbol(KK)
typeof(sy);        // "symbol"
// 相同参数 Symbol() 返回的值不相等
let sy1 = Symbol("KK"); 
sy == sy1; // false
sy === sy1; // false

```  

###### 3.1 使用场景  
1. 作为属性名  
由于每一个 Symbol 的值都是不相等的，所以 Symbol 作为对象的属性名，可以保证属性不重名。  
```javascript
let sy = Symbol("key1");

// 写法1
let syObject = {};
syObject[sy] = "kk";
console.log(syObject);  // {Symbol(key1): "kk"}
console.log(syObject[sy]);  // kk

// 写法2
let syObject = {
  [sy]: "kk"
};
console.log(syObject);   // {Symbol(key1): "kk"}

// 写法3  
let syObject = {};
Object.defineProperty(syObject, sy, {value: "kk"});
console.log(syObject);
```  
**Symbol 作为对象属性名时不能用.运算符，要用方括号。因为.运算符后面是字符串，所以取到的是字符串 sy 属性，而不是 Symbol 值 sy 属性。**  
**PS** Symbol 值作为属性名时，该属性是共有属性不是是有属性，可以在类的外部访问。但是不会出现在for...in、for...of的循环中，也不会被Object.keys()、Object.getOwnPropertyNames()返回。  
如果要读取一个对象的Symbol属性，可以通过Object.getOwnPropertySymbols() 和 Reflect.ownKeys()取到。  
```javascript
let sy = Symbol("key1");
let syObject = {};
syObject[sy] = "KK";
console.log(syObject); // {Symbol(key): 'KK'}

for(let i in syObject)
  console.log(i) // 无输出

Object.keys(syObject); // []
Object.getOwnPropertySymbols(syObject);   // [Symbol(key1)]
Reflect.ownKeys(syObject);                 // [Symbol(key1)]
```  

2. 定义常量

3. Symbol.for()  
Symbol.for()类似单例模式，首先会在全局搜索被登记的Symbol中是否有该字符串参数作为名称的 Symbol 值，如果有即返回该 Symbol 值，若没有则新建并返回一个以该字符串参数为名称的 Symbol 值，并登记在全局环境中供搜索。  
```javascript
let yellow = Symbol("Yellow");
let yellow1 = Symbol.for("Yellow");
yellow === yellow1; // false

let yellow2 = Symbol.for("Yellow");
yellow1 === yellow2; //true

console.log(Symbol.keyFor(yellow)); // undefined
console.log(Symbol.keyFor(yellow1)); // Yellow
console.log(Symbol.keyFor(yellow2)); // Yellow
```  

4. Symbol.keyFor()  
返回一个已登记的Symbol类型指的key，用来检测该字符串参数作为名称的Symbol值是否已被登记。  
```javascript
let yellow1 = Symbol.for("Yellow");
Symbol.keyFor(yellow1); // Yellow

```  

#### IV ES6 Map 与 Set  
Map 对象保存键值对。任何值（对象或者原始值）都可以作为一个键或一个值。  
> Map 和 Objects 的区别  
> * 一个Object的键只能是字符串或者Symbols，但一个Map的键可以是任意值。  
> * Map 中的键值是有序的（FIFO原则），而添加到对象Object中的键不是。  
> * Map 的键值对个数可以从size属性获取，而Object的键值对个数只能手动计算。  
> * Object 都有自己的原型，原型链的键名有可能和你自己在对象上的设置的键名产生冲突。  

###### 4.1 Map 中 键 key
1. key 是字符串
```javascript
var myMap = new Map();
var keyString = "a string"; 
myMap.set(keyString, "和键'a string'关联的值");
myMap.get(keyString);    // "和键'a string'关联的值"
myMap.get("a string");   // "和键'a string'关联的值"
                         // 因为 keyString === 'a string'
```
2. key 是对象  
```javascript
var myMap = new Map();
var keyObj = {}, 
 
myMap.set(keyObj, "和键 keyObj 关联的值");  

myMap.get(keyObj); // "和键 keyObj 关联的值"
myMap.get({}); // undefined, 因为 keyObj !== {}
```

3. key 是函数  
```javascript
var myMap = new Map();
var keyFunc = function () {}, // 函数
 
myMap.set(keyFunc, "和键 keyFunc 关联的值");
 
myMap.get(keyFunc); // "和键 keyFunc 关联的值"
myMap.get(function() {}) // undefined, 因为 keyFunc !== function () {}
```

4. key 是NaN  
虽然 NaN 和任何值甚至和自己都不相等(NaN !== NaN 返回true)，NaN作为Map的键来说是没有区别的。
```javascript
var myMap = new Map();
myMap.set(NaN, "not a number");
 
myMap.get(NaN); // "not a number"
 
var otherNaN = Number("foo");
myMap.get(otherNaN); // "not a number"
```  

###### 4.2 Map 的迭代  
1. for...of  
```javascript
var myMap = new Map();
myMap.set(0,"zero");
myMap.set(1,"one");
// 遍历
for(var [key,value] of myMap){
  console.log(key + "=" + value);
}
// 0=zero  1=one  

// 这个 entries 方法返回一个新的 Iterator 对象，它按插入顺序包含了 Map 对象中每个元素的 [key, value] 数组。
for(var [key,value] of myMap.entries()) {
  console.log(key + "+" + value);
}

// keys 方法返回一个新的 Iterator 对象， 它按插入顺序包含了 Map 对象中每个元素的键
for(var key of myMap.keys()) {
  console.log(key); // 0 1
}

//  values 方法返回一个新的 Iterator 对象，它按插入顺序包含了 Map 对象中每个元素的值
for(var value of myMap.values()) {
  console.log(value); // 0 1
}
```  

2. forEach()  
```javascript
var myMap = new Map();
myMap.set(0,"zero");
myMap.set(1,"one");

myMap.forEach(function(value,key) {
  console.log(key + "=" + value);
});
```  

###### 4.3 Map 对象的操作  
1. Map 与 Array的转换  
```javascript
var kvArray = [["key1":"value1"],["key2":"value2"]];

// Map 构造函数可以将一个 二维 键值对数组转换成一个 Map 对象  
var myMap = new Map(kvArray);

// 使用 Array.from 函数可以将一个 Map 对象转换成一个二维键值对数组  
var outArray = Array.from(myMap);
```  
2. Map 克隆  
```javascript
var myMap1 = new Map([["key1":"value1"],["key2":"value2"]]);
var myMap2 = new Map(myMap1);
// Map 对象构造函数生成实例，迭代出新的对象。
```

3. Map 的合并  
```javascript
var first = new Map([[1, 'one'], [2, 'two'], [3, 'three'],]);
var second = new Map([[1, 'uno'], [2, 'dos']]);  
// 合并两个 Map 对象时，如果有重复的键值，则后面的会覆盖前面的，对应值即 uno，dos，three
var merged = new Map([...first, ...second]);
```  

#### V Set 对象  
Set 对象允许你存储任何类型的唯一值，无论是原始值或者是对象引用。  
* Set 对象存储的值总是唯一的，所以需要判断两个值是否恒等。有几个特殊值需要特殊对待  
* +0 与 -0 在存储判断唯一性的时候是恒等的，所以不重复；  
* undefined 与 undefined 是恒等的，所以不重复；  
* NaN 与 NaN 是不恒等的，但是在 Set 中只能存一个，不重复。  

```javascript
let mySet = new Set();
 
mySet.add(1); // Set(1) {1}
mySet.add(5); // Set(2) {1, 5}
mySet.add(5); // Set(2) {1, 5} 这里体现了值的唯一性
mySet.add("some text"); 
// Set(3) {1, 5, "some text"} 这里体现了类型的多样性
var o = {a: 1, b: 2}; 
mySet.add(o);
mySet.add({a: 1, b: 2}); 
// Set(5) {1, 5, "some text", {…}, {…}} 
// 这里体现了对象之间引用不同不恒等，即使值相同，Set 也能存储
```  
###### 5.1 类型转换  
* Array
```javascript
// Array 转 Set
var mySet = new Set(["value1","value2","value3"]);  

// 用...操作符，将Set 转 Array  
var myArray = [...mySet];
// 或
vat myArray = Array.from(mySet);
```  
* String  
```javascript
// String 转 Set
var mySet = new Set("hello"); // Set(4) {"h", "e", "l", "o"}
// 注：Set 中 toString 方法是不能将 Set 转换成 String
```  
###### 5.2 Set 对象的作用  
1. 数组去重  
```javascript
var mySet = new Set([1,2,3,4,4]);
console.log([...mySet]); // [1, 2, 3, 4]
```
2. 并集  
```javascript
var a = new Set([1,2,3]);
var b = new Set([4,2,3]);
var union = new Set([...a,...b]);
console.log(union);  //  {1, 2, 3, 4}
```  

3. 交集
```javascript
var a = new Set([1,2,3]);
var b = new Set([4,2,3]);
var intersect = new Set([...a].filter(x => b.has(x))); // a与b的差
console.log(intersect);
```

4. 差集  
```javascript
var a = new Set([1,2,3]);
var b = new Set([4,2,3]);
var diff = new Set([...a].filter(x => !b.has(x))); 
console.log(diff); // {1}
```

#### VI ES6 Reflect 与 Proxy 


#### VII ES6 字符串  
**拓展的方法**  
1. 子字符串的识别：ES6 之前判断字符串是否包含子串，用 indexOf 方法，ES6 新增了子串的识别方法。
* str.includes(substr)：返回布尔值，判断是否找到参数字符串。
* str.startsWith(substr)：返回布尔值，。。。。。。。。。。是否在开头
* str.endsWith(substr)：返回布尔值，。。。。。。。。。。是否在结尾

2. 字符串重复 .repeat()

3. 字符串补全
* padStart(length,value)： 返回新的字符串，表示用参数字符串从头部（左侧）补全原字符串。
* padEnd：
**实例**  
```javascript
console.log("h".padStart(5,"o")); // ooooh
console.log("123".padStart(10,"0"));  // "0000000123"
```

4. 模板字符串  
模板字符串相当于加强版的字符串，用反引号``，除了作为普通字符串，还可以用来定义多行字符串，还可以在字符串中添加变量和表达式。  
* 基本用法  
```javascript
// 普通字符串
let string = `Hello '\n' world`;
// Hello
// world

// 多行字符串
let string1 = `Hey,
can you stop angry with me now`;
// Hey,
// .....

// 字符串中插入变量和表达式
// ${} 中可以房子变量名和JavaScript表达式
let name = "LiMing";
let age = 24;
let info = `My name is ${name}, I am ${age + 1} years old net year.`;
// ...

// 字符串中调用函数
function f() { return "have fun!";}
let string2 = `Game Start,${f()}`;

```
**PS:** 模板字符串中的换行和空格都是会被保留的。

* 标签模板
是一个函数的调用，其中调用的参数是模板字符串。  
```javascript
alert`Hello world~`;
// 等价于
alert('Hello world!');
```
当模板字符串中带有变量，会将模板字符串参数处理成多个参数。
```javascript

function f(stringArr,...values){
 let result = "";
 for(let i=0;i<stringArr.length;i++){
  result += stringArr[i];
  if(values[i]){
   result += values[i];
        }
    }
 return result;
}
let name = 'Mike';
let age = 27;
f`My Name is ${name},I am ${age+1} years old next year.`;
// "My Name is Mike,I am 28 years old next year."
 
f`My Name is ${name},I am ${age+1} years old next year.`;
// 等价于
f(['My Name is',',I am ',' years old next year.'],'Mike',28);

```


#### VIII ES6 数值  
###### 8.1 数值的表示  
* 二进制表示新写法：前缀0b 或 0B
```javascript
console.log(ob11 === 3); // true
```
* 八进制表示新写法：前缀0o 或 0O
```javascript
console.log(0o11 === 9); // true
```

* 常量  
Number.EPSILON  
Number.EPSILON 属性表示1与大于1的最小浮点数之间的差  
它的值接近于 2.2204460492503130808472633361816E-16，或者 2-52。  
```javascript
// 测试数值是否在误差范围内:
0.1 + 0.2 === 0.3; // false
// 在误差范围内即视为相等
equal = (Math.abs(0.1 - 0.3 + 0.2) < Number.EPSILON); // true
```  

* 属性特性  

#### IX ES6 对象
1. 对象字面量  
* 属性的简洁表示法  
ES6 允许对象的属性直接写变量，这时候属性名是变量名，属性值也是变量名  
```javascript
const age = 12;
const name = "Amy";
const person = {age, name};
person   //{age: 12, name: "Amy"}
//等同于
const person = {age: age, name: name}

```

2. 对象的扩展运算符  
扩展运算符(...)用于取出参数对象所有可遍历属性，然后拷贝到当前对象。
* 基本用法  
```javascript
let person = {name: "Amy", age: 15};
let someone = {...person};
console.log(someone); //  {name: "Amy", age: 15}
```
* 可用于合并两个对象  
```javascript
let age = {age: 15};
let name = {name: "Amy"};
let person = {...age,...name};
console.log(person); //  {age:15,name: "Amy"}
```  
**PS:** 自定义的属性和扩展运算符对象里面属性相同的时候：  
自定义属性在扩展运算符后面，则扩展运算符对象内部同名的属性将被覆盖掉。  
```javascript
let person = {name: "Amy",age:15};
let someone = {...person2, name: "Mike", age: 17};
console.log(someone); // { name: "Mike", age: 17}

// 自定义属性在扩展运算符前面，则变成设置新对象默认属性值。
let person = {name: "Amy", age: 15};
let someone = {name: "Mike", age: 17, ...person};
someone;  //{name: "Amy", age: 15}

// 拓展运算符后面是空对象，没有任何效果也不会报错。
let a = {...{}, a: 1, b: 2};
a;  //{a: 1, b: 2}

// 拓展运算符后面是null或者undefined，没有效果也不会报错。
let b = {...null, ...undefined, a: 1, b: 2};
b;  //{a: 1, b: 2}
```

3. 对象 Object 的新方法  
* Object.assign(target,source_1, ...)
用于将元数据的所有可枚举属性复制到目标对象中
```javascript
// 基本用法
let target = {a: 1};
let object2 = {b: 2};
let object3 = {c: 3};
Object.assign(target,object2,object3);  
// 第一个参数是目标对象，后面的参数是源对象
target;  // {a: 1, b: 2, c: 3 }
```
**PS：**  
如果目标对象和源对象有同名属性，或者多个源对象有同名属性，则后面的属性会覆盖前面的属性。  
如果该函数只有一个参数，当参数为对象时，直接返回该对象；当参数不是对象时，会先将参数转为对象然后返回。  
因为null 和 undefined 不能转化为对象，所以会报错。
```javascript
Object.assign(3);         // Number {3}
typeof Object.assign(3);  // "object"

Object.assign(null);       // TypeError: Cannot convert undefined or null to object
Object.assign(undefined);  // TypeError: Cannot convert undefined or null to object
// 当参数不止一个时，null 和 undefined 不放第一个，即不为目标对象时，会跳过 null 和 undefined ，不报错
Object.assign(1,undefined);  // Number {1}
Object.assign({a: 1},null);  // {a: 1}
 
Object.assign(undefined,{a: 1});  // TypeError: Cannot convert undefined or null to object

// 同名属性替换：
targetObj = { a: { b: 1, c:2}};
sourceObj = { a: { b: "hh"}};
Object.assign(targetObj, sourceObj);
targetObj;  // {a: {b: "hh"}}

// 数组处理
Object.assign([2,3], [5]);  // [5,3]
// 会将数组处理成对象，所以先将 [2,3] 转为 {0:2,1:3} ，然后再进行属性复制，所以源对象的 0 号属性覆盖了目标对象的 0。
```
**PS:**
assign 的属性拷贝是浅拷贝：
复制的对象共用一个内存地址，修改其中一个属性值，会影响另一个的属性值。  

* Object.is(value1,value2)  
用来比较两个值是否严格相等。
**基本用法** 
```javascript
Object.is("q","q"); // true
Object.is(1,1); // true
Object.is([1],[1]) // false
Object.is({q:1},{q,1}) // false

// 与 (===) 的区别
// +0不等于-0
// NaN 等于本身
```


#### X ES6 数组  
###### 10.1 数组创建  
1. Array.of()
将参数中所有值作为元素形成数组  
```javascript
console.log(Array.of(1,2,3,4)); [1,2,3,4]

// 参数值可以是不同类型  
console.log(Array.of(1,'2',true));  // [1,'2',true]

// 参数为空时，返回空数组
console.log(Array.of());  // []
```
2. Array.from()  
将类数组对象或可迭代对象转化为数组。也可以使用slice方法
```javascript
// 参数为数组,返回与原数组一样的数组
console.log(Array.from([1, 2])); // [1, 2]
 
// 参数含空位
console.log(Array.from([1, , 3])); // [1, undefined, 3]
```  
语法：
Array.from(arrayLike[, mapFn[, thisArg]]);
返回值为转换后的数组。  
```javascript
// arrayLike  想要转换的类数组对象或可迭代对象。  
console.log(Array.from([1, 2, 3])); // [1, 2, 3]

//mapFn 可选，map 函数，用于对每个元素进行处理，放入数组的是处理后的元素。
console.log(Array.from([1, 2, 3], (n) => n * 2)); // [2, 4, 6]

// thisArg 可选，用于指定 map 函数执行时的 this 对象。
let map = {
    do: function(n) {  return n * 2; }
}
let arrayLike = [1, 2, 3];
console.log(Array.from(arrayLike, function (n){
    return this.do(n);
}, map)); // [2, 4, 6]
```  
**类数组对象**  
一个类数组对象必须含有 length 属性，且元素属性名必须是数值或者可转换为数值的字符。  
```javascript
let arr = Array.from({
  0: '1',
  1: '2',
  2: 3,
  length: 3
});
console.log(arr); // ['1', '2', 3]
 
// 没有 length 属性,则返回空数组
let array = Array.from({
  0: '1',
  1: '2',
  2: 3,
});
console.log(array); // []
 
// 元素属性名不为数值且无法转换为数值，返回长度为 length 元素值为 undefined 的数组  
let array1 = Array.from({
  a: 1,
  b: 2,
  length: 2
});
console.log(array1); // [undefined, undefined]
```
**PS：** from() 根据length来创建数组，长度就是length属性值
**转换可迭代对象**  
* 转换 map
```javascript
let map = new Map();
map.set('key0','value0');
map.set('key1','value1');
console.log(Array.from(map));
// [['key0', 'value0'],['key1','value1']]
```
* 转换 set
```javascript
let arr = [1,2,3]
let set = new Set(arr);
console.log(Array.from(set)); // [1,2,3]
```
* 转换字符串
```javascript
let str = "hello";
console.log(Array.from(str)); // ['h', 'e', 'l', 'l', 'o']
```

###### 10.2 扩展方法  
1. find()
2. findeIndex()
3. fill()
4. entries()
5. keys()
6. values()
7. includes()
8. flat()
9. faltMap()

###### 10.3 数组缓冲区
数组缓冲区是内存中的一段地址。  
定型数组的基础。  
实际字节数在创建时确定，之后只可以修改其中的数据，不可以修改大小。  

* 创建数组缓冲区  
```javascript
let buffer = new ArrayBuffer(10);
console.log(buffer.byteLength); // 10
// 分割已有的数组缓冲区
let buffer1 = buffer.slice(1,3);
console.log(buffer1.byteLength); // 2
```
* 视图  
视图是用来操作内存的接口。  
视图可以操作数组缓冲区或缓冲区字节的子集，并按照其中一种数值数据类型来读取和写入数据。  
DataView类型是一种通用的数组缓冲区视图，其支持所有8种数值型数据类型。
```javascript
// 默认 DataView 可操作数组缓冲区全部内容
let buffer = new ArrayBuffer(10);
    dataView = new DataView(buffer); 
dataView.setInt8(0,1);
console.log(dataView.getInt8(0)); // 1
 
// 通过设定偏移量(参数2)与长度(参数3)指定 DataView 可操作的字节范围
let buffer1 = new ArrayBuffer(10);
    dataView1 = new DataView(buffer1, 0, 3); // 0,1,2可以用
dataView1.setInt8(5,1); // RangeError 
```

###### 10.4 定型数组  
数组缓冲区的特定类型的视图。  
可以强制使用特定的数据类型，而不是使用通用的DataView对象来操作数组缓冲区。  
* 创建  
通过数组缓冲区生成
```javascript
let buffer = new ArrayBuffer(10);
  view = new Int8Array(buffer);
console.log(view.byteLength); //10
```  
通过构造函数
```javascript
let view = new Int32Array(10);
console.log(view.byteLength); // 40
console.log(view.length); // 10

// 不传参则默认长度为0
// 在这种情况下数组缓冲区分配不到空间，创建的定型数组不能用来保存数据
let view1 = new Int32Array();
console.log(view1.byteLength); // 0
console.log(view1.length);     // 0

// 可接受参数包括定型数组、可迭代对象、数组、类数组对象
let arr = Array.from({
  0: '1',
  1: '2',
  2: 3,
  length: 3
});
let view2 = new Int16Array([1, 2]),
    view3 = new Int32Array(view2),
    view4 = new Int16Array(new Set([1, 2, 3])),
    view5 = new Int16Array([1, 2, 3]),
    view6 = new Int16Array(arr);
console.log(view2 .buffer === view3.buffer); // false
console.log(view4.byteLength); // 6
console.log(view5.byteLength); // 6
console.log(view6.byteLength); // 6
```

**PS:** 
定型数组可以使用entries()、keys()、values()进行迭代。  
```javascript
let view = new Int16Array([1,2]);
for(let [key,value] of view.entries()) {
  console.log(key + ':' + value);
}
// 0:1
// 1:2
```  
###### 10.5 扩展运算符  
* 复制数组  
```javascript
let arr = [1,2];
arr1 = [..arr]; // [1,2]

// 数组含有空位
let arr = [1,,2];
arr1 = [..arr]; // [1,undefined,2]
```
* 合并数组
```javascript
[...arr1,...arr2]
```

#### XI ES6 函数
###### 11.1 函数参数的扩展  
1. 默认参数
```javascript
function fn(name,age = 17) {
  console.log(name + "," + age);
}
// PS：使用函数默认参数时，不允许有同名参数，会报错
// null 值被认为是有效的值传递
```
2. 不定参数  
不定参数用来表示不确定参数个数，形如，...变量名，由...加上一个具名参数标识符组成。具名参数只能放在参数组的最后，并且有且只有一个不定参数。  

###### 11.2 箭头函数  
**PS：**  
箭头函数没有 this、super、arguments和new.target绑定。  
箭头函数体中的this对象，是定义函数时的对象，而不是使用函数时的对象。  
不可以作为构造函数，也就是不能使用new命令，否则会报错。  

* 适合使用的场景  
ES6 之前，JavaScript 的 this 对象一直很令人头大，回调函数，经常看到 var self = this 这样的代码，为了将外部 this 传递到回调函数中，那么有了箭头函数，就不需要这样做了，直接使用 this 就行。  
```javascript
// 回调函数
var Person = {
    'age': 18,
    'sayHello': function () {
      setTimeout(function () {
        console.log(this.age);
      });
    }
};
var age = 20;
Person.sayHello();  // 20
 
var Person1 = {
    'age': 18,
    'sayHello': function () {
      setTimeout(()=>{
        console.log(this.age);
      });
    }
};
var age = 20;
Person1.sayHello();  // 18
```
* 不适合使用的场景  
1. 定义函数的方法，且该方法中包含this。  
```javascript
var person = {
  'age':18,
  'sayHello': () => {
    console.log(this.age);
  }
};
var age = 20;
person.sayHello(); // 20
var person1 = {
  'age':18,
  'sayHello':fucntion() {
    console.log(this.age);
  }
};
var age = 20;
person1.sayHello(); // 18
```
2. 需要动态this的时候  
例如，做为事件函数时  
```javascript
var button = document.getElementById('userClick');
button.addEventListener('click',() => {
  this.classList.toggle('on');
});
```
button的监听函数是箭头函数，所以监听函数里面的this指向的是定义的时候外层的this对象，即window，导致无法操作到被点击的按钮对象。

#### XII Class 类  
在ES6中，class (类)作为对象的模板被引入，可以通过 class 关键字定义类。  
class 的本质是 function。  
它可以看作一个语法糖，让对象原型的写法更加清晰、更像面向对象编程的语法。  

#### XIII 模块  
在ES6之前，实现模块化使用的是RequireJS 或者 seaJS（分别是基于AMD规范的模块化库，和基于CMD规范的莫阔花裤）。
ES6引入模块化，设计思想是在编译时就能够确定模块的依赖关系，以及输入和输出的变量。  
ES6的模块化分为导出export与导入import两个模块。  
**特点**  
ES6 的模块自动开启严格模式，use strict  
模块中可以导入和导出各种类型的变量，比如函数，对象，字符串，数字，布尔值，类等  
每个模块都有自己的上下文，每一个模块内声明的变量都是局部变量，不会污染全局作用域。  
每一个模块只加载一次（是单例的），若再去加载同目录下同文件，直接从内存中读取。  

* export 与 import  
基本用法  
模块导入导出各种类型的变量，如字符串、数值、函数、类。  
① 导出的函数声明与类声明必须要有名称（export default命令另外考虑）  
② 不仅能导出声明还能导出引用（例如函数）
③ export命令可以出现在模块的任何位置，但是必须处于模块顶层
④ import命令会提升到整个模块的头部，首先执行

```javascript
/*-----export [test.js]-----*/
let myName = "Tom";
let myAge = 20;
let myfn = function(){
    return "My name is" + myName + "! I'm '" + myAge + "years old."
}
let myClass =  class myClass {
    static a = "yeah!";
}
export { myName, myAge, myfn, myClass }
 
/*-----import [xxx.js]-----*/
import { myName, myAge, myfn, myClass } from "./test.js";
console.log(myfn());// My name is Tom! I'm 20 years old.
console.log(myAge);// 20
console.log(myName);// Tom
console.log(myClass.a );// yeah!

```
建议使用大括号指定要输出的一组变量写在文档尾部，明确导出的接口。  
函数和类都需要有对应的名称，导出文档尾部也避免了无对应名称。

* as 的用法  
export 命令导出的接口名称，须和模块内部的变量有一一对应关系。  
导入的变量名，须和导出接口名称相同，即顺序可以不一致。  
```javascript
/*-----export [test.js]-----*/
let myName = "Tom";
export { myName as exportName }
 
/*-----import [xxx.js]-----*/
import { exportName } from "./test.js";
console.log(exportName);// Tom
// 使用 as 重新定义导出的接口名称，隐藏模块内部的变量

// 2. 不同模块导出接口名称命名重复， 使用 as 重新定义变量名。
/*-----export [test1.js]-----*/
let myName = "Tom";
export { myName }
/*-----export [test2.js]-----*/
let myName = "Jerry";
export { myName }
/*-----import [xxx.js]-----*/
import { myName as name1 } from "./test1.js";
import { myName as name2 } from "./test2.js";
console.log(name1);// Tom
console.log(name2);// Jerry
```
**import命令的特点**  
**只读属性：** 不允许在加载模块的脚本练，改写接口的引用指向，即可以改写import变量类型为对象的属性值，不能改写import变量为基本类型的值。
```javascript
import {a} from "./xxx.js"
a = {}; // error

a.foo = "hello"; // a = {foo: 'hello'}
```
**单例模式：** 多次重复执行同一句import语句，那么只会执行一次，而不会执行多次。