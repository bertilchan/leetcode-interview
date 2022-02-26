### 题目链接

「[剑指 Offer 50. 第一个只出现一次的字符](https://leetcode-cn.com/problems/di-yi-ge-zhi-chu-xian-yi-ci-de-zi-fu-lcof/)」

### 解题思路

1.遍历字符串，用a代表第一次出现的字符索引，然后来判断该字符是否会出现第二次

2.如果b为-1，则返回该字符；否则返回空字符串

### 代码

```javascript
/**
 * @param {string} s
 * @return {character}
 */
var firstUniqChar = function(s) {
    for(let i = 0; i < s.length; i++) {
        a = s.indexOf(s[i])
        b = s.indexOf(s[i], a + 1)
        if(b === -1) {
            return s[i]
        }
    }
    return " "
};
```

