#### Algorithm

Leetcode69，这道题本身很简单，是通过自己的方式去求一个的数的开平方。但是却可以通过二分法的方法来解决这个问题，具体的代码如下, 这个地方有一个坑，那就是 mid 的类型一定要是 long， 否则运算的过程中会溢出，导致结果不对:

```java
public int mySqrt(int x) {
        int begin = 0;
        int end = x;

        while (begin <= end) {
            long mid = begin + (end -  begin) / 2;
            if (mid * mid == x) {
                return (int)mid;
            } else if (mid * mid < x) {
                begin = (int) (mid + 1);
            } else {
                end = (int) (mid - 1);
            }
        }

        return end;
    }
```

#### Review

这篇文章是关于黑客技能的另外一篇文章，这篇文章主要用来构建自己的命令行环境：

https://hacker-tools.github.io/command-line/

- 很多时候在输入命令的时候需要输入很大一串，但是通过 alias 和 function 定义一些我们常用的命令。
- 尽管 bash 已经成为命令行中的默认选项，但是我们也还是可以选择比 bash 更加强大的 zsh 来作为脚本框架。 zsh 是 bash 的超集。
- 有很多的终端仿真程序可以选择，这个可以根据自己的使用环境来进行选择，但是 **tmux** 却是每个终端都值得拥有的。
- 命令行实用工具，有很多的经过改良的工具可以让我们使用起来更加的有效率，比如使用 **fasd** 代替 **cd**，使用 **bat** 代理了 **cat** 等等。


#### Tip

在日常访问远程服务器时，我们很多时候需要保持在服务器端的状态，但是命令行很多时候会出现超时重连的状况。如果使用 **tmux** 就可以解决这个问题，使用 tmux 登录服务器时，如果超时了，在服务器的状态也不会丢失，重新登录到服务器之后，还可以从之前的状态继续工作。

#### Share

这周写了一篇关于 Java IO 简介的内容。

http://www.rayjun.cn/2018/07/24/Java-IO-%E6%B5%81%E7%AE%80%E4%BB%8B/
