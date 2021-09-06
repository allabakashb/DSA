# Slowest Key
* [Examples](#example)
* [Brute Force Solution](#bruteforce)
* [Optimized Solution](#optimized)
* [Notes](#notes)

<a id="example"></a>
## Examples
```
Input: releaseTimes = [9,29,49,50], keysPressed = "cbcd"
Output: "c"
Input: releaseTimes = [12,23,36,46,62], keysPressed = "spuda"
Output: "a"
```
<a id="bruteforce"></a>
## Brute Force Solution
### Java Solution
##### Time Complexity :: O(N)
##### Space Complexity :: O(1)
```java
class Solution {
  public char slowestKey(int[] releaseTimes, String keysPressed) {
    int max = releaseTimes[0];
    char maxChar = keysPressed.charAt(0);
    for (int i = 1; i < releaseTimes.length; i++) {
      int duration = releaseTimes[i] - releaseTimes[i-1];
      if (duration > max) {
        maxChar = keysPressed.charAt(i);
        max = duration;
      } else if (duration == max && maxChar < keysPressed.charAt(i)) {
        maxChar = keysPressed.charAt(i);
      }
    }
    return maxChar;
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
