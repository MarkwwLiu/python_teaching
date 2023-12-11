# Python3 虛擬環境設定

### 簡介
學習如何在Python中建立並使用虛擬環境，以隔離專案的相依套件。

這確保了一個乾淨且獨立的環境，避免不同專案之間的衝突。

### 步驟

1. **打開終端機並進入專案目錄**
   - 打開終端機，進入你的Python專案目錄。

2. **建立新的虛擬環境**
   - 執行以下指令建立名為 `myenv` 的新虛擬環境：
     ```bash
     python3 -m venv myenv
     ```
   這將在當前目錄下建立一個名為 `myenv` 的虛擬環境。

   ![建立後產生的 'myenv' 資料夾](https://raw.githubusercontent.com/MarkwwLiu/python3_teacnihg/main/img/SCR-20231209-fkb-2.png)

3. **啟動虛擬環境**
   - 使用以下指令啟動虛擬環境：
     - 在 macOS 和 Linux:
       ```bash
       source myenv/bin/activate
       ```
   這將切換你的終端機至虛擬環境。

   ![進入到虛擬環境內](https://raw.githubusercontent.com/MarkwwLiu/python3_teacnihg/main/img/SCR-20231209-fmb-2.png)

4. **確認虛擬環境啟動**
   - 為了確認你在虛擬環境中，執行以下指令。由於虛擬環境是乾淨的，它不應顯示任何套件。
     ```bash
     pip3 freeze
     ```
   ![確認進入虛擬環境](https://raw.githubusercontent.com/MarkwwLiu/python3_teacnihg/main/img/SCR-20231209-fol-2.png)

5. **在虛擬環境中安裝套件**
   - 在虛擬環境中，使用以下類似的指令安裝套件：
     ```bash
     pip3 install requests
     ```
   ![安裝套件](https://raw.githubusercontent.com/MarkwwLiu/python3_teacnihg/main/img/SCR-20231209-fqd-2.png)
   ![確認安裝套件](https://raw.githubusercontent.com/MarkwwLiu/python3_teacnihg/main/img/SCR-20231209-frb-2.png)

6. **退出虛擬環境**
   - 使用以下指令退出虛擬環境：
     ```bash
     deactivate
     ```
   ![退出虛擬環境](https://raw.githubusercontent.com/MarkwwLiu/python3_teacnihg/main/img/SCR-20231209-fsu.png)

### 結論
透過這些步驟，你已成功在Python中建立並使用虛擬環境。

虛擬環境確保了專案的相依套件與系統的相依套件互相獨立，避免了不同專案之間的衝突。

### [返回首頁](../README.md)

#### 關於我的連結
- GitHub: https://github.com/MarkwwLiu
- Facebook: https://www.facebook.com/TestMrMark
- Linkedin: https://www.linkedin.com/in/%E7%B4%8B%E7%91%8B-%E5%8A%89-03356584/
- CakeResume: https://www.cakeresume.com/me/ak790718

##### link: https://github.com/MarkwwLiu/python_teaching/blob/main/env/env.md
