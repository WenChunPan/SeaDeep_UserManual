<!-- 事前先進入虛擬環境 -->

# 環境安裝

需要先進入想使用的虛擬環境內再開始以下步驟：

**1. 安裝套件**

```
pip install mkdocs mkdocs-material
```

**2. 下載專案**

```
git clone https://github.com/WenChunPan/SeaDeep_UserManual.git
```

# 本地預覽

資料夾結構為
```
SeaDeep_UserManual-main/
  └── SeaDeep_UserManual-main/
        ├── mkdocs.yml
        ├── docs/
```

**1. 需要移動到專案資料夾（根目錄）**
```
cd SeaDeep_UserManual-main\SeaDeep_UserManual-main
```

**2. 在環境下於 `terminal` 輸入以下指令**
```
mkdocs serve
```
**3. 使用以下網址打開瀏覽器**

```
http://127.0.0.1:8000
```

# 部署到自己的 GitHub


**1. 初始化 Git**

在專案根目錄 `SeaDeep_UserManual-main` 資料夾執行 `git` 指令。

```
git init
git add .
git commit -m "first commit"
```


**2. 建立自己的 GitHub Repository**

在你的帳號建立一個新的倉庫，如：

```
https://github.com/你的帳號/倉庫名
```


**3. 連接遠端**

```
git branch -M main
git remote add origin https://github.com/你的帳號/倉庫名.git
```

**4. 推送到 GitHub**

```
git push -u origin main
```


**5. 等待 Git Actions 自動部署（CI/CD）**

`push` 後 ，`GitHub Actions` 會執行其中的 `deploy.yml`（CI/CD），將 `docs/` 內所有檔案自動部署成網站。


**6. 確認 GitHub Pages 設定**

進入 `GitHub repo`：`Settings` → `Pages`

確認設定如下：
* **Source**：選擇 `Deploy from a branch`
* **Branch**：選擇 `gh-pages`

幾分鐘後會出現公開網址，例如：`https://你的帳號.github.io/你的倉庫/`

![image](https://hackmd.io/_uploads/Sy58Iaj3gg.png)


**7. 完成部署**

此後只要修改` docs/` 裡的 Markdown 檔案並執行：
```
git add .
git commit -m "update docs"
git push
```

網站就會自動更新
