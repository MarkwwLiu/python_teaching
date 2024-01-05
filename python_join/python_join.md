# Python `join()` 方法多用途教學

在 Python 中，`join()` 方法是一個強大的工具，可用於不同情境下的字串連接。以下是各種使用情境的 `join()` 方法範例。

## 1. `join()` 方法概述

`join()` 方法用於將多個元素連接成字串，主要參數為分隔符號 (`sep`)。

```python
print(type(test_list))
```

### 參數說明

- `sep`: 分隔符號，可以為空。將要連接的元素使用 `sep` 作為分隔符號，生成一個新的字串。

## 2. `join()` 方法應用

### 2.1 串列（List）

```python
test_list = ['A', 'B', 'C']

print('-'.join(test_list))  # A-B-C
print('#'.join(test_list))  # A#B#C
print(' '.join(test_list))  # A B C
```

### 2.2 字串（Str）

```python
test_str = 'ABC'

print(''.join(test_str))    # ABC
print(':'.join(test_str))   # A:B:C
print('! '.join(test_str))  # A! B! C
```

### 2.3 元組（Tuple）

```python
test_tuple = ('A', 'B', 'C')

print(''.join(test_tuple))  # ABC
print(':'.join(test_tuple)) # A:B:C
print('$'.join(test_tuple)) # A$B$C
```

### 2.4 字典（Dict）

```python
test_dict = {'A': 1, 'B': 2, 'C': 3}

print(''.join(test_dict))  # ABC
print(':'.join(test_dict)) # A:B:C
print('*'.join(test_dict)) # A*B*C
```

## 3. `os.path.join` 方法取得路徑

### 3.1 資料夾絕對路徑

```python
import os

path = "/Users/mark"
print(os.path.join(path, "Desktop", "TEST_Folder", "")) # /Users/mark/Desktop/TEST_Folder/
print(os.path.join(path, "Desktop", "TEST_Folder"))     # /Users/mark/Desktop/TEST_Folder
```

### 3.2 檔案絕對路徑

```python
import os

path = "/User/mark"
print(os.path.join(path, "User/Desktop", "file.txt"))
print(os.path.join(path, "User", "Desktop", "file.txt"))
# 兩者結果都是 /User/mark/User/Desktop/file.txt
```

## 4. `join()` 搭配 `if`

`join()` 搭配 `if` 可以過濾掉不需要的元素。

```python
test_list = ['Hi', '', 'Mark', 'OK']

print(' '.join(t for t in test_list if t))  # Hi Mark OK

test_list = ['Hi ', '', ' Ken', ' ', 'Fail']
print(' '.join(t.strip() for t in test_list if t.strip()))  # Hi Ken Fail
```

這樣的處理方式可以有效地清理多餘的空白元素，達到更清晰的字串連接效果。

藉由這些範例，你可以更靈活地使用 `join()` 方法，應用在不同的情境中。

### [返回首頁](../README.md)

#### 關於我的連結
- GitHub: https://github.com/MarkwwLiu
- Linkedin: https://www.linkedin.com/in/%E7%B4%8B%E7%91%8B-%E5%8A%89-03356584/
- CakeResume: https://www.cakeresume.com/me/ak790718

##### link: https://github.com/MarkwwLiu/python_teaching/blob/main/python_join/python_join.md
