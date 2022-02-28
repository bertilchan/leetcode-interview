### 题目链接

「[剑指 Offer 10- I. 斐波那契数列](https://leetcode-cn.com/problems/fei-bo-na-qi-shu-lie-lcof/)」

### 解题思路

1.斐波那契数的边界条件是 F(0)=0 和 F(1)=1。当 n>1 时，每一项的和都等于前两项的和，因此有如下递推关系：

F(n)=F(n-1)+F(n-2)

2.由于斐波那契数存在递推关系，因此可以使用动态规划求解。

3.需要注意此题答案需要取模

### 代码

```javascript
/**
 * @param {number} n
 * @return {number}
 */
var fib = function(n) {
    const MOD = 1000000007;
    if (n < 2) {
        return n;
    }
    let p = 0, q = 0, r = 1;
    for (let i = 2; i <= n; i++) {
        p = q; 
        q = r; 
        r = (p + q) % MOD;
    }
    return r;
};
```

