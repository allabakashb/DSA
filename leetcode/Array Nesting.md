# Array Nesting
* [Examples](#example)
* [Brute Force Solution](#bruteforce)
* [Optimized Solution](#optimized)
* [Notes](#notes)

<a id="example"></a>
## Examples
```
Input: [5,4,0,3,1,6,2]
Output: 4
Input: [0,1,2]
Output: 1
```
<a id="bruteforce"></a>
## Brute Force Solution
##### Time Complexity :: O(N*N)
##### Space Complexity :: O(N*N)
### Java Solution
```java
class Solution {
  public int arrayNesting(int[] nums) {
    int maxLength = 0;
    for (int i = 0; i < nums.length; i++) {
      int index = i;
      boolean[] visited = new boolean[nums.length];
      int len = 0;
      while (!visited[index]) {
        visited[index] = true;
        index = nums[index];
        ++len;
      }
      maxLength = Math.max(len, maxLength);
    }
    return maxLength;
  }
}
```
### JavaScript Solution
```javascript
var arrayNesting = function(nums) {
  let maxLen = 0;
  for (let i = 0; i < nums.length; i++) {
      let index = i, len = 0;
      let visited = [];
      while (!visited[index]) {
          visited[index] = true;
          index = nums[index];
          ++len;
      }
      maxLen = Math.max(maxLen, len);
  }
  return maxLen;
};
```
<a id="optimized"></a>
## Optimized Solution
##### Time Complexity :: O(N)
##### Space Complexity :: O(N)
### Java Solution
```java
class Solution {
  public int arrayNesting(int[] nums) {
    int maxLen = 0;
    int[] dp = new int[nums.length];
    for (int i = 0; i < nums.length; i++) {
      maxLen = Math.max(maxLen, recurse(nums, i, dp));
    }
    return maxLen;
  } 
  private int recurse(int[] nums, int index, int[] dp) {
    if (dp[index] < 0) return 0;
    if (dp[index] > 0) return dp[index];
    dp[index] = -1;
    dp[index] = recurse(nums, nums[index], dp) + 1;
    return dp[index];
  }
}
```
### JavaScript Solution
```javascript
var arrayNesting = function(nums) {
  function recurse(nums, index, dp) {
    if (dp[index] != 0) return Math.max(0, dp[index]);
    dp[index] = -1;
    dp[index] = recurse(nums, nums[index], dp) + 1;
    return dp[index];
  }
  let maxLen = 0, dp = [];
  for (let i = 0; i < nums.length; i++) {
    maxLen = Math.max(maxLen, recurse(nums,i, dp));
  }
  return maxLen;
}
```
<a id="notes"></a>
## Notes
