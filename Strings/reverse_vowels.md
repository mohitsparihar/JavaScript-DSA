# Reverse Vowels of a String

* [Leetcode problem 345](https://leetcode.com/problems/reverse-vowels-of-a-string/description/?envType=study-plan-v2&envId=leetcode-75)

## Problem Statement

Given a string `s`, reverse only all the vowels in the string and return it.

The vowels are 'a', 'e', 'i', 'o', and 'u', and they can appear in both lower and upper cases, more than once.

#### Example

* Example 1:
```js
Input: s = "hello"
Output: "holle"
```

* Example 2:
```js
Input: s = "leetcode"
Output: "leotcede"
```

#### Constraints:
* `1 <= s.length <= 3 * 105`
* `s` consist of printable ASCII characters.

## Solution

```js
var reverseVowels = function (s) {
    const arr = s.split('');
    const vowels = new Set(['a', 'e', 'i', 'o', 'u']);
    let left = 0;
    let right = s.length - 1;

    while (left < right) {
        if (vowels.has(arr[left].toLowerCase()) && vowels.has(arr[right].toLowerCase())) {
            [arr[left], arr[right]] = [arr[right], arr[left]];
            left++;
            right--;
        }
        if (!vowels.has(arr[left].toLowerCase())) {
            left++;
        }
        if (!vowels.has(arr[right].toLowerCase())) {
            right--;
        }
    }
    return arr.join('')
}
```