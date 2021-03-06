#### Algorithm
Leetcode 746，这道题是爬楼梯问题的变体，在每一步楼梯上增加了一个消耗值，要求最后的爬完楼梯的最少消耗，这道题中有两个陷阱：
- 在解决爬楼梯问题中，采用递归的方式会重复计算，做这道题中也是一样，要去除掉那些重复计算的值。
- 在每次计算爬楼梯的同时，我们要计算出最小消耗，而且只需要保存这个最小消耗的值。

代码如下:

```java
public int minCostClimbingStairs(int[] cost) {
        int add[] = new int[cost.length];

        climb(cost, cost.length - 1, add);
        
        return Math.min(cost[cost.length - 1], cost[cost.length - 2]);
    }

    private int climb(int[] cost, int n, int[] add) {
        if (n == 0) {
            return cost[0];
        }
        if (n == 1) {
            return  cost[1];
        }
        if (add[n] != 1) { 
            cost[n] += Math.min(climb(cost, n -1, add),climb(cost, n - 2, add));
            add[n] = 1;
        }
        return cost[n];
    }
```

#### Review

在这篇文章中，详细解释了网飞广告和处理流程：

面临的**业务**问题:
- 网飞面向全球，用户的种类多样化，市场团队需要给不同的人推送不同的内容和消息，而且还需要区分不同的平台
- 制作一个广告的流程很多，制作、A/B测试、格式化和本土化、质量控制、内容更新等问题。

从这些业务问题里面可以提取出三个主要的**技术**问题:
- 广告装配：一个可量化的广告生产和构建的自动工作流；
- 创意的质量控制: 一系列的工具和服务来通过低成本的方式控制数千个广告单元功能和语义的正确性；
- 广告目录管理：基于机器学习的方法来尽可能容易的管理广告；

广告的装配是一个非常复杂的问题，需要不同的广告类型、不同的平台、广告的概念、格式化、A/B测试和本地化等问题。 网飞是通过开发一个动态的广告制作和配置平台来实现的。

广告的质量控制从两个方面来控制，一个广告本身的问题，比如错别字、错误的内容等，还有一方面是去检查在不同平台上的限制，广告的字数是不是超过了 google 或者 facebook 的限制。

当广告通过了装配和质量控制后，就会进入到广告的管理阶段。这一阶段就是广告的正式投放阶段了，广告会根据之前通过机器学习计算出来的用户模型将不同的广告推送到不同的用户手中，当然广告也不是直接就能够投放的，需要根据本地化和 A/B 测试的计划来。


#### Tip

现在主流的编辑器中基本都加入一个在项目中全局搜索来搜索项目中的文件。在 emacs 中也可以完成这个事情，通过 `find-file-in-project` 这个插件可以帮助完成这些事情。


#### Share

写了一篇关于 Jenkins的文章

http://www.rayjun.cn/2018/12/23/Jenkins-%E7%AE%80%E6%98%8E%E6%95%99%E7%A8%8B/