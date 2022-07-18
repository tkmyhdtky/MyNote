<!--
 * @Author: WangZhao wz1847584786@163.com
 * @Date: 2022-07-01 10:38:48
 * @LastEditors: WangZhao wz1847584786@163.com
 * @LastEditTime: 2022-07-01 10:53:50
 * @FilePath: \LeetCoded:\Document\学习笔记\Spring\AOP.md
 * @Description:
 *
 * Copyright (c) 2022 by WangZhao wz1847584786@163.com, All Rights Reserved.
-->
# AOP

Aspect Oriented Programming,面向切面编程，一种编程范式，知道开发者如何组织程序结构

- 作用：在不惊动原始设计的基础上为其进行功能增强
- Spring理念：无入侵式/无侵入式

## 核心概念

- 连接点(JoinPoint):程序执行过程中的任意位置，粒度为执行方法、抛出异常、设置变量等
  - 在SpringAOP中，理解为方法执行
- 切入点(PointCut):匹配连接点的式子
  - 在SpringAOP中，一个切入点可以只描述一个具体方法，也可以匹配多个方法
- 通知(Advice):在切入点处执行的操作，也就是共性功能
  - 在SpringAOP中，功能最终以方法的形式呈现
- 通知类：定义通知的类
- 切面（Aspect):描述通知与切入点的对应关系
