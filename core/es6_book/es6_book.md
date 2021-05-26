
# **ES6标准入门**
- [电子书地址](https://wangdoc.com/es6/)
- [代码仓库](https://github.com/wangdoc/es6-tutorial)

------
## **Promise对象**
- [我的promise代码地址](https://github.com/techpang666/js_relearn/blob/master/code/promise/promise.js)

>Promise的含义

Promise 是异步编程的一种解决方案，比传统的解决方案(回调函数和事件)更合理和更强大

ES6 将其写进了语言标准，统一了用法，原生提供了`Promise`对象

所谓Promise，简单说就是一个容器，里面保存着某个未来才会结束的事件（通常是一个异步操作）的结果

`Promise`是一个对象

Promise 提供统一的 API

Promise对象有以下**两个特点**
- 对象的状态不受外界影响
- 一旦状态改变，就不会再变，任何时候都可以得到这个结果

**对象的状态不受外界影响**

Promise对象代表一个异步操作

- pending（进行中）
- fulfilled（已成功）
- rejected（已失败）

**只有异步操作的结果**，可以决定当前是哪一种状态

任何其他操作都无法改变这个状态

**一旦状态改变，就不会再变，任何时候都可以得到这个结果**

- pending变为fulfilled
- pending变为rejected

如果改变已经发生了，你再对Promise对象**添加回调函数**，也会立即得到这个结果

事件（Event）完全不同，事件的特点是

**如果你错过了它，再去监听，是得不到结果的**

就可以将异步操作以同步操作的流程表达出来，**避免了层层嵌套的回调函数**

**Promise也有一些缺点**

首先，**无法取消Promise**，一旦新建它就会立即执行，无法中途取消

其次，如果**不设置回调函数**，Promise内部抛出的错误，不会反应到外部

第三，当**处于pending状态**时，无法得知目前进展到哪一个阶段（刚刚开始还是即将完成）。

如果某些事件不断地反复发生，一般来说，使用**Stream模式**是比部署Promise更好的选择


























------
![end](https://gitee.com/techpang/img_emoji_libs/raw/master/img_bed/markdown_images/end.jpg '富婆加我吧不想努力了')
