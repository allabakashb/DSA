# Reverse Linked List
* [Examples](#example)
* [Brute Force Solution](#bruteforce)
* [Optimized Solution](#optimized)
* [Notes](#notes)

<a id="example"></a>
## Examples
```
Input: head = [1,2,3,4,5]
Output: [5,4,3,2,1]
Input: head = [1,2,3,4,5,6]
Output: [6,5,4,3,2,1]
```
<a id="bruteforce"></a>
## Brute Force Solution
##### Time Complexity :: O(N)
##### Space Complexity :: O(1)
### Java Solution
```java
class Solution {
  public ListNode reverseList(ListNode head) {
    ListNode ref = null;
    while (head != null) {
      ListNode next = head;
      head = head.next;
      next.next = ref;
      ref = next;
    }
    return ref;
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
