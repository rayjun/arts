#### Algorithm
LeetCode234，这道题求的是一个单向链表是不是回文的，暴力破解法也可以处理，但是使用一个栈来辅助会事半功倍，利用快慢指针找到中间节点，把前半部分的数值存入栈中，然后再往后遍历慢指针，与栈顶元素对比，如果出现不一样的数字，则不是回文的，否则就是回文的：

```java
public boolean isPalindrome(ListNode head) {

        if (head == null) {

            return true;

        }

        LinkedList<Integer> stack = new LinkedList<Integer>();

        ListNode slow = head;

        ListNode fast = head;

        while(fast != null && fast.next != null) {

            stack.push(slow.val);

            slow = slow.next;

            fast = fast.next.next;

        }


        if (fast != null) {

            slow = slow.next;

        }
           while (slow != null) {
                if (!stack.isEmpty() &&stack.pop() == slow.val) 
            {

                     slow = slow.next;

                } else {

                     return false;

                }

           }         
           return stack.isEmpty() && true;

    }
```

### Review
这周翻译了一篇文章，关于一个在线的编辑器（CodeSandbox）的文章。

这是 CodeSandbox 的第三个版本，在这个版本中，CodeSandbox 带来了全新的特性，全面引入了 VSCode 的编辑方式和快捷键，而且也带来了全新的设计界面。

在新版中，写代码有更好的体验，左边写代码，右边就能看到执行的结果，体验相比与之前的版本有了很大的提高，而且在后续的版本中，CodeSandbox 会有更加全面的补充。

// Todo 补充原文章

### Tip
无

### Share

在翻译 CodeSandbox 的基础之上。皓哥把这篇文章改了收集各类在线编辑器，目前还在收集当中：

https://github.com/coolshellx/articles/blob/master/02-Online.Code.IDE.Introduction.md
