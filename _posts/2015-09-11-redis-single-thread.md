---        
layout: default
title: Redis 单线程模式
---

<h2>{{ page.title }}</h2>
<p>Redis incr 如何实现原子性 </p>
<p>{{ page.date | date_to_string }}</p>

之前研究Java AtomicInteger是如何保持原子性的，就联想到redis里incr命令字实现了 AtomicInteger里incrementAndGet方法类似的功能，那么这两者的实现的方式有什么区别。

##Java AtomicInteger incrementAndGet
最简单的，a++；翻译成a＝a+1 涉及到两步，就不是原子性的；
在了解Atomic之前，需要了解Unsafe。注意Unsafe本身涉及到大量底层内存分配操作，存在一定的危险性，所以叫做Unsafe。

##Redis incr
redis的incr实现相对而言要简单很多，从底层来看，redis是一个单线程模式，不管应用多少并发，在底层都是一个串行处理。

事件驱动模型