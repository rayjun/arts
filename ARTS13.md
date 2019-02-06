#### Algorithm

Leetcode581， 这道题是要在一个数组中找出最短的一段需要排序的子数组。这道题的关键就在于需要找出数组的前面部分和后面部分的有序部分。这里有一个小技巧，那就是后半部分的有序部分从头开始找，前半部分的有序的部分从后面开始找，这样就能找出最后的两端排好序的部分，中间剩余的部分就是需要排序的部分， 代码如下：

```java


public int findUnsortedSubarray(int[] nums) {
    int begin = 0;
    int end = -1;
    int n = nums.length - 1;
    int max = nums[0];
    int min = nums[n];
    for (int i = 1; i < nums.length; i++) {
        max = Math.max(max, nums[i]);
        min = Math.min(min, nums[n - i]);
        if (nums[i] < max) {
            end = i;
        }
        if (nums[n - i] > min) {
            begin = n - i;
        }
    }
    return end - begin + 1;
}

```

#### Review

https://medium.com/s/oversight/facebook-doesnt-care-about-you-cb7bc457344c

2018 年对于脸书来说是不友好的一年，在这一年里，不但公司的市值受到重创，而且关于隐私方面的问题估计会给脸书带来持续的负面影响。对于脸书来说，可能是近些年来步子跨的太大，灵魂没有跟上，结果扯着蛋了。在上面那篇文章中，列举了脸书的很多罪状，基本上都是属于那种为了挣钱，其他的都可以不管，隐私，诱导青少年付费等问题。脸书的工程师够多了，现在脸书需要停下来想想下一步怎么走，也许脸书现在最需要的是哲学家。


##### Tip

之前一直使用的都是 emacs 的 helm，但是最近感觉 helm，但是 helm 太重，跟不上手速，于是最近把 helm 切换到了 ivy，这才感觉是真正的适合进行编辑的方式，总之太棒了。

#### Share

年底了，这一篇作为自己的年终总结：

http://www.rayjun.cn/2019/02/04/2018%E5%B9%B4%E6%80%BB%E7%BB%93/