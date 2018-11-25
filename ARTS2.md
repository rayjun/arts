### ARTS分享第2周：

平时知乎用的少，一上来看到回答被耗子叔赞了，觉得更有动力写下去了，哈哈~~

#### Algorithm：

Leetcode922，这道题是 Leetcode905 的升级版，在这道题当中，奇偶数不再要求分开在两边， 二是每个值都必须要与下标的奇偶性相同，这个数组是偶数，而且奇数和偶数的个数是相同的。 这道题通过加上一个数组的额外空间可以很快的解出来，我的思路是不使用多余的数组，在一个数组中进行运算。思路如下： 

- 使用两个值 even 和 odd，一个指向偶数的下标，一个指向奇数的下标，初始 even=0, odd = 1 
- 然后定义 index = 0，开始遍历数组如果值为偶数，则插入到偶数下标下，然后 even+=2，index = even，奇数同理 
- 当 even 和 odd 同时大于数组的长度时停止，此时数组已经排列好。 

这道题的结题思路与 Leetcode905 的思路是一样的。通过多定义两个下标来完成在一个组数内进行操作。 

代码如下: 

```
 public int[] sortArrayByParityII(int[] A) {
              if(A.length <= 1) {
                    return A;
                }
                int even = 0;
                int odd =  1;
                int index = 0;
                int temp = 0;
                while(even < A.length && odd < A.length) {
                    if(A[index]%2 == 0) {
                        if(even != index) {
                            temp = A[even];
                            A[even] = A[index];
                            A[index] = temp;
                        }
                        even += 2;
                        index = even;
                    }else {
                        if(odd != index) {
                            temp = A[odd];
                            A[odd] = A[index];
                            A[index] = temp;
                        } 
                        odd += 2;
                        index = odd;
                    }
                }
               return A;
    }
```



#### Review:

https://hackernoon.com/ten-years-in-nobody-has-come-up-with-a-use-case-for-blockchain-ee98c180100hackernoon.com



区块链出生十年了，但是还是没有人想明白到底可以用区块链来做什么。这篇文章对目前区块链可能得应用场景出发，分别列举了目前的技术可以更加高效的取代区块链。 比如在支付方面：现有的技术更加高效安全。 比如智能合约： 不安全，而且更不友好。 比如在存储方面：dropbox 可能更好。 

但是我觉得这篇文件讲的部分都是太过于片面，都是从单一角度去理解区块链，区块链很多有价值的方面其实都没有被提及，比如信任机制，区块链的生成机制等方面。 

#### TIP:

Java、javascript等语言经常开会讨论怎样的代码才是最佳实践，并且花费了大量的时间和精力讨论标准。而 Go 语言从不开这个会，其他的语言就很奇怪，Go 语言慢条斯理的说，因为我有 gofmt。 

gofmt 是一个 go 语言官方推出的统一代码风格的工具。gofmt 是一个 命令行工具，如果传入的是一个目录， gofmt 会格式化目录中所有的 go 文件，包括嵌套目录的，如果传入的是一个具体的文件，那么就只会格式化一个具体的文件。 

而且在编辑器和 IDE 工具中，可以设置为在保存文件的时候自动执行 gofmt 工具。这样就快速保存代码，而不用手动执行 gofmt 工具。 

#### Share:

这周写了一篇文章，从技术的角度去如何去理解区块链：

[从技术的角度上来看，什么是区块链](http://www.rayjun.cn/2018/11/18/%E4%BB%8E%E6%8A%80%E6%9C%AF%E7%9A%84%E8%A7%92%E5%BA%A6%E4%B8%8A%E6%9D%A5%E7%9C%8B%EF%BC%8C%E4%BB%80%E4%B9%88%E6%98%AF%E5%8C%BA%E5%9D%97%E9%93%BE/)