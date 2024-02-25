### 9. Python 標準函式庫概覽——第二部份

這部分將深入探討Python標準庫中的進階功能，包括數據格式化、模板化、二進制數據處理、多執行緒、日誌記錄等。

#### 9.1 輸出格式化 (Output Formatting)

Python提供了多種方式來格式化輸出，包括舊式的`%`格式化、`str.format()`方法，以及f-string。

**Sample Code**:
```python
name = "World"
print(f"Hello, {name}!")  # 使用f-string
```

#### 9.2 模板化 (Templating)

`string`模組中的`Template`類提供了一種更新字符串的簡單機制，這對於從外部來源動態生成文本非常有用。

**Sample Code**:
```python
from string import Template
t = Template('${name} owes me $${amount}')
print(t.substitute(name='Alice', amount=100))
```

#### 9.3 二進制資料記錄編排 (Binary Data Record Layouts)

`struct`模組提供了`pack()`和`unpack()`函數，用於處理存儲在字符串中的固定大小的二進制數據記錄。

**Sample Code**:
```python
from struct import pack, unpack
packed_data = pack('i4sh', 7, b'foo', 8)
print(unpack('i4sh', packed_data))
```

#### 9.4 多執行緒 (Multi-threading)

`threading`模組允許你創建和管理獨立的線程，每個線程執行不同的任務。

**Sample Code**:
```python
import threading

def worker():
    """Thread worker function"""
    print('Worker')

threads = []
for i in range(5):
    t = threading.Thread(target=worker)
    threads.append(t)
    t.start()
```

#### 9.5 日誌記錄 (Logging)

`logging`模組提供了一個靈活的記錄事件、錯誤、警告等信息的機制。

**Sample Code**:
```python
import logging
logging.basicConfig(level=logging.INFO)
logging.info('This is an info message')
```

#### 9.6 弱引用 (Weak References)

`weakref`模組允許Python程序員創建對對象的弱引用，這樣可以在不防止對象被自動回收的情況下引用對象。

**Sample Code**:
```python
import weakref

class MyClass:
    pass

obj = MyClass()
r = weakref.ref(obj)

print(r())  # 獲取對象，如果對象還活著的話
```

#### 9.7 使用於 List 的工具

`array`模組提供了一種array類型，這是一種比Python的list更有效的存儲數字數據的方式。

**Sample Code**:
```python
from array import array
a = array('i', [1, 2, 3, 4, 5])
print(a)
```

#### 9.8 十進制 (Decimal) 浮點數運算

`decimal`模組提供了`Decimal`數據類型用於十進制浮點運算。這對於需要高精度計算的金融應用程序特別有用。

**Sample Code**:
```python
from decimal import Decimal

result = Decimal('0.1') + Decimal('0.2')
print(result)  # 正確處理了浮點數精度問題
```

這些進階特性和模組擴展了Python的功能，使其成為一個更強大、更靈活的編程語言。