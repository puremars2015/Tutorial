### 8. Python 標準函式庫概覽

Python 的標準函式庫提供了豐富的模組和函數，支持各種日常編程任務。從檔案處理到網路通訊，再到日期和時間操作，這些工具都是現成可用的。

#### 8.1 作業系統介面

`os` 模組提供了許多與操作系統交互的函數。

**Sample Code**:
```python
import os
print(os.getcwd())  # 顯示當前的工作目錄
```

#### 8.2 檔案之萬用字元 (File Wildcards)

`glob` 模組提供了一個函數用於從目錄通配符搜索中生成文件列表。

**Sample Code**:
```python
import glob
print(glob.glob('*.py'))  # 列出所有的 .py 檔案
```

#### 8.3 命令列引數

`sys` 模組的 `argv` 屬性可用於獲取命令行參數。

**Sample Code**:
```python
import sys
print(sys.argv)  # 命令行參數列表，argv[0] 是腳本名稱
```

#### 8.4 錯誤輸出重新導向與程式終止

`sys` 模組同樣提供了標準輸入、標準輸出和標準錯誤流的對象。

**Sample Code**:
```python
sys.stderr.write('Warning, log file not found starting a new one\n')
```

#### 8.5 字串樣式比對

`re` 模組支援正則表達式，用於各種字符串搜尋和替換任務。

**Sample Code**:
```python
import re
print(re.findall(r'\bf[a-z]*', 'which foot or hand fell fastest'))
```

#### 8.6 數學相關

`math` 模組提供了浮點數學運算函數；`random` 提供了生成隨機數的工具。

**Sample Code**:
```python
import math
print(math.cos(math.pi / 4))
```

```python
import random
print(random.choice(['apple', 'pear', 'banana']))
```

#### 8.7 網路存取

`urllib` 模組可以用於處理從 URL 讀取數據。

**Sample Code**:
```python
from urllib.request import urlopen
with urlopen('http://tycho.usno.navy.mil/cgi-bin/timer.pl') as response:
    for line in response:
        line = line.decode('utf-8')  # Decoding the binary data to text.
        if 'EST' in line or 'EDT' in line:  # look for Eastern Time
            print(line)
```

#### 8.8 日期與時間

`datetime` 模組提供了日期和時間處理的類和函數。

**Sample Code**:
```python
from datetime import date
now = date.today()
print(now)
```

#### 8.9 資料壓縮

`zlib`, `gzip`, `bz2`, `lzma` 模組支援常見的數據壓縮和解壓縮。

**Sample Code**:
```python
import zlib
s = b'witch which has which witches wrist watch'
print(len(s))
t = zlib.compress(s)
print(len(t))
```

#### 8.10 效能量測

`timeit` 模組可以測量小段代碼的執行時間。

**Sample Code**:
```python
from timeit import Timer
print(Timer('t=a; a=b; b=t', 'a=1; b=2').timeit())
```

#### 8.11 品質控管

`doctest` 和 `unittest` 模組支援開發者進行代碼的測試。

**Sample Code**:
```python
def average(values):
    """Computes the arithmetic mean of a list of numbers.
    
    >>> print(average([20, 30, 70]))
    40.0
    """
    return sum(values) / len(values)

import doctest
doctest.testmod()   #

 自動驗證嵌入測試
```

#### 8.12 標準模組庫

Python 的標準庫非常廣泛，從文本處理到網路協議，幾乎無所不包。

這些標準庫的概覽和示例代碼提供了一個快速開始的指南，幫助開發者有效利用 Python 豐富的標準函式庫進行開發。