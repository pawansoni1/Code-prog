# Code-prog
Hello
Q.4 Write programs to implement Queue using an array and linked list.
 
# Queue implementation using an array

queue = []
MAX = 5

def enqueue(value):
    if len(queue) == MAX:
        print("Queue Overflow")
    else:
        queue.append(value)
        print(value, "inserted into queue")

def dequeue():
    if len(queue) == 0:
        print("Queue Underflow")
    else:
        print(queue.pop(0), "deleted from queue")

def display():
    if len(queue) == 0:
        print("Queue is empty")
    else:
        print("Queue elements:", queue)


enqueue(10)
enqueue(20)
enqueue(30)

display()

dequeue()
display()

Output: 10 inserted into queue 
20 inserted into queue 
30 inserted into queue 
Queue elements: [10, 20, 30] 
10 deleted from queue 
Queue elements: [20, 30]

# Queue implementation using a linked list

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None


class Queue:
    def __init__(self):
        self.front = None
        self.rear = None

    def enqueue(self, value):
        new_node = Node(value)

        if self.rear is None:
            self.front = self.rear = new_node
        else:
            self.rear.next = new_node
            self.rear = new_node

        print(value, "inserted into queue")

    def dequeue(self):
        if self.front is None:
            print("Queue Underflow")
        else:
            print(self.front.data, "deleted from queue")
            self.front = self.front.next

            if self.front is None:
                self.rear = None

    def display(self):
        if self.front is None:
            print("Queue is empty")
        else:
            temp = self.front
            print("Queue elements:", end=" ")

            while temp:
                print(temp.data, end=" ")
                temp = temp.next

            print()


q = Queue()

q.enqueue(10)
q.enqueue(20)
q.enqueue(30)

q.display()

q.dequeue()
q.display()

Output: 10 inserted into queue 
20 inserted into queue 
30 inserted into queue
