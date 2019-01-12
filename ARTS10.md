#### Algorithm

Leetcode147，这道题是要求用插入排序的方式去给链表排序。由于链表没有数组那种可以按照下标随机访问的特性，所以在插入的过程中需要注意控制已经排好序列的位置，控制好这个，其他的就按照插入排序来就可以了。代码如下:

```java
public ListNode insertionSortList(ListNode head) {
        ListNode p = new ListNode(Integer.MIN_VALUE);
        p.next = head;
        head = p;
        ListNode begin = head; // 有序序列的开头
        ListNode index = head; // 有序序列的结尾
        p = head.next;
        while (p != null) {
                ListNode i = head;
                // 在没有遍历到有序序列结尾的情况下继续比较
                while (i != index && begin.next != null) {
                    if (p.val < begin.next.val) { // 找到位置，插入
                        index.next = p.next;
                        p.next = begin.next;
                        begin.next = p;
                        p = index.next;
                        begin = head;
                        break;
                    } else { // 没有找到位置，继续遍历
                        begin = begin.next;
                        i = i.next;
                    }
                }
                if (i == index) {
                    p = p.next;
                    index = index.next;
                    begin = head;
                }
        }
        return head.next;
}

```


#### Review

https://winterbe.com/posts/2014/03/16/java-8-tutorial/#method-and-constructor-references

Java 8 对于 Java 程序员来说是一个坎，很多人至今都没有跨过这个坎，这篇文章用很清晰的语言和简单的例子介绍了 Java8 中最为重要的特性。主要介绍了以下的特性：

- 接口的 **default** 方法
- **lambda** 表达式
- 方法引用
- 可复用注解
- streams Api
- 功能性接口
- map 的扩展
- 新的 Date Api


#### Tip

git bisect 这个命令很有意思，可以帮助我们找到哪次开发引入了错误。
http://www.ruanyifeng.com/blog/2018/12/git-bisect.html


#### Share

这周写了一篇 Git 的入门教程:

http://www.rayjun.cn/2019/01/12/Git%E7%AE%80%E6%98%8E%E6%95%99%E7%A8%8B/