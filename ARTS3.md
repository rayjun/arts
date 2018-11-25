### ARTS分享第3周：

#### Algorithm：

Leetcode41，这道题要求的是一个乱序的数组中，缺失的最小的正整数。 

这道题也有好几种解法，首先可以对数组进行排序，然后遍历一下数组，找出最小缺失的那个数，但是这样的时间复杂度容易通不过。一个比较好的解法如下: 

- 遍历一下数组，将数组中的元素放到 nums[i] == i +1 位置上 

- 再遍历一次，找出那个 nums[i] != i+1那个位置，i+1就是我们要求的值。 

代码如下: 

```java
public static int firstMissingPositive(int[] nums) {
    int result = 0;
    int i = 0;
    while(i < nums.length){
        if(nums[i] == i+1 || nums[i] <= 0 || nums[i] > nums.length || nums[nums[i] - 1] == nums[i])
        {
          i++;
        }
        else {
            int k1 = i;
            int k2 = nums[i] - 1;
            int temp = nums[k1];
            nums[k1] = nums[k2];
            nums[k2] = temp;
        }
    }
    i = 0;
    while(i < nums.length && nums[i] == i +1) {
      i++;
    }
    result = i + 1;
    return result;
}
```



#### Review

这周又将比特币的白皮书看了几遍。反复的复习这些资料，总能从中学到新的东西。 

比特币的初衷是为了构建一个没有第三方机构的电子支付系统（虽然现在离初衷有点远）。在传统的金融机构中，需要一个被信任的第三方来防止双重支出，比特币的目标就是来干掉这个第三方，然后完全依赖系统本身来保证交易的安全性。 

当然，导目前为止，比特币还没有达到它的目标，虽然比特币本身解决了双重支出的问题，但是但实际的使用过程中，还是有非常多的问题，比如交易的不可逆，比如密钥丢失就会导致所有的比特币都会丢失，虽然再系统内，交易是安全的，但是在实际的日常中，比特币是不安全的，丢失之后也没有追回财产的的途径。比特币要实现它的目标还有很长的路要走。 



#### Tip

go 语言不支持包管理一直广受诟病，在 go1.11 中，终于引入了 go modules。go modules 通过引入 go.mod 文件来解决之前的包管理缺失的情况，同时也弱化了 GOPATH 的作用，在后续 go 的版本中，GOAPTH 可能会被去掉。go modules 会完全的替代 GOPATH。 

虽然目前 go modules 的功能还不完善，但是在后续的版本中应该会被不断的完善。以下这些代码详细的展示了 go modules 的用法。 

[go modules示例](https://github.com/go-modules-by-example/index) 



#### Share

区块链这个词大家都很熟悉，但是对于区块链的结构，知道的人怕是不多，这周的这篇文章介绍了区块链的形成方式。

[区块链的形成方式](http://www.rayjun.cn/2018/11/25/%E5%8C%BA%E5%9D%97%E9%93%BE%E4%B8%AD%E7%9A%84%E9%93%BE%E5%88%B0%E5%BA%95%E6%80%8E%E4%B9%88%E5%BD%A2%E6%88%90%E7%9A%84/)