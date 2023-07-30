Question #2: Array Deduping

Write an algorithm that removes duplicates from an array. Do not use a function like filter() to solve this. Once you have solved the problem, demonstrate how it can be solved with filter(). Solve the problem with and without recursion.

Example
Input: [7, 9, "hi", 12, "hi", 7, 53]

Output: [7, 9, "hi", 12, 53]

Without Recursion:
 
        function removeDuplicate(array) {
            if (array.length == 0 || array.length == 1) {
                return array;
            }
            let uniqueArr = [];
            for (let i = 0, i < array.length, i++)
                if (!uniqueArr.includes(i)) {
                    uniqueArr.push(i);
                }
            return uniqueArr;
        }

With Recursion:

        function removeDuplicatesRecursively(array) {

            if (array.length <= 1) {
                return array;
            }

            const head = array[0];
            const tail = removeDuplicatesRecursively(array.slice(1));

            if (tail.indexOf(head) !== -1) {
                return tail;
            } else {
                return [head].concat(tail);
            }
        };
        
With filter():

        let arr = ["apple", "mango", "apple",
                "orange", "mango", "mango"];
        
        function removeDuplicates(arr) {
            return arr.filter((item,
                index) => arr.indexOf(item) === index);
        }
        console.log(removeDuplicates(arr));


