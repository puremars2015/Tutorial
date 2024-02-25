### 5. 輸入和輸出

在Python中，有多種方法可以實現數據的輸入和輸出。這不僅包括簡單的打印輸出，還包括格式化輸出以及讀寫文件中的數據。

#### 5.1 更華麗的輸出格式

Python提供了多種工具和技術，用於生成格式化的輸出，讓輸出更加易讀易懂。

##### 5.1.1 格式化的字串文本 (Formatted String Literals)

格式化的字符串字面量（也稱為f-strings）允許你在字符串前加上`f`或`F`，並在其中包含Python表達式的值。

```python
name = "Eric"
age = 74
print(f"Hello, {name}. You are {age}.")
```

##### 5.1.2 字串的 format() method

`format()`方法允許你進行複雜的變量替換和值格式化。

```python
print("Hello, {}. You are {}.".format(name, age))
```

你也可以指定替換的順序：

```python
print("Hello, {1}. You are {0}.".format(age, name))
```

##### 5.1.3 手動格式化字串

對於更複雜的格式化，你可以手動處理字符串。這包括使用切片和串接操作來創建和修改字符串。

##### 5.1.4 格式化字串的舊方法

在較老的Python代碼中，你可能會遇到使用`%`操作符的字符串格式化。雖然這種格式化方法仍然受到支持，但不推薦使用。

```python
print("Hello, %s. You are %s." % (name, age))
```

#### 5.2 讀寫檔案

Python對文件的讀寫操作同樣提供了豐富的API。

##### 5.2.1 檔案物件的 method

當你打開文件時，可以使用文件對象的方法來讀取或寫入數據。

- 使用`open()`函數打開文件，並返回一個文件對象。
- `read()`或`readlines()`方法可以用來讀取文件內容。
- `write()`方法用於將字符串寫入文件。

```python
with open('example.txt', 'r') as f:
    read_data = f.read()
# 確保文件被正確關閉
```

##### 5.2.2 使用 json 儲存結構化資料

`json`模組提供了一種很方便的方式來編碼和解碼JSON數據。你可以使用它來在Python字典和JSON格式之間進行轉換。

```python
import json
# 將Python對象編碼成JSON字符串
json_string = json.dumps([1, 'simple', 'list'])
# 將JSON字符串解碼為Python對象
json.loads(json_string)
```

使用這些技術，你可以有效地處理Python程序中的輸入和輸出操作，無論是簡單的文本數據還是複雜的結構化數據。