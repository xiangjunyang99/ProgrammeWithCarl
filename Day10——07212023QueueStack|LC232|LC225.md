** To Do List **
- Queue and Stack
- LeetCode232 - Implement Queue using Stacks
- LeetCode225 - Implement Stack using Queues



## LeetCode232 - Implement Queue using Stacks

    def __init__(self):
        self.stack_in = []
        self.stack_out = []

    def push(self, x: int) -> None:
        self.stack_in.append(x)

    def pop(self) -> int:
        if self.empty():
            return None
        
        if self.stack_out:
            return self.stack_out.pop()
        else:
            for i in range(len(self.stack_in)):
                self.stack_out.append(self.stack_in.pop())
            return self.stack_out.pop() 

    def peek(self) -> int:
        ans = self.pop()
        self.stack_out.append(ans)
        return ans

    def empty(self) -> bool:
        return not(self.stack_in or self.stack_out)

- LeetCode 232 asks us to use two stacks to realize a queue structure.
- Typically, a queue could push(add an element to the structure), peek(take a look at the top element), pop(take out the first element) and empty(pop out all elements in the structure)
- 


## LeetCode225 - Implement Stack using Queues
    def __init__(self):
        self.queue_in = deque()
        self.queue_out = deque()

    def push(self, x: int) -> None:
        self.queue_in.append(x)


    def pop(self) -> int:
        if self.empty():
            return None
        for i in range(len(self.queue_in)-1):
            self.queue_out.append(self.queue_in.popleft())
        self.queue_in,self.queue_out = self.queue_out, self.queue_in
        return self.queue_out.popleft()

    def top(self) -> int:
        if self.empty():
            return None
        return self.queue_in[-1]


    def empty(self) -> bool:
        return len(self.queue_in)==0

- We are only allowed to use two queues to realize a stack structure.
- All the functions of a normal stack (push, top, pop, and empty).

