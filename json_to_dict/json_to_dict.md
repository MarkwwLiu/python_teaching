# 用 Python 讀取 JSON 檔案並轉換成字典型態

Python是一種功能豐富的程式語言，適用於多種應用領域。

在軟體開發中，我們經常需要處理資料，而JSON（JavaScript Object Notation）常被用作資料交換的格式，尤其是在網路應用程式中。

以下是一段使用Python語言編寫的簡潔程式碼，展示了如何讀取JSON檔案並將其內容轉換成Python字典（dictionary）型態。

```python
# json_to_dict.py

import os
import json

def PATH(p):
    return os.path.abspath(os.path.join(os.path.dirname(__file__), p))

def json_parser(raw_data):
    # json -> dict of python
    return json.loads(raw_data)

def get_json_to_dict_data():
    # 取得- json
    json_file_path = str(PATH('./test.json'))

    with open(json_file_path, "r") as read_package:
        raw_data = read_package.read()

    # 將 json 轉成 dict
    package_dict = json_parser(raw_data)

    return package_dict

get_json_file = get_json_to_dict_data()

print(get_json_file)
```

```json
# test.json

{
    "123": "tttt",
    "1123": [
        "123",
        "fffff"
    ],
    "fffff": "awinni12344%%^^",
    "kkkkffff": "\u4f60\u597d\u554a\uff01\uff01"
}
```

這個程式碼的主要目的是讀取名為"test.json"的JSON檔案，並將其內容轉換成Python中的字典型態。現在，讓我們一步一步來解釋這個程式碼的功能：

1. **`PATH(p)` 函數**

   - 這是一個輔助函數，用來取得指定檔案相對路徑。

   - 這對於確保我們可以在不同的環境中正確地取得檔案路徑很有用。

2. **`json_parser(raw_data)` 函數**

   - 這個函數的目的是將JSON格式的字串轉換成Python字典。

   - 在JSON資料的應用中，這是一個常見的操作，因為我們經常需要在Python中使用JSON格式的資料。

3. **`get_json_to_dict_data()` 函數**

   - 這是主要的功能函數，它結合了前兩個函數，實現了讀取JSON檔案並轉換成字典的整個流程。

   - 首先，透過`PATH`函數取得"test.json"的路徑，然後使用`with open`保證檔案在使用完畢後被正確關閉。

   - 接著，讀取JSON檔案的內容並使用`json_parser`函數將其轉換成Python字典。

   - 最後，將得到的字典存放在`package_dict`變數中。

4. **`print(get_json_file)`**

   - 最後，這一行印出了轉換後的JSON資料，讓開發者能夠檢查是否正確讀取並轉換。

總的來說，這個程式碼是一個簡單而實用的例子，展示了如何在Python中處理JSON檔案。這對於任何需要讀取和處理JSON格式資料的應用都是相當基礎且重要的。


### [返回首頁](../README.md)

#### 關於我的連結
- GitHub: https://github.com/MarkwwLiu
- Facebook: https://www.facebook.com/TestMrMark
- Linkedin: https://www.linkedin.com/in/%E7%B4%8B%E7%91%8B-%E5%8A%89-03356584/
- CakeResume: https://www.cakeresume.com/me/ak790718

##### link: https://github.com/MarkwwLiu/python_teaching/blob/main/json_to_dict/json_to_dict.md
