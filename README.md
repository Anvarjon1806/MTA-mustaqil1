# 🌳 Daraxt (Tree) Ma'lumotlar Tuzilmasi

**Daraxt (tree)** — bu ma'lumotlar tuzilmasining ierarxik (pogʻonali) shakli bo‘lib, tugunlar (nodes) orqali tashkil etiladi. Har bir tugun maʼlumot va boshqa tugunlarga ishoralarni saqlaydi.

---

## 🔹 Asosiy Tushunchalar

- **Tugun (Node)**: Daraxtdagi har bir element.
- **Ildiz (Root)**: Daraxtning boshlangʻich tuguni.
- **Ota (Parent)**: Tugunning yuqoridagi tuguni.
- **Bola (Child)**: Tugunning pastidagi tugunlar.
- **Barg (Leaf)**: Bolalari bo‘lmagan tugun.
- **Sath (Level)**: Tugunning ildizdan boshlab joylashgan pog‘onasi.
- **Chuqurlik (Depth)**: Tugunning ildizdan bo‘lgan masofasi.
- **Balandlik (Height)**: Daraxtning eng chuqur tuguniga qadar bo‘lgan sathlar soni.

---

## 🌲 Daraxt Turlari

| Turi | Tavsifi |
|------|---------|
| **Binary Tree** | Har tugun eng ko‘pi bilan 2 ta bola tugunga ega |
| **Binary Search Tree (BST)** | Chap bola < ota < o‘ng bola |
| **Balanced Tree** | Tugunlar iloji boricha muvozanatli joylashgan |
| **AVL Tree** | O‘z-o‘zini balanslovchi BST |
| **B-Tree / B+ Tree** | Fayl tizimi va DBMS da ishlatiladi (ko‘p bolali) |

---

## 🔁 Daraxtni Aylanib Chiqish Usullari (Traversal)

1. **Preorder** – `Root → Left → Right`
2. **Inorder** – `Left → Root → Right` *(BST da tartiblangan chiqadi)*
3. **Postorder** – `Left → Right → Root`
4. **Level-order** – Sathma-sath aylanadi (queue yordamida)

---

## 🧠 Misol: Inorder Traversal (Python)

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None

def inorder(root):
    if root:
        inorder(root.left)
        print(root.data, end=' ')
        inorder(root.right)

# Daraxt yaratish
root = Node(10)
root.left = Node(5)
root.right = Node(15)

# Traversal
inorder(root)
