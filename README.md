
## JavaScript Problems


![Logo](https://cdn-icons-png.flaticon.com/128/5968/5968292.png)

## Table of Contents

- [Reverse a String Without Using Built-in Functions](#1-reverse-a-string-without-using-built-in-functions)
- [Check if a String is a Palindrome, Ignoring Case](#2-check-if-a-string-is-a-palindrome-ignoring-case)

## Author

- [@harshvardhan](https://www.linkedin.com/in/harshvardhan-singh-baghel-691b67a1/)


## 1. Reverse a String Without Using Built-in Functions

```javascript
function reverseString(str) {
    // Create an empty string to store the reversed string
    let reversedStr = "";

    // Loop through the original string from the end to the beginning
    for (let i = str.length - 1; i >= 0; i--) {
        // Append each character to the reversed string
        reversedStr += str[i];
    }

    // Return the reversed string
    return reversedStr;
}

// Example usage:
const originalString = "Hello, World!";
const reversedString = reverseString(originalString);
console.log("Original String: ", originalString);
console.log("Reversed String: ", reversedString);
```


## 2. Check if a String is a Palindrome, Ignoring Case

```javascript
function isPalindrome(str) {
    // Convert the string to lowercase to ignore case
    str = str.toLowerCase();
    
    // Initialize pointers for the start and end of the string
    let start = 0;
    let end = str.length - 1;

    // Loop until the pointers meet in the middle
    while (start < end) {
        // If the characters at the start and end do not match, it's not a palindrome
        if (str[start] !== str[end]) {
            return false;
        }

        // Move the pointers towards the middle
        start++;
        end--;
    }

    // If all characters matched, it is a palindrome
    return true;
}

// Example usage:
const testString1 = "Racecar";
const testString2 = "Hello";
console.log(`Is "${testString1}" a palindrome?`, isPalindrome(testString1)); // true
console.log(`Is "${testString2}" a palindrome?`, isPalindrome(testString2)); // false
```


## 3. Count the Number of Vowels and Consonants in a String

```javascript
function countVowelsAndConsonants(str) {
    // Convert the string to lowercase to handle case insensitivity
    str = str.toLowerCase();

    // Initialize counters for vowels and consonants
    let vowelsCount = 0;
    let consonantsCount = 0;

    // Define a string of vowels for easy checking
    const vowels = "aeiou";

    // Loop through each character in the string
    for (let char of str) {
        // Check if the character is a letter
        if (char >= 'a' && char <= 'z') {
            // Check if the character is a vowel
            if (vowels.includes(char)) {
                vowelsCount++;
            } else {
                consonantsCount++;
            }
        }
    }

    // Return an object with the counts of vowels and consonants
    return {
        vowels: vowelsCount,
        consonants: consonantsCount
    };
}

// Example usage:
const testString = "Hello, World!";
const counts = countVowelsAndConsonants(testString);
console.log(`In the string "${testString}":`);
console.log("Number of vowels:", counts.vowels); // Output: 3
console.log("Number of consonants:", counts.consonants); // Output: 7
```


## 4. Find the Longest Substring Without Repeating Characters

```javascript
function longestSubstringWithoutRepeating(str) {
    // Initialize variables to keep track of the longest substring and current substring
    let longest = "";
    let current = "";

    // Create a set to store characters in the current substring
    let charSet = new Set();

    // Initialize pointers for the sliding window
    let start = 0;
    let end = 0;

    // Loop through the string with the end pointer
    while (end < str.length) {
        // If the character at the end pointer is not in the set, add it to the set and update current substring
        if (!charSet.has(str[end])) {
            charSet.add(str[end]);
            current += str[end];
            end++;
        } else {
            // If the character is in the set, remove the character at the start pointer from the set and update current substring
            charSet.delete(str[start]);
            current = current.slice(1);
            start++;
        }

        // Update the longest substring if the current substring is longer
        if (current.length > longest.length) {
            longest = current;
        }
    }

    // Return the longest substring
    return longest;
}

// Example usage:
const testString = "abcabcbb";
const longestSubstring = longestSubstringWithoutRepeating(testString);
console.log(`The longest substring without repeating characters in "${testString}" is "${longestSubstring}".`); // Output: "abc"
```

## 5. Check if a String Contains Only Digits

```javascript
function containsOnlyDigits(str) {
    // Check if the string is empty
    if (str.length === 0) {
        return false;
    }

    // Loop through each character in the string
    for (let char of str) {
        // Check if the character is not a digit
        if (char < '0' || char > '9') {
            return false;
        }
    }

    // If all characters are digits, return true
    return true;
}

// Example usage:
const testString1 = "123456";
const testString2 = "123a56";
console.log(`Does "${testString1}" contain only digits?`, containsOnlyDigits(testString1)); // Output: true
console.log(`Does "${testString2}" contain only digits?`, containsOnlyDigits(testString2)); // Output: false
```

## 6. Remove All Punctuation from a String

```javascript
function removePunctuation(str) {
    // Define a regular expression to match all punctuation characters
    const punctuationRegex = /[!"#$%&'()*+,\-./:;<=>?@[\\\]^_`{|}~]/g;

    // Use the regular expression to replace all punctuation characters with an empty string
    return str.replace(punctuationRegex, '');
}

// Example usage:
const testString = "Hello, World!";
const cleanedString = removePunctuation(testString);
console.log(`Original String: "${testString}"`); // Output: Hello, World!
console.log(`String without punctuation: "${cleanedString}"`); // Output: Hello World
```

## 7. Swap Case of Each Character in a String

```javascript
function swapCase(str) {
    // Initialize an empty string to store the result
    let swappedStr = "";

    // Loop through each character in the string
    for (let char of str) {
        // Check if the character is uppercase
        if (char >= 'A' && char <= 'Z') {
            // Convert to lowercase and add to the result string
            swappedStr += char.toLowerCase();
        } else if (char >= 'a' && char <= 'z') {
            // Convert to uppercase and add to the result string
            swappedStr += char.toUpperCase();
        } else {
            // If it's not a letter, add the character as is
            swappedStr += char;
        }
    }

    // Return the result string with swapped case
    return swappedStr;
}

// Example usage:
const testString = "Hello, World!";
const swappedString = swapCase(testString);
console.log(`Original String: "${testString}"`); // Output: Hello, World!
console.log(`Swapped Case String: "${swappedString}"`); // Output: hELLO, wORLD!
```

## 8. Find the First Non-Repeating Character in a String

```javascript
function firstNonRepeatingCharacter(str) {
    // Create a map to store character counts
    const charCountMap = new Map();

    // Loop through each character in the string to count occurrences
    for (let char of str) {
        if (charCountMap.has(char)) {
            charCountMap.set(char, charCountMap.get(char) + 1);
        } else {
            charCountMap.set(char, 1);
        }
    }

    // Loop through the string again to find the first non-repeating character
    for (let char of str) {
        if (charCountMap.get(char) === 1) {
            return char;
        }
    }

    // If no non-repeating character is found, return null
    return null;
}

// Example usage:
const testString1 = "swiss";
const testString2 = "teeter";
console.log(`First non-repeating character in "${testString1}":`, firstNonRepeatingCharacter(testString1)); // Output: "w"
console.log(`First non-repeating character in "${testString2}":`, firstNonRepeatingCharacter(testString2)); // Output: "r"
```

## 9. Convert a String to a Character Array and Back

```javascript
// Function to convert a string to a character array
function stringToCharArray(str) {
    // Initialize an empty array to store characters
    let charArray = [];

    // Loop through each character in the string and push to the array
    for (let char of str) {
        charArray.push(char);
    }

    return charArray;
}

// Function to convert a character array back to a string
function charArrayToString(charArray) {
    // Initialize an empty string to store the result
    let str = "";

    // Loop through each character in the array and append to the string
    for (let char of charArray) {
        str += char;
    }

    return str;
}

// Example usage:
const originalString = "Hello, World!";
const charArray = stringToCharArray(originalString);
console.log("Character Array:", charArray); // Output: ["H", "e", "l", "l", "o", ",", " ", "W", "o", "r", "l", "d", "!"]

const convertedString = charArrayToString(charArray);
console.log("Converted String:", convertedString); // Output: "Hello, World!"
```

## 10. Count the Number of Words in a String Using Regex

```javascript
function countWords(str) {
    // Define a regular expression to match words
    const wordRegex = /\b\w+\b/g;

    // Use the regular expression to find all words in the string
    const words = str.match(wordRegex);

    // Return the number of words found
    return words ? words.length : 0;
}

// Example usage:
const testString1 = "Hello, World! This is a test.";
const testString2 = "  Another    example with   multiple spaces.  ";
console.log(`Number of words in "${testString1}":`, countWords(testString1)); // Output: 6
console.log(`Number of words in "${testString2}":`, countWords(testString2)); // Output: 6
```

## 11. Implement String Compression Using Counts of Repeated Characters

```javascript
function compressString(str) {
    // Initialize an empty string to store the compressed result
    let compressedStr = "";

    // Initialize a counter for the current character
    let count = 1;

    // Loop through the string
    for (let i = 0; i < str.length; i++) {
        // If the next character is the same as the current character, increment the count
        if (str[i] === str[i + 1]) {
            count++;
        } else {
            // Append the current character and count to the compressed string
            compressedStr += str[i] + count;
            // Reset the count to 1 for the next character
            count = 1;
        }
    }

    // Return the compressed string if it is shorter than the original string
    // Otherwise, return the original string
    return compressedStr.length < str.length ? compressedStr : str;
}

// Example usage:
const testString1 = "aabcccccaaa";
const compressedString1 = compressString(testString1);
console.log(`Original String: "${testString1}"`); // Output: aabcccccaaa
console.log(`Compressed String: "${compressedString1}"`); // Output: a2b1c5a3

const testString2 = "abcdef";
const compressedString2 = compressString(testString2);
console.log(`Original String: "${testString2}"`); // Output: abcdef
console.log(`Compressed String: "${compressedString2}"`); // Output: abcdef (since compressed string is not shorter)
```

## 12. Extract a Substring Between Two Characters

```javascript
function extractSubstring(str, startChar, endChar) {
    // Find the index of the start character
    const startIndex = str.indexOf(startChar);
    if (startIndex === -1) {
        return ""; // Start character not found
    }

    // Find the index of the end character
    const endIndex = str.indexOf(endChar, startIndex + 1);
    if (endIndex === -1) {
        return ""; // End character not found
    }

    // Extract the substring between the start and end characters
    return str.substring(startIndex + 1, endIndex);
}

// Example usage:
const testString1 = "Hello [World]!";
const substring1 = extractSubstring(testString1, '[', ']');
console.log(`Extracted Substring: "${substring1}"`); // Output: "World"

const testString2 = "This is an (example) string.";
const substring2 = extractSubstring(testString2, '(', ')');
console.log(`Extracted Substring: "${substring2}"`); // Output: "example"
```

## 13. Check if Two Strings are Rotations of Each Other

```javascript
function areRotations(str1, str2) {
    // Check if the lengths of the strings are equal
    if (str1.length !== str2.length) {
        return false;
    }

    // Concatenate the first string with itself
    const concatenated = str1 + str1;

    // Check if the second string is a substring of the concatenated string
    return concatenated.includes(str2);
}

// Example usage:
const string1 = "ABCD";
const string2 = "CDAB";
const string3 = "ACBD";

console.log(`Are "${string1}" and "${string2}" rotations of each other?`, areRotations(string1, string2)); // Output: true
console.log(`Are "${string1}" and "${string3}" rotations of each other?`, areRotations(string1, string3)); // Output: false
```

## 14. Find All Permutations of a Given String

```javascript
function findPermutations(str) {
    const results = [];

    // Base case: if the string length is 1, return the string as the only permutation
    if (str.length === 1) {
        results.push(str);
        return results;
    }

    // Recursive case: find all permutations of the string
    for (let i = 0; i < str.length; i++) {
        // Remove the character at index i and find permutations of the remaining string
        const remaining = str.slice(0, i) + str.slice(i + 1);
        const remainingPermutations = findPermutations(remaining);

        // Add the removed character to the front of each permutation of the remaining string
        for (let permutation of remainingPermutations) {
            results.push(str[i] + permutation);
        }
    }

    return results;
}

// Example usage:
const testString = "ABC";
const permutations = findPermutations(testString);
console.log(`Permutations of "${testString}":`, permutations);
// Output: ["ABC", "ACB", "BAC", "BCA", "CAB", "CBA"]
```

## 15. Find the Minimum Number of Steps to Convert One String to Another

```javascript
function editDistance(str1, str2) {
    const m = str1.length;
    const n = str2.length;

    // Create a 2D array to store the edit distances
    const dp = Array(m + 1).fill(null).map(() => Array(n + 1).fill(0));

    // Initialize the first row and column of the array
    for (let i = 0; i <= m; i++) {
        dp[i][0] = i;
    }
    for (let j = 0; j <= n; j++) {
        dp[0][j] = j;
    }

    // Fill in the rest of the array
    for (let i = 1; i <= m; i++) {
        for (let j = 1; j <= n; j++) {
            if (str1[i - 1] === str2[j - 1]) {
                dp[i][j] = dp[i - 1][j - 1];
            } else {
                dp[i][j] = 1 + Math.min(dp[i - 1][j], dp[i][j - 1], dp[i - 1][j - 1]);
            }
        }
    }

    // The edit distance is the value in the bottom-right corner of the array
    return dp[m][n];
}

// Example usage:
const string1 = "kitten";
const string2 = "sitting";
console.log(`Edit Distance between "${string1}" and "${string2}":`, editDistance(string1, string2));
// Output: 3
```

## 16.

```javascript

```

## 17.

```javascript

```

## 18.

```javascript

```

## 19.

```javascript

```

## 20.

```javascript

```

## 21.

```javascript

```

## 22.

```javascript

```

## 23.

```javascript

```

## 24.

```javascript

```

## 25.

```javascript

```

## 26.

```javascript

```

## 27.

```javascript

```

## 28.

```javascript

```

## 29.

```javascript

```

## 30.

```javascript

```

