---        
layout: default
title: coin in a line
---

<h2>{{ page.title }}</h2>
<p>lintcode -- coin in a line 解题分析 </p>
<p>{{ page.date | date_to_string }}</p>

<h3>题目</h3>

有 n 个硬币排成一条线。两个参赛者A，B轮流从右边依次拿走 1 或 2 个硬币，直到没有硬币为止。拿到最后一枚硬币的人获胜。

请判定 第一个玩家 是输还是赢？

样例
n = 1, 返回 true.

n = 2, 返回 true.

n = 3, 返回 false.

n = 4, 返回 true.

n = 5, 返回 true.


<h3>结论</h3>

 参数传入n，A能控制第一或者第二，B能控制第三。
 int result = n ％ 3

如果result == 1 ,那么A每次控制取到1，4，7等即可
如果result == 2 ,那么A每次控制取到2，5，8等即可
如果result == 0 ,那么B每次控制取到3，6，9等即可

前提是：假设A，B都对这个规则很了解。不能乱来 , 不然投机不成蚀把米^_^