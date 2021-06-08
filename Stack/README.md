# Stack

A stack is an ordered list in which insertion and deletion are done at one end, called
top. The last element inserted is the first one to be deleted. Hence, it is called the Last in First out(LIFO) or First in Last out (FILO) list.<br>

**Example**: A pile of plates in a cafeteria is a good example of a
stack. The plates are added to the stack as they are cleaned and they are placed on the top. When a
plate, is required it is taken from the top of the stack. The first plate placed on the stack is the last one to be used.

![stack](image/stack.png)<br>

## Stack ADT
The following operations make a stack an ADT. For simplicity, assume the data is an integer type.
### Main stack operations
- Push(): Inserts data onto stack.
- Pop(): Removes and returns the last inserted element from the stack.

### Auxiliary stack operations

- Top(): Returns the last inserted element without removing it.
- Size():Returns the number of elements stored in the stack.
- IsEmptyStack():Indicates whether any elements are stored in the stack or not.
- IsFullStack(): Indicates whether the stack is full or not.

## Applications:
### Direct applications
- Balancing of symbols
- Infix-to-postfix conversion
- Evaluation of postfix expression
- Implementing function calls (including recursion)
- Finding of spans (finding spans in stock markets, refer to Problems section)
- Page-visited history in a Web browser [Back Buttons]
- Undo sequence in a text editor
- Matching Tags in HTML and XML
### Indirect applications
- Auxiliary data structure for other algorithms (Example: Tree traversal algorithms)

## Problems:

| Problems    | Soultion  |      
| :------------- |:-------------:| 
| Evaluation of Postfix Expression  | [Here](https://www.geeksforgeeks.org/stack-set-4-evaluation-postfix-expression/) |
| Get minimum element from stack  | [Here](https://www.geeksforgeeks.org/design-a-stack-that-supports-getmin-in-o1-time-and-o1-extra-space/) |
| Implement stack using array  | [Here](https://www.geeksforgeeks.org/stack-data-structure-introduction-program/) |
| Implement Stack using Linked List  | [Here](https://www.geeksforgeeks.org/stack-data-structure-introduction-program/) |
| Implement two stacks in an array  | [Here](https://www.geeksforgeeks.org/implement-two-stacks-in-an-array/) |
| Maximum of minimum for every window size  | [Here](https://www.geeksforgeeks.org/find-the-maximum-of-minimums-for-every-window-size-in-a-given-array/) |
| Next larger element  | [Here](https://www.geeksforgeeks.org/next-greater-element/) |
| Parenthesis Checker  | [Here](https://www.geeksforgeeks.org/check-for-balanced-parentheses-in-an-expression/) |
| Sort a stack  | [Here](https://www.geeksforgeeks.org/sort-a-stack-using-recursion/) |
| Special Stack  | [Here](https://www.tutorialcup.com/interview/stack/min-stack.htm) |
| Stack using two queues  | [Here](https://www.geeksforgeeks.org/implement-stack-using-queue/) |
| Stock span problem  | [Here](https://www.geeksforgeeks.org/the-stock-span-problem/) |