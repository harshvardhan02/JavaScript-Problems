
## JavaScript Problems


![Logo](https://cdn.worldvectorlogo.com/logos/logo-javascript.svg)


## Authors

- [@harshvardhan](https://www.linkedin.com/in/harshvardhan-singh-baghel-691b67a1/)


## Reverse a String Without Using Built-in Functions

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

