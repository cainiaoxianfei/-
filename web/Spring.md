

# 	Spring系统架构

![image-20221124095603489](E:\学习笔记\assets\image-20221124095603489.png)

![image-20221124095824996](E:\学习笔记\assets\image-20221124095824996.png)



## 2.核心容器Ioc

![image-20221124100858380](E:\学习笔记\assets\image-20221124100858380.png)

![image-20221124102308218](E:\学习笔记\assets\image-20221124102308218.png)

![image-20221124102459672](E:\学习笔记\assets\image-20221124102459672.png)



## 3. Ioc入门案例

![image-20221124192348499](../assets/image-20221124192348499.png)

**依赖于servlet还是要导入servlet坐标，还要导入tomcat插件。**



![image-20221124194450880](../assets/image-20221124194450880.png)

![image-20221124194505276](../assets/image-20221124194505276.png)

![image-20221124195123330](../assets/image-20221124195123330.png)



## 4. DI

![image-20221125142912511](../assets/image-20221125142912511.png)

**set方法是容器调用的**



![image-20221125143023116](../assets/image-20221125143023116.png)



## 5. bean的基础配置

==别名配置==

![image-20221125144702907](../assets/image-20221125144702907.png)



==作用范围==

![image-20221125150025872](../assets/image-20221125150025872.png)

**默认是单例，创建的是同一个对象。**

![image-20221125150046024](../assets/image-20221125150046024.png)



### 5.1 bean(对象)的三种实例化

![image-20221125152727084](../assets/image-20221125152727084.png)

![image-20221125153923475](../assets/image-20221125153923475.png)

![image-20221125171006940](../assets/image-20221125171006940.png)



### 5.2 bean的生命周期

![image-20221125174150558](../assets/image-20221125174150558.png)

![image-20221125174120439](../assets/image-20221125174120439.png)

![image-20221125174131147](../assets/image-20221125174131147.png)

![image-20221125174253745](../assets/image-20221125174253745.png)

![image-20221125174510281](../assets/image-20221125174510281.png)



## 6. setter注入

![image-20221126105655173](../assets/image-20221126105655173.png)

![image-20221126145330913](../assets/image-20221126145330913.png)

![image-20221126145346130](../assets/image-20221126145346130.png)

**注入属性没有顺序**。



## 7.构造器注入

![image-20221126151403237](../assets/image-20221126151403237.png)

![image-20221126151420821](../assets/image-20221126151420821.png)

![image-20221126151749967](../assets/image-20221126151749967.png)



## 8. 依赖自动装配

![image-20221126155931855](../assets/image-20221126155931855.png)

![image-20221126163004775](../assets/image-20221126163004775.png)





## 9.注入集合对象

==**也是使用的setter方法注入，需要在使用的类中创建set方法**==

![image-20221126161802047](../assets/image-20221126161802047.png)

![image-20221126162255667](../assets/image-20221126162255667.png)

![image-20221126162400761](../assets/image-20221126162400761.png)

![image-20221126162411199](../assets/image-20221126162411199.png)

![image-20221126162423329](../assets/image-20221126162423329.png)



## 10.数据源管理对象

![image-20221126164437825](../assets/image-20221126164437825.png)





## 11.加载properties文件

![image-20221126165813245](../assets/image-20221126165813245.png)

![image-20221126172336686](../assets/image-20221126172336686.png)



## 12.容器

![image-20221126173013281](../assets/image-20221126173013281.png)

![image-20221126173046208](../assets/image-20221126173046208.png)

![image-20221126173741913](../assets/image-20221126173741913.png)





## 13.前面内容的总结

![image-20221126174556902](../assets/image-20221126174556902.png)

![image-20221126174709943](../assets/image-20221126174709943.png)

![image-20221126174739065](../assets/image-20221126174739065.png)





# 注解开发

## 1.注解开发定义bean

![image-20221126204602455](../assets/image-20221126204602455.png)

**1.注意，还是通过spring的context空间进行扫描，需要先开辟context空间，开辟空间参考11.**



**2.以下三种都是衍生注解，作用是一样的**

![image-20221126205739344](../assets/image-20221126205739344.png)



## 2.纯注解开发模式

**==舍弃spring配置文件转为使用java类代替==**

![image-20221126210521983](../assets/image-20221126210521983.png)

**@ComponentScan用于扫描对应目录下的bean.**

![image-20221126210708642](../assets/image-20221126210708642.png)





## 3.注解开发管理bean的生命周期

![image-20221126211732408](../assets/image-20221126211732408.png)



## 4.注解开发做依赖注入

![image-20221126225329549](../assets/image-20221126225329549.png)

**需要在类中提供无参构造方法，但一般类中都默认带有无参构造方法**



### 1.引用类型注入

![image-20221126225548470](../assets/image-20221126225548470.png)



### 2.简单类型的注入

![image-20221126225744965](../assets/image-20221126225744965.png)

**value能够直接读取到properties中的数据，不需要配置任何东西**

**使用${}能够获取到properties中的数据，但是在获取username属性时，会自动获取到系统的名字。**



### 3.properties文件注入

![image-20221126230110319](../assets/image-20221126230110319.png)

**在Springconfig配置类中写注解**



### 4.管理第三方bean

![image-20221127144751351](../assets/image-20221127144751351.png)

![image-20221127144823581](../assets/image-20221127144823581.png)



### 5.为第三方bean实现资源注入

![image-20221127150946000](../assets/image-20221127150946000.png)

![image-20221127151611374](../assets/image-20221127151611374.png)





### 6.总结

![image-20221127151757490](../assets/image-20221127151757490.png)





## Spring整合MyBatis

![image-20221127154903102](../assets/image-20221127154903102.png)

![image-20221127154935560](../assets/image-20221127154935560.png)



## Spring整合Junit

![image-20221127200257546](../assets/image-20221127200257546.png)

![image-20221127202416948](../assets/image-20221127202416948.png)



# Aop

## 1.Aop简介

![image-20221127201128545](../assets/image-20221127201128545.png)

![image-20221127201732271](../assets/image-20221127201732271.png)

![image-20221127201846098](../assets/image-20221127201846098.png)



## 2.Aop入门案例

![image-20221127203217632](../assets/image-20221127203217632.png)

![image-20221127203951461](../assets/image-20221127203951461.png)

![image-20221127204001648](../assets/image-20221127204001648.png)

![image-20221127204015712](../assets/image-20221127204015712.png)

![image-20221127204025114](../assets/image-20221127204025114.png)

![image-20221127204112242](../assets/image-20221127204112242.png)

![image-20221127204122243](../assets/image-20221127204122243.png)

![image-20221127204130915](../assets/image-20221127204130915.png)







## 3.Aop的工作流程

![image-20221127210735082](../assets/image-20221127210735082.png)

![image-20221127210810829](../assets/image-20221127210810829.png)

**AOP工作核心是使用代理模式，通过匹配对应的切入点生成对应的原始类的代理，再走代理模式增强代码功能。**

**使用Aop后不知道为什么注入对象为实现类时会报错，无法找到实现类的bean**





## 4.Aop切入点表达式

![image-20221129153921113](../assets/image-20221129153921113.png)

![image-20221129154118208](../assets/image-20221129154118208.png)

![image-20221129154324911](../assets/image-20221129154324911.png)

![image-20221129161859135](../assets/image-20221129161859135.png)

**以搜索效率和准确度为重点，怎么准确怎么快就怎么写。**





## 5.Aop的通知类型

![image-20221129164653606](../assets/image-20221129164653606.png)

![image-20221129164707387](../assets/image-20221129164707387.png)

![image-20221129164725015](../assets/image-20221129164725015.png)

![image-20221129164537111](../assets/image-20221129164537111.png)

![image-20221129164820435](../assets/image-20221129164820435.png)

![image-20221129164800569](../assets/image-20221129164800569.png)





## 6.案例

![image-20221129172200341](../assets/image-20221129172200341.png)

![image-20221129172149225](../assets/image-20221129172149225.png)





## 7.Aop通知获取数据

![image-20221129220858232](../assets/image-20221129220858232.png)

![image-20221129224118389](../assets/image-20221129224118389.png)



![image-20221129224856205](../assets/image-20221129224856205.png)

**环绕方法能够获取参数，并且返回修改后的参数**

```java
//环绕通知获取参数并返回修改后的参数
public Object servicetongzhi(ProceedingJoinPoint pjp) throws Throwable {
    //获取参数
    Object[] args = pjp.getArgs();
    System.out.println(Arrays.toString(args));
    //给参数去空格
    for (int i = 0; i < args.length; i++) {
        //如果object对象中的参数类型为String类型
        if (args[i].getClass().equals(String.class)){
            //将数组中的类型转换为String类型并去空格
            args[i] = args[i].toString().trim();
        }
    }
    //将修改好的参数传递回去
    Object ret = pjp.proceed(args);
    //返回参数
    return ret;
}
```



## 8.总结

![image-20221201214552437](../assets/image-20221201214552437.png)

![image-20221201214805472](../assets/image-20221201214805472.png)

![image-20221201214926909](../assets/image-20221201214926909.png)

![image-20221201215158094](../assets/image-20221201215158094.png)





# Spring事务

![image-20221201215926602](../assets/image-20221201215926602.png)

**保障业务和数据层同时成功同时失败**



## 1.Spring事务管理的使用

![image-20221202101832541](../assets/image-20221202101832541.png)

![image-20221201220915990](../assets/image-20221201220915990.png)

**1.在JdbcConfig配置文件中添加bean**

**2.以后要是数据库中使用的不是Jdbc的事务那就换接口下面的DataSourceTransactionManager();**





## 2.Spring事务角色

![image-20221201222048600](../assets/image-20221201222048600.png)

![image-20221201222107153](../assets/image-20221201222107153.png)











## 3.事务的传播行为

![image-20221202104014795](../assets/image-20221202104014795.png)



![image-20221202105502314](../assets/image-20221202105502314.png)



![image-20221202104944533](../assets/image-20221202104944533.png)

```java
@Transactional(propagation = Propagation.REQUIRES_NEW);如果有事务我就新开一个事务，如果没有我也新开一个事务
```





# SpringMVC

## 1.简介

![image-20221202144437068](../assets/image-20221202144437068.png)

![image-20221202150432280](../assets/image-20221202150432280.png)



## 2.入门案例

![image-20221202150207207](../assets/image-20221202150207207.png)

![image-20221202150229768](../assets/image-20221202150229768.png)

![image-20221202150238684](../assets/image-20221202150238684.png)

![image-20221202150252557](../assets/image-20221202150252557.png)





**入门案例中使用到的注解：**



![image-20221202150401323](../assets/image-20221202150401323.png)



**入门案例中Tomcat加载SpringMVC配置的接口：**

![image-20221202150610936](../assets/image-20221202150610936.png)

![image-20221202150730268](../assets/image-20221202150730268.png)

![image-20221202150738694](../assets/image-20221202150738694.png)





## 3.入门案例工作流程

![image-20221202171132844](../assets/image-20221202171132844.png)



## 4.bean加载控制

![image-20221202172651155](../assets/image-20221202172651155.png)

**这里是方式二：**

![image-20221202172745906](../assets/image-20221202172745906.png)



**简化Spring的加载书写**

![image-20221202173312721](../assets/image-20221202173312721.png)
