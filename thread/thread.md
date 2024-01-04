# Python ThreadPoolExecutor 的使用範例

Python 提供了 `concurrent.futures` 模組，其中的 `ThreadPoolExecutor` 是一個強大的工具，可用於實現並行執行多個任務。

以下是一個簡單的程式碼示例，演示了如何使用 `ThreadPoolExecutor` 並發地執行任務，以及使用 `as_completed` 和 `map` 方法獲取執行結果。

```python
from concurrent.futures import ThreadPoolExecutor, as_completed

def say_hello_to(name):
    return f'Hi, {name}'

names = ['Mark', 'Ben', 'Bill', 'Alex', 'Jenny', 'Joho']

# 使用 ThreadPoolExecutor 並發地執行 say_hello_to 函數
with ThreadPoolExecutor(max_workers=5) as executor:
    futures = [executor.submit(say_hello_to, n) for n in names]

    # 使用 as_completed 等待任務完成並獲取結果
    for future in as_completed(futures):
        print(future.result())

print("*" * 10)

def say_hello1_to(name):
    return f'Hi, {name}'

names1 = ['Mark', 'Ben', 'Bill', 'Alex', 'Jenny']

# 使用 ThreadPoolExecutor 的 map 方法簡化程式碼
with ThreadPoolExecutor(max_workers=4) as executor:
    results = executor.map(say_hello1_to, names1)

# 直接獲取執行結果並輸出
for i in results:
    print(i)
```

```bash
Hi, Mark
Hi, Joho
Hi, Alex
Hi, Ben
Hi, Bill
Hi, Jenny
**********
Hi, Mark
Hi, Ben
Hi, Bill
Hi, Alex
Hi, Jenny
```

這段程式碼首先定義了一個 `say_hello_to` 函數，該函數接受一個名字，並返回一個打招呼的字串。

接著，我們建立了一個名為 `names` 的名字清單，並使用 `ThreadPoolExecutor` 的 `submit` 方法以最多 5 個執行緒的方式並發地執行 `say_hello_to` 函數。

`as_completed` 方法用於等待任務完成，並按完成順序獲取結果。

接著，我們定義了另一個 `say_hello1_to` 函數和一個新的名字清單 `names1`。

這次我們使用 `ThreadPoolExecutor` 的 `map` 方法，它更為簡潔，直接返回執行結果。

最後，我們輸出了兩組任務的執行結果。

這個示例展示了如何有效地使用 `ThreadPoolExecutor` 進行並行任務處理，這對於需要處理大量任務的應用程式來說是一個實用且效率高的工具。

1. **`as_completed` 方法**

   - 在第一個方法中，我們使用 `executor.submit` 將任務提交給執行器，這返回了一個 `Future` 對象的清單，表示每個任務的未來結果。

   - 然後，我們使用 `as_completed` 方法等待這些 `Future` 對象完成，並按照完成的順序獲取結果。

   - `as_completed` 方法提供了更靈活的控制，可以即時獲取完成的任務結果。

2. **`map` 方法**

   - 在第二個方法中，我們使用 [`executor.map`](executor.map) 直接將函數應用於名字的清單，返回的結果是一個迭代器。

   - `map` 方法會按照輸入的順序返回執行結果，並且可以直接遍歷迭代器獲取結果。

   - `map` 方法簡化了程式碼，適合當你希望簡單地獲取所有結果而不需要即時掌握每個任務的完成狀態時使用。

總的來說，`as_completed` 提供更多的控制和即時性，而 `map` 提供了一種簡潔的方式來處理並行任務的結果。

選擇使用哪一種方法取決於你的需求和對結果掌握的時機。

在一般情況下，`map` 方法相對於 `as_completed` 可能會稍微更快。

這是因為 `map` 會按照任務的順序直接返回結果，而不需要即時等待其他尚未完成的任務。

相比之下，`as_completed` 方法提供了更多的即時性和控制，但這可能會帶來一些額外的開銷。

當你在迭代 `as_completed` 的 `Future` 對象時，它會立即返回已經完成的任務，而不需要等待其他尚未完成的任務。

這對於某些特定的使用情境可能更加有彈性，但在某些情況下可能會稍微減慢執行速度。

然而，這種差異通常是微小的，而實際的效能取決於很多因素，包括任務的性質、硬體性能、並行任務的數量等。

因此，建議在具體的使用情境中進行測試，以確定

哪種方法最適合你的需求。

### [返回首頁](../README.md)

#### 關於我的連結
- GitHub: https://github.com/MarkwwLiu
- Linkedin: https://www.linkedin.com/in/%E7%B4%8B%E7%91%8B-%E5%8A%89-03356584/
- CakeResume: https://www.cakeresume.com/me/ak790718

##### link: https://github.com/MarkwwLiu/python_teaching/blob/main/thread/thread.md
