## Problem statement

For two strings `s` and `t`, we say `t divides s` if and only if `s = t + ... + t` (i.e., `t` is concatenated with itself one or more times).

Given two strings `str1` and `str2`, return the largest string `x` such that `x` divides both `str1` and `str2`.

- Leetcode problem [1071](https://leetcode.com/problems/greatest-common-divisor-of-strings/?envType=study-plan-v2&envId=leetcode-75)

#### Constraints

- `1 <= str1.length, str2.length <= 1000`
- `str1` and `str2` consist of English uppercase letters.

#### Example

```js
gcdOfStrings("ABCABC", "ABC") // "ABC"
gcdOfStrings("ABABAB", "AB") // "AB"
gcdOfStrings("LEET", "CODE") // ""
```

## Solution

```js
let gcdOfStrings = function(str1, str2) {
      if (str1 + str2 !== str2 + str1) {
        return "";
    }
    const gcd = (a, b) => (b === 0 ? a : gcd(b, a % b));
    const length = gcd(str1.length, str2.length);
    return str1.slice(0, length);
};
```
