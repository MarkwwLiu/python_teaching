# 探索 Python 迭代工具：itertools 與 more_itertools 實戰

在現代 Python 開發中，遇到複雜的迭代和數據處理時，強大的迭代工具是開發者的得力助手。

本文將深入介紹兩個常用的 Python 套件，itertools 和 more_itertools，並演示它們在實際應用中的優越性。

在開始之前，確保你已經安裝了 more_itertools 套件。你可以使用以下指令進行安裝：

```bash
$ pip3 install more_itertools
```

## itertools.cycle - 環狀走訪列表

```python
from itertools import cycle

count = 1
test_list = ['A', 'B', 'C', 'D']

for x in cycle(test_list):
    print(count, x)
    if count == 8:
        break
    count += 1
"""
1 A
2 B
3 C
4 D
5 A
6 B
7 C
8 D
"""
```

使用 `itertools.cycle`，我們實現了簡單而強大的環狀走訪列表功能，適用於需要無限循環某個列表的場景。

## itertools.filterfalse - 過濾符合條件的元素

```python
from itertools import filterfalse

input_users = [
    {'user_id': 1, 'habits': ['fishing', 'hiking']},
    {'user_id': 2, 'habits': []},
    {'user_id': 3, 'habits': ['drawing']},
    {'user_id': 4, 'habits': ['swimming']},
]

for user in filterfalse(lambda d: d['habits'], input_users):
    print(user)
"""
{'user_id': 2, 'habits': []}
"""
```

`itertools.filterfalse` 讓我們輕鬆地找出沒有特定習慣的使用者，這對於篩選資料非常有用。

## itertools.groupby - 依照條件進行分組

```python
from itertools import groupby

input_grouped = [
    {'id': 1, 'group': 'A'},
    {'id': 4, 'group': 'B'},
    {'id': 5, 'group': 'B'},
    {'id': 2, 'group': 'C'},
    {'id': 3, 'group': 'C'},
    {'id': 6, 'group': 'C'},
]

for group, members in groupby(input_grouped, lambda x: x['group']):
    print(group, list(members))

"""
A [{'id': 1, 'group': 'A'}]
B [{'id': 4, 'group': 'B'}, {'id': 5, 'group': 'B'}]
C [{'id': 2, 'group': 'C'}, {'id': 3, 'group': 'C'}, {'id': 6, 'group': 'C'}]
"""
```

`itertools.groupby` 使得我們能夠根據特定條件輕鬆地進行分組，這在數據分析和統計中非常實用。

## itertools.product - 計算多個可迭代對象的笛卡兒積

```python
from itertools import product

for x, y in product(range(1, 3), range(1, 3)):
    print(x, y, x*y)
"""
1 1 1
1 2 2
2 1 2
2 2 4
"""
```

`itertools.product` 簡化了多層迴圈的實現，特別適用於計算笛卡兒積的情境。

## more_itertools.flatten - 將多維陣列扁平化

```python
from more_itertools import flatten

input_nested = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

for value in flatten(input_nested):
    print(value)

"""
1
2
3
4
5
6
7
8
9
"""
```

`more_itertools.flatten` 讓我們輕鬆地將多維陣列扁平化，使得操作更加直觀。

## more_itertools.grouper - 分組並補滿長度

```python
from more_itertools import grouper

for group in grouper([1, 2, 3, 4, 5, 6, 7], 2):
    print(group)
"""
(1, 2)
(3, 4)
(5, 6)
(7, None)
"""
```

`more_itertools.grouper` 用於將資料進行分組，並可選擇是否補齊至指定長度，這在批次處理資料時非常有用。

## more_itertools.ichunked - 不補滿長度的分組

```python
from more_itertools import ichunked

for chunk in ichunked([1, 2, 3, 4, 5, 6, 7], 3):
    print(list(chunk))
"""
[1, 2, 3]
[4, 5, 6]
[7]
"""
```

`more_itertools.ichunked` 同樣用於分組，但不補齊至指定長度，更適合處理不規則長度的資料。

## more_itertools.chunked - 分組並補滿長度

```python
from more_itertools import chunked

iterable = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
print(list(chunked(iterable, 3)))

"""
[[0, 1, 2], [3, 4, 5], [6, 7, 8], [9]]
"""
```

`more_itertools.chunked` 也用於分組，並可選擇是否補

齊至指定長度，提供了與 `grouper` 相似的功能。

## more_itertools.divide - 分割資料為兩組

```python
from more_itertools import divide

group_1, group_2 = divide(2, [1, 2, 3, 4, 5, 6])
print(list(group_1))
print(list(group_2))

"""
[1, 2, 3]
[4, 5, 6]
"""
```

`more_itertools.divide` 將資料分為兩組，使得我們能夠更靈活地操作和處理資料。

itertools 和 more_itertools 提供了豐富的迭代工具，使得 Python 程式設計更加靈活和高效。

這些工具不僅減少了冗長的程式碼，還提供了許多方便實用的功能，使得開發者能夠更輕鬆地應對不同的資料處理場景。

掌握這些工具，將使你的程式碼更具可讀性、可維護性，同時提高開發效率。

無論是處理資料集合、進行統計分析還是進行批次處理，itertools 和 more_itertools 都是不可或缺的利器。

希望這篇文章能夠讓你更深入地了解這兩個強大的套件，並在實際應用中獲得更好的效果。

### [返回首頁](../README.md)

#### 關於我的連結
- GitHub: https://github.com/MarkwwLiu
- Facebook: https://www.facebook.com/TestMrMark
- Linkedin: https://www.linkedin.com/in/%E7%B4%8B%E7%91%8B-%E5%8A%89-03356584/
- CakeResume: https://www.cakeresume.com/me/ak790718

##### link: https://github.com/MarkwwLiu/python_teaching/blob/main/itertools/itertools.md
