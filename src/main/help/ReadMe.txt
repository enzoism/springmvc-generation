SpringmMVC基础框架搭建过程备注
1、创建一个SpringMVC单Maven项目，创建java/resources/test三个文件目录，并进行试运行操作
    访问网址：http://localhost:8080/index.html
    maven的confi/setting已经放在help/maven下，可以进行手动替换

2、创建配置文件：pom.xml/web.xml/spring/springMVC/mybatis/jdbc
- pom.xml文件配置
    直接引入所需文件即可

- web.xml文件配置
    主题思路：
    - spring配置：只需要文件扫描包+数据库连接池即可
    - springMVC配置：web.xml配置servlet的DispatcherServlet，需要配置视图拦截规则+MVC标注扫描
    - mybatis配置：配合spring配置，进行文件的解耦而已
    - jdbc配置：配合mybatis，进行数据的解耦而已

3、使用MyBatisGenerator，创建Java类，然后运行TestMyBatisGeneration文件，里面会快速的创建数据库，生产相关的代码文件
- 在数据库中创建表信息（先创建数据库，可以使用powerDesigner进行设计）
- 具体的配置信息在mbg.xml中进行配置，此时任何文件都没有，直接进行Test方法执行即可
- 然后根据自己的情况，创建dao中自己的方法，然后在Mappper中进行实现
- 创建一个dao层的测试类，可以进行快速的数据功能测试

4、创建controller和service，直接对dao层的数据进行调用即可
- RESTFUL风格的接口
- AJAX数据的请求接收


5、未完成功能
- 访问权限管控（SpringSecurity/Shiro）
- 高并发的流量管控（限流）
- 日志系统配置（log4j进行日志的分离配置）
- 通用的异常处理（Filter进行日志异常统一处理）
- Swagger的接口调试
- 搜索引擎使用（Solr/ElasticSearch）
- 用户的未登陆访问拦截（单点登陆）
- Other

==================================整理==================================
1.搭建项目
2.配置pom.xml
3.配置web.xml引入spring、springmvc、mybatis相关
4.执行sql语句
5.进行mybatis逆向工程，生成相关的代码
6.修改mapper的代码逻辑，完成自己的功能需求
7.前端页面操作逻辑修改
