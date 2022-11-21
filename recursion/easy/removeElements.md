 Intuition
We need to update the link from the previous element to the next one.
So better to go to the end of the list and then on the "way back" check if element should be deleted. If it should be deleted then return link to the next element.
<!-- Describe your first thoughts on how to solve this problem. -->

# Approach
- Define boundary condition
- Recursion function call
- Check node value
- Return next or current node
<!-- Describe your approach to solving the problem. -->

# Complexity
- Time complexity:
$$O(n)$$
<!-- Add your time complexity here, e.g. $$O(n)$$ -->
- Space complexity:
$$O(n)$$
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code
```
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @param {number} val
 * @return {ListNode}
 */
var removeElements = function(head, val) {
    if(!head){
        return null;
    }
    
    head.next = removeElements(head.next, val);
    if(head.val === val){
        return head.next;
    }
    return head;
};
```