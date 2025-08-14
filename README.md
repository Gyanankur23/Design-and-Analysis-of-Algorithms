text
# Design-and-Analysis-of-Algorithms

📘 **Question Bank Solution**

---

## Q1. What Is an Algorithm? Explain Its Fundamental Steps Using the Example of Finding the Area of a Rectangle

An **algorithm** is a finite, well-defined sequence of instructions designed to solve a specific problem.

**Fundamental Steps:**
1. Problem Definition – Identify inputs and output.
2. Analysis – Understand constraints/data types.
3. Design – Logical sequence of steps.
4. Implementation – Code or pseudocode.
5. Testing & Verification – Check correctness/efficiency.

**Example: Area of a Rectangle**

*Pseudocode:*
Step 1: Read L, W
Step 2: area ← L × W
Step 3: Print area

text

*Flowchart:*
┌───────────┐
│ Start │
└─────┬─────┘
│
┌─────▼─────┐
│ Read L, W │
└─────┬─────┘
│
┌─────▼─────────┐
│ area = L × W │
└─────┬─────────┘
│
┌─────▼─────┐
│ Print area│
└─────┬─────┘
│
┌─────▼─────┐
│ End │
└───────────┘

text

---

## Q2. Short Note on Algorithm with an Example

An algorithm must be:
- **Finite** – must terminate.
- **Deterministic** – every step is clear.
- **General** – works for valid inputs.
- **Efficient** – reasonable resources.

**Example: Linear Search**
for i from 1 to n do
if A[i] == X then
return i
return “Not Found”

text

---

## Q3. Types of Complexity in Data Structures

- **Time Complexity** – Steps as input size grows.
- **Space Complexity** – Extra memory used.
- **Auxiliary Space** – Temp space (e.g., recursive stack).
- **Amortized Complexity** – Avg. over many ops.

---

## Q4. Short Note on Complexity

- **Worst Case** – Maximum resources needed.
- **Best Case** – Minimum resources.
- **Average Case** – Expected resources.
- **Purpose:** Helps compare/choose algorithms.

---

## Q5. Five Fundamentals of Data Structures

1. Abstraction – Hidden implementation.
2. Organization – Memory layout.
3. Operations – Insert, delete, search, traverse.
4. Efficiency – Resource trade-offs.
5. Modularity – Reusable components.

---

## Q6. Different Types of Time Complexity

- O(1) – Constant (e.g., array access)
- O(log n) – Logarithmic (binary search)
- O(n) – Linear (traversal)
- O(n log n) – Merge/heap sort
- O(n²) – Nested loops/bubble sort
- O(2ⁿ), O(n!) – Exponential/factorial (brute force)

---

## Q7. Recursive Algorithm & Its Time Complexity

**Example: Factorial**
function fact(n):
if n == 0 then
return 1
else
return n × fact(n-1)

text
- **Time:** O(n)
- **Space:** O(n) (recursion stack)

---

## Q8. Non-Recursive Algorithm with Example

**Example: Iterative Factorial**
function fact_iter(n):
result ← 1
for i from 1 to n do
result ← result × i
return result

text
- **Time:** O(n)
- **Space:** O(1)

---

## Q9. Short Note on Linked List

A **linked list** is a dynamic structure where each node has:
- Data
- Next pointer

**Advantages:** Dynamic size, easy insert/delete  
**Disadvantages:** No random access, extra pointer memory

---

## Q10. Doubly Linked List with Diagram

Each node:
[ prev | data | next ]

text
Diagram:
NULL ← ⇄ ⇄ → NULL

text
- head.prev = NULL
- tail.next = NULL

---

## Q11. Algorithm: Insert Node at Beginning of Doubly Linked List

*Pseudocode:*
procedure InsertAtBeginning(head, value):
newNode ← allocate Node
newNode.data ← value
newNode.prev ← NULL
newNode.next ← head
if head ≠ NULL then
head.prev ← newNode
head ← newNode
return head

text

---

## Q12. Algorithm: Delete Node from Beginning of Doubly Linked List

*Pseudocode:*
procedure DeleteAtBeginning(head):
if head = NULL then return NULL
toDelete ← head
head ← head.next
if head ≠ NULL then head.prev ← NULL
free(toDelete)
return head

text

---

## Q13. Algorithm: Insert Node at Given Position in Singly Linked List

*Pseudocode:*
procedure InsertAtPosition(head, value, pos):
newNode ← allocate Node
newNode.data ← value
if pos = 1:
newNode.next ← head
head ← newNode
return head
temp ← head
for i from 1 to pos-2 do
temp ← temp.next
newNode.next ← temp.next
temp.next ← newNode
return head

text

---

## Q14. Array vs. Linked List (5 Points)

| Feature   | Array              | Linked List           |
|-----------|--------------------|----------------------|
| Memory    | Contiguous         | Dynamic, scattered   |
| Access    | O(1) random access | O(n) traversal       |
| Insertion | Costly (O(n))      | Efficient (O(1))     |
| Size      | Fixed              | Flexible             |
| Overhead  | No pointers        | Extra pointer/node   |

---

## Q15. Circular Linked List with Diagram

Diagram:
→ →
↑ ↓
└───────────────┘

text
- Last node points to head.
- Used in round-robin scheduling.

---

## Q16. Delete Last Node in Singly Linked List

*Pseudocode:*
procedure DeleteLast(head):
if head = NULL then return NULL
if head.next = NULL then
free(head); return NULL
temp ← head
while temp.next.next ≠ NULL do
temp ← temp.next
free(temp.next)
temp.next ← NULL
return head

text

---

## Q17. Explain Stack with Diagram

A **stack** is a LIFO structure.

Diagram:
Top →

text
- Push: add to top.
- Pop: remove from top.

---

## Q18. Operations in Stack

- push(x): Insert at top  
- pop(): Remove top  
- peek(): View top  
- isEmpty(): Check for empty  
- isFull(): For arrays only

---

## Q19. Push and Pop Algorithms of Stack

**Push:**
procedure push(stack, x):
if stack.top = stack.size-1 then error "Overflow"
stack.top ← stack.top + 1
stack[stack.top] ← x

text
**Pop:**
procedure pop(stack):
if stack.top = -1 then error "Underflow"
x ← stack[stack.top]
stack.top ← stack.top - 1
return x

text

---

## Q20. Short Note on Stack

- Linear, LIFO data structure
- Used in recursion, parsing, undo ops
- Implemented via array or linked list
- Push/pop: O(1)
- Supports modular, efficient code flow

---

Let me know if you want this exported as a `.md` file or styled for GitHub Pages! 🚀
- Can be implemented via array or linked list.  
- Space complexity: O(n), time for push/pop: O(1).  
- Fundamental in parsing, call-stack management, undo mechanisms.  

---

All algorithms include clear steps and ASCII-style diagrams to illustrate node/link relationships or control flow.
