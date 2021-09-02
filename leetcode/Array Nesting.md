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
        visited[i] = true;
        index = nums[i];
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

```
<a id="optimized"></a>
## Optimized Solution
### Java Solution
```java

```
### JavaScript Solution
```javascript

```
<a id="notes"></a>
## Notes
