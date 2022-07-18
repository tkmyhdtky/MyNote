<!--
 * @Author: WangZhao wz1847584786@163.com
 * @Date: 2022-06-29 09:16:33
 * @LastEditors: WangZhao wz1847584786@163.com
 * @LastEditTime: 2022-06-29 09:34:40
 * @FilePath: \LeetCoded:\Document\学习笔记\REST开发.md
 * @Description: 
 * 
 * Copyright (c) 2022 by WangZhao wz1847584786@163.com, All Rights Reserved. 
-->
# REST开发

## REST风格简介

REST(Representational State Transfer),表现形式状态转换

- 传统风格资源描述形式
  - `http://localhost/user/getById?id=1`
  - `http://localhost/user/saveUser`
- REST风格描述形式
  - `http://localhost/user/1`
  - `http://localhost/user`

> 按照REST风格访问资源时使用**行为动作**区分对资源进行了何种操作

|地址|操作|
|:-:|:-:|
|`http://localhost/users`|查询全部用户信息 GET(查询)|
|`http://localhost/users/1`|查询指定用户信息 GET(查询)|
|`http://localhost/users`|添加用户信息 POST(新增/保存)|
|`http://localhost/users`|修改用户信息 PUT(修改/更新)|
|`http://localhost/users/1`|删除用户信息 DELETE(删除)|

- 根据REST风格对资源进行访问称为RESTful

**注意:上述行为时约定方式,约定不是规范,可以打破,所以称REST风格,而不是REST规范**
**描述模块的名称通常使用附属,也就是加ｓ的格式描述,表示此类资源,而非单个资源**

- 优点
  - 隐藏资源的访问行为,无法通过地址得知对资源是何种操作
  - 书写简化
