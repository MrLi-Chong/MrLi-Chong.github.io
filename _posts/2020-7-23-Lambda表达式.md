# Lambda

## 常用的函数式接口方法

- Supplier代表一个输出

- Consumer代表一个输入

- BiConsumer代表两个输入

- Function代表一个输入，一个输出（一般输入和输出不同类型）

- BiFunction代表两个输入，一个输出（一般输入和输出不同类型）

- UnaryOperator代表一个输入，一个输出（输入和输出是相同类型的）

- BinaryOperator代表两个输入，一个输出（输入和输出是相同类型的）

## 方法的引用分类

| 类型         | 语法               | 对应的lambda表达式                 |
| ------------ | ------------------ | ---------------------------------- |
| 静态方法引用 | 类名::staticMethod | (args)->类名.staticMethod(args)    |
| 实例方法引用 | inst::instMethod   | (args)->inst.instMethod(args)      |
| 对象方法引用 | 类名::instMethod   | (inst,args)->类名.instMethod(args) |
| 构造方法引用 | 类名::new          | (args)->new 类名(args)             |

# Stream

Stream是一组用来处理数组、集合的API

## 特性

1. 不是数组结构，没有内部存储
2. 不支持索引访问
3. 延迟计算
4. 支持并行
5. 很容易生成数组或集合（List,Set）
6. 支持过滤、查找、转换、汇总、聚合等操作

## 中间操作

- 过滤filter
- 去重distinct
- 排序sorted
- 截取limit前多少个、skip跳过前多少个
- 转换map/flatMap
- 其他peek

## 终止操作

- 循环forEach
- 计算main、max、count、average
- 匹配anyMatch、allMatch、noneMatch、findFirst、finAny
- 汇聚reduce
- 收集器toArray collect

## Stream的创建

1. 通过数组
2. 通过集合
3. 通过Stream.generate方法来创建
4. 通过Stream.iterate方法来创建
5. 其他API创建

## parallel并行流

设置并行执行的线程数

```java
System.setProperty("java.util.concurrent.ForkJoinPool.common.parallelism","线程数量");
```



## sequential顺序流