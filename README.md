# spring
spring的一些学习笔记
###  IoC和DI的关系是什么。
1. Spring是具有IoC特性的框架。
2. 实现IoC是由Spring容器来完成的，Spring容器通过DI建立起对象（组件、Bean）之间的关系。
3. 可以这样理解：DI是IoC实现的一种手段，Ioc的理论通过DI来实现。

-----
### 什么是AOP及其好处。
参考答案：
Aspect Oriented Programming 面向方面编程或面向切面编程。
AOP关注点是共同处理，可以通过配置将其作用到某一个或多个目标对象上。好处是实现组件重复利用，改善程序结构，提高灵活性。将共通组件与目标对象解耦。


### 5种类型的通知，在内部调用时的顺序是什么。

参考答案:

	try{
	调用前置通知
	环绕前置处理
	调用目标对象方法
	环绕后置处理
	调用后置通知
	}catch(Exception e){
	调用异常通知
	}finally{
	调用最终通知
	}
  
  
### 写出三个可以Bean组件上配置的注解。

参考答案：

- @Service 业务逻辑层，就是我们的service或者manager层。
- @Repository 持久层，就是我们常说的DAO层。
- @Component （字面意思就是组件），它在你确定不了事哪一个层的时候使用。

### 写出三个配置Spring AOP时使用的注解。

- @Aspect : 将组件指定为方面组件
- @Pointcut : 定义一个空方法,使用该注解指定一个切入点表达式.
- @Around : 定义环绕通知填空题（读代码、加注释）

### Spring提供的两种事务管理方式是什么。

参考答案：
Spring提供了两种事务管理方式

  a.编程式事务管理
  b.声明式事务管理
  
  
### 请简述sping mvc的流程。

参考答案：

1. 客户端发送请求
2. 客户端发送的请求到达控制器,控制器由Servlet（DispatcherServlet）实现的，来完成请求的转发
3. 该控制器（DispatcherServlet）调用了一个用于映射的类HandlerMapping，
该类用于将请求映射到对应的处理器来处理请求。
4. HandlerMapping将请求映射到对应的处理器Controller（相当于Action）
在Spring当中如果写一些处理器组件，一般实现Controller接口
5. 在Controller中就可以调用一些Service或DAO来进行数据操作
6. ModelAndView用于存放从DAO中取出的数据，还可以存放响应视图的一些数据。
7. 如果想将处理结果返回给用户，那么在Spring框架中还提供一个试图组件
ViewResolver，该组件根据Controller返回的标示，找到对应的试图，将响应
response返回给用户
  
