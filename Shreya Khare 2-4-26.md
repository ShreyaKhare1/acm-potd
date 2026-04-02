<img width="1900" height="873" alt="Screenshot 2026-04-02 080124" src="https://github.com/user-attachments/assets/946deff1-86b5-42a9-acd1-148b1f8adf13" />
# Remove Duplicates from Sorted Linked List

##  Problem

Given the head of a **sorted linked list**, delete all duplicates such that each element appears only once.

---

##  Approach

* Traverse the linked list using a pointer `temp`
* If current node value equals next node value → remove duplicate
* Otherwise move pointer forward
* Since list is sorted, duplicates appear consecutively

---

##  Complexity

* **Time Complexity:** O(n)
* **Space Complexity:** O(1)

---

##  Java Code

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode deleteDuplicates(ListNode head) {
        ListNode temp = head;

        while(temp != null && temp.next != null){
            if(temp.val == temp.next.val){
                temp.next = temp.next.next;
            }
            else{
                temp = temp.next;
            }
        }

        return head;
    }
}
```

---

##  Dry Run

Input:

```
1 → 1 → 2 → 3 → 3
```

Steps:

```
1 == 1 → remove duplicate
1 → 2 → 3 → 3

1 != 2 → move forward
2 != 3 → move forward

3 == 3 → remove duplicate
```

Output:

```
1 → 2 → 3
```

---



---
