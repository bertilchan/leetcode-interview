### 题目链接

「[剑指 Offer 38. 字符串的排列](https://leetcode.cn/problems/zi-fu-chuan-de-pai-lie-lcof/)」

### 解题思路

1.使用递归：依次去掉字符串一个字符，得到剩余字符串的全排列，将去掉的字符与剩余字符串的全排列拼接，最后将拼接完的所有字符串放入数组，并去重，返回这个数组给上一级

2.递归结束条件：当前字符串长度小于等于1

### 代码

```javascript
/**
 * @param {string} s
 * @return {string[]}
 */
var permutation = function(s) {
    if (s.length === 0) return [''];
    if (s.length === 1) return [s];
    const res = [];
    const len = s.length;
    for (let i = 0; i < len; i++) {
        const char = s[i];
        // newStr = 去掉char后剩下的字符
        let newStr = s.slice(0, i) + s.slice(i + 1);
        // 递归产生newStr的全排列
        const next = permutation(newStr);
        // 将char与newStr的全排列拼接，放入res
        next.forEach(item => {
            res.push(char + item);
        });
    }
    // 去重
    return [...new Set(res)];
};
```

