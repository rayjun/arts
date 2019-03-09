#### Algorithm

leetcode98。这道题是判断一棵树是否是搜索二叉树，搜索二叉树有一个特点，那就是一个节点左边的值一点小于该节点，一个节点右边的值一定大于该节点，这道题可以使用中序遍历的方式把树遍历出来，如果这是一棵二叉树，那么每个节点左边的值都小于它每个节点右边的值都大于它, 代码如下:

```java
public boolean isValidBST(TreeNode root) {
           if (root == null) {
                return true;
           }
           double inorder = -Double.MAX_VALUE;
           Stack<TreeNode> stack = new Stack<>();
           TreeNode currentNode = root;
           while (currentNode != null || !stack.empty()) {
            while (currentNode != null) {
                stack.push(currentNode);
                currentNode = currentNode.left;
            }
            currentNode = stack.pop();
            if (currentNode.val <= inorder) {
                 return false;
            }
            inorder = currentNode.val;
            currentNode = currentNode.right;
        }
           return true;
    }
```


#### Review

https://hacker-tools.github.io/command-line/ 命令行的环境作为一个程序员会接触的非常多。

命令对于操作计算机是一个非常有效率的方法，命令行提供了一系列的接口(awk、sed、grep、find)等，
这些命令往往有很多的参数，不同的参数可以完成的功能是完全不一样的。

如何使用这些命令需要长时间的练习，比如获取使用次数最多的10个命令可以通过如下的方式获得:

```shell
cat .bash_history | sort | uniq -c | sort -rn | head -n 10 (or cat .zhistory | sort | uniq -c | sort -rn | head -n 10 for zsh)
```

同时命令行的环境也是可以进行定制的，比如有很多的终端软件可以选择，终端字体的大小、颜色、操作习惯等也都是可以调整的。

原生的很多命令使用起来的体验不够好，但是也可以找到很多的替代:

比如使用 fasd 替代 cd，使用 bat 替代 cat，fd 替代 find ， trash 替代 rm。

#### Tip

在命令行环境中，grep 是一个很有用的命令，不但自身的查询能力强大，而且可以结合管道等功能完成很复杂的功能。但是也有更好的替代品，比如  ag(the_sliver_searcher)。这个相比于 grep 的优势是搜索的速度极快，而且支持搜索结果的高亮。使用起来也很简单:

```shell
$ ag "string-to-search"
```

#### Share

这周写了一篇关于 Java NIO 的基础篇：

http://www.rayjun.cn/2018/07/28/Java-NIO-%E7%AE%80%E6%98%8E%E6%95%99%E7%A8%8B/