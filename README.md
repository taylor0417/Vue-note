* [vue](#vue)
  * [一、Vue\.js介绍](#%E4%B8%80vuejs%E4%BB%8B%E7%BB%8D)
  * [二、Hello World](#%E4%BA%8Chello-world)
  * [三、常用基本指令](#%E4%B8%89%E5%B8%B8%E7%94%A8%E5%9F%BA%E6%9C%AC%E6%8C%87%E4%BB%A4)
    * [1、v\-model](#1v-model)
    * [2、v\-for](#2v-for)
    * [3、v\-on](#3v-on)
    * [4、v\-show](#4v-show)


vue
===

一、Vue.js介绍
--------------

---

Vue.js也称为Vue，读音类似view，错误读音v-u-e，由华人尤雨溪开源并维护。

Vue有以下特点：

-	是一个构建用户界面的框架

-	是一个轻量级MVVM（Model-View-ViewModel）框架，和angular、react类似

-	数据驱动+组件化的前端开发（核心思想）

-	通过简单的API实现**响应式的数据绑定**和**组合的视图组件**

-	更容易上手、小巧

二、Hello World
---------------

---

```javascript
  <h1 id="app">{{content}}</h1>
  <script>
      var app = new Vue ({
          el: '#app',
          data: {
              content: 'Hello World'
          }
      })
  </script>
```

三、常用基本指令
----------------

---

指令用来扩展HTML功能。vue内置了很多指令。

### 1、v-model

---

它能轻松实现表单输入和应用状态之间的双向绑定。

```javascript
  <div id="main">
    <input type="text" v-model="content">
    <br> {{content}}
  </div>

  <script src="./js/vue.js"></script>
  <script>
   new Vue({
       el: '#main',
       data: {
           content: ''
       }
   })
  </script>
```

在这里，使用<font color="#006600">v-model</font>指令将输入框的值与vue实例中的content进行绑定。此后，二者中的任一值发生变化，另一个值都会跟随变化。

### 2、v-for

---

用于遍历数组、对象等。

```javascript
  <div id="app">
    <ul>
      //v-for="'内容' in '对象或数组'"
      <li v-for="item in list">{{item}}</li>
    </ul>
  </div>
  <script>
    var app = new Vue({
      el: '#app',
      data: {
        list: ['第一条内容','第二条内容','第三条内容']
      }
    })
  </script>
```

### 3、v-on

---

用于绑定事件，用法：v-on:事件="函数"。

```javascript
  //综合案例简单的todolist
  <div id="app">
        <input type="text" v-model="inputValue">
        <button v-on:click="btnClick">提交</button>
        <ul>
            <li v-for="item in list">{{item}}</li>
        </ul>
    </div>
    <script>
        var app = new Vue({
            el: '#app',
            data: {
                list: [],
                inputValue: ''
            },
            methods: {
                btnClick: function () {
                    this.list.push(this.inputValue);
                    this.inputValue = '';
                }
            }
        })
    </script>
```

### 4、v-show

---

用来显示或隐藏元素，<font color="#006600">v-show</font>是通过display实现。当v-show的值为true时显示，为false时隐藏。

```javascript
  <div id="app">
      <button @click="change">显示/隐藏</button>
      <h1 v-show="flag">我是隐藏的内容</h1>
  </div>
  <script>
      var app = new Vue({
          el: '#app',
          data: {
              flag: true
          },
          methods: {
              change: function () {
                  this.flag = !this.flag;
              }
          }
      })
  </script>
```
