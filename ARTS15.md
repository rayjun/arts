#### Algorithm
Leetcode20，这是一道很经典的关于**栈**的题，使用栈基本就能解决这个问题，但是在实际编码的过程中，有一个小技巧，在栈中存储括号时，应当存储括号的另一半，比如 '(' 应该存成 ')'，这样在最后比较的时候就很好比较。代码如下:

```java
public boolean isValid(String s) {
        Stack<Character> stack = new Stack<>();
        for (int i = 0; i < s.length(); i++) {
            if (s.charAt(i) == '(') {
                stack.push(')');
            }else if (s.charAt(i) == '[') {
                stack.push(']');
            } else if (s.charAt(i) == '{') {
                stack.push('}');
            }
            else {
                if (stack.empty() || stack.pop() != s.charAt(i)) {
                    return false;
                }
            }
        }
        if(!stack.empty()) {
            return false;
        }
        return true;
    }
```

#### Review

https://hacker-tools.github.io/virtual-machines/

这周主要看了 hacker tools 系列的关于虚拟机和容器的文章。虚拟机和容器有着很好的隔离性，虚拟机的环境不会影响到本机环境。而且可以对虚拟机的环境随时进行快照。在任意时刻可以回到之前的任意快照。

虚拟机安装起来比较复杂而且比较占系统的资源。但是容器就好的多，不占系统资源。容器可以被用来做系统部署，持续集成等用处。


##### Tip

git 中 rebase 是一个很神奇的命令，既可以用来合并分支，也可以用来合并多次提交的 commit。如何合并多次的 commit，使用如下的方式就可以:

```shell
$ git rebase -i parantCommitId
```
其中 parantCommitId 是最需要合并的最后一次 commit 的前一次 commit 的哈希值。进入交互式界面后把需要合并的commit 的 pick 修改为 squash，然后合并 commit。 

#### Share

这周继续 Git，这篇文章讲解了关于 Git 的一些高阶用法：

http://www.rayjun.cn/2019/02/17/Git-%E9%AB%98%E9%98%B6%E6%95%99%E7%A8%8B/

