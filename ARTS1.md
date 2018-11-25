### ARTS分享第1周：

耗子的专栏刚出的时候就买了，也一直在跟着学，虽然后中间也跳过了很多内容（信息量太大）。Leetcode 一直在刷，但是 Bolg 写的数量不够多，那么就从这里正式开始吧~



#### Algorithm

这是一道和数组相关的题，常规的解题思路并不是很困难，只需要使用两个额外的数组，但是会带来额外的空间复杂度。这个算法可以优化，只需要在数组内进行操作，不需要额外的空间，以下是我的思路：

- 从数组的两段进行插入，偶数从数组开头开始插入，奇数从数组末尾开始插入
- 使用一个游标来标记当前遍历到的数组下标，并判断当前下标对应的值是偶数还是奇数
- 然后将值交换到对应的端，并记下下一个下标继续比较直到偶数的下标与奇数的下标相遇
- 算法的时间复杂度为 ![O(n)](https://www.zhihu.com/equation?tex=O(n)),空间复杂度为 ![O(1)](https://www.zhihu.com/equation?tex=O(1))

代码示例：

```java
 public static int[] sortArrayByParity(int[] A) {

        if(A.length <= 1) {
            return A;
        }
        // 偶数下标
        int start = 0;
        // 奇数下标
        int end = A.length - 1;
        // 当前遍历的下标
        int index = 0;
        int temp = 0;
        while(start < end) {
            if(A[index]%2 == 0) {
                // 如果当前的位置就是需要插入的位置，则直接下一个
                if(start == index) {
                    start++;
                } else {
                    temp = A[start];
                    A[start] = A[index];
                    A[index] = temp;
                    start++;
                }
                // 重新设置下标
                index = start;
            }else {
                if(end == index) {
                    end--;
                } else {
                    temp = A[end];
                    A[end] = A[index];
                    A[index] = temp;
                    end--;
                } 
                index = end;
            }
        }
        return A;
    }
```



#### Review

https://medium.com/@jimmysong/why-blockchain-is-hard-60416ea4c5c

自从从耗子的专栏中知道了 Medium 之后，就一直在上面阅读了，不但能找到第一手的资料，还能顺便学英语。这周我看的是一篇与区块链相关的文章，文章的链接已经放在上面了。

这篇文章简单介绍了一下什么是区块链，区块链本身没有很新的技术，而且从技术的角度来说，有很多值得被吐槽的地方，比如区块链就是一个巨慢的分布式的数据库。而且区块链从开发的角度上来说也非常的不友好：

- 开发的过程很慢很严格（因为出了bug代价很大）
- 架构很难设计
- 维护起来很难
- 扩展很难（因为少兼容以前的数据）

既然有这么多的不好的地方，那么为什么还要使用区块链呢，因为区块链能够消除单点故障。

但是大多数的企业其实是用不上区块链的，因为很多的企业需要经常性的升级和扩展，但是为什么这么多的公司还是想要和区块链技术扯上关系呢？当然是因为区块链离钱很近。

#### Tip

我发现身边很多人不想学 Java，他们老是吐槽写 Java 代码需要很笨重的 IDE。这会有了这个工具后，你们再没有理由了：[Java in Vscode](https://link.zhihu.com/?target=https%3A//code.visualstudio.com/docs/languages/java)，这个工具是微软官方推出的 Vscode 插件，基本上支持当前主流的 Java 开发，Maven、Gradle、Tomcat、Springboot。

#### Share

这周写了一篇与区块链相关的文章，欢迎吐槽：

[简单聊一聊区块链](https://mp.weixin.qq.com/s/NB6ieVCegHSKmzlzX1js-A)