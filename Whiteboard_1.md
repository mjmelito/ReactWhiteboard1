Question #1: Turning Strings to URLs

URLs cannot have spaces. Instead, all spaces in a string are replaced with %20. Write an algorithm that replaces all spaces in a string with %20.

You may not use the replace() method or regular expressions to solve this problem. Solve the problem with and without recursion.

Example
string: "Jasmine Ann Jones"

Output: "Jasmine%20Ann%20Jones"

Without Recursion:

        function replaceSpaces(string) {
            let urlString = " ";
            for (let i = 0; i < string.length; i++) {
                if (string.charAt(i) === " ") {
                    urlString.concat(String("%20"));
                } else {
                    urlString.concat(string.charAt(i));
                }
            }
            return urlString;
        };


With Recursion:

        function replaceSpacesRecursive(string) {
            if (string.length === 0) {
                return " ";
            }

            if (string.charAt(0) === " ") {
                return "%20" + replaceSpacesRecursive(string.slice(1));
            } else {
                return string.charAt(0) + replaceSpacesRecursive(string.slice(1));
            }
        };