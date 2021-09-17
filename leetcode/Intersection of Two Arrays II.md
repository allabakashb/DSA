# Intersection of Two Arrays II
* [Examples](#example)
* [Brute Force Solution](#bruteforce)
* [Optimized Solutions1](#optimized1)
* [Optimized Solutions2](#optimized2)
* [Notes](#notes)

<a id="example"></a>
## Examples
```
Input: nums1 = [1,2,2,1], nums2 = [2,2]
Output: [2,2]
Input: nums1 = [4,9,5], nums2 = [9,4,9,8,4]
Output: [4,9]
Explanation: [9,4] is also accepted.
```
<a id="bruteforce"></a>
## Brute Force Solution
##### Time Complexity :: O(N*M)
##### Space Complexity :: O(min(M, N))
### Java Solution
```java
class Solution {
    public int[] intersect(int[] nums1, int[] nums2) {
        if (nums1.length > nums2.length) return intersect(nums2, nums1);
        boolean[] taken = new boolean[nums1.length];
        List<Integer> res = new ArrayList<>();
        for (int i = 0; i < nums2.length; i++) {
            for (int j = 0; j < nums1.length; j++) {
                if (!taken[j] && nums1[j] == nums2[i]) {
                    res.add(nums1[j]);
                    taken[j] = true;
                    break;
                }
            }
        }
        return res.stream().mapToInt(k->k).toArray();
    }
}
```
### JavaScript Solution
```javascript
function intersect(nums1, nums2) {
    if (nums2.length < nums1.length) return intersect(nums2, nums1);
    let res = [], taken = [];
    for (let i = 0; i < nums2.length; i++) {
        for (let j = 0; j < nums1.length; j++) {
            if (!taken[j] && nums1[j] === nums2[i]) {
                res.push(nums2[i]);
                taken[j] = true;
                break;
            }
        }
    }
    return res;
}
```

<a id="optimized1"></a>
## Optimized Solution 1

##### Time Complexity :: NlogN + MlogM => O(NlogN)
##### Space Complexity :: O(N)
```java
class Solution {
    public int[] intersect(int[] nums1, int[] nums2) {
        Arrays.sort(nums1);
        Arrays.sort(nums2);

        List<Integer> res = new ArrayList<>();
        int i = 0, j = 0;
        while (i < nums1.length && j < nums2.length) {
            if (nums1[i] == nums2[j]) {
                res.add(nums1[i]);
                ++i;
                ++j;
            } else if (nums1[i] < nums2[j]) {
                ++i;
            } else {
                ++j;
            }
        }
        return res.stream().mapToInt(k->k).toArray();
    }
}

```
### JavaScript Solution
```javascript
function intersect(num1, num2) {
    num1.sort((n1, n2)=>n1-n2);
    num2.sort((n1, n2)=>n1-n2);
    let i = 0, j = 0;
    let res = [];
    while (i < num1.length && j < num2.length) {
        if (num1[i] === num2[j]) {
            res.push(nums1[i]);
            ++i;
            ++j;
        } else if (num1[i] < num2[j]) {
            ++i;
        } else {
            ++j;
        }
    }
    return res;
}

```
<a id="optimized2"></a>
## Optimized Solution 2
##### Time Complexity :: O(M+N)
##### Space Complexity :: O(min(M, N))
### Java Solution
```java
class Solution {
    public int[] intersect(int[] nums1, int[] nums2) {
        if (nums1.length > nums2.length) return intersect(nums2, nums1);
        Map<Integer, Integer> map = new HashMap<>();
        for (int i = 0; i < nums1.length; i++) {
            map.put(nums1[i], map.getOrDefault(nums1[i], 0)+1);
        }
        List<Integer> res = new ArrayList<>();
        for (int j = 0; j < nums2.length; j++) {
            if (map.containsKey(nums2[j])) {
                Integer count = map.get(nums2[j]);
                if (count > 0) {
                    res.add(nums2[j]);
                    map.put(nums2[j], count-1);
                }
            }
        }
        return res.stream().mapToInt(k->k).toArray();
    }
}
```
### JavaScript Solution
```javascript
function intersect(nums1, nums2) {
    if (nums1.length > nums2.length) return intersect(nums2, nums1);
    let res = [], map = new Map();
    for (let n of nums1) {
        let c = map.get(n);
        map.set(n, !c ? 1 : c+1);
    }
    for (let n of nums2) {
        if (map.has(n)) {
            let c = map.get(n);
            if (c > 0) {
                map.set(n, c-1);
                res.push(n);
            }
        }
    }
    return res;
}

```
<a id="notes"></a>
## Notes
