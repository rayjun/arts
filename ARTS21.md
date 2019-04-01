#### Algorithm
LeetCode160，找出两条链表的相交的节点。需要注意的是，这道题比较的是节点的引用，而不是节点的值。
这道题可以使用两个指针进行遍历，当两个指针指向同一个节点时，就得到了结果：

```java
public ListNode getIntersectionNode(ListNode headA, ListNode 
headB) {  
            ListNode a = headA;
          ListNode b = headB;
          // 此处注意，需要比较的是节点的引用是不是相同的，而不是比较值

          while (a != b) {

            if (a == null)  a = headB;

              else a= a.next;

              if (b == null)  b = headA;

              else b = b.next;

        }
         return a;

    }

```

### Review
http://christophjanz.blogspot.com/2014/10/five-ways-to-build-100-million-business.html?m=1

则是一篇很有意思的文章，文章讲述了如何用五种方法来创办一个市值十亿美金的独角兽公司。文章分析了，如果要达到十亿级别，需要拥有的客户群体：

- 1 千个每年可以付给你 10 万美金的企业客户
- 1 万个每年可以付给你 1 万美金的中小企业
- 10 万个每年可以付给你 1 千美金的小企业
- 1 百万个每年可以给你 100 美金的个人用户
- 1 千万可以给你带来 10 美金广告费的活跃用户

然后分别将这五类的归类为不同的公司。把做成这些公司规模的过程分成猎大象、猎鹿、猎兔子、猎老鼠、猎苍蝇。并分别举出了这五类公司中具有代表性的公司。

这五类的公司分别代表了不同的商业模式。


### Tip
在 linux 或者 mac 系统中，可以通过 crontab 来定制定时任务。但是 crontab 定制任务时比较复杂，而且很容易出错。在 Mac 中使用定时任务就容易的多了。使用 launchctl 加上 plist 就可以轻松的完成定时任务的定制。

### Share

[如何在 Mac OS X 中优雅的使用定时任务](http://www.rayjun.cn/2019/03/31/Mac-OS-%E4%B8%AD%E5%A6%82%E4%BD%95%E4%BC%98%E9%9B%85%E7%9A%84%E5%88%9B%E5%BB%BA%E5%AE%9A%E6%97%B6%E4%BB%BB%E5%8A%A1/)
