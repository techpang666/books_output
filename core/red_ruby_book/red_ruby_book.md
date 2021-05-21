
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

>为什么DOM是必需的

由于网景和微软采用不同思路开发DHTML，开发者写一个HTML页面就可以在任何浏览器中运行的好日子就此终结

就在这时，万维网联盟（W3C，World Wide Web Consortium）开始了制定DOM标准的进程

1998年10月，DOM Level 1成为W3C的推荐标准

这个规范由两个模块组成：DOM Core和DOM HTML

前者提供了一种映射XML文档，从而方便访问和操作文档任意部分的方式

后者扩展了前者，并增加了特定于HTML的对象和方法

























------
![end](https://gitee.com/techpang/img_emoji_libs/raw/master/img_bed/markdown_images/end.jpg '富婆加我吧不想努力了')
