#### Algorithm

Leetcode134：这是一个经典的贪心问题。这题中要把握两个点。一个是油量的总和是不是大于等于消耗的总和。第二是找出油量可以正向积累的起点 ，意思就是在开始过站后油量不会为负的起点。代码如下:

```java

public int canCompleteCircuit(int[] gas, int[] cost) {
    if (gas.length <= 0 || cost.length <= 0) {
        return -1;
    }
    int total = 0;
    int temp = 0;
    int index = 0;
    for (int i = 0; i < gas.length; i++) {
        total += gas[i] - cost[i];
        temp += gas[i] - cost[i];
        if (temp < 0) {
            index = i + 1;
            temp = 0;
        }
    }
    return total < 0 ? -1 : index;
}
```


#### Review

这周看了 winterbe java8 Stream 的详细教程：https://winterbe.com/posts/2014/07/31/java8-stream-tutorial-examples/

Stream 有 **non-interfering** 和 **stateless** 两个特性，分别指 **stream** 的数据在进行 **stream** 操作时数据不能被变更，以及传入 **stream** 中的 **lambda** 表达式中没有依赖外部的可变变量。

##### 1. Stream 的类型

Stream 可以分成两类：

- 串联 Stream
- 并行 Stream

原生数据类型 Stream 与常规 Stream 有一些差别，原生数据类型的 Stream 另外支持 average() 和 sum() 等方法。 

##### 2. Stream 的处理顺序

中间操作只有在中观操作存在时才会执行。对于 Stream 中的每一个元素，并不会在一个操作里面将所有的元素都处理，而是一个元素将所有的操作都执行完了之后才会处理第二个元素。可以通过调整中间操作的顺序来减少方法的调用次数。


##### 3. Stream 的重用

Java8 中，只要一个 Stream 执行了终端操作，Stream 就关闭了，就不能执行其他的操作了。如果要重用，那就使用 **Supplier** 来重用 Stream。


##### Tip

Java8 虽然出来很久了，但是很多 Java 程序员还是没有跨过这个坎，使用 Java8 中的用法可以大大减少 Java8 的冗余代码。


#### Share

这周总结了一下关于写作的一些想法。

http://www.rayjun.cn/2019/01/27/%E5%AD%A6%E4%BC%9A%E5%86%99%E4%BD%9C/