### 6. 錯誤和例外

在Python中，錯誤和例外是程式執行時遇到問題的兩種主要形式。理解它們並學會如何處理是寫出穩健代碼的關鍵。

#### 6.1 語法錯誤 (Syntax Error)

語法錯誤，也稱為解析錯誤，是學習Python時最常遇到的錯誤類型。如果Python代碼的語法不正確，解釋器就會拋出語法錯誤。

```python
# 錯誤示例
while True print('Hello world')
```

#### 6.2 例外 (Exception)

即使Python代碼的語法是正確的，在執行時也可能發生錯誤，這些錯誤被稱為“例外”。多數例外都不會被程序處理，並以錯誤信息的形式顯示。

```python
# 錯誤示例
1 / 0
```

#### 6.3 處理例外

你可以使用`try`和`except`語句來處理可能引發的例外，以防止例外中斷你的程序。

```python
try:
    x = 1 / 0
except ZeroDivisionError:
    print("Cannot divide by zero.")
```

#### 6.4 引發例外

使用`raise`語句來引發指定的例外。你可以定義例外的類型和提供錯誤信息。

```python
raise ValueError("A value error happened.")
```

#### 6.5 例外鏈接 (Exception Chaining)

在Python中，你可以使用`from`關鍵字來鏈接例外，以顯示原始例外的直接因果關係。

```python
try:
    raise KeyError
except KeyError as e:
    raise ValueError from e
```

#### 6.6 使用者自定的例外

通過繼承`Exception`類，你可以創建自定義的例外。

```python
class MyError(Exception):
    pass
```

#### 6.7 定義清理動作

使用`finally`語句來定義無論是否發生例外都需要執行的清理動作。

```python
try:
    raise KeyboardInterrupt
finally:
    print('Goodbye, world!')
```

#### 6.8 預定義的清理動作

`with`語句允許對象實現正確的資源管理，如文件或網絡連接，確保使用後即被清理。

```python
with open("myfile.txt") as f:
    for line in f:
        print(line)
```

#### 6.9 引發及處理多個無關的例外

可以在一個`except`語句中處理多個例外類型，將它們作為元組列出。

```python
try:
    # your code here
except (RuntimeError, TypeError, NameError):
    pass
```

#### 6.10 用註解使例外更詳細

在引發或處理例外時，添加註解可以提供更多上下文，幫助其他開發者理解代碼的意圖。

這些概念和技巧幫助開發者更好地理解和控制程序中的錯誤和例外，從而提高代碼的穩定性和可靠性。