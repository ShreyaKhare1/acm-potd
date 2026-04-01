<img width="1898" height="909" alt="Screenshot 2026-04-01 183131" src="https://github.com/user-attachments/assets/7326499a-b679-4429-81c8-7ba4bf98d890" />
Merge Two Sorted Linked Lists
🧠 Problem

Given two sorted linked lists, merge them into one sorted linked list and return it.

💡 Approach
Use a dummy node to simplify edge cases
Compare nodes from both lists
Attach the smaller node to result
Move pointer forward
Attach remaining nodes at the end
⏱ Complexity
Time Complexity: O(n + m)
Space Complexity: O(1) (in-place)
🧾 Code (Java)
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
    public ListNode mergeTwoLists(ListNode list1, ListNode list2) {
        ListNode temp1 = list1;
        ListNode temp2 = list2;
        
        ListNode dummy = new ListNode();
        ListNode curr = dummy;

        while (temp1 != null && temp2 != null) {
            if (temp1.val < temp2.val) {
                curr.next = temp1;
                temp1 = temp1.next;
            } else {
                curr.next = temp2;
                temp2 = temp2.next;
            }
            curr = curr.next;
        }

        if (temp1 != null) {
            curr.next = temp1;
        }

        if (temp2 != null) {
            curr.next = temp2;
        }

        return dummy.next;
    }
}
🔍 Dry Run
Input
list1: 1 → 3 → 5
list2: 2 → 4 → 6
Steps
dummy → _
compare 1 and 2 → take 1
dummy → 1

compare 3 and 2 → take 2
dummy → 1 → 2

compare 3 and 4 → take 3
dummy → 1 → 2 → 3

compare 5 and 4 → take 4
dummy → 1 → 2 → 3 → 4

compare 5 and 6 → take 5
dummy → 1 → 2 → 3 → 4 → 5

attach remaining → 6
Output
1 → 2 → 3 → 4 → 5 → 6

