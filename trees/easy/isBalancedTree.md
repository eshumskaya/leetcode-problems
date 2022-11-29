# Intuition
<!-- Describe your first thoughts on how to solve this problem. -->

# Approach
<!-- Describe your approach to solving the problem. -->

# Complexity
- Time complexity:
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity:
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code
```
/**
 * Definition for a binary tree node.
 * function TreeNode(val, left, right) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.left = (left===undefined ? null : left)
 *     this.right = (right===undefined ? null : right)
 * }
 */
/**
 * @param {TreeNode} root
 * @return {boolean}
 */
var height = function(root){
    if(!root){
        return 0;
    }
    
    var leftHeight = height(root.left);
    var rightHeight = height(root.right);
    if(leftHeight === -1 || rightHeight === -1){
        return -1;
    }
    if(Math.abs(leftHeight - rightHeight)>1){
        return -1;
    }
    return Math.max(leftHeight, rightHeight)+1;
}
var isBalanced = function(root) {
  return height(root)!==-1;

};
```