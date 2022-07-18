<!--
 * @Author: wangzhao wz1847584786@163.com
 * @Date: 2022-07-05 15:01:50
 * @LastEditors: wangzhao wz1847584786@163.com
 * @LastEditTime: 2022-07-05 17:46:08
 * @FilePath: \学习笔记\Vue\Vue.md
 * @Description:
 *
 * Copyright (c) 2022 by wangzhao wz1847584786@163.com, All Rights Reserved.
-->
# Vue

## Vue基础

1. 导入Vue.js

   ```html
        <script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>
   ```

2. 创建Vue实例对象，设置el属性和data属性
3. 使用简洁的模板语法把数据渲染到页面上

   ```html
        <div id="app">
            {{ message }}
        </div>
        <script>
            var app = new Vue({
                el: "#app",
                data: {
                    message: "hello world",
                }
            })
        </script>
   ```

### el：挂载点

- el是用来设置Vue实例挂载的元素
  - 范围：el选项命中的元素及其内部的后代元素
  - 选择器：建议使用ID选择器，也可以使用其他选择器
  - 在双标签内使用，不能再HTML和BODY中使用

### data:数据对象

- Vue中用到的数据定义在data中
- data中可以写复杂类型的数据
- 渲染负责类型数据时，遵守js的语法即可

## 本地应用

### 内容绑定，事件绑定

#### v-text

设置标签的文本值(textContent)

- 默认写法会替换全部内容，使用差值表达式{{}}可以替换指定的内容

  ```html
        <h3 v-text="message1+'!!!'">此处文字不起错用</h3>
  ```

- 内部支持表达式拼接

#### v-html

- 设置标签的innerHTML
- 内容中有HTML结构会被解析为标签

> v-text中只会解析成文本

#### v-on

- 为元素绑定事件
- 指令可以简写为@
- 绑定的方法定义在methods属性中
- 方法内部可以通过this关键字可以访问定义在data中的数据

```html
    <div id="app">
        <input type="button" value="v-on指令" v-on:click="doIt"><br>
        <p v-text="message"></pv-text></p>
    </div>
    <script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>
    <script>
        var app = new Vue({
            el:"#app",
            data:{
                message:"hello world"
            },
            methods:{
                doIt:function(){
                    this.message+="点击一次";
                }
            }
        })
    </script>
```

### 显示切换，属性绑定

#### v-show

- 根据表达式的真假，切换元素的显示和隐藏
- 原理:修改元素的display,实现显示隐藏
- 指令后的内容，最终都会解析会布尔值:值为true元素显示，值为false元素隐藏
- 数据改变之后，对应元素的显示状态会同步更新

```html
    <div id="app">
        <input type="button" value="切换" @click="change"></button>
        <p v-show="isShow">可见文字</p>
    </div>
    <script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>
    <script>
        var app = new Vue({
            el:"#app",
            data:{
                isShow:true
            },
            methods:{
                change:function(){
                    this.isShow=!this.isShow
                }
            }
        })
    </script>
```

#### v-if

- 根据表达式的真假，切换元素的显示和隐藏(操作dom元素)
- 本质是通过操作dom元素来切换显示状态
- 值为true，元素存在dom树中，值为false，元素从dom树中移除

> 频繁切换使用v-show,切换消耗小,反之使用v-if
