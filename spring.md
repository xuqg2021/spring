# spring

## IOC 控制翻转

## DI 依赖注入

spring有IOC容器，存放bean的容器

加载xml、解析xml，封装BeanDefinition，实例化、放到容器中、从容器中取出

spring使用map作为容器存放bean

spring Bean --> scope --> singleton\prototype\request\session

使用反射方式创建实例比较灵活，new的方式比较死板	

BeanFactory容器的根接口

重要的三个类

```java
BeanFactory
```

```java
AbstractAutowireCapableBeanFactory
```

```
DefaultListableBeanFactory
```

在容器创建过程中需要动态改变bean的信息怎么办？

PostProcessor  (后置处理器)-- > BeanPostProcessor(增强bean信息)、BeanFacoryPostProcessor（增强beandefinition信息）

创建对象：1. 实例化，在堆中开辟空间，对象的属性都是默认值。2. 初始化，给属性设置值（1，填充属性，2，执行初始化）init-method。

实例化，填充属性，设置Aware接口的属性，BeanPostProcessorbefore，执行init-method方法，BeanPostProcessorafter，得到完整对象，放到容器空间里。