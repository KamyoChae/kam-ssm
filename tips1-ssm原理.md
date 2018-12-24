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


![png](https://github.com/KamyoChae/kam-ssm/blob/master/images/ssmlive.png)
使用方法：

要完成一个功能：

先写实体类entity，定义对象的属性，（可以参照数据库中表的字段来设置，数据库的设计应该在所有编码开始之前）。

写Mapper.xml（Mybatis），其中定义你的功能，对应要对数据库进行的那些操作，比如 insert、selectAll、selectByKey、delete、update等。

写Mapper.java，将Mapper.xml中的操作按照id映射成Java函数。

写Service.java，为控制层提供服务，接受控制层的参数，完成相应的功能，并返回给控制层。

写Controller.java，连接页面请求和服务层，获取页面请求的参数，通过自动装配，映射不同的URL到相应的处理函数，并获取参数，对参数进行处理，之后传给服务层。

写JSP页面调用，请求哪些参数，需要获取什么数据。

DataBase ===> Entity ===> Mapper.xml ===> Mapper.Java ===> Service.java ===> Controller.java ===> Jsp.

--------------------- 
作者：CSU_Dennis 
来源：CSDN 
原文：https://blog.csdn.net/dennis_wu_/article/details/73437097 
