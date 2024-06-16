# ADTs

1.  A classic problem in computer science is the problem of implementing a queue using two stacks. Consider the following stack ADT interface:

    ```c
    // Creates a new empty stack
    Stack StackNew(void);
    
    // Pushes an item onto the stack
    void StackPush(Stack s, int item);
    
    // Pops an item from the stack and returns it
    // Assumes that the stack is not empty
    int StackPop(Stack s);
    
    // Returns the number of items on the stack
    int StackSize(Stack s);
    ```

    Use the stack ADT interface to complete the implementation of the queue ADT below:

    ```c
    #include "Stack.h"
    
    struct queue {
    	Stack s1;
    	Stack s2;
    };
    
    Queue QueueNew(void) {
    	Queue q = malloc(sizeof(struct queue));
    	q->s1 = StackNew();
    	q->s2 = StackNew();
    	return q;
    }
    
    void QueueEnqueue(Queue q, int item) {
    	// TODO
    }
    
    int QueueDequeue(Queue q) {
    	// TODO
    }
    ```