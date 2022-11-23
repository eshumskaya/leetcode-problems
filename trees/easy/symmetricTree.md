# Intuition
<!-- Describe your first thoughts on how to solve this problem. -->

# Approach
<!-- Describe your approach to solving the problem. -->

# Complexity
- Time complexity:
<!-- Add your time complexity here, e.g. $$O(n)$$ -->
s
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
var preOrderTraversal = function(rightTree, leftTree){
    if(!rightTree){
        if(leftTree){
            return false;
        }
        else{
            return true;
        }
    }
    if(!leftTree){
        if(rightTree){
            return false;
        }
        else{
            return true;
        }
    }
    if(rightTree.val !== leftTree.val){
        return false;
    }

    return preOrderTraversal(rightTree.left, leftTree.right) && preOrderTraversal(rightTree.right, leftTree.left);
}
var isSymmetric = function(root) {
    return preOrderTraversal(root.right, root.left);
};
```