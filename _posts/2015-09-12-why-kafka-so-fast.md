---        
layout: default
title: kafka 消息持久化机制
---

<h2>{{ page.title }}</h2>
<p>why kafka so fast </p>
<p>{{ page.date | date_to_string }}</p>

##术语
Broker, Topic, Partition

一台服务器就是有一个Broker，Topic是一个虚拟概念，按照不同的业务来创建。Topic会划分成多个Partition，partition分割规则，需在配置文件里进行配置。

kafka服务器的特别之处在于持久化消息。

##zero byte copy
kafka能实现快速写入文件的另一个重要技术点：零字节拷贝。
内存分为用户态和内核态，通常的一个写入读出操作需要让字节在用户态和内核态之间进行若干次拷贝才行达到目的。
零字节拷贝的重要意义在于减少拷贝次数，提升效率。