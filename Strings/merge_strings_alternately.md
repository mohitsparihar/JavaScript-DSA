## Problem statement

You are given two strings word1 and word2. Merge the strings by adding letters in alternating order, starting with word1. If a string is longer than the other, append the additional letters onto the end of the merged string.

Return the merged string.

#### Example

##### Example 1:

```
Input: word1 = "abc", word2 = "pqr"
Output: "apbqcr"
Explanation: The merged string will be merged as so:
word1:  a   b   c
word2:    p   q   r
merged: a p b q c r
```

##### Example 2:
```
Input: word1 = "ab", word2 = "pqrs"
Output: "apbqrs"
Explanation: Notice that as word2 is longer, "rs" is appended to the end.
word1:  a   b 
word2:    p   q   r   s
merged: a p b q   r   s
```

##### Example 3:
```
Input: word1 = "abcd", word2 = "pq"
Output: "apbqcd"
Explanation: Notice that as word1 is longer, "cd" is appended to the end.
word1:  a   b   c   d
word2:    p   q 
merged: a p b q c   d
```
## Solution

### Solution 1

```js
var mergeAlternately = function(word1, word2) {
    let mergedString = "";

    let maxLength = word2.length;
    if (word1.length > word2.length) {
        maxLength = word1.length;
    }

    for (let i = 0; i < maxLength; i++) {
        if (word1.length > i) {
        mergedString += word1[i];
        }
        if (word2.length > i) {
        mergedString += word2[i];
        }
    }

    return mergedString;
};
```

### Solution 2

```js
var mergeAlternately = function(word1, word2) {
    let result = "";
    let length = Math.max(word1.length, word2.length)
    for(let i = 0; i < length; i++) {
        result += (word1[i] || "") + (word2[i] || "");
    }
    return result;
};
```