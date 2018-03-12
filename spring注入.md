## Spring 
 为什么要注入（DI/IOC） 
 因为对象是有关系的！
 在软件运行期间，对象之间根据业务需要有关联关系
 引用变量，在运行期间动态绑定到对象
 进而解决的对象的耦合性

## Spring的注入
### 1 支持两种方式注入
	   A 构造器参数注入（不常用）
	   B set方法输入（Bean属性注入）
### 2 Spring支持各种类型数据的注入
	   A 基本类型数据（含String）
	   B 对象（Bean）的注入
	     1) 引用方式
	       <property name="egg" ref="egg"/>
	     2) 匿名Bean，没有ID的Bean (不常用)
	     <bean id="food" class="Food">
	       <property name="egg" >
	         <bean class="Egg"/>
	       </property>
	     </bean>
	   C 集合的注入 list set map properties
	     1) 集合中元素可以是基本类型
	     2) 集合中元素可以是Bean对象
	     3) 引用方式注入集合 
	       使用命名空间 util:
	   D Spring 表达式注入
	     1) 从Bean对象中读取数据，注入到其他Bean
	     2) 支持从 Bean属性读取，List集合读取
	       Map集合，Properties集合
	     3) 语法与 JSP EL 表达式相同
	     
	     常见用途：读取properties文件

## 软件的结构与Spring
  软件一般都采用“经典”的“设计模式”

  软件经典结构：3层架构

  表现层：就是软件的界面,用来呈现数据,与用户交互

  业务层: 封装的了软件的核心功能（业务逻辑功能）

  数据层: 提供业务实体的 CRUD(增删改查)，也
   叫持久化层

  Spring 可以将软件的各个层次模块进行集成
  管理。


### 表现层：Spring MVC 登录框

业务层： UserService 
         User login(String name, String pwd)

数据层：UserDao (OracleUserDao MySqlUserDao)
          User findByName(String name)

JdbcDataSource 管理数据库连接

db.properties
applicationContext.xml
