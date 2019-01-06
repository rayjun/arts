#### Algorithm

Leetcode849，这道题是要求一个只有0和1的数组中，找到一个 0 的位置，这个位置距离 1 的位置最远。这里有一个简单的思路，就是遍历一次，找出所有的由两个 1 包含的 0 的区间，然后找出最大的区间，就可以得到结果，代码如下：

```java
 public int maxDistToClosest(int[] seats) {
         int left = -1, maxDis = 0;
        int len = seats.length;
        
        for (int i = 0; i < len; i++) {
            if (seats[i] == 0) continue;

            if (left == -1) {
                maxDis = Math.max(maxDis, i);
            } else {
                maxDis = Math.max(maxDis, (i - left) / 2);
            }
            left = i;
        }
        
        if (seats[len - 1] == 0) {
            maxDis = Math.max(maxDis, len - 1 - left);
        }
        
        return maxDis;
    }
```

#### Review
https://medium.com/new-york-times-opinion/in-search-of-lost-screen-time-60a160779618

> 如果我们把手机丢弃一年，我们会用这些时间和钱来做什么？

美国 2018 年人均花 **$1380** 和 **1460** 小时在手机上。

**种树**：
这些钱在美国可以买半英亩土地， 可以种植 150 棵树。

**恋爱**：
根据调查，手机依赖会让两个人的关系更加不确定。29%的美国人宁愿放弃三个月的性生活也不愿意放弃手机一个礼拜。

**政治活动**:
这些时间足够他们一年每周三次去和州议员见面交流。

**环境清理**:
用买手机的钱去清理垃圾，足够清理美国积累了 70 的年的海洋塑料垃圾。

**阅读**：
按照平均 280字/分钟的阅读速度，可以读完 20 本 130 万字的书。


#### Tip

大多数的数据库性能问题其实都可以通过建立索引来解决。

#### Share

这周解决了一个关于数据性能的问题，索引顺带写了一篇关于索引的文章:
http://www.rayjun.cn/2019/01/06/MySQL%E7%B4%A2%E5%BC%95%E7%AE%80%E6%98%8E%E6%95%99%E7%A8%8B/