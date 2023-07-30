Question #4: Checking for Uniqueness

Write an algorithm that determines whether all the elements in a string are unique. You may not convert the string into an array or use array methods to solve this problem. The algorithm should return a boolean.

Example
Input: "hello"

Output: false

Input: "copyright"

Output: true

Without Recursion:

    function areAllCharactersUnique(string) {
        let seenChars = new Set();

        for (const char of string) {
            if (seenChars.has(char)) {
                return false;
            }
            seenChars.add(char);
         }

        return true;
    }


With Recursion:

    function areAllCharactersUnique(string, index = 0, seenChars = new Set()) {
        if (index === string.length) {
            return true;
        }

        const char = string[index];

        if (seenChars.has(char)) {
            return false;
        }

        seenChars.add(char);

        return areAllCharactersUnique(string, index + 1, seenChars);
    }