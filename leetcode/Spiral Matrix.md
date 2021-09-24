# Spiral Matrix
* [Examples](#example)
* [Brute Force Solution](#bruteforce)
* [Optimized Solution](#optimized)
* [Notes](#notes)

<a id="example"></a>
## Examples
```
Input: matrix = [[1,2,3],[4,5,6],[7,8,9]]
Output: [1,2,3,6,9,8,7,4,5]
Input: matrix = [[1,2,3,4],[5,6,7,8],[9,10,11,12]]
Output: [1,2,3,4,8,12,11,10,9,5,6,7]
```
<a id="bruteforce"></a>
## Brute Force Solution
##### Time Complexity :: O(M*N)
##### Space Complexity :: O(M*N)
### Java Solution
```java
class Solution {
    public List<Integer> spiralOrder(int[][] matrix) {

        List<Integer> res = new ArrayList<>();
        int rowStart = 0, colStart = 0, dir = 0, rowEnd = matrix.length, colEnd = matrix[0].length; 

        while (rowStart < rowEnd && colStart < colEnd) {
            switch(dir) {
                case 0:
                    for (int l = colStart; l < colEnd; l++) {
                        res.add(matrix[rowStart][l]);
                    }
                    ++rowStart;
                    break;
                case 1:
                    for (int l = rowStart; l < rowEnd; l++) {
                        res.add(matrix[l][colEnd-1]);
                    }
                    --colEnd;
                    break;
                case 2:
                    for (int l = colEnd-1; l >= colStart; l--) {
                        res.add(matrix[rowEnd-1][l]);
                    }
                    --rowEnd;
                    break;
                case 3:
                    for (int l = rowEnd-1; l >= rowStart; l--) {
                        res.add(matrix[l][colStart]);
                    }
                    ++colStart;
                    dir = -1;
                    break;
            }
            ++dir;
        }

        return res;
    } 
}

```
### JavaScript Solution
```javascript
function spiralOrder(matrix) {
    let rowStart = 0, colStart = 0, rowEnd = matrix.length, colEnd = matrix[0].length, dir = 0;
    let res = [];
    while (rowStart < rowEnd && colStart < colEnd) {
        switch(dir) {
            case 0:
                for (let i = colStart; i < colEnd; i++) {
                    res.push(matrix[rowStart][i]);
                }
                ++rowStart;
                break;
            case 1:
                for (let i = rowStart; i < rowEnd; i++) {
                    res.push(matrix[i][colEnd-1]);
                }
                --colEnd;
                break;
            case 2:
                for (let i = colEnd-1; i >= colStart; i--) {
                    res.push(matrix[rowEnd-1][i]);
                }
                --rowEnd;
                break;
            case 3:
                for (let i = rowEnd-1; i >= rowStart; i--) {
                    res.push(matrix[i][colStart]);
                }
                ++colStart;
                dir = -1;
                break;
        }
        ++dir;
    }
    return res; 
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
# Just follow fill direction and while should run for both co-ordinate limits