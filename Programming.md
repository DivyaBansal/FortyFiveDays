
Dynamic programming;
- Optimal substructure
- Overlapping subproblems

Mixin programming: is a style of software development, in which units of functionality are created in a class and then mixed in with other classes. A mixin class acts as the parent class, containing the desired functionality.

A shallow copy doesn't create a copy of nested objects, instead it just copies the reference of nested objects.

Stack: LIFO 
insertion/deletion only at one end (the top)
```
def push(self, item):
		self.items.append(item)
def pop(self):
	self.items.pop()
```
Queue: FIFO
addition at the rear end, removal at the front
```
def enqueue(self, item):
		self.items.insert(0, item)
def dequeue():
	return self.items.pop()
```
Priority Queue:
Like queue as the front element is removed first but the order of elements in the queue is determined by their priority. 
"min heap": the smallest key is always at the front - "max heap": in which the largest key value is always at the front

Traversals:
preorder: root, left, right
inorder: left, root, right
postorder: left , right, root