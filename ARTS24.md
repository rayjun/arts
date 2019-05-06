#### Algorithm
LeetCode189。

将一个数组移位。题目很简单，但是需要注意有一个坑就是整个数组是需要从前往后移的。

**时间复杂度: O(K\*N)**
**空间复杂度: O(1)**

```java
public void rotate(int[] nums, int k) {
        for (int i = k; i > 0; i--) {
			int tmp = nums[nums.length - 1];
			int j = nums.length - 2;
			for (; j >= 0; j--) {
				nums[j + 1] = nums[j];
			}
			nums[j+1] = tmp;
		}
    }
```

### Review

https://insights.stackoverflow.com/survey/2019/

StackOverFlow 2019 报告：

今年有超过 90000 万个开发者参与了调查。参与调查的开发者主要来自于**欧洲**、**北美**、**亚洲**。在调查中，关于工作和文化之类的数据在不同的地域之间有很大的差别，所以我觉得这部分数据并没有什么意思。让我觉得有意思的数据是下面这些:

- 超过 50% 的人在 16 岁就开始写代码，编程已经逐渐变成了一项基础的技能，像英语一样
- 超过 50% 访问 stackoverflow 的职业不是程序员，常见的编程问题在 stackoverflow 上都能找到答案，平均为每个开发者每周节省了 30-90分钟，编程的门槛正在降低，大量没有接受过专业训练的人也在开始学习编程
- 超过 70% 的开发者有本科以上的文凭，虽然编程的门槛低，但是编程对于知识的储备要求还是比较高
- 超过 50% 的开发者会做全栈开发。因为云基础设施的完善，开发一个应用的门槛和所需要的人正在减少。
- Laravel 是一个 PHP 的框架，超过 60% 的开发者喜欢使用 Laravel 开发 Web 应用，Laravel 是一个全栈的框架，这是为什么 Laravel 受欢迎的重要因素

### Share

总结了一下数据结构:
[数据结构简明教程](http://www.rayjun.cn/2019/04/28/%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E7%AE%80%E6%98%8E%E6%95%99%E7%A8%8B/)