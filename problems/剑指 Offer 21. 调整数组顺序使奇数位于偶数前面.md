### 题目链接

「[剑指 Offer 21. 调整数组顺序使奇数位于偶数前面](https://leetcode-cn.com/problems/diao-zheng-shu-zu-shun-xu-shi-qi-shu-wei-yu-ou-shu-qian-mian-lcof/)」

### 解题思路

1.首先新建一个结果集数组，然后遍历数组

2.若为偶数则添加到结果集数组的末尾；若为奇数则添加到结果集数组的开头

### 代码

```javascript
/**
 * @param {number[]} nums
 * @return {number[]}
 */
var exchange = function(nums) {
    const res = []
    for(const num of nums) {
        if(num % 2 === 0) {
        res.push(num)
        } else {
        res.unshift(num)
        }
    }
    return res
};
```

