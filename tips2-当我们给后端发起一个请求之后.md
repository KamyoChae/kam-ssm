# 当我们给后端发起一个请求之后

当我们在浏览器发起一个请求之后，ssm后端究竟做了什么事情？

今晚看到一张图，觉得写得挺清晰的，在这里说一下自己的理解。

![png](https://github.com/KamyoChae/kam-ssm/blob/master/images/ssmlive.png)
## 后端的流程
1.首先，用户给后端发起一个请求之后，这个请求会跳到后端的分发器里面（dispacherservlet）。

2.通过这个分发器，控制映射。我们将请求分发到一个映射里面，可以暂时认为这个映射（Hander Mapping）只是一个拷贝的副本。

3.控制这个映射的方式是用这个映射去找到处理这个请求的controller。

4.而这个controller就会找server层的东西

5.匹配上了就返回一些数据给controller层

6.controller拿到server层的数据之后，处理一下（也有可能不处理）就直接包装成一个东西扔给视图解析器了。而这个东西就是model and view，也就是前端常说的mv

7.Model And View扔给视图解析器了。

8.视图层解析完成之后，又回到分发器这里

9.通过分发器把解析出来的结果分给显示数据的jsp页面

以上 就是整个ssm工作的大概流程(当然其中还有一些细节没有讲到，比如分发器怎么分发 视图解析器怎么解析之类)。
