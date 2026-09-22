# 3.-delete_by_value.py
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None


class LinkedList:
    def __init__(self):
        self.head = None

    def insert_end(self, data):
        new_node = Node(data)

        if self.head is None:
            self.head = new_node
            return

        current = self.head

        while current.next:
            current = current.next

        current.next = new_node

    def delete_by_value(self, value):
        if self.head is None:
            print("List is empty")
            return

        if self.head.data == value:
            self.head = self.head.next
            return

        current = self.head

        while current.next:
            if current.next.data == value:
                current.next = current.next.next
                return

            current = current.next

        print("Value not found")

    def display(self):
        current = self.head

        while current:
            print(current.data, end=" -> ")
            current = current.next

        print("None")


ll = LinkedList()

ll.insert_end(10)
ll.insert_end(20)
ll.insert_end(30)
ll.insert_end(40)

print("Before deletion:")
ll.display()

ll.delete_by_value(30)

print("After deleting 30:")
ll.display()
