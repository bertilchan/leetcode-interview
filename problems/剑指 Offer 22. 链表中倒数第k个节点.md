### 题目链接

「[剑指 Offer 22. 链表中倒数第k个节点](https://leetcode-cn.com/problems/lian-biao-zhong-dao-shu-di-kge-jie-dian-lcof/)」

### 解题思路

1.首先计算机链表的长度size

2.由于倒数第k个节点相当于正数第(size-k+1)个，因此让head指针左移(size-k)次即可

### 代码

```javascript
/**
 * @param {ListNode} head
 * @param {number} k
 * @return {ListNode}
 */
var getKthFromEnd = function(head, k) {
    let size = 0, curr = head;
    while(curr){
        curr = curr.next;
        size ++;
    }
    while(size - k > 0){
        head = head.next;
        size--;
    }
    return head;
};
```

