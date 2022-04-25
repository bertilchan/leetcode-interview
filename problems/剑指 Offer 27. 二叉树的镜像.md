### 题目链接

「[剑指 Offer 27. 二叉树的镜像](https://leetcode-cn.com/problems/er-cha-shu-de-jing-xiang-lcof/)」

### 解题思路

1.首先递归左右子节点，然后不断进行左右子节点的位置交换即可

### 代码

```javascript
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @return {TreeNode}
 */
var mirrorTree = function(root) {
    if (!root) return null;
    
    const left = mirrorTree(root.left);
    const right = mirrorTree(root.right);
    root.left = right;
    root.right = left;
    return root;
};
```

