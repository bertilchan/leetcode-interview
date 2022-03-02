### 题目链接

「[剑指 Offer 09. 用两个栈实现队列](https://leetcode-cn.com/problems/yong-liang-ge-zhan-shi-xian-dui-lie-lcof/)」

### 解题思路

1.定义两个栈A和B，分别为入队栈和出队栈（栈：先进后出；队列：先进先出）

2.appendTail操作即放到入队栈中

3.deleteHead则从出队栈中拿（前提是入队栈先全部清空，放到出队栈中），如果没有则返回-1

### 代码

```javascript
var CQueue = function() {
    this.stackA = []
    this.stackB = []
};

/** 
 * @param {number} value
 * @return {void}
 */
CQueue.prototype.appendTail = function(value) {
    this.stackA.push(value)
};

/**
 * @return {number}
 */
CQueue.prototype.deleteHead = function() {
    if(this.stackB.length) {
        return this.stackB.pop()
    }else {
        while(this.stackA.length) {
            this.stackB.push(this.stackA.pop())
        }
        if(!this.stackB.length) {
            return -1
        }else {
            return this.stackB.pop();
        }
    }
};

/**
 * Your CQueue object will be instantiated and called as such:
 * var obj = new CQueue()
 * obj.appendTail(value)
 * var param_2 = obj.deleteHead()
 */
```

