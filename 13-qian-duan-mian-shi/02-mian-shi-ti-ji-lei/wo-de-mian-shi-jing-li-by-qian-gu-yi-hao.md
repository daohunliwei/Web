# 20180323

## 什么是闭包，闭包有什么作用。

## ES6的新特性有哪些。

作用域、函数扩展（扩展运算符、默认参数、箭头函数）、异步promise、模块化。

## 追问：const常量有什么作用？确定不能修改吗？修改之后会报错吗？你有没有试过？

当时我的答案是斩钉截铁地说不能改，其实我说错了。后来查了一下，准确答案是：

* 如果是值类型，值不可变
* 如果是引用类型，地址不可变

所以说，虽然我不能修改引用类型的指向，但是我可以修改引用类型里的属性值。

参考链接：[https://segmentfault.com/q/1010000012836140?sort=created](https://segmentfault.com/q/1010000012836140?sort=created)

## 追问：const的原理是什么？

面试官问：如果你定义了const，什么是常量？是它的值还是引用？比如说，我定义了一个const 的array，那我能往里面插入数据吗？

## 箭头函数和匿名函数有什么区别吗？

箭头函数和匿名函数有个明显的区别：箭头函数内部的this是词法作用域，由上下文确定。

普通函数的this指向是动态作用域；箭头函数的this指向是依据词法作用域。

参考链接：[https://zhuanlan.zhihu.com/p/25093389](https://zhuanlan.zhihu.com/p/25093389)

## 可以讲一下promise的状态吗？

## 追问：如果我写setTimeout（0），再写一个promise，哪个先执行？

我回答错了。

正确答案是：任务队列可以有多个，promise的任务队列，优先级更高。具体答案还需要再仔细看看。

## http有了解吗？

* 可以讲一下它的握手过程吗？
* http的缓存有了解吗？
* get和post区别

## 做过CDN吗？

答得不具体。

百度百科的解释是：其基本思路是尽可能避开互联网上有可能影响数据传输速度和稳定性的瓶颈和环节，使内容传输的更快、更稳定。

## Vue相关

* vue的双向绑定怎么实现的？我是说怎么实现？

我当时是回答MVVM模式。其实还需要答出Object.defineProperty\( \)的细节，以及虚拟DOM。

* Vue里还有什么呢？

数据驱动、组件化。

## 事件绑定：onClick和addEventListener的区别

## 说一下DOM里的事件冒泡

## 用Webpack做过哪些功能？

## 追问：ES6转成ES5，改动代码，发现页面自动刷新。你说一下整个流程。

问的是webpack 自动刷新的流程。我没回答好。

## 追问：既然webpack可以用来配置服务器，如果我要联调，怎么办？

问：启动了webpack，就可以直接连接到后端吗？

## 说一下跨域

## gzip压缩有了解吗

## 你做过什么项目？说一下？

答：我做过电商网站。

追问：遇到过什么问题吗？

答：我遇到了性能的问题。

追问：那你说一下性能的问题

我就答出了性能相关的五大点。

## node和express有了解吗？

## 追问requireJS，是异步的吗？

是异步的。

## Vue你是怎么用的？是把所有的代码都写在一个页面里的吗

答：我是模块化写的。

问：怎么分类？

追问：vuex的的作用

## 移动端的触摸事件了解吗？

* touchstart touchmove touchend touchcancel（touchcancel当触点由于某些原因被中断时触发）
* 模拟 swipe 事件：记录两次 touchmove 的位置差，如果后一次在前一次的右边，说明向右滑了。

## 移动端的浏览器和电脑浏览器的 touch事件，有区别吗？

我说我没了解过。

追问：移动端默认会有0.2秒的延迟。

我后来查了一下：

点击延迟：是指移动端浏览器在 touchend 和 click 之间存在 300ms ～ 350ms 的延迟。

为了判断用户是否是进行双击操作。因为移动端双击是放大文字的手势操作。

主要是从点击屏幕上的元素到触发元素的 click 事件，移动浏览器会有大约 300 毫秒的等待时间。这是因为浏览器想看看你是不是要进行双击（double tap）操作。

解决方法：

* 将click事件换成touch end事件
* FastClick：FastClick的实现原理是在检测到touchend事件的时候，会通过DOM自定义事件立即出发模拟一个click事件，并把浏览器在300ms之后真正的click事件阻止掉。

事件发生顺序：在移动端，手指点击一个元素，会经过：touchstart --&gt; touchmove -&gt; touchend --》click。

## 如何自定义事件

自定义事件的代码如下：

```javascript
    var myEvent = new Event('clickTest');
    element.addEventListener('clickTest', function () {
        console.log('smyhvae');
    });

    //元素注册事件
    element.dispatchEvent(myEvent); //注意，参数是写事件对象 myEvent，不是写 事件名 clickTest
```

## 说一下状态码

## 手机端的web开发，怎么和原生做交互？

问：比如web网页，想调用手机的拍照功能，怎么做？再比如怎么分享到朋友圈？

## vue的生命周期，有了解吗

create和mount有什么区别吗

什么时候执行update
