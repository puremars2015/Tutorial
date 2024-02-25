### 7. Class（類別）

Python 的類別是對象導向編程的核心，提供了一種組織代碼和數據的方法，使得它們易於重用和擴展。

#### 7.1 關於名稱與物件的一段話

在 Python 中，名稱是對象的引用。這意味著當你創建一個變量時，你創建了一個對象的引用，而不是該對象本身。

**Sample Code**:
```python
a = 'Hello'  # 'a' 是對字符串對象 'Hello' 的引用
b = a        # 'b' 也成為對相同字符串對象的引用
```

#### 7.2 Python 作用域 (Scope) 及命名空間 (Namespace)

命名空間是從名稱到對象的映射。作用域決定了命名空間中名稱的可見性。

##### 7.2.1 作用域和命名空間的範例

每個函數調用創建一個新的局部命名空間，而模塊和類定義則在其自己的命名空間中操作。

**Sample Code**:
```python
def scope_test():
    def do_local():
        spam = "local spam"

    def do_nonlocal():
        nonlocal spam
        spam = "nonlocal spam"

    def do_global():
        global spam
        spam = "global spam"

    spam = "test spam"
    do_local()
    print("After local assignment:", spam)
    do_nonlocal()
    print("After nonlocal assignment:", spam)
    do_global()
    print("After global assignment:", spam)

scope_test()
print("In global scope:", spam)
```

#### 7.3 初見 class

類別允許我們定義自己的數據類型。

##### 7.3.1 Class definition（類別定義）語法

**Sample Code**:
```python
class MyClass:
    """A simple example class"""
    i = 12345

    def f(self):
        return 'hello world'
```

##### 7.3.2 Class 物件

創建類後，可以使用類來創建新的實例對象。

**Sample Code**:
```python
x = MyClass()
```

##### 7.3.3 實例物件

每個類實例都可以擁有自己的屬性和方法。

**Sample Code**:
```python
class Complex:
    def __init__(self, realpart, imagpart):
        self.r = realpart
        self.i = imagpart

x = Complex(3.0, -4.5)
x.r, x.i  # 返回 (3.0, -4.5)
```

##### 7.3.4 Method 物件

方法是屬於對象的函數。

**Sample Code**:
```python
class MyClass:
    def f(self):
        return 'hello world'
    
# 方法的調用
obj = MyClass()
print(obj.f())  # 輸出: hello world
```

##### 7.3.5 Class 及實例變數

類變數是共享的，它們可以被類的所有實例訪問。實例變數是每個對象的獨有數據。

**Sample Code**:
```python
class Dog:

    kind = 'canine'         # class variable shared by all instances

    def __init__(self, name):
        self.name = name    # instance variable unique to each instance

d = Dog('Fido')
e = Dog('Buddy')
d.kind                  # shared by all dogs
e.kind                  # shared by all dogs
d.name                  # unique to d
e.name                  # unique to e
```

#### 7.4 隨意的備註

類內部的命名應遵循 Python 的命名慣例，以避免與內置名稱衝突或引起混淆。

#### 7.5 繼

承 (Inheritance)

繼承允許我們定義一個繼承另一個類的所有屬性和方法的新類。

##### 7.5.1 多重繼承

Python 支持多重繼承，允許一個類繼承多個基類。

**Sample Code**:
```python
class Base1:
    pass

class Base2:
    pass

class MultiDerived(Base1, Base2):
    pass
```

#### 7.6 私有變數

以兩個下劃線開頭的變數名表示私有變數，只能在類內部訪問。

**Sample Code**:
```python
class MyClass:
    __private_variable = 0

    def __private_method(self):
        return 'This is private'
```

#### 7.7 補充說明

類屬性與方法的詳細使用，包括特殊方法如`__init__`（構造器）和`__str__`（字符串表示）等，應深入學習以充分利用類的功能。

#### 7.8 疊代器 (Iterator)

疊代器允許對象在一系列值上進行迭代。

**Sample Code**:
```python
class Reverse:
    """Iterator for looping over a sequence backwards."""
    def __init__(self, data):
        self.data = data
        self.index = len(data)

    def __iter__(self):
        return self

    def __next__(self):
        if self.index == 0:
            raise StopIteration
        self.index = self.index - 1
        return self.data[self.index]

# 使用
rev = Reverse('spam')
for char in rev:
    print(char)
```

#### 7.9 產生器 (Generator)

產生器是簡單而強大的工具，用於創建迭代器。它們是通過簡單的函數來寫的，使用`yield`語句。

**Sample Code**:
```python
def reverse(data):
    for index in range(len(data)-1, -1, -1):
        yield data[index]

# 使用
for char in reverse('golf'):
    print(char)
```

#### 7.10 產生器運算式

產生器運算式是理解和實現簡潔的生成器的一種方式，類似於列表推導但用於生成器。

**Sample Code**:
```python
gen_expr = (x * x for x in range(10))
for x in gen_expr:
    print(x)
```

這些基礎概念和範例代碼提供了對 Python 類別的初步了解，涵蓋從基礎到一些進階特性的使用。深入學習這些概念將有助於開發更復雜、高效和可重用的代碼結構。