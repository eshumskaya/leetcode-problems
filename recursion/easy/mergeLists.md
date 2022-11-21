# Intuition
Try to solve for the basic cases, when there is one element in each list or there is one element in one list and another list is empty.

# Approach
- Add boundary restrictions (when one of the lists is empty)
- Compare two values
- Go to the next element of the list that has current smaller value

# Complexity
- Time complexity:
$$O(n+m)$$

- Space complexity:
$$O(n+m)$$

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
 * @param {ListNode} list1
 * @param {ListNode} list2
 * @return {ListNode}
 */
var mergeTwoLists = function(list1, list2) {
    if(!list1){
        return list2;
    }
    if(!list2){
        return list1;
    }
    if(list1.val < list2.val) {
        list1.next = mergeTwoLists(list1.next, list2);
        return list1;
    }
    else {
        list2.next = mergeTwoLists(list1, list2.next);
        return list2;
    }
};
```