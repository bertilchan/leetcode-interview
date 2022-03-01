### 题目链接

「[剑指 Offer 10- II. 青蛙跳台阶问题](https://leetcode-cn.com/problems/qing-wa-tiao-tai-jie-wen-ti-lcof/)」

### 解题思路

1.如果只有0阶或者1阶，则直接返回1。(后面直接从2阶及以上开始，防止0/1阶导致数组出现空指针)

2.dp[i]：跳上n级台阶，有dp[i]种方法

3.从i=3开始遍历，因为必须要有前两个存在，且存在dp[n] = dp[n-1] + dp[n-2]的关系。需要注意结果要取模。

### 代码

```javascript
/**
 * @param {number} n
 * @return {number}
 */
var numWays = function(n) {
    if (n <= 1) return 1
    const dp = new Array(n)
    dp[1] = 1
    dp[2] = 2
    for (let i = 3; i <= n; i++) {
        dp[i] = (dp[i-1] + dp[i-2]) % 1000000007
    }
    return dp[n]
};
```

