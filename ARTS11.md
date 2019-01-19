#### Algorithm

Leetcode 605，这道题是想找出在一个数组中如何插入合适的数字，然两两数字之间相隔都有0，这只需要遍历一遍数组，看看有多少个合适的位置可以插入数字，如果插入的数据数量可以满足输入的数量就返回 true，否则返回 false。代码如下：

```java
public boolean canPlaceFlowers(int[] flowerbed, int n) {
    if (flowerbed.length < 1) {
        return false;
    }
    for (int i = 0; i < flowerbed.length; i++) {
        if( n == 0) {
            break;
        }
        if (i == 0) {
            if ((flowerbed[0] == 0 && flowerbed.length > 1&& flowerbed[1] == 0) || (flowerbed[0] == 0 && flowerbed.length <= 1)) {
                n--;
                flowerbed[0] = 1;
            }
        }
        else if (i == flowerbed.length - 1) {
            if (flowerbed[i] == 0 && flowerbed[ i-1] == 0) {
                n--;
                flowerbed[i] =1;
            }
        } else {
            if (flowerbed[i] == 0 && flowerbed[i-1] == 0 && flowerbed[i+1] == 0) {
            n--;
            flowerbed[i] = 1;
            }
        }
    }
    if ( n == 0) {
        return true;
    }
    return false;
}

```

#### Review

这周重新把 https://winterbe.com/posts/2014/03/16/java-8-tutorial/ Java8 的这篇新特性文章重新看了一遍并且翻译出来，真的特别适合快速学习 Java8 的新特性。


#### Tip

这周彻底把 Java8 的 lambda 表达式联系熟练了，然后回头一看，代码短了好了。


#### Share

这周翻译了 Java8 的入门文章，在这里:

http://www.rayjun.cn/2019/01/19/Java8%E7%AE%80%E6%98%8E%E6%95%99%E7%A8%8B/