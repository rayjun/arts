#### Algorithm
Leetcode28，实际就是实现 Java 中 indexOf() 方法。具体使用的方法就是遍历一遍字符串，长度为 needle 长度的子串是否在 字符串中出现。

**时间复杂度：O(N) **
**空间复杂度: O(1) **

```java
public int strStr(String haystack, String needle) {
         if (null == needle || Objects.equals("", needle)) {
		 	 return 0;
		 }
		 if (needle.length() > haystack.length()) {
             return -1;
         }
		 
		 for (int j = 0; j < haystack.length(); j++) {
			 if (j + needle.length() <=  haystack.length()) {
				 if (Objects.equals(haystack.substring(j, j + needle.length()), needle)) {
					 return j;
				 }
			 }
		 }
		 return -1; 
    }

```
### Review

https://hacker-tools.github.io/package-management/

一个软件通常是基于其他软件进行开发的，所以软件之间存在依赖的关系。依赖管理已经成为越来越多语言的特性了。

一般来说，这些依赖都会放在依赖仓库中，不同的编程语言一般都有着自己的仓库。仓库中通常存储这这个软件所有的版本的源代码和二进制文件。


版本通常使用版本号来表示：
`x.y.z`，其中 `x` 是主版本号，`y` 是小版本号，`z` 是补丁的版本号。

在使用依赖管理的过程中，有些依赖管理工具会使用 `lock file` 来确认依赖是否安装完整。

不同的依赖管理工具有自己的方式来解决依赖中的一些问题，比如循环依赖问题等。

使用依赖管理器与直接使用源码还有一个很不同的地方在于使用依赖管理器不需要将源代码拷贝到自己的项目中，这样就可以避免混乱，如果有必要对依赖进行扩展，那么直接去更新依赖并且更新依赖的版本号就可以了。

### Tip

在浏览器中，如何彻底的禁用缓存是一个不太好处理的问题，通常的操作总会在一种情况下会失效，但是有一种方式肯定是有效的，那就是通过在 url 添加随机数或者日期毫秒数的方法，在这个情况下，浏览器无法获取到缓存，只能去服务器请求数据了。

### Share

把 Java 并发编程的内容整理了一下：
[Java 并发编程基础](http://www.rayjun.cn/2019/04/08/Java-%E5%B9%B6%E5%8F%91%E7%BC%96%E7%A8%8B%E5%9F%BA%E7%A1%80/)
