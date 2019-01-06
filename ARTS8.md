#### Algorithm
Leetcode746 这道题是爬楼梯题目的变体，在每一步楼梯中加入了不同的权重，那么在递归计算的时候，只需要计算代价最小的那个就可以了,代码如下：

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

https://www.feval.fr/posts/microservices/

这是一篇讲微服务的文章，作者分析了在什么时候不适合使用微服务技术。

在过去的四年中，微服务已经成为事实上的架构标准。因为微服务有弹性扩容、高可用、低耦合等优点。
微服务是一种新的组件设计和部署模式，尽量使每一个服务保持简单，可以独立进行部署和修改。

**微服务的挑战**：

- 微服务很难设计
- 服务很复杂，因为 CAP 决定了分布式系统的复杂行，而且网络是一个很复杂的因素，同时分布式的应用很难调试。
- 需要组织一个跨职能的团队，包括开发、运维、测试等角色
- 微服务的是否成功很考验一个团队的应变能力，这就需要团队成员的能力很强。

**什么时候不应该使用微服务**：

- 应用太小时
- 当业务逻辑不清晰或者不确定时
- 团队还不能适应转向微服务化，而且团队对微服务的理解不清晰、微服务的相关技能储备不足时

但是微服务对于复杂系统是一个很好的解决方案，但是需要在合适的时间点引入。

#### Tip

这周学习了一个 go 的爬虫框架 colly，这个框架最大的特点就是快，充分发挥了 go 语言的特性。而且很简单就可以支持分布式的爬虫。

#### Share

年底了，分享一下今年的书单：
http://www.rayjun.cn/2018/12/29/%E6%88%91%E7%9A%842018%E5%B9%B4%E4%B9%A6%E5%8D%95/