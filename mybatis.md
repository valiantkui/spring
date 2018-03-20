##  (1)mybatis是什么？
开源的持久层框架
## (2)编程步骤

1. 导包
  mybatis.jar
2. 添加mybatis配置文件
3. 写实体类。

 **注:** 实体类的属性名与表的字段表要求一样
      大小写无所谓

4. 写映射文件
# spring集成mybatis
## (1)编程步骤

1. 导包
     spring-webmvc，mybatis，mybatis-spring，spring-jdbc，dbcp，ojdbc，junit
2. 添加spring配置文件

    **注: ** mybatis的配置信息可以添加到spring的配置文件当中(只需要配置SqlSessionFactoryBean).
3. 实体类
4. 映射文件
5. Mapper映射器
6. 在spring的配置文件当中，添加MapperScannerConfigurer。
该bean负责调用SqlSession的getMapper方法，创建符合Mapper映射器要求的对象
###### 
 **注:** 该bean会将这个对象添加到spring容器里面。
## (2)只扫描特定的Mapper映射器

1. 开发一个注解。比如@MybatisRepository。
2. 将该注解添加到需要扫描的映射器。
3. 配置MapperScannerConfig，设置annotationClass，指定注解类。
## (3)另外一种集成方式(了解)

1. 导包。
2. 添加spring配置文件
###### 
 **注:** 删除MapperScannerConfig的配置
3. 实体类
4. 映射文件
5. DAO接口。
6. 写DAO实现类。
###### 
 **注:** 注入SqlSessionTemplate，调用该对象的方法。
7. 配置SqlSessionTemplate
8. 不要忘记添加组件扫描。

