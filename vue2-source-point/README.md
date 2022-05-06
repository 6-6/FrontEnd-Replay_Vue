# Vue.js 2.0 源码重点学习
此项目是想要简单、快速，带着问题的思考下，了解 Vue.js 这种 MVVM 框架的原理。

参考文章：
https://juejin.cn/post/6989106100582744072

## Vue2.X 响应式原理
在Vue2.X 响应式中使用到了 ```defineProperty``` 进行数据劫持，所以我们对它必须有一定的了解，那么我们先来了解它的使用方法把， 这里我们来使用 ```defineProperty``` 来模拟 Vue 中的 data。

### 1.defineProperty 的应用
[defineProperty数据劫持](./vmodel/defineProperty1.html)

### 2.defineProperty 修改多个参数为响应式
看了上面的示例只能修改一个属性，实际上我们 data 中数据不可能只有一个，所以需要在此基础上改造下。
[defineProperty数据劫持](./vmodel/defineProperty2.html)

### 3.发布订阅模式
在Vue 响应式中应用到了 发布订阅模式 我们先来了解下

发布者、 订阅者、 信号中心 举个现实中例子 作者(发布者)写一篇文章 发到了掘金(信号中心) ,掘金可以处理文章然后推送到了首页，然后各自大佬(订阅者)就可以订阅文章

在Vue 中的例子 就是EventBus $on $emit，请看例子：
[defineProperty数据劫持](./publishSubscribe/vueEvent.html)
