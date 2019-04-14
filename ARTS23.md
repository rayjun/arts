#### Algorithm

Leetcode128，判断一个字符串是否是回文字符串，字符串只需要比较字母和数字，其他的字符都不需判断。我的解法是用了两个栈，这样的做法是代码可读性高。
**时间复杂度: O(N)**
**空间复杂度: O(N)**

```java
 public boolean isPalindrome(String s) {
       LinkedList<Character> stack1 = new LinkedList<Character>();
		LinkedList<Character> stack2 = new LinkedList<Character>();
		
		char[] chars = s.toCharArray();
		
		for (int i = 0; i < chars.length; i++) {
			if (isAlph(chars[i]) || isNum(chars[i])) {
				stack1.push(chars[i]);
			}
		}
		
		for (int i = chars.length - 1; i >= 0; i--) {
			if (isAlph(chars[i]) || isNum(chars[i])) {
				stack2.push(chars[i]);
			}
		}
		
		while (!stack1.isEmpty() && !stack2.isEmpty()) {
			char c1 = stack1.pop();
			char c2 = stack2.pop();
			
			if (c1 != c2 ) {
				if (isAlph(c1) && isAlph(c2)) {
					if (Math.abs(c1 - c2) != 32) {
						return false;
					}
				} else {					
					return false;
				}
			}
		}
		
		return true;
    }
    
    private boolean isAlph(char c) {
		if ((c >= 65 && c <= 90) || (c >= 97 && c <= 122)) {
			return true;
		}
		return false;
	}
	
	private boolean isNum(char c) {
		if (c >= 48 && c <= 57) {
			return true;
		}
		return false;
	}
```

### Review

https://hacker-tools.github.io/security/

在如今的网络环境中，个人隐私很容易就会被泄露，然后被黑客所利用。当然了，只要你面对的不是 NSA 和 Mossd，你就都会有办法保护好你的隐私的。

有很多的办法可以让你保护好自己的隐私。在[这里](https://techsolidarity.org/resources/basic_security.htm)有很多的安全建议可以帮助你做好基本的安全措施。

然后在保护密码上我们可以使用 [1password](https://1password.com/)，在聊天工具上，我们可以选择点对点的聊天工具，比如 Whatsapp。E-mail 其实不是一个很好的选择。

对于文件，很多情况下是有必要进行加密的，比如利用 PGP 进行加密，还有在使用网络时，我们也需要注意安全，比如不要去连接开放的 wifi 密码，和不信任的 VPN 等。在发布 WEB 服务时，最好是要使用 HTTPS。


### Share

这周把 SQL 的基础总结了一下:

[SQL 简明教程](http://www.rayjun.cn/2019/04/14/SQL-%E7%AE%80%E6%98%8E%E6%95%99%E7%A8%8B/)