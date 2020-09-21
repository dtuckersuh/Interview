# Array Notes
- Is array sorted or partially sorted? If it is, some form of binary search should be possible
    - Interviewer usually is looking for solution faster than O(n)
- Can you sort array? Sorting first may significantly simplify the problem
    - Make sure order of elements does not need to be preserved before attempting sort
- For questions regarding summation or multiplication of subarrays, pre-computation using hasing or prefix/suffix sum/product might be useful
- If given sequence and interviewer asks for O(1) space, it might be possible to use array itself as a hash table
    - For example, if array only has values 1 to N, where N is length of array, negate that value at that index (minus 1) to indicate presence of that number

## Arrays are sequences
- Duplicate values could affect answer
- Watch for out of bounds errors
- Slicing and concatenating arrays require O(n) time
    - Use start and end indices to demarcate a subarray/range where possible
- Sometimes you can traverse array from right rather than left

# Sliding Window
- The sliding window pattern is used to perform a required operation on a specific window size of a given array or linked list, such as finding the longest subarray containing all 1s.

![Sliding Window](https://hackernoon.com/images/G9YRlqC9joZNTWsi1ul7tRkO6tv1-8i6d3wi0.jpg)

- Some identifiers of sliding window problems
    - Problem input is linear data structure such as linked list, array or string
    - You are asked to find longest/shorted substring, subarray, or desired value
- Common problems
    - Maximum sum subarray of size 'K' (easy)
    - Longest substring with 'K' distinct characters (medium)
    - String anagrams (hard)
