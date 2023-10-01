## Problem statement

You are given a longer text and a shorter pattern. Your task is to implement an efficient algorithm to find all occurrences of the pattern within the text. Return the starting positions (indices) in the text where the pattern is found.

#### Input:

text (string): The longer text in which you need to search for occurrences of the pattern. (1 <= text.length <= 10^5)
pattern (string): The substring pattern you want to find in the text. (1 <= pattern.length <= 10^5)

#### Output:

An array of integers representing the starting positions (0-based indices) in the text where the pattern is found. If the pattern is not found in the text, return an empty array.

#### Example

```js
const text = "ABABABABAB";
const pattern = "ABA";

const result = efficientStringSearch(text, pattern);
console.log(result); // Output should be [0, 2, 4, 6]
```


