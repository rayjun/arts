#### Algorithm

LeetCode198，这是一道关于打家劫舍的题，就是要求抢劫一排商店，但是不能抢劫相邻的两家，要求最后抢到的钱最多。这道题使用简单的递归就能解决，在递归的过程中缓存结果:

**时间复杂度**: $O(N)$
**空间复杂度**: $O(N)$

```java
public int rob(int[] nums) {
           if (nums.length == 0) {
                return 0;
           }
           int[] map = new int[nums.length];

           for (int i = 0; i < nums.length; i++) {
            map[i] = -1;
            }
           return find(nums, map, nums.length - 1); 
}

     private int find(int[] nums, int[] map, int index) {
           if (index < 0) {
                return 0;
           }
           if (index >= 0) {

                if (map[index] != -1) {
                     return map[index];
                }
           }
           map[index] = Math.max(find(nums, map, index - 1), 
find(nums, map, index - 2) + nums[index]);
           return map[index];

     }
```

### Review



### Tip



### Share

这周写哥篇很长的文章，所以就算是 Review 和 Tip 一起处理了吧，这篇文章是在皓哥的帮助下完成的：
http://www.rayjun.cn/2019/03/18/%E5%A6%82%E4%BD%95%E6%89%93%E9%80%A0%E4%B8%80%E4%B8%AA%E9%AB%98%E6%95%88%E7%9A%84%E5%B7%A5%E4%BD%9C%E7%8E%AF%E5%A2%83/

