Question #5: Array Sorting

Write an algorithm that sorts an array without using the sort() method. There are many different sorting algorithms — take the time to read about the following:

Quick sort
Merge sort
Heap sort
Insertion sort
Bubble sort
Selection sort

You may implement any of the above algorithms (or your own) to solve the problem — as long as it doesn't use sort().

Example
Input: [9, 2, 7, 12]

Output: [2, 7, 9, 12]

Merge Sort:

    function mergeSort(arr) {
        if (arr.length <= 1) {
            return arr; 
        }

        const mid = Math.floor(arr.length / 2);
        const leftHalf = arr.slice(0, mid);
        const rightHalf = arr.slice(mid);

        const sortedLeft = mergeSort(leftHalf);
        const sortedRight = mergeSort(rightHalf);

        return merge(sortedLeft, sortedRight);
    }

    function merge(left, right) {
        let result = [];
        let leftIndex = 0;
        let rightIndex = 0;

        // Compare elements from both arrays and merge them in sorted order
        while (leftIndex < left.length && rightIndex < right.length) {
            if (left[leftIndex] < right[rightIndex]) {
                result.push(left[leftIndex]);
                leftIndex++;
            } else {
                result.push(right[rightIndex]);
                rightIndex++;
            }
        }   

        result = result.concat(left.slice(leftIndex)).concat(right.slice(rightIndex));

        return result;
    }