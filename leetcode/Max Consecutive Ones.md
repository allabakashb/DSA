# Max Consecutive Ones
* [Examples](#example)
* [Brute Force Solution](#bruteforce)
* [Optimized Solution](#optimized)
* [Notes](#notes)

<a id="example"></a>
## Examples
```
Input: nums = [1,1,0,1,1,1]
Output: 3
Input: nums = [1,0,1,1,0,1]
Output: 2
```
<a id="bruteforce"></a>
## Brute Force Solution
##### Time Complexity :: O(N)
##### Space Complexity :: O(1)
### Java Solution
```java
class Solution {
    public int findMaxConsecutiveOnes(int[] nums) {
        int max = 0, i = 0, count = 0;
        while (i < nums.length) {
            if (nums[i++] == 0) {
                max = Math.max(max, count);
                count = 0;
            } else {
                ++count;
            }
        }
        return Math.max(count, max);
    }
}
```
### JavaScript Solution
```javascript
function findMaxConsecutiveOnes(nums) {
    let max = 0, count = 0;
    for (let n of nums) {
        if (n == 1) {
            ++count;
        } else {
            max = Math.max(max, count);
            count = 0;
        }
    }
    return Math.max(max, count);
}
```
<a id="optimized"></a>
## Optimized Solution
##### Time Complexity :: 
##### Space Complexity :: 
### Java Solution
```java

```
### JavaScript Solution
```javascript

```
<a id="notes"></a>
## Notes
# Edge Case, last 3 digits - 110111