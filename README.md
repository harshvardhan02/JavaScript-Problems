
## JavaScript Problems


![Logo](https://cdn.worldvectorlogo.com/logos/logo-javascript.svg)


## Authors

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

## 11.

```javascript

```

## 12.

```javascript

```

## 13.

```javascript

```

## 14.

```javascript

```

## 15.

```javascript

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

