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
 * @return {number}
 */
var toInt = function(ch){
    switch(ch){
        case 'I': return 1;
        case 'V': return 5;
        case 'X': return 10;
        case 'L': return 50;
        case 'C': return 100;
        case 'D': return 500;
        case 'M': return 1000;
    }
}
var romanToInt = function(s) {
    var i = s.length - 1;
    var sum = 0;
    while(i>=0){
        var second = s[i];
        var first = null;
        if(i-1>=0){
            first = s[i-1];
        }
        if(first === null){
            sum+=toInt(second);
            return sum;
        }
        if((first === 'I' && (second === 'V' || second === 'X'))
           || (first === 'X' && (second === 'L' || second === 'C'))
           || (first === 'C' && (second === 'M' || second === 'D'))){
               sum+=toInt(second) - toInt(first);
               i=i-2;
        }
        else {
            sum+=toInt(second);
            i=i-1;
        }
    }
    return sum;
};
```