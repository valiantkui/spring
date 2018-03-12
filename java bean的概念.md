 ## Java Bean（POJO）实现如下规则的Java对象
 #### 1 必须有包（package）
 #### 2 必须有无参数构造器
 #### 3 实现序列化接口
 #### 4 有getXXX setXXX方法定义的Bean属性XXX
  String getName()
   void setName(String n)

   定义了Bean 属性 name  与 对象的属性不同!

   比如：EL表达式可以访问Bean属性！

 #### 5 toString 
  equals hashCode 有ID 基本都重写
