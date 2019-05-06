#### Algorithm
Leetcode94

使用非递归的方式中序遍历一棵二叉树。在遍历的过程中需要用到一个栈来辅助。

**时间复杂度: $O(N)$**
**空间复杂度: $O(N)$**

```java
public List<Integer> inorderTraversal(TreeNode root) {
	     List<Integer> result = new ArrayList<Integer>();
	     
	     if (root == null) {
	    	 return result;
	     }
	     
	     Stack<TreeNode> stack = new Stack<TreeNode>();
	     stack.push(root);
	     
	     TreeNode tmp = stack.pop();
	     while (tmp != null || !stack.empty()) {
	    	 
	    	 while (tmp != null) {
	    		stack.push(tmp);
	    		tmp = tmp.left;
	    	 }
	    	 tmp = stack.pop();
	    	 result.add(tmp.val);
	    	 tmp = tmp.right;
	     }
	     
		 return result;
	 }
```

### Rwview

学习数据结构和算法可能是学习编程过程中最难的部分。大部分人都没有跨过这个坎。
https://medium.freecodecamp.org/i-built-an-app-that-makes-learning-algorithms-and-data-structures-way-more-fun-46fbb8afacaf

这篇文章中，这个作者分享了自己学习数据结构和算法的过程，并且开发了一款学习数据结构的 APP。

作者是自学的编程，之前也没有科班的基础，也不是很擅长数学。但是却开发出了学习数据结构的 APP，他开发这款 APP 的动力就是可以更加轻松的学习数据结构和算法。

这个数据结构与算法沙盒的 APP 在这里。每个算法都用动态图的形式展现出来，
很容易看懂。很难相信这个 APP 是一个计算机小白开发出来的，而且基于 React Native 的开发独立 APP 也正在准备中。

编程一直是这几年的风口，写代码再也不是需要经过专门培训的人才能干的事了。只要对编程感兴趣，网上就有大量的教程可以学习。有很多的论坛可以去交流讨论，只要愿意花时间。慢慢的编程将会变成一个通识技能，日常中做的任何事情可能都和编程有关。学编程就像原来学习英语、语文一样，变成一个必修课、一个必备的技能。

### Share

分享一个算法的学习总览:
[算法简明教程](http://www.rayjun.cn/2017/05/06/%E7%AE%97%E6%B3%95%E7%AE%80%E6%98%8E%E6%95%99%E7%A8%8B/)



