### Algorithm
Leetcode238

这道题需要求的是在给定一个数组，如何求除了自身之外其他元素的乘积，要求空间复杂度是 $O(1)$。我的解法是将所有的元素相乘，然后再遍历一遍数组，除以每个元素，也就得到了结果。但是有一个陷阱，就是要注意数组中的 0。

时间复杂度：**$O(N)$**
空间复杂度：**$O(1)$**

```java
public int[] productExceptSelf(int[] nums) {
		int result = 0;
		int zeroCount = 0;
		for (int i = 0; i < nums.length; i++) {
			if (nums[i] != 0) {
				if (result == 0) {
					result = nums[i];
					continue;
				}
				result *=  nums[i];
			} else {
				zeroCount += 1;
			}
		}

		for (int i = 0; i < nums.length; i++) {
			if (nums[i] != 0) {
				if (zeroCount > 0) {
					nums[i] = 0;
				} else {
					nums[i] = result / nums[i];
				}
			} else {
				if (zeroCount <= 1) {
					nums[i] = result;
				} else {
					nums[i] = 0;
				}
			}
		}

		return nums;
    }
```

### Review

如何过上更好的生活，赚更多的钱？变得更出名？也许吧。

在这个研究中，
https://www.youtube.com/watch?v=8KkKuTCFvzI，分别对哈佛大学的学生和贫民窟的小孩进行了长达 75 年的持续调查。

然后从中获取到了一个信息，无论是对于精英还是平民、对于穷人还是富人，与周围的人保持一个好的关系可以让人生活的更加健康和快乐。

很简单对不对，最好的东西往往最不起眼。

### Share

索引时使用数据库所没法避免的一个坎，这篇文章中聊了一下 MySQL 索引的底层数据结构:

[MySQL索引与B+树](http://www.rayjun.cn/2019/05/14/MySQL%E7%B4%A2%E5%BC%95%E4%B8%8EB+%E6%A0%91/)
