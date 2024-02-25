### 2. 深入了解流程控制

在Python中，流程控制是通過條件語句、循環及函式來實現的，這些都是程式設計中非常重要的元素。讓我們進一步探索這些概念。

#### 2.1 if 陳述式

`if`語句用於根據一個或多個條件執行不同的代碼塊。它可以單獨使用，也可以與`elif`（else if的縮寫）和`else`結合使用來覆蓋更多的條件分支。

```python
x = 10
if x > 5:
    print("x is greater than 5")
elif x == 5:
    print("x is exactly 5")
else:
    print("x is less than 5")
```

#### 2.2 for 陳述式

`for`循環用於遍歷序列（如列表或字符串）中的每個元素，對每個元素執行代碼塊。

```python
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)
```

#### 2.3 range() 函式

`range()`函式生成一個數字序列，常用於`for`循環中。

```python
for i in range(5):  # 生成從0到4的數字
    print(i)
```

#### 2.4 迴圈內的 break 和 continue 陳述式及 else 子句

- `break`用於提前退出循環。
- `continue`跳過當前迴圈的剩餘部分，直接開始下一次迴圈。
- 循環可以有一個`else`子句；它在迴圈正常結束時執行，但循環被`break`終止時不執行。

```python
for i in range(5):
    if i == 3:
        break
    print(i)
else:
    print("Loop finished")
```

#### 2.5 pass 陳述式

`pass`是一個空操作語句，當語法上需要一個語句但程序不需要任何行動時，可以使用`pass`。

```python
if x > 0:
    pass  # TODO: add logic here
```

#### 2.6 match 陳述式

`match`語句（Python 3.10+）提供了模式匹配的功能，類似於其他語言中的switch或case語句。

```python
command = "hello"
match command:
    case "hello":
        print("Hello to you too!")
    case "bye":
        print("Goodbye!")
    case _:
        print("Unknown command")
```

#### 2.7 定義函式 (function)

函式是通過`def`關鍵字定義的，它封裝了可重用的代碼塊。

```python
def greet(name):
    print(f"Hello, {name}!")
```

#### 2.8 深入了解函式定義

##### 2.8.1 預設引數值

函式參數可以有預設值，在呼叫函式時如果未提供參數，則使用預設值。

```python
def greet(name, message="Hello"):
    print(f"{message}, {name}!")
```

##### 2.8.2 關鍵字引數

呼叫函式時可以使用參數名稱來指定參數，這稱為關鍵字引數。

```python
greet(message="Hi", name="John")  # Hi, John!
```

##### 2.8.3 特殊參數

###### 2.8.3.1 位置或關鍵字引數 (Positional-or-Keyword Arguments)

這是預設的參數類型，意味著參數可以通過位置或關鍵字來指定。

###### 2.8.3.2 僅限位置參數 (Positional-Only Parameters)

使用`/`來標示參數僅可通過位置指定。

```python
def func(a, b, /, c):
    print(a, b, c)
```

###### 2.8.3.3 僅限關鍵字引數 (Keyword-Only Arguments)

使用`*`來標示參數僅可通過關鍵字指定。

```python
def func(*, a, b):
    print(a, b)
```

###### 2.8.3.4 函式範例

結合使用上述特殊參數。

###### 2.8.3.5 回顧

這些特性讓函式的接口更加清晰、靈活。

##### 2.8.4 任意引數列表 (Arbitrary Argument Lists)

使用`*args`來接受任意數量的位置參數，使用`**kwargs`來接受任意數量的關鍵字參數。

```python
def func(*args, **kwargs):
    print(args)  # 位置參數
    print(kwargs)  # 關鍵字參數
```

##### 2.8.5 拆解引數列表（Unpacking Argument Lists）

使用`*`來拆解列表或元組，使用`**`來拆解字典，以在函式呼叫中傳遞參數。

##### 2.8.6 Lambda 運算式

Lambda函式是一種匿名函式，用於創建小型函式

。

```python
add = lambda x, y: x + y
print(add(5, 3))
```

##### 2.8.7 說明文件字串 (Documentation Strings)

函式可以有一個說明字符串（docstring），用於解釋函式的作用。

```python
def my_function():
    """This is a docstring."""
    pass
```

##### 2.8.8 函式註釋 (Function Annotations)

函式參數和返回值可以有註釋，用於說明類型。

```python
def greet(name: str) -> None:
    print(f"Hello, {name}!")
```


#### 2.9 程式碼風格 (Coding Style)

Python有一套風格指南PEP 8，建議遵循以保持代碼的清晰和一致性。重點包括使用4個空格進行縮進、限制行長、使用空行分隔函式和類等。
