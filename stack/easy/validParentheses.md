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
 * @param {string} s
 * @return {boolean}
 */
var isValid = function(s) {
    var stack = [];

    for(var ch of s){
        switch(ch) { 
            case '(':
            case '{':
            case '[':
                stack.push(ch);
                break;
            case ')':
                if(stack.length === 0) return false;
                if(stack.pop() !== '(') return false;
                break;
            case '}':
                if(stack.length === 0) return false;
                if(stack.pop() !== '{') return false;
                break;
            case ']':
                if(stack.length === 0) return false;
                if(stack.pop() !== '[') return false;
                break;
        }
    }
    return stack.length === 0;

};
```