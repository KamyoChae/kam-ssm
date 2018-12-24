## ssm是什么作用？

SSM框架是spring MVC ，spring和mybatis框架的整合，是标准的MVC模式

## ssm做了什么？

将整个系统划分了四层：表现层，controller层，service层，DAO层

## ssm能做什么？

第一个S：使用spring MVC负责请求的转发和视图的管理

第二个S：spring实现业务对象管理

剩下的M：mybatis作为数据对象的持久化引擎


原理：

SpringMVC：

1.客户端发送请求到DispacherServlet（分发器）

2.由DispacherServlet控制器查询HanderMapping，找到处理请求的Controller

3.Controller调用业务逻辑处理后，返回ModelAndView

4.DispacherSerclet查询视图解析器，找到ModelAndView指定的视图

5.视图负责将结果显示到客户端
 
