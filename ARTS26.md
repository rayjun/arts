### Algorithm
Leetcode204

这道题要求判断一个数字包含多少个小于它本身的素数。

我采用的是分治的算法，最后统计总数：

**时间复杂度: $O(n^2)$**
**空间复杂度: $O(n)$**

```java
public int countPrimes(int n) {
        if (n - 1 < 2) {
			return 0;
		}
		Map<String,Integer> count = new HashMap<>(n/2);
		countPart(2, n -1, count);
		return count.size();
    }
    
    private void countPart(int begin, int end, Map<String,Integer> result) {
		if (end < begin) {
			return;
		}

		int mid = begin + ((end - begin) >> 1);

		if (isPrime(mid)) {
			if (!result.containsKey(""+mid)) {
				result.put(""+mid, 1);
			}
		}

		countPart(begin, mid - 1, result);
		countPart(mid + 1, end, result);
	}


	private boolean isPrime(int n) {
		if (n <= 1) { return false;}
		for (int i = 2; i * i <= n; i++) {
			if (n % i == 0) { return false;}
		}
		return true;
	}
```

### Review

学习一门新的技能到底要多长时间，有人告诉我们答案了，不要 10000 小时，只需要 20 小时。

这里说的掌握一门新的技术并不不是说的精通，毕竟对于大多数的技能，我们并不需要做到精通，只是会用就行。

很多时候会用是打开另一扇大门的钥匙，要精通一个技能，20小时肯定不够，但是学会足够了。那么如何开始呢？很简单，分两步走:

- 关闭手机
- 开始练习，坚持 20 小时

这个想法来自于这个 TED 演讲：

https://www.youtube.com/watch?v=5MgBikgcWnY&t=125s

### Share

写了一篇关于 Redis 的文章：

[Redis 简明教程](http://www.rayjun.cn/2019/05/12/Redis-%E7%AE%80%E6%98%8E%E6%95%99%E7%A8%8B/)
