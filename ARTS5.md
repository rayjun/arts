#### Algorithm
Leetcode 141，这是一道经典的链表题，在这道题里面。需要判断链表上有没有形成环，解题的思路有很多种。最为经典的方法就是快慢指针，
设置两个指针，快指针每次走两步，慢指针每次走一次，后续如果两个指针可以相遇，说明链表有换，否则就是没有环， 代码如下：

```java
 public boolean hasCycle(ListNode head) {
        ListNode fast = head;
        ListNode slow = head;

        while(fast != null && fast.next != null) {
            fast = fast.next.next;
            slow = slow.next;
            if(fast == slow) {
                return true;
            }
        }
        return false;
    }
```


#### Review

https://medium.com/netflix-techblog/engineering-to-improve-marketing-effectiveness-part-1-a6dd5d02bab7

网飞(netflix)增长的方式就是通过制造优质、原创而且只能在网飞平台看到的内容来吸引用新用户。

需要做到这一点，那么网飞就需要知道不同地区的用户都喜欢什么样的内容，所以这就决定了网飞是一家数据驱动的公司。数据驱动的公司需要有强大的技术团队来作为支撑，提升工作效率。

技术团队帮助市场团队可以从以下的几个方面来提高效率：

- 通过技术来改善工作流程，帮助市场团队从繁杂的具体事务中抽身出来，集中精力到创意方面
- 建设系一个统一的广告制作和分发平台
- 通过技术的手段来优化市场工作的效率，比如通过谷歌和脸书的算法来改善预算花费的效率

为了提高生产效率，自动化非常重要。

重要的工具：
- 数字资产管理
- 云端视频剪切
- 营销视频组装
- 云端加密


#### Tip

因为很喜欢 emacs，但是又非常习惯 vim 的快捷键，emacs 中有一个插件 evil，这个插件在emacs 中使用 vim 的编辑习惯，然后又可以使用 emacs 的模式和 orgmode。虽然 evil 币 vim还是有点不足。但是已经够用了。

#### Share

[Cas 系统简介](http://www.rayjun.cn/2018/12/09/Cas-%E7%B3%BB%E7%BB%9F%E7%AE%80%E4%BB%8B/)