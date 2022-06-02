### 题目链接

「[剑指 Offer 03. 数组中重复的数字](https://leetcode.cn/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof/)」

### 解题思路

1.首先对数组进行排序，然后遍历数组，如果出现相邻元素相等，则返回即可

### 代码

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var findRepeatNumber = function(nums) {
    nums.sort()
    for(let i = 0; i < nums.length - 1; i++){
       if(nums[i] === nums[i + 1]) {
            return nums[i]
        }
    }
};
```

