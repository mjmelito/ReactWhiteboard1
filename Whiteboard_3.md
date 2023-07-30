Question #3: Compressing Strings

Write an algorithm that takes a string with repeated characters and compresses them, using a number to show how many times the repeated character has been compressed. For instance, aaa would be written as 3a. Solve the problem with and without recursion.

Example
Input: "aaabccdddda"

Output: "3ab2c4da"

Without Recursion:


    function compressString(inputString) {
        if (inputString.length === 0) {
            return inputString;
        }

        let compressedString = '';
        let count = 1;

        for (let i = 0; i < inputString.length; i++) {
            if (inputString[i] === inputString[i + 1]) {
                count++;
            } else {
                compressedString += count > 1 ? count + inputString[i] : inputString[i];
                count = 1;
            }
        }

        return compressedString;
    }



With Recursion:

    function compressStringRecursively(inputString) {
        if (!inputString || inputString.length <= 1) {
            return inputString;
        }
        let count = 1;
        if (inputString[0] === inputString[1]) {
            count++;
            return compressStringRecursively(inputString.substring(1));
        } else {
            let compressedPart = count > 1 ? count + inputString[0] : inputString[0];
            return compressedPart + compressStringRecursively(inputString.substring(1));
        }
    }