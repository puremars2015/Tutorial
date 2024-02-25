

### 3. 資料結構

Python提供了多種強大的內建資料結構，如串列(list)、元組(tuple)、集合(set)和字典(dictionary)等，這些都是處理數據和進行數據結構操作的基礎。

#### 3.1 進一步了解 List（串列）

List是Python中最基本的資料結構之一，支持多種操作，包括但不限於索引、切片、添加和移除元素。

##### 3.1.1 將 List 作為 Stack（堆疊）使用

Stack是後進先出(LIFO)的結構，可以使用list來實現stack的功能，主要通過`append()`方法添加元素，通過`pop()`方法移除最後一個元素。

```python
stack = []
stack.append('a')
stack.append('b')
stack.append('c')
print(stack.pop())  # 移除並返回 'c'
print(stack)        # ['a', 'b']
```

##### 3.1.2 將 List 作為 Queue（佇列）使用

Queue是先進先出(FIFO)的結構。使用list直接實現queue可能效率不高，因為插入或刪除列表的開頭需要O(n)的時間。因此，建議使用`collections.deque`來實現高效的隊列。

```python
from collections import deque
queue = deque(["Eric", "John", "Michael"])
queue.append("Terry")           # Terry 進入隊列
print(queue.popleft())          # 'Eric' 離開隊列
print(queue)                    # deque(['John', 'Michael', 'Terry'])
```

##### 3.1.3 List Comprehensions（串列綜合運算）

List comprehensions提供了一種簡潔的方式來創建列表。

```python
squares = [x**2 for x in range(10)]
```

##### 3.1.4 巢狀的 List Comprehensions

可以在一個list comprehension中使用另一個list comprehension。

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9],
]
flattened = [num for row in matrix for num in row]
```

#### 3.2 del 陳述式

`del`陳述式用於刪除列表中的一個或多個元素。

```python
a = [-1, 1, 66.25, 333, 333, 1234.5]
del a[0]    # 刪除第一個元素
del a[2:4]  # 刪除從索引2到4（不包括4）的元素
```

#### 3.3 Tuples 和序列 (Sequences)

Tuple是不可變的序列，通過圓括號`()`構造。

```python
t = 12345, 54321, 'hello!'
```

#### 3.4 集合 (Sets)

Set是一個無序且元素唯一的容器。可以使用大括號`{}`或`set()`函式創建。

```python
basket = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}
print(basket)  # 顯示 {'orange', 'banana', 'pear', 'apple'}
```

#### 3.5 字典（Dictionary）

Dictionary是一種映射類型，使用鍵值對存儲。

```python
tel = {'jack': 4098, 'sape': 4139}
tel['guido'] = 4127
```

#### 3.6 迴圈技巧

在字典中迭代時，可以使用`items()`方法同時獲取鍵和值。

```python
for k, v in tel.items():
    print(k, v)
```

#### 3.7 深入了解條件 (Condition)

Python

支持條件表達式，可以在一行內完成if-else判斷。

```python
'a' if True else 'b'
```

#### 3.8 序列和其他資料類型之比較

Python允許對不同類型的序列進行比較操作，比較是字典式的，從第一個不同的元素開始決定結果。

這些資料結構的深入理解和應用是掌握Python的關鍵。通过實踐和探索，你將能夠更有效地使用這些工具來構建強大的程序。