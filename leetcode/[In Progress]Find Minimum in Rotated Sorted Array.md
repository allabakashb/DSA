# Find Minimum in Rotated Sorted Array
* [Examples](#example)
* [Brute Force Solution](#bruteforce)
* [Optimized Solution](#optimized)
* [Notes](#notes)

<a id="example"></a>
## Examples
```
Input: [3,4,5,6,7,1,2]
Output: 1
Input: [5,6,7,1,2,3,4]
Output: 1
Input: [6,7,1,2,3,4,5]
Output: 1
Input: [3,4,5,6,7,8,1,2]
Output: 1
Input: [5,6,7,8,1,2,3,4]
Output: 1
Input: [7,8,1,2,3,4,5,6]
Output: 1
```
<a id="bruteforce"></a>
## Brute Force Solution
Time Complexity :: O(N)
Space Complexity :: O(1)
### Java Solution
```java
class Solution {
    public int findMin(int[] nums) {
        int min = Integer.MAX_VALUE;
        for (int n: nums) {
          min = Math.min(min, n);
        }
        return min;
    }
}
```
### JavaScript Solution
```javascript
var findMin = function(nums) {
    let min = Infinity;
    for (let n of nums) {
        min = Math.min(min, n);
    }
    return min;
}
```
<a id="optimized"></a>
## Optimized Solution
Time Complexity :: O(log N)
Space Complexity :: O(1)
### Java Solution
```java
class Solution {
    public int findMin(int[] nums) {
        int start = 0, end = nums.length-1;
        while (start < end) {
            int mid = (start + end) / 2;
            if (nums[mid] > nums[end]) {
                start = mid + 1;
            } else {
                end = mid;
            }
        }
        return nums[start];
    }
}
```
### JavaScript Solution
```javascript

```
<a id="notes"></a>
## Notes
