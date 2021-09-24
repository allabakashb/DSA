# Expression Add Operators
* [Examples](#example)
* [Brute Force Solution](#bruteforce)
* [Optimized Solution](#optimized)
* [Notes](#notes)

<a id="example"></a>
## Examples
```
Input: num = "123", target = 6
Output: ["1*2*3","1+2+3"]
Input: num = "232", target = 8
Output: ["2*3+2","2+3*2"]
Input: num = "105", target = 5
Output: ["1*0+5","10-5"]
Input: num = "00", target = 0
Output: ["0*0","0+0","0-0"]
```
<a id="bruteforce"></a>
## Brute Force Solution
##### Time Complexity :: 
##### Space Complexity :: 
### Java Solution
```java
class Solution {
    public List<String> addOperators(String num, int target) {
        char[] numArray = new char[num.length*2-1];
        for (int i = 0; i < numArray.length; i+=2) {
            numArray[i] = num.charAt(i/2);
        }
        List<String> res = new ArrayList<>();
        backtrack(0, 0, target, numArray, res);
        return res;
    }
    private void backtrack(int i, int val, int target, char[] numsArray, List<String> res) {
        if (i >= numsArray.length) {
            if (target == val) {
                res.add(new String(numsArray));
            }
            return;
        }
        int curr = numsArray[i] - '0';
        numsArray[i+1] = '+';
        backtrack(i+2, val+curr, target, numsArray, res);
        numsArray[i+1] = '-';
        backtrack(i+2, val-curr, target, numsArray, res);
        numsArray[i+1] = '*';
        backtrack(i+2, val*curr, target, numsArray, res);
        numsArray[i+1] = ' ';
    }
}

```
### JavaScript Solution
```javascript

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
