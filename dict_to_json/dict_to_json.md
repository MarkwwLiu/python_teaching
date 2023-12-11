# 如何使用 Python 將字典轉換為 JSON 並儲存至檔案

在軟體開發中，我們經常需要將數據以結構化的格式保存，其中 JSON（JavaScript Object Notation）是一種常見的選擇。

透過 Python，我們可以輕鬆將字典轉換為 JSON 並將其儲存為一個檔案。

## 步驟 1: 匯入必要的模組

首先，我們需要匯入必要的模組，這裡使用 `datetime`、`json` 和 `os`：

```python
from datetime import datetime
import json
import os
```

## 步驟 2: 準備一個字典數據

我們準備一個示例字典數據，這裡稱為 `example_dict`：

```python
example_dict = {
    "123": "tttt",
    "1123": ["123", "fffff"],
    "fffff": "d12c%%^^",
    "c": "你好啊！！"
}
```

## 步驟 3: 定義主要函數

現在，我們定義一個名為 `main` 的函數，用於儲存字典數據為 JSON 檔案：

```python
def main(save_json_path, save_json_name, data_dict):
    """
    :param save_json_path: 你要儲存 JSON 的位置
    :param save_json_name: 你要將字典存入到 JSON 的檔案名稱叫做什麼
    :param data_dict: 字典資料
    """
    now_time = datetime.now().strftime("%Y-%m-%d %H:%M:%S")

    with open(save_json_path + save_json_name + ".json", 'w') as json_file:
        json.dump(data_dict, json_file)
    print("[%s] JSON 檔案儲存至: %s" % (now_time, save_json_path + save_json_name + ".json"))

# 使用示例字典進行函數調用
main(save_json_path=os.getcwd() + '/', save_json_name='test', data_dict=example_dict)
```

## 步驟 4: 解釋主要函數

- `save_json_path`：指定 JSON 檔案的儲存路徑，這裡使用 `os.getcwd()` 獲取當前工作目錄。

- `save_json_name`：指定 JSON 檔案的名稱，這裡為 `test`。

- `data_dict`：傳入我們想要儲存為 JSON 的字典數據。

## 步驟 5: 實際運行

運行這個腳本，將會生成一個名為 `test.json` 的 JSON 檔案，其中包含了我們提供的字典數據。

這是一個簡單而有效的方法，可以方便地將 Python 字典數據轉換為 JSON 並儲存至檔案。

這在數據傳輸和儲存方面都很有用，特別是在與其他應用程序交互時。

### [返回首頁](../README.md)

#### 關於我的連結
- GitHub: https://github.com/MarkwwLiu
- Facebook: https://www.facebook.com/TestMrMark
- Linkedin: https://www.linkedin.com/in/%E7%B4%8B%E7%91%8B-%E5%8A%89-03356584/
- CakeResume: https://www.cakeresume.com/me/ak790718

##### link: https://github.com/MarkwwLiu/python_teaching/blob/main/dict_to_json/dict_to_json.md
