## ssm是什么作用？

SSM框架是spring MVC ，spring和mybatis框架的整合，是标准的MVC模式

## ssm做了什么？

将整个系统划分了四层：表现层，controller层，service层，DAO层

## ssm能做什么？

第一个 S：使用spring MVC负责请求的转发和视图的管理

第二个 S：spring实现业务对象管理

剩下的 M：mybatis作为数据对象的持久化引擎


## 原理：

### SpringMVC：

1.客户端发送请求到DispacherServlet（分发器）

2.由DispacherServlet控制器查询HanderMapping，找到处理请求的Controller

3.Controller调用业务逻辑处理后，返回ModelAndView

4.DispacherSerclet查询视图解析器，找到ModelAndView指定的视图

5.视图负责将结果显示到客户端
 
### Spring：

我们平时开发接触最多的估计就是IOC容器，它可以装载bean（也就是我们Java中的类，当然也包括service dao里面的），有了这个机制，我们就不用在每次使用这个类的时候为它初始化，很少看到关键字new。另外spring的aop，事务管理等等都是我们经常用到的。



### Mybatis：

mybatis是对jdbc的封装，它让数据库底层操作变的透明。mybatis的操作都是围绕一个sqlSessionFactory实例展开的。

mybatis通过配置文件关联到各实体类的Mapper文件，Mapper文件中配置了每个类对数据库所需进行的sql语句映射。在每次与数据库交互时，通过sqlSessionFactory拿到一个sqlSession，再执行sql命令。
