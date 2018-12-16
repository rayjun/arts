#### Algorithm

Leetcode242 这道题需要解决的是判断两个字符串中包含的字符是否相同。这里我的做法是使用一个HashMap，遍历一个字符串，把每个字符当作 map 的key，数量记作 value。

然后遍历另一个字符串，如果字符在 map 中不存在，直接返回 false， 如果存在而且 value 为1 ，则直接从 map 中删除这一项，如果 value 不为1，则value减1，遍历结束后判断 map 是否为空，为空则返回 true， 否则返回 false，代码如下：


```java
 public boolean isAnagram(String s, String t) {

        if (s.length() != t.length()) {
            return false;
        }

        Map<Character, Integer> charactersMap = new HashMap<Character, Integer>(); 
        
        for (int i = 0; i < s.length(); i++) {
            if(!charactersMap.containsKey(s.charAt(i))) {
                charactersMap.put(s.charAt(i), 1);
            } else {
                charactersMap.put(s.charAt(i), charactersMap.get(s.charAt(i)) + 1);
            }
        }

        for (int i = 0; i < t.length(); i++) {
            if (!charactersMap.containsKey(t.charAt(i))) {
                return false;
            } else if(charactersMap.get(t.charAt(i)) == 1) {
                charactersMap.remove(t.charAt(i));
            } else {
                charactersMap.put(t.charAt(i), charactersMap.get(t.charAt(i))- 1);
            }
        }

        if(charactersMap.size() == 0) {
            return true;
        } else {
            return false;
        }
    }
```


#### Review

https://link.zhihu.com/?target=https%3A//medium.com/netflix-techblog/https-medium-com-netflixtechblog-engineering-to-improve-marketing-effectiveness-part-2-7dd933974f5e

这篇文章是上周那篇文章的续集，在这篇文章里面，作者详细分析了网飞的广告平台中技术团队与广告团队的协作方式细致的合作方式，其中提到的最重要，也是最多的就是自动化，技术团队会帮助时长团队把所有的任务都尽量的自动化，把一些固定的任务做成流程化的过程，比如广告的组装，只要市场团队制定好创意，自动化的工具就可以很方便的把创意变成实际的宣传内容。


#### Tip

这周新学习了 Vim 的块操作，通过块操作，可以非常方便的操作多行操作。

#### Share

这周详细研究了一下 CAS 系统的认证过程

[Cas 认证过程深入研究](https://link.zhihu.com/?target=http%3A//www.rayjun.cn/2018/12/16/Cas-%25E8%25AE%25A4%25E8%25AF%2581%25E8%25BF%2587%25E7%25A8%258B%25E7%25A0%2594%25E7%25A9%25B6/)