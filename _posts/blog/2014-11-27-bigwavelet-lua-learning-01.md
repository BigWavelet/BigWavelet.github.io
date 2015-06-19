---
layout: post
title: LUA 学习日记（一）
description: LUA基础数据类型 
category: blog

---
Roberto Ierusalimschy 的['Programming in Lua, Second Edition'](http://pan.baidu.com/share/link?shareid=463130&uk=487907638)对初学者来讲，是一本不错的参考书。      

那么如何搭建lua环境呢，windows用户下载[lua for windows](https://www.slimwareutilities.com/community/info.php?id=813153&type=software) 。安装时勾选安装SciTe编辑器即可。  

今天主要写一点关于Lua的数据类型的东西吧。Lua是动态类型语言，变量不要类型定义。
其中有8个基本类型非别是：nil, boolean, number, string, userdata, function, thread 和table。
如果我们希望知道某给定变量的类型，可以使用type函数获得，例如

		
				 
				print(type(a))  --> nil   ('a' is not initialized) 
				a = 10 
				print(type(a))  --> number 
				a = "a string!!" 
				print(type(a))  --> string 
				a = print    -- yes, this is valid! 
				a(type(a))     --> function 

细心的小伙伴可能发现，我们可以像使用变量一样来使用print函数。有没有很神奇呢。下面分别介绍以下8种基本数据类型。

## nil
nil 是Lua中的一种特殊的数据类型，其只有一种取值:nil。 一个全局变量没有赋值之前，其默认的取值为nil。 
因此，如果给一个全局变量赋值nil则可以删除该变量。	

## booleans
该类型的变量有两个取值：false 和true。值得注意的是，在控制结构的条件中出力false和nil为假，其他值都为
真。<font color='red'>在Lua中，即使0或者空串都是真</font>。			

## nubmers
该类型表示实数。值得注意的是，在lua中没有整数的概念。数字的基本表示如下例所示

				4    0.4    4.57e-4    0.4e-7

## strings
表示字符序列，即字符串。<font color='red'>lua中的字符串是不可以修改的</font>. 字符串用单引号，双引号
表示皆可。跟C语言比较类似，可以用\转义符。

				a = "a line" 
				b = 'another line' 
同时，值得注意的是，lua会在string和number之间自动进行类型转换，当一个字符串使
用算术操作符时，string 就会被转成数字。

				print("10" + 1)     --> 11 
				print("10 + 1")     --> 10 + 1 
				print("-5.3e - 10" * "2")  --> -1.06e-09 
				print("hello" + 1)    -- ERROR (cannot convert "hello")	

如果需要显示将string转成数字，可以使用函数tonumber(),如果string 不是正确的数字，该函数将返回nil。
同理，可以调用tostring()将数字转成字符串。

## userdata & threads
userdata 可以将 C 数据存放在 Lua 变量中， userdata 在 Lua 中除了赋值和相等比较
有预定义的操作。userdata 用来描述应用程序或者使用 C 实现的库创建的新类型。

## functions
函数是第一类值（和其他变量相同），意味着函数可以存储在变量中，可以作为函数
参数，也可以作为函数的返回值。这个特性给了语言很大的灵活性：一个程序可以重
定义函数增加新的功能或者为了避免运行不可靠代码创建安全运行环境而隐藏函数，
外这特性在 Lua 实现面向对象中也起了重要作用. 

## table

未完待续。。。

