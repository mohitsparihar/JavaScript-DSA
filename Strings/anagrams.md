## Problem statement

Given two strings, write a function to determine if the second string is an anagram of the first. Anagram is a word, phrase, or name formed by rearranging the letters of another, such as cinema, formed iceman.

#### Example

```js
validAnagram("", "") // true
validAnagram("aaz", "zza") // false
validAnagram("anagram", "nagaram") // true
validAnagram("rat", "car") // false
validAnagram("awesome", "awesom") // false
validAnagram("qwerty", "qeywrt") // true
validAnagram("texttwisttime", "timetwisttext") // true
```

## Solution

```js
function validAnagram(first, second) {
    if (first.length !== second.length) {
        return false;
    }

    const lookup = {};

    for (let i = 0; i < first.length; i++) {
        let letter = first[i];
        // if letter exists, increment, otherwise set to 1
        lookup[letter] ? lookup[letter] += 1 : lookup[letter] = 1;
    }

    for (let i = 0; i < second.length; i++) {
        let letter = second[i];
        // can't find letter or letter is zero then it's not an anagram
        if (!lookup[letter]) {
            return false;
        } else {
            lookup[letter] -= 1;
        }
    }

    return true;
}
```
