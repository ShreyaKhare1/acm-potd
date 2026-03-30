<img width="1888" height="892" alt="Screenshot 2026-03-30 091621" src="https://github.com/user-attachments/assets/14121e01-e5c2-4d58-8fe7-1561a4ee1135" />
# Linked List Cycle Detection (Floyd’s Tortoise and Hare)

This Java method checks whether a singly linked list contains a cycle using the **two-pointer technique**.

## Approach
- Use two pointers:
  - **slow** → moves one step at a time
  - **fast** → moves two steps at a time
- If there is a cycle, both pointers will eventually meet.
- If `fast` reaches `null`, there is no cycle.

## Code

```java
/**
 * Definition for singly-linked list.
 * class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) {
 *         val = x;
 *         next = null;
 *     }
 * }
 */
public class Solution {
    public boolean hasCycle(ListNode head) {
        ListNode slow = head;
        ListNode fast = head;

        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;

            if (slow == fast) {
                return true;
            }
        }
        return false;
    }
}
