# Reverse Words in a String

* [Leetcode problem 151](https://leetcode.com/problems/reverse-words-in-a-string/description/?envType=study-plan-v2&envId=leetcode-75)

## Problem Statement

Given an input string `s` , reverse the order of the words.

A word is defined as a sequence of `non-space` characters. The words in s will be separated by at least one space.

Return a string of the words in reverse order concatenated by a `single space` .

Note that s may contain leading or trailing spaces or multiple spaces between two words. The returned string should only have a single space separating the words. Do not include any extra spaces.

#### Example

* Example 1:

```js
Input: s = "the sky is blue"
Output: "blue is sky the"
```

* Example 2:

```js
Input: s = "  hello world  "
Output: "world hello"
// Explanation: Your reversed string should not contain leading or trailing spaces.
```

* Example 3:

```js
Input: s = "a good   example"
Output: "example good a"
// Explanation: You need to reduce multiple spaces between two words to a single space in the reversed string.
```

Constraints:

1 <= s.length <= 104
s contains English letters (upper-case and lower-case), digits, and spaces ' '.
There is at least one word in s.

## Solution

```js
function reverseString(s) {
    s = s.trim();
    const arr = s.split(/\s+/);
    let left = 0;
    let right = arr.length - 1;

    while (left < right) {
        [arr[left], arr[right]] = [arr[right], arr[left]];
        left++;
        right--;
    }
    return arr.join(" ");
}
```
