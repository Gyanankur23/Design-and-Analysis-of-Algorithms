# Design-and-Analysis-of-Algorithms

# Question Bank Solution 

## Q1. What Is an Algorithm? Explain Its Fundamental Steps Using the Example of Finding the Area of a Rectangle

An algorithm is a finite, well-defined sequence of instructions designed to perform a specific task or solve a particular problem.  

Fundamental steps of any algorithm:  
1. Problem Definition – Clearly state inputs and desired output.  
2. Analysis – Understand constraints (e.g., data types, range).  
3. Design – Devise a step-by-step procedure.  
4. Implementation – Translate the procedure into code or pseudocode.  
5. Testing & Verification – Run with sample inputs; verify correctness and efficiency.  

Example: Compute area of a rectangle (given length L and width W):  
`
Step 1: Read L, W
Step 2: area ← L × W
Step 3: Print area
`

Flowchart (ASCII):  
`
┌───────────┐
│ Start     │
└─────┬─────┘
      │
┌─────▼─────┐
│ Read L, W │
└─────┬─────┘
      │
┌─────▼─────────┐
│ area = L * W  │
└─────┬─────────┘
      │
┌─────▼─────┐
│ Print area│
└─────┬─────┘
      │
┌─────▼─────┐
│ End       │
└───────────┘
`

---

## Q2. Short Note on Algorithm with an Example

An algorithm must be:  
- Finite (terminates after a number of steps).  
- Deterministic (each step is precisely defined).  
- General (works for all valid inputs).  
- Efficient (reasonable use of time and memory).  

Example: Linear Search – find element X in array A[1…n]  
`
for i from 1 to n do
  if A[i] == X then
    return i
return “Not Found”
`

---

## Q3. Types of Complexity in Data Structures

1. Time Complexity – number of elementary operations as a function of input size (e.g., O(1), O(n), O(n log n)).  
2. Space Complexity – extra memory required beyond input (e.g., in-place vs. auxiliary).  
3. Auxiliary Complexity – temporary space used by an algorithm (stack, recursion).  
4. Amortized Complexity – average cost per operation over a sequence (e.g., dynamic array resizing).  

---

## Q4. Short Note on Complexity

- Worst-Case Complexity – maximum time/space over all inputs of size n.  
- Best-Case Complexity – minimum time/space (often trivial).  
- Average-Case Complexity – expected time/space given a probability distribution of inputs.  
- Used to compare algorithms and predict performance on large datasets.  

---

## Q5. Five Fundamentals of Data Structures

1. Abstraction – hide implementation details, expose operations (e.g., push/pop for stacks).  
2. Organization – logical layout in memory (contiguous vs. linked).  
3. Operations – insert, delete, traverse, search, update.  
4. Efficiency – trade-off between time and space for operations.  
5. Reusability & Modularity – implement once, reuse across programs (e.g., library modules).  

---

## Q6. Different Types of Time Complexity

- O(1): constant time (array indexing).  
- O(log n): logarithmic (binary search).  
- O(n): linear (single loop).  
- O(n log n): linearithmic (merge sort, heap sort).  
- O(n²): quadratic (simple sorting like bubble sort).  
- O(2ⁿ), O(n!): exponential/factorial (brute-force combinatorics).  

---

## Q7. Recursive Algorithm & Its Time Complexity

Example: Factorial  
`
function fact(n):
  if n == 0 then
    return 1
  else
    return n × fact(n-1)
`
- Time Complexity: T(n) = T(n–1) + O(1) → O(n)  
- Space Complexity: O(n) auxiliary (call stack)  

Flow (n=3): 3→2→1→0, then unwind.

---

## Q8. Non-Recursive Algorithm with Example

Example: Iterative Factorial  
`
function fact_iter(n):
  result ← 1
  for i from 1 to n do
    result ← result × i
  return result
`
- Time Complexity: O(n)  
- Space Complexity: O(1) auxiliary  

---

## Q9. Short Note on Linked List

A linked list stores nodes where each node holds data and a pointer to the next node.  
- Advantages: dynamic size, easy insertion/deletion.  
- Disadvantages: no random access, extra memory for pointers.  

---

## Q10. Doubly Linked List with Diagram

Each node has: [ prev | data | next ]  
`
Head
  ↓
┌─────┬──────┬─────┐    ┌─────┬──────┬─────┐    ┌─────┬──────┬─────┐
│ NULL│  10  │  ↔  │──▶ │ 20  │  20  │  ↔  │──▶ │ 30  │  30  │NULL│
└─────┴──────┴─────┘    └─────┴──────┴─────┘    └─────┴──────┴─────┘
`
Pointers:  
- head.prev = NULL  
- tail.next = NULL  

---

## Q11. Algorithm: Insert Node at Beginning of Doubly Linked List

Pseudocode:  
`
procedure InsertAtBeginning(head, value):
  newNode ← allocate Node
  newNode.data ← value
  newNode.prev ← NULL
  newNode.next ← head
  if head ≠ NULL then
    head.prev ← newNode
  head ← newNode
  return head
`
Diagram before/after insertion of 5:  
`
Before: head→ [NULL│10│next…]
After:  head→ [NULL│ 5 │ ↔ ] → [Prev│10│Next]
`

---

## Q12. Algorithm: Delete Node from Beginning of Doubly Linked List

`
procedure DeleteAtBeginning(head):
  if head = NULL then
    return NULL
  toDelete ← head
  head ← head.next
  if head ≠ NULL then
    head.prev ← NULL
  free(toDelete)
  return head
`

---

## Q13. Algorithm: Insert Node at Given Position in Singly Linked List

`
procedure InsertAtPosition(head, value, pos):
  newNode ← allocate Node; newNode.data ← value
  if pos = 1:
    newNode.next ← head
    head ← newNode
    return head
  temp ← head
  for i from 1 to pos-2 do
    if temp = NULL then break
    temp ← temp.next
  if temp = NULL then error “Position out of range”
  newNode.next ← temp.next
  temp.next ← newNode
  return head
`
Diagram: Insert at position 3.  

---

## Q14. Array vs. Linked List (5 Points)

1. Memory: Array is contiguous; linked list is dynamic and scattered.  
2. Access: Array supports O(1) random access; list requires O(n) traversal.  
3. Insertion/Deletion: Array O(n) worst; list O(1) if pointer known.  
4. Size: Fixed (array) vs. flexible (list).  
5. Overhead: Array has no pointer overhead; list stores extra pointers.  

---

## Q15. Circular Linked List with Diagram & Memory Representation

Nodes connected end-to-start:  
`
       ┌────┐    ┌────┐    ┌────┐
head→ │[10│▶]─▶│[20│▶]─▶│[30│▶]─┐
       └┬───┘    └┬───┘    └┬───┘ │
        │         │         │    │
        └────────────────────┘
`
Memory: each node’s next of last points to head.

---

## Q16. Delete Last Node in Singly Linked List

`
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
`
Diagram: before/after tail removal.

---

## Q17. Explain Stack with Diagram

A stack is LIFO (last-in, first-out).  

Push and Pop happen at the top:  
`
│ 30 │  ← top
│ 20 │
│ 10 │
└────┘
`

---

## Q18. Operations in Stack

- push(x): add x at top  
- pop(): remove and return top  
- peek()/top(): view top without removing  
- isEmpty(): check if stack is empty  
- isFull() (in fixed-size stack)  

---

## Q19. Push and Pop Algorithms of Stack

`
procedure push(stack, x):
  if stack.top = stack.size-1 then error “Overflow”
  stack.top ← stack.top + 1
  stack[stack.top] ← x

procedure pop(stack):
  if stack.top = -1 then error “Underflow”
  x ← stack[stack.top]
  stack.top ← stack.top - 1
  return x
`

---

## Q20. Short Note on Stack

- Abstract data type offering LIFO access.  
- Used for expression evaluation, backtracking, recursion simulation.  
- Can be implemented via array or linked list.  
- Space complexity: O(n), time for push/pop: O(1).  
- Fundamental in parsing, call-stack management, undo mechanisms.  

---

All algorithms include clear steps and ASCII-style diagrams to illustrate node/link relationships or control flow.
