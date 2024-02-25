### 10. 虛擬環境與套件

虛擬環境和套件管理是Python開發中的重要概念，它們幫助開發者在隔離的環境中安裝和管理依賴，從而避免版本衝突並確保項目的可重現性。

#### 10.1 簡介

虛擬環境是一個獨立的目錄樹，包含一個Python安裝以及多個額外套件。這使得你可以在不影響全局安裝的情況下，為不同項目安裝不同版本的套件。

#### 10.2 建立虛擬環境

你可以使用`venv`模塊來創建一個虛擬環境。這個模塊是Python 3.3及以後版本的一部分。

**Sample Code**:
```bash
# 在當前目錄下創建一個名為venv的虛擬環境
python3 -m venv venv

# 激活虛擬環境
# 在Windows上:
venv\Scripts\activate
# 在Unix或macOS上:
source venv/bin/activate
```

一旦虛擬環境被激活，你就可以在這個環境中安裝和使用套件，而不會影響到其他項目或是系統級的Python安裝。

#### 10.3 用 pip 管理套件

`pip`是Python的套件安裝器，允許你安裝、升級和移除套件。在激活的虛擬環境中使用pip，將僅影響該環境。

**Sample Code**:
```bash
# 安裝一個套件
pip install requests

# 列出已安裝的套件
pip list

# 移除一個套件
pip uninstall requests
```

使用虛擬環境和pip，你可以為每個項目創建一個乾淨且獨立的開發環境，這對於管理項目依賴和避免版本衝突至關重要。