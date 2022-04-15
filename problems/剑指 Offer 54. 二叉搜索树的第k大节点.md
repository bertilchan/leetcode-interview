### 题目链接

「[剑指 Offer 54. 二叉搜索树的第k大节点](https://leetcode-cn.com/problems/er-cha-sou-suo-shu-de-di-kda-jie-dian-lcof/)」

### 解题思路

1.二叉搜索树的特点：或者是一棵空树，或者是具有下列性质的二叉树： 若它的左子树不空，则左子树上所有结点的值均小于它的根结点的值； 若它的右子树不空，则右子树上所有结点的值均大于它的根结点的值； 它的左、右子树也分别为二叉排序树。

2.使用右根左的中序遍历，就能得到递减的序列，因此遍历了第k次的当前节点所求的第k大节点

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
 * @param {number} k
 * @return {number}
 */
var kthLargest = function(root, k) {
    let node;
    if (!root) return node;
    // 中序遍历：右根左
    const dfs = (root) => {
        if (!root) return null;
        dfs(root.right);
        k--;
        if (!k) return (node = root.val);
        dfs(root.left);
    };
    dfs(root);
    return node;
};
```

