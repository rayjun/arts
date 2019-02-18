#### Algorithm
Leetcode23，这是一道合并多个有序链表的题，有多个思路，可以直接使用暴力的方式去遍历，然后合并，使用这种方式容易超时，所以解决这个问题，我使用的是归并方法，使用这个方法效率很高，具体代码如下：

```java
    public ListNode mergeKLists(ListNode[] lists) {
        return merge(lists, 0, lists.length - 1);
    }
    
    private ListNode merge(ListNode[] lists, int begin, int end) {
        if (begin < end) {
            int mid = (begin + end) / 2;
            ListNode head1 = merge(lists, begin, mid);
            ListNode head2 = merge(lists, mid + 1, end);

            ListNode newNode = null;
            if (head1 == null) {
                return head2;
            }
            if (head2 == null) {
                return head1;
            }
            if (head1.val > head2.val) {
                newNode = new ListNode(head2.val);
                head2 = head2.next;
            } else {
                newNode = new ListNode(head1.val);
                head1 = head1.next;
            }
            ListNode tmp = newNode;

            while (head1 != null && head2 != null) {
                if (head1.val > head2.val) {
                    tmp.next = new ListNode(head2.val);
                    head2 = head2.next;
                } else {
                    tmp.next = new ListNode(head1.val);
                    head1 = head1.next;
                }
                tmp = tmp.next;
            }

            if (head1 != null) {
                tmp.next = head1;
            } else {
                tmp.next = head2;
            }
            return newNode;
        } else if (begin == end) {
            return lists[begin];
        } else {
            return null;
        }
    }
```

#### Review
最近发现了一个不错的资源， https://hacker-tools.github.io/， 这个教程里面涵盖了一个黑客所需要具备的基本技能，主要包括的课程如下:

- 虚拟机和容器
- Shell 和脚本
- 命令行环境
- 数据整理
- 编辑器
- 版本控制
- 配置文件
- 备份
- 自动化
- 机器自检
- 程序自检
- 包/依赖管理
- 操作系统定制
- 远程机器
- Web 和浏览器
- 安全和隐私

整个的课程系列不长也不难，是属于入门系列的课程，但是同时也推荐了很多的课程可以让你后续继续学习。这些技能及成为一个好的黑客的基本功。

##### Tip

在处理大量的文本类数据的时候，比如在处理日志数据的时候，其实在 Linux 系统中有了很好的工具可以帮助我们完成这些工作。就是 sed 和 awk。

#### Share

这周写了一篇关于 git 底层数据结构的文章:

http://www.rayjun.cn/2019/02/10/Git-%E5%BA%95%E5%B1%82%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E7%A0%94%E7%A9%B6/
