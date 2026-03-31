<img width="1593" height="747" alt="Screenshot 2026-03-31 123008" src="https://github.com/user-attachments/assets/8643e300-f91d-49d5-969e-52b8771b3b9f" />
# Find Middle of Linked List (Slow & Fast Pointer)

## 🧠 Problem

Given the head of a singly linked list, return the **middle node**.
If there are **two middle nodes**, return the **second middle**.

---

## 🚀 Approach — Slow & Fast Pointer

* Use two pointers:

  * `slow` → moves **1 step**
  * `fast` → moves **2 steps**
* When `fast` reaches the end, `slow` will be at the **middle**.

---

## ✅ Java Code

```java
public ListNode middleNode(ListNode head) {
    if (head == null) {
        return null;
    }

    ListNode slow = head;
    ListNode fast = head;

    while (fast != null && fast.next != null) {
        slow = slow.next;
        fast = fast.next.next;
    }

    return slow;
}
```

---

## 📌 Example 1

```
Input:  1 -> 2 -> 3 -> 4 -> 5
Output: 3
```

## 📌 Example 2

```
Input:  1 -> 2 -> 3 -> 4 -> 5 -> 6
Output: 4
```

(returns second middle)

---

## ⏱️ Complexity

* **Time:** O(N)
* **Space:** O(1)

---

## 🎯 Key Points

* No extra space needed
* Single traversal
* Most optimal solution
* Works for even & odd length lists

---

## 💡 Dry Run

```
1 -> 2 -> 3 -> 4 -> 5

slow = 1, fast = 1
slow = 2, fast = 3
slow = 3, fast = 5
stop → slow = middle
```
