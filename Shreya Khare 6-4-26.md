Idea
Use two stacks s1 and s2
push() → always push into s1
pop() / peek() → move elements from s1 to s2 only when s2 is empty
This maintains queue order
Code (Java)
class MyQueue {
    Stack<Integer> s1 = new Stack<>();
    Stack<Integer> s2 = new Stack<>();

    public void push(int x) {
        s1.push(x);
    }

    public int pop() {
        if(empty()) return -1;

        if(s2.isEmpty()){
            while(!s1.isEmpty()){
                s2.push(s1.pop());
            }
        }
        return s2.pop();
    }

    public int peek() {
        if(empty()) return -1;

        if(s2.isEmpty()){
            while(!s1.isEmpty()){
                s2.push(s1.pop());
            }
        }
        return s2.peek();
    }

    public boolean empty() {
        return s1.isEmpty() && s2.isEmpty();
    }
}
Complexity
Operation	Time Complexity
push()	O(1)
pop()	O(1) amortized
peek()	O(1) amortized
empty()	O(1)
<img width="1900" height="903" alt="image" src="https://github.com/user-attachments/assets/848fa19d-0809-477b-ab02-303cbb27ca63" />
