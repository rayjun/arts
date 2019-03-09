#### Algorithm

Leetcode977，这是一道新题，求一个升序数组每个元素平方后的排序值。

这道题很简单，有一个地方可以改良一下，就是首先判断一下原数组的第一个值是不是为负数，如果为负
数，那么求平方后的数组就需要重新排序，如果不为负数，请平方后的数组就不需要排序了:

**时间复杂度**: $O(nlogn)$
**空间复杂度**: $O(1)​$

```Java
 public int[] sortedSquares(int[] A) {
       if (A.length == 0) {
			return A;
		}
		boolean isNet = true;
		
		if (A[0] >= 0) {
			isNet = false;
		}
		
		for (int i = 0; i < A.length; i++) {
			A[i] = A[i] * A[i];
		}
		
		if (isNet == true) {
			Arrays.sort(A);
		}
				
		return A;    
 }
```

### Review

https://hacker-tools.github.io/web/

日常工作中，浏览器使用的非常多，如何使用浏览器更有效率也是值得学习的一个技能。


#### 快捷键

单靠点击来操作浏览器有点低效，熟悉常用的快捷键很值得。

- **鼠标中键** 在新的 tab 中打开一个链接
- **Ctrl+T** 打开一个新的 tab
- **Ctrl+Shift+T** 重新打开最近关闭的一个 tab
- **Ctrl+L** 选中浏览器搜索框中的内容
- **Ctrl+F** 浏览器页面中搜索内容

#### 搜索操作符

搜索引擎通常提供了一些操作符让 web 搜索更加有效率：

- **bar foo** 强制要求搜索结果中包含 bar 和 foo
- **foo site::bar.com** 在 bar.com 的范围内搜索 foo
- **foo -bar** 在搜索结果中不包含 bar
- **foo filetype:pdf** 搜索指定的文件类型
- **(foo|bar)** 搜索结果中包含 foo 或者 bar


### Tip

这周学到了一些很有意思的位操作符。用位操作符可以完成很多不可思议的东西，比如下面的位操作：

```java
~n + 1
```
实际上这个操作时用来求一个数的相反数。其他的详细见我这周的文章。

### Share

这周的文章详细写了位操作符相关的内容：

http://www.rayjun.cn/2019/03/09/%E4%BB%8ELeetCode371-%E7%90%86%E8%A7%A3%E4%BD%8D%E8%BF%90%E7%AE%97/