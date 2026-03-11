# Tree-Search-program-39


class Node:
    def __init__(self, key, name):
        self.key = key
        self.name = name
        self.left = None
        self.right = None

def insert(root,key,name):
    if not root:
        return Node(key,name)
    if key < root.key:
        root.left = insert(root.left,key,name)
    else:
        root.right = insert(root.right,key,name)
    return root

def search(root,key):
    if not root:
        return None
    if root.key == key:
        return root
    elif key < root.key:
        return search(root.left,key)
    else:
        return search(root.right,key)

root = None
root = insert(root,101,"Alice")
root = insert(root,102,"Bob")
root = insert(root,103,"Carol")

emp = search(root,102)
print(f"Employee found: {emp.name}" if emp else "Employee not found")



Employee found: Bob
