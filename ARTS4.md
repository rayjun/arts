#### Algorithm

Leetcode206，这是一道经典的链表面试题，要求反转一个单链表，这道题的难度其实不大，但是在写代码的过程中非常容易出错。该题的思路如下：

- 使用两个变量分别指向当前节点，和当前节点的上一个节点
- 在反转的过程中需要再使用一个变量来指向当前节点的下一个点

代码如下：

```java
public ListNode reverseList(ListNode head) {
        ListNode current = head;
        ListNode prev = null;

        while(current != null) {
            ListNode temp = current.next;
            current.next = prev;
            prev = current;
            current = temp;
        }

        return prev;
    }
```

#### Review

https://medium.com/thewashingtonpost/the-chinese-gene-editing-experiment-was-an-outrage-the-broader-scientific-community-shares-blame-258f1454ddca

这周发生了一件大事，就是南方科技大学的贺建奎使用基因编辑技术编辑了一个人类的胚胎细胞，并产生了一对双胞胎。华盛顿邮报发了一篇报道来讨论这个事情。总体上的态度就是觉得这件事引起了整个科学界的愤慨。这件事情也告诉我们，我们应该花更多的时间和规则来治理基因编辑的实验，不能让这个实验泛滥起来。


#### Tip

这周新学到了一个 Vim 的命令：cw。在 Vim 的 normal 模式下，依次按下 cw 可以删除从光标处到当前这个单词的末尾同时进入 insert 模式。之前完成同样的工作我使用的是 viwd，完成同样的事情，需要多使用两个键。


#### Share

这周接手的一个项目使用的版本管理工具是 SVN。由于不习惯使用图形工具，于是将 SVN 在命令行常用的命令总结了一下：

http://www.rayjun.cn/2018/12/02/SVN-%E5%91%BD%E4%BB%A4%E8%A1%8C%E7%AE%80%E6%98%93%E6%95%99%E7%A8%8B/