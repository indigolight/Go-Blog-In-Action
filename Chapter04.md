WP
==
WP 当然指的是当前最好的博客系统(没有之一)[WordPress][0]. 看不看[WP数据库描述][1]我心里都知道在表设计上是无法做的比 WP 更好了.
好吧既然没有信心做的更好, 那干脆就简化一下.
数据库表的设计跟[WordPress][0]有非常大的相似度. 在这里面贴数据库表结构的代码是枯燥无趣的.
简单提几点.

窄表
===
窄表就是尽量减少表字段数量, 用数据记录替代增加表字段. 终极形态就是`key,value`. 当然没有必要窄到这个程度. WP 当然也是使用窄表的典范.
对应窄表的是宽表, 或者叫胖表. 口水之战多有发生. [TypePress][2]要使用窄表.
而且做了足够的精简, 一个系统应该随使用或者需求逐步丰富, 而不是一开始就很复杂.

隐私保护
=======
时常听到有网站因`神马`造成用户资料失窃. 那么干脆我们的数据里面对于敏感数据一开始就进行加密处理, 比如用户登录名(多数是email地址)和密码全面用`MD5`进行加密处理. 而且这个加密是在浏览器端进行的, 除非因找回密码需要提交`email`, 否则连服务器都不曾见过敏感数据原始值, 自然无法失窃. 如果加密的数据失窃还被解密了, 那就真没有其他办法了.

[0]: https://wordpress.org/
[1]: http://codex.wordpress.org/zh-cn:%E6%95%B0%E6%8D%AE%E5%BA%93%E6%8F%8F%E8%BF%B0
[2]: https://github.com/achun/typepress