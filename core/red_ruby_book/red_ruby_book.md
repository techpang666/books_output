
# **红宝书输出行动⚡️**
>品读一下 动动手code一下  
>[一些勘误及资源](https://www.ituring.com.cn/book/2472)  

------
## **210520**

>前言

这可不是寻常的民房，而是一间“黑客屋”，里面十几位才华横溢的软件工程师经常通宵达旦地工作。虽然过的不是什么高档次生活——他们坐的都是别人扔在大街上的那种沙发床和旧椅子——他们在这间房子里每天所写代码的数量和质量却引人瞩目。连续工作几小时后，大多数人会把精力投入到公司的另一个子项目上，然后又是几个小时的工作。不太会写代码的人也常受启发，发现自己学习的渴望，然后仅仅几个星期后就变成了代码能手

Brendan  Eich只用10天就写出了JavaScript的第一版

ECMA-262规范定义了JavaScript，但JavaScript没有唯一正确的实现

与其宿主关系密切。实际上宿主为JavaScript定义了与外界交互所需的全部API：DOM、网络请求、系统硬件、存储、事件、文件、加密，还有数以百计的其他API

Chrome有Blink/V8，Firefox有Gecko/SpiderMonkey，Safari有WebKit/JavaScriptCore，微软有Trident/EdgeHTML/Chakra

对JavaScript更准确的定位应该是一组浏览器实现

Proxy（代理）和Reflect（反射） API。代理和反射用于拦截和修改这门语言的基本操作

在变量超出作用域时如何回收内存

内置引用类型，包括Object、Array、Map、WeakMap、Set和WeakSet

Promise类型和async/await

ES6类及其与原型式继承的紧密关系

所有BOM对象都会涉及，包括window、document、location、navigator和screen等

事件在JavaScript中的本质

早期的XMLHttpRequest和现代的Fetch API

------
## **210521**

>什么是JavaScript

1995年，JavaScript问世

在此之前，要验证某个必填字段是否已填写，或者某个输入的值是否有效，需要与服务器的一次往返通信

匿名（lambda）函数

元编程

闭包

要真正学好用好JavaScript，理解其本质、历史及局限性是非常重要的

Mocha/LiveScript/JavaScript

它在服务器端叫LiveWire

微软发布了IE3，其中包含自己名为JScript（叫这个名字是为了避免与网景发生许可纠纷）的JavaScript实现

1997年，JavaScript 1.1作为提案被提交给欧洲计算机制造商协会（Ecma）

ECMA-262，也就是ECMAScript（发音为“ek-ma-script”）这个新的脚本语言标准

1998年，国际标准化组织（ISO）和国际电工委员会（IEC）也将ECMAScript采纳为标准（ISO/ IEC-16262）

自此以后，各家浏览器均以ECMAScript作为自己JavaScript实现的依据

>JavaScript实现

- 核心（ECMAScript）
- 文档对象模型（DOM）
- 浏览器对象模型（BOM）

这门语言没有输入和输出之类的方法

Web浏览器只是ECMAScript实现可能存在的一种宿主环境

其他宿主环境还有服务器端JavaScript平台Node.js

如果不涉及浏览器的话，ECMA-262到底定义了什么？在基本的层面，它描述这门语言的如下部分：
- 语法
- 类型
- 语句
- 关键字
- 保留字
- 操作符
- 全局对象

ECMA-262要求支持Unicode标准（以支持多语言）

对象要与平台无关（Netscape JavaScript 1.1的对象不是这样，比如它的Date对象就依赖平台）

ECMA-262第3版第一次真正对这个标准进行更新

更新了字符串处理、错误定义和数值输出。此外还增加了对正则表达式、新的控制语句、try/catch异常处理的支持

这标志着ECMAScript作为一门真正的编程语言的时代终于到来了

第4版包括强类型变量、新语句和数据结构、真正的类和经典的继承，以及操作数据的新手段

第4版对这门语言来说跳跃太大了 ECMA-262第4版在正式发布之前被放弃

ECMAScript3.1变成了ECMA-262的第5版，于2009年12月3日正式发布

原生的解析和序列化JSON数据的JSON对象、方便继承和高级属性定义的方法，以及新的增强ECMAScript引擎解释和执行代码能力的严格模式

ECMA-262第6版，俗称ES6、ES2015或ES  Harmony（和谐版），于2015年6月发布

ES6正式支持了类、模块、迭代器、生成器、箭头函数、期约、反射、代理和众多新的数据类型

ECMA-262第7版，也称为ES7或ES2016，于2016年6月发布

Array.prototype.includes和指数操作符

ECMA-262第8版，也称为ES8、ES2017，完成于2017年6月

- 异步函数（async/await）
- SharedArrayBuffer
- Atomics API
- Object.values()/Object.entries()/Object. getOwnPropertyDescriptors()
- 字符串填充方法
- 支持对象字面量最后的逗号

ECMA-262第9版，也称为ES9、ES2018，发布于2018年6月

- 异步迭代
- 剩余和扩展属性
- 一组新的正则表达式特性
- Promise finally()
- 模板字面量修订

ECMA-262第10版，也称为ES10、ES2019，发布于2019年6月

- Array.prototype.flat()/flatMap()
- String.prototype.trimStart()/trimEnd()
- Object.fromEntries()
- Symbol.prototype.description
- 定义了Function.prototype.toString()的返回值
- 固定了Array.prototype.sort()的顺序
- 解决了与JSON字符串兼容的问题
- 定义了catch子句的可选绑定

>ECMAScript符合性是什么意思

- 支持ECMA-262中描述的所有“类型、值、对象、属性、函数，以及程序语法与语义”；
- 支持Unicode字符标准。

符合性实现还可以满足下列要求。

- 增加ECMA-262中未提及的“额外的类型、值、对象、属性和函数”。ECMA-262所说的这些额外内容主要指规范中未给出的新对象或对象的新属性。
- 支持ECMA-262中没有定义的“程序和正则表达式语法”（意思是允许修改和扩展内置的正则表达式特性）

JavaScript 1.3增加了对Unicode标准的支持，并做到了所有对象都与平台无关，同时保留了JavaScript 1.2所有的特性

2008年，五大浏览器（IE、Firefox、Safari、Chrome和Opera）全部兼容ECMA-262第3版

IE8率先实现ECMA-262第5版，并在IE9中完整支持。Firefox  4很快也做到了

>文档对象模型（DOM，Document Object Model）

应用编程接口（API），用于在HTML中使用扩展的XML

DOM将整个页面抽象为一组分层节点 HTML或XML页面的每个组成部分都是一种节点 包含不同的数据

```html
<html>
  <head>
    <title>Sample Page</title>
  </head>
  <body>
    <p>Hello World!</p>
  </body>
</html>
```

**上面的代码可以通过DOM解析为下面的节点结构**

- html
  - head
    - title
      - Sample Page
  - body
    - p
      - Hello World!

DOM通过创建表示文档的树，让开发者可以随心所欲地控制网页的内容和结构

使用DOM API，可以轻松地删除、添加、替换、修改节点

------
## **210522**

>为什么DOM是必需的

由于网景和微软采用不同思路开发DHTML，开发者写一个HTML页面就可以在任何浏览器中运行的好日子就此终结

就在这时，万维网联盟（W3C，World Wide Web Consortium）开始了制定DOM标准的进程

1998年10月，DOM Level 1成为W3C的推荐标准

这个规范由两个模块组成：DOM Core和DOM HTML

前者提供了一种映射XML文档，从而方便访问和操作文档任意部分的方式

后者扩展了前者，并增加了特定于HTML的对象和方法

DOM并非只能通过JavaScript访问，而且确实被其他很多语言实现了

不过对于浏览器来说，DOM就是使用ECMAScript实现的

如今已经成为JavaScript语言的一大组成部分

DOM Level 1的目标是映射文档结构，而DOM Level 2的目标则宽泛得多

增加了对鼠标和用户界面事件、范围、遍历（迭代DOM节点的方法）的支持

通过对象接口支持了层叠样式表（CSS）

DOM Level 1中的DOM Core也被扩展以包含对XML命名空间的支持

DOM Level 2新增了以下模块，以支持新的接口

- DOM视图：描述追踪文档不同视图（如应用CSS样式前后的文档）的接口
- DOM事件：描述事件及事件处理的接口
- DOM样式：描述处理元素CSS样式的接口
- DOM遍历和范围：描述遍历和操作DOM树的接口

DOM Level 3增加了以统一的方式加载和保存文档的方法（包含在一个叫DOM Load and Save的新模块中）

还有验证文档的方法（DOM Validation）

在Level 3中，DOM Core经过扩展支持了所有XML 1.0的特性，包括XML Infoset、XPath和XML Base

W3C不再按照Level来维护DOM了，而是作为DOM  Living  Standard来维护，其快照称为DOM4

DOM4新增的内容包括替代Mutation Events的Mutation Observers

并没有一个标准叫“DOM Level 0”，这只是DOM历史中的一个参照点

DOM Level 0可以看作IE4和Netscape Navigator 4中最初支持的**DHTML**

除了DOM Core和DOM HTML接口，有些其他语言也发布了自己的DOM标准。下面列出的语言是基于XML的，每一种都增加了该语言独有的DOM方法和接口

可伸缩矢量图（SVG，Scalable Vector Graphics）

>Web浏览器对DOM的支持情况

DOM标准在Web浏览器实现它之前就已经作为标准发布了

IE在第5版中尝试支持DOM，但直到5.5版才开始真正支持，该版本实现了DOM Level 1的大部分

Firefox 3+支持全部的Level 1、几乎全部的Level 2，以及Level 3的某些部分

>浏览器对象模型（BOM）

用于支持访问和操作浏览器的窗口

使用BOM，开发者可以操控浏览器显示页面之外的部分

而BOM真正独一无二的地方，当然也是问题最多的地方，就是它是唯一一个没有相关标准的JavaScript实现

HTML5改变了这个局面，这个版本的HTML以正式规范的形式涵盖了尽可能多的BOM特性

由于HTML5的出现，之前很多与BOM有关的问题都迎刃而解了

BOM主要针对浏览器窗口和子窗口（frame）

- 弹出新浏览器窗口的能力；
- 移动、缩放和关闭浏览器窗口的能力；
- navigator对象，提供关于浏览器的详尽信息；
- location对象，提供浏览器加载页面的详尽信息；
- screen对象，提供关于用户屏幕分辨率的详尽信息；
- performance对象，提供浏览器内存占用、导航行为和时间统计的详尽信息；
- 对cookie的支持；
- 其他自定义对象，如XMLHttpRequest和IE的ActiveXObject。

多数浏览器对JavaScript的支持，指的是实现ECMAScript和DOM的程度

>小结

JavaScript是一门用来与网页交互的脚本语言，包含以下三个组成部分

- ECMAScript：由ECMA-262定义并提供核心功能。
- 文档对象模型（DOM）：提供与网页内容交互的方法和接口。
- 浏览器对象模型（BOM）：提供与浏览器交互的方法和接口。

JavaScript的这三个部分得到了五大Web浏览器（IE、Firefox、Chrome、Safari和Opera）不同程度的支持

所有浏览器基本上对ES5（ECMAScript 5）提供了完善的支持

而对ES6（ECMAScript 6）和ES7（ECMAScript 7）的支持度也在不断提升

这些浏览器对DOM的支持各不相同，但对Level 3的支持日益趋于规范

HTML5中收录的BOM会因浏览器而异，不过开发者仍然可以假定存在很大一部分公共特性

------
## **210523**

>`<script>`元素

```html
<script
src="./test.js"
async
charset="UTF-8"
crossorigin="use-credentials"
defer
integrity="hash"
language
type="text/javascript"
>
console.log(666);
</script>
```

`src="./test.js"`

表示包含要执行的代码的外部文件

`async`

表示应该立即开始下载脚本

但不能阻止其他页面动作(下载资源或等待其他脚本加载)

只对外部脚本文件有效

`charset="UTF-8"`

规定在外部脚本文件中使用的字符编码

当外部脚本文件中的字符编码与HTML文档中的编码不同时就会用到charset属性

只对外部脚本文件有效

`crossorigin="anonymous/use-credentials"`

配置相关请求的CORS（跨源资源共享）设置 默认不使用CORS

`crossorigin= "anonymous"`配置文件请求不必设置凭据标志

`crossorigin="use-credentials"`设置凭据标志 意味着出站请求会包含凭据

`defer`

表示脚本可以延迟到文档完全被解析和显示之后再执行

只对外部脚本文件有效

在IE7及更早的版本中 对行内脚本也可以指定这个属性

`integrity="hash"`

允许对比接收到的资源和指定的加密签名以验证子资源完整性（SRI，Subresource Integrity）

如果接收到的资源的签名与这个属性指定的签名不匹配 则页面会报错 脚本不会执行

这个属性可以用于确保内容分发网络（CDN，Content Delivery Network）不会提供恶意内容

`language`

**废弃**

最初用于表示代码块中的脚本语言（如"JavaScript"、"JavaScript 1.2"或"VBScript"）

`type="text/javascript"`

代替language，表示代码块中脚本语言的内容类型（也称MIME类型）

按照惯例，这个值始终都是"text/javascript"

尽管"text/javascript"和"text/ecmascript"都已经废弃了

JavaScript文件的MIME类型通常是"application/x-javascript" 不过给type属性这个值有可能导致脚本被忽略

在非IE的浏览器中有效的其他值还有"application/javascript"和"application/ecmascript"

**如果这个值是module**

则代码会被当成ES6模块 而且只有这时候代码中才能出现import和export关键字

使用`<script>`的方式有两种

通过它直接在网页中嵌入JavaScript代码/通过它在网页中包含外部JavaScript文件

要嵌入行内JavaScript代码 直接把代码放在`<script>`元素中就行

```html
<script>
  function test() {
    console.log(666);
  }
</script>
```

包含在`<script>`内的代码会被从上到下解释

在上面的例子中 被解释的是一个函数定义 并且该函数会被保存在**解释器环境中**

在`<script>`元素中的代码被计算完成之前 页面的其余内容不会被加载 也不会被显示

在使用行内JavaScript代码时 要注意代码中不能出现字符串`</script>`

比如下面的代码会导致浏览器报错

```html
<script>
  function test() {
    console.log('</script>');
  }
</script>
```

浏览器解析行内脚本的方式决定了它在看到字符串`</script>`时 会将其当成结束的`</script>`标签

想避免这个问题 只需要转义字符`“\”`即可

```html
<script>
  function test() {
    console.log('<\/script>');
  }
</script>
```

这样修改之后 代码就可以被浏览器完全解释不会导致任何错误

要包含外部文件中的JavaScript 就必须使用src属性

`<script src="example.js"></script>`

文件本身只需包含要放在`<script>`的起始及结束标签中间的JavaScript代码(意思是不要`<script>`)

与解释行内JavaScript一样 在解释外部JavaScript文件时 页面也会阻塞（阻塞时间也包含下载文件的时间）

在XHTML文档中 可以忽略结束标签

`<script src="example.js" />`

以上语法不能在HTML文件中使用 因为它是无效的HTML

有些浏览器不能正常处理 比如IE

------
## **210524**

按照惯例 外部JavaScript文件的扩展名是`.js`

这不是必需 浏览器不会检查所包含JavaScript文件的扩展名

这就为使用服务器端脚本语言动态生成JavaScript代码

或者在浏览器中将JavaScript扩展语言（如TypeScript，或React的JSX）转译为JavaScript提供了可能性

服务器经常会根据文件扩展来确定响应的正确MIME类型

如果不打算使用`.js`扩展名 一定要确保服务器能返回正确的`MIME`类型

使用了src属性的`<script>`元素不应该再在标签中再包含其他JavaScript代码

如果两者都提供的话，则浏览器只会下载并执行脚本文件，从而忽略行内代码

它可以包含来自外部域的JavaScript文件

跟`<img>`元素很像

`<script>`元素的src属性可以是一个完整的URL

而且这个URL指向的资源可以跟包含它的HTML页面不在同一个域中

浏览器在解析这个资源时，会向src属性指定的路径发送一个GET请求，以取得相应资源，假定是一个JavaScript文件

**这个初始的请求不受浏览器同源策略限制**

但返回并被执行的JavaScript则受限制

当然，这个请求仍然受父页面HTTP/HTTPS协议的限制

来自外部域的代码会被当成加载它的页面的一部分来加载和解释 这个能力可以让我们通过不同的域分发JavaScript

在包含外部域的JavaScript文件时，要确保该域是自己所有的，或者该域是一个可信的来源

integrity属性是防范这种问题的一个武器，但这个属性也不是所有浏览器都支持

浏览器都会按照`<script>`在页面中出现的顺序依次解释它们

前提是它们没有使用defer和async属性

第二个`<script>`元素的代码必须在第一个`<script>`元素的代码解释完毕才能开始解释

>标签位置

所有`<script>`元素都被放在页面的`<head>`标签内

这种做法的主要目的是把外部的CSS和JavaScript文件都集中放到一起

不过，把所有JavaScript文件都放在`<head>`里

也就意味着必须把所有JavaScript代码都下载、解析和解释完成后，才能开始渲染页面（页面在浏览器解析到`<body>`的起始标签时开始渲染）

对于需要很多JavaScript的页面，这会导致页面渲染的明显延迟，在此期间浏览器窗口完全空白

为解决这个问题，现代Web应用程序通常将所有JavaScript引用放在`<body>`元素中的页面内容后面

```html
<body>
  <!-- 页面内容 -->
  <script src="./test.js"></script>
</body>
```

`HTML4.01`为`<script>`元素定义了一个叫defer的属性

这个属性表示脚本在执行的时候不会改变页面的结构

也就是说，脚本会被延迟到整个页面都解析完毕后再运行

因此，在`<script>`元素上设置defer属性，相当于告诉浏览器**立即下载，但延迟执行**

```html
<script defer src="./test.js"></script>
```

HTML5规范要求脚本应该按照它们出现的顺序执行，因此第一个推迟的脚本会在第二个推迟的脚本之前执行

而且两者都会在`DOMContentLoaded`事件之前执行

推迟执行的脚本**不一定总会按顺序执行或者在DOMContentLoaded事件**之前执行

因此最好**只包含一个这样的脚本**

defer属性只对外部脚本文件才有效。这是HTML5中明确规定的

因此支持HTML5的浏览器会**忽略行内脚本的defer属性**

IE4~7展示出的都是旧的行为，IE8及更高版本则支持HTML5定义的行为

对defer属性的支持是从IE4、Firefox 3.5、Safari 5和Chrome 7开始的

其他所有浏览器则会忽略这个属性，按照通常的做法来处理脚本

考虑到这一点，**还是把要推迟执行的脚本放在页面底部比较好**

**对于XHTML文档，指定defer属性时应该写成defer="defer"**

------
## **210525**

>异步执行脚本

async属性与defer类似

两者也都只适用于外部脚本，都会告诉浏览器立即开始下载

不过，与defer不同的是，标记为async的脚本并不保证能按照它们出现的次序执行

```html
<script async src="./test.js"></script>
<script async src="./test2.js"></script>
```

第二个脚本可能先于第一个脚本执行

重点在于它们之间没有依赖关系

给脚本添加async属性的目的是告诉浏览器，不必**等脚本下载和执行完后再加载页面(也就是直接绕过这个脚本 走后面的代码)**，同样也**不必等到该异步脚本下载和执行后**再加载其他脚本

正因为如此，异步脚本不应该在加载期间修改DOM(因为修改不了)

```html
<body>
  test
  <script async src="./test.js"></script>
</body>
```

```js
document.write('test')
```

异步脚本保证会在页面的load事件前执行

但可能会在DOMContentLoaded之前或之后

Firefox  3.6、Safari  5和Chrome  7支持异步脚本

使用async也会告诉页面你不会使用document.write，不过好的Web开发实践根本就不推荐使用这个方法

**对于XHTML文档，指定async属性时应该写成async="async"**

>动态加载脚本

可以使用DOM API

通过向DOM中动态添加script元素同样可以加载指定的脚本

只要创建一个script元素并将其添加到DOM即可

```html
<!-- demo.html -->

<script src="./test.js"></script>
```

```js
// test.js

let script = document.createElement('script')
script.src = './demo.js'
// 设置为同步加载
script.async = false
document.head.appendChild(script)
```

```js
// demo.js

console.log(666);
```

**在把HTMLElement元素添加到DOM且执行到这段代码之前不会发送请求(不执行代码哪来的动态script标签 里面的请求个鬼鬼)**

以这种方式创建的`<script>`元素是以异步方式加载的，相当于添加了async属性

不过这样做可能会有问题，因为所有浏览器都支持`createElement()`方法，但**不是所有浏览器都支持async属性**

因此，如果要统一动态脚本的加载行为，可以明确将其设置为同步加载

以这种方式获取的资源对**浏览器预加载器是不可见的**。这会严重影响它们在资源获取队列中的优先级。

根据应用程序的工作方式以及怎么使用，这种方式可能会严重影响性能。

要想让预加载器知道这些动态请求文件的存在，可以在文档头部显式声明它们

```html
<link rel="preload" href="./test.js">
```

>XHTML中的变化

可扩展超文本标记语言（XHTML，Extensible HyperText Markup Language）

是将HTML作为XML的应用重新包装的结果

与HTML不同，在XHTML中使用JavaScript必须指定**type属性**且值为`text/javascript`

**HTML中则可以没有这个属性**

XHTML虽然已经退出历史舞台，但实践中偶尔可能也会遇到遗留代码

在XHTML中编写代码的规则比HTML中严格，这会影响使用`<script>`元素嵌入JavaScript代码

下面的代码块虽然在HTML中有效，但在XHML中是无效的

```js
if (a < b) {}
```

在HTML中，解析`<script>`元素会应用特殊规则 XHTML中则没有这些规则

这意味着`a < b`语句中的小于号（<）会被解释成一个标签的开始

并且由于作为标签开始的小于号后面不能有空格，这会导致语法错误

避免XHTML中这种语法错误的方法有两种

第一种是把所有小于号（<）都替换成对应的HTML实体形式`&lt;`

```js
if (a &lt; b) {}
```

缺点是会影响阅读

第二种方法是把所有代码都包含到一个CDATA块中

在XHTML（及XML）中，CDATA块表示文档中可以包含任意文本的区块

其内容不作为标签来解析，因此可以在其中包含任意字符

包括小于号，并且不会引发语法错误

```html
<script type="text/javascript"><![CDATA[
  ...code
]]></script>
```

在兼容XHTML的浏览器中，这样能解决问题。但在不支持CDATA块的非XHTML兼容浏览器中则不行

为此，CDATA标记必须使用JavaScript注释来抵消

```html
<script type="text/javascript">
// <![CDATA[
  ...code
// ]]>
</script>
```

这种格式适用于所有现代浏览器 可以通过XHTML验证，而且对XHTML之前的浏览器也能优雅地降级

XHTML模式会在页面的MIME类型被指定为"application/xhtml+xml"时触发

**并不是所有浏览器都支持以这种方式送达的XHTML**

>废弃的语法

1995年 Netscape2发布以来，所有浏览器都将JavaScript作为默认的编程语言

type属性使用一个MIME类型字符串来标识`<script>`的内容，但MIME类型**并没有跨浏览器标准化**

即使浏览器默认使用JavaScript，在某些情况下某个无效或无法识别的MIME类型也可能导致浏览器跳过（不执行）相关代码

因此，除非你使用XHTML或`<script>`标签要求或包含非JavaScript代码

**最佳做法是不指定type属性**

`<script>`这个元素需要应用特殊的解析规则，而这在不支持JavaScript的浏览器（特别是Mosaic）中会导致问题

不支持的浏览器会把`<script>`元素的内容输出到页面上，从而破坏页面的外观

对不支持JavaScript的浏览器**隐藏**嵌入的JavaScript代码

最终方案是把**脚本代码包含在一个HTML注释中**

```html
<script><!--
	function sayHi() {
		console.log('Hi!')
	}
//--></script>
```

Mosaic等浏览器就可以忽略`<script>`标签中的内容

而支持JavaScript的浏览器则必须识别这种模式，将其中的内容作为JavaScript来解析

虽然这种格式仍然可以被所有浏览器识别和解析，但已经**不再必要**，而且不应该再使用了

在XHTML模式下，这种格式也会导致脚本被忽略，因为代码处于有效的XML注释当中

>行内代码与外部文件

- 可维护性

开发者就可以独立于使用它们的HTML页面来编辑代码

- 缓存

浏览器会根据特定的设置缓存所有外部链接的JavaScript文件

这意味着如果两个页面都用到同一个文件，则该文件只需下载一次

这最终意味着页面加载更快

- 适应未来

通过把JavaScript放到外部文件中，就不必考虑用XHTML或前面提到的注释黑科技

包含外部JavaScript文件的语法**在HTML和XHTML中**是一样的

在配置浏览器请求外部文件时，要重点考虑的一点是它们会占用多少带宽

在SPDY/HTTP2中，预请求的消耗已显著降低

以轻量、独立JavaScript组件形式向客户端送达脚本更具优势

在初次请求时，如果浏览器支持SPDY/HTTP2，就可以从同一个地方取得一批文件，并将它们逐个放到浏览器缓存中

从浏览器角度看，通过SPDY/HTTP2获取所有这些独立的资源与**获取一个大JavaScript文件的延迟**差不多

在第二个页面请求时，由于你已经把应用程序切割成了轻量可缓存的文件，第二个页面也依赖的某些组件

**此时已经存在于浏览器缓存中了**

当然，这里假设浏览器支持SPDY/HTTP2，只有比较新的浏览器才满足

如果你还想支持那些比较老的浏览器，可能还是**用一个大文件更合适**

>文档模式

IE5.5发明了文档模式的概念，即可以使用doctype切换文档模式

最初的文档模式有两种：混杂模式（quirks  mode）和标准模式（standards  mode）

前者让IE像IE5一样（支持一些非标准的特性），后者让IE具有兼容标准的行为

虽然这两种模式的主要区别只体现在**通过CSS渲染的内容方面**

但对JavaScript也有一些关联影响，或称为**副作用**

第三种文档模式：准标准模式（almost standards mode）

这种模式下的浏览器支持很多标准的特性，但是没有标准规定得那么严格

主要区别在于**如何对待图片元素周围的空白**（在表格中使用图片时最明显）

混杂模式在所有浏览器中都以省略文档开头的doctype声明作为开关

这种约定并不合理，因为混杂模式在不同浏览器中的差异非常大，不使用黑科技基本上就没有浏览器一致性可言

**标准模式通过下列几种文档类型声明开启**

```html
<!-- HTML 4.01 Strict -->
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<!-- XHTML 1.0 Strict -->
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<!-- HTML5 -->
<!DOCTYPE html>
```

**准标准模式通过过渡性文档类型（Transitional）和框架集文档类型（Frameset）来触发**

```html
<!-- HTML 4.01 Transitional -->
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<!-- HTML 4.01 Frameset -->
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN" "http://www.w3.org/TR/html4/frameset.dtd">
<!-- XHTML 1.0 Transitional -->
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<!-- XHTML 1.0 Frameset -->
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Frameset//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-frameset.dtd">
```

>`<noscript>`元素

针对早期浏览器不支持JavaScript的问题，需要一个页面优雅降级的处理方案。最终，`<noscript>`元素出现，被用于给不支持JavaScript的浏览器提供替代内容

它可以包含任何**可以出现在`<body>`中的HTML元素**，`<script>`除外

在下列两种情况 浏览器将显示包含在`<noscript>`中的内容
- 浏览器不支持脚本
- 浏览器对脚本的支持被关闭

```html
<noscript>
	<p>如果浏览器支持脚本，则用户永远不会看到它</p>
</noscript>
```

>小结

- 要包含外部JavaScript文件，必须将src属性设置为要包含文件的URL。文件可以跟网页在同一台服务器上，**也可以位于完全不同的域**。
- 所有`<script>`元素会依照它们在网页中出现的次序被解释。在**不使用defer和async属性**的情况下，包含在`<script>`元素中的代码必须严格按次序解释。
- 对不推迟执行的脚本，浏览器必须解释完位于`<script>`元素中的代码，然后**才能继续渲染**页面的剩余部分。为此，通常应该把`<script>`元素放到**页面末尾**，介于主内容之后及`</body>`标签之前。
- 可以使用defer属性把脚本**推迟到文档渲染完毕后再执行**。推迟的脚本原则上按照它们被列出的次序执行。
- 可以使用async属性表示脚本**不需要等待其他脚本，同时也不阻塞文档渲染**，即异步加载。异步脚本**不能保证**按照它们在页面中出现的次序执行。
- 通过使用`<noscript>`元素，可以指定在浏览器不支持脚本时显示的内容。**如果浏览器支持并启用脚本**，则`<noscript>`元素中的任何内容都不会被渲染





















------
## **一些扩展**

>Element/HTMLElement/HTMLHtmlElement三者的区别

- Element对象表示XML文档中的元素
- HTMLElement对象表示HTML中的一个元素
- 都是继承Document的HTMLHtmlElement(老版已弃用)

HTMLElement对象继承了Element对象的标准属性 也实现了一些非标准属性

它们都可以看成是DOM(文档对象模型) DOM是W3C(万维网联盟)的推荐标准

>HTML/XML/XHTML三者的区别

- HTML: HyperText Markup Language / 超文本标记语言
- XML: Extensible Markup Language / 可扩展标记语言
- XHTML: Extensible Hypertext Markup Language / 可扩展超文本标记语言

HTML是用来描述和定义网页内容的标记语言 是构成网页的最基本的东西

所谓超文本 就是说它除了能标记文本 还能标记其他的内容 比如图片/链接/音频/视频等

它的作用就是一个规范 告诉所有浏览器都统一标准

比如我给这段文字加个`<p>`标签

那就是告诉浏览器 这是一个段落 浏览器看到后就会正确解析 产生相应的行为

XML的表现形式就是给一个文档加一堆标签 说明每段文字是干什么的 有什么意义

这样做的目的是方便存储/传输/分享数据 人和机器都可以很方便的阅读

XML和HTML有一个明显的区别就是

HTML的标签都是预定义的 你不可以自己随便增加

比如你不能自己写一个标签`<test>` 但是XML可以 你可以自己发明标签

HTML和XML一结合就产生了XHTML XHTML就是以XML的语法形式来写HTML

XHTML出现的原因是 HTML是一种语法形式比较松散的标记语言 语法要求也不严格

比如大小可以混用 属性值随便加不加引号 单引号还是双引号也随便 标签也可以不闭合

HTML标准的制定者W3C就把XML的语法形式往HTML上一套 就出现了XHTML

可以把XHTML理解为HTML的严格语法形式 除此之外其它方面基本一样

XHTML有一些强制的要求

1. 必须包含一个文件头声明`<!DOCTYPE>`
2. 所有元素名必须小写
3. 所有空元素必须关闭
4. 所有属性名必须小写
5. 所有属性值必须加引号
6. 所有布尔值属性必须加上属性值












------
![end](https://gitee.com/techpang/img_emoji_libs/raw/master/img_bed/markdown_images/end.jpg '富婆加我吧不想努力了')
