# 環境設定

## 1. 移動mini.exe

1. 打開 「 SeaDeep-mini-sample-main 」 資料夾
2. 進入 「 bin 」 資料夾
3. 進入 「 windows 」 資料夾
4. 複製mini.exe
5. 放至與Python主程式執行檔（train.py）相同的資料夾內

<figure><img src="../../.gitbook/assets/image (201).png" alt=""><figcaption><p>移動mini.exe</p></figcaption></figure>

## 2. 移動其他3個檔案

1. 打開 「 quick\_start 」 資料夾
2. 複製 「 mini\_sdk 」 資料夾與 「 mini.yaml 」 、 「 infer.py 」 2個檔案
3. 放至與Python主程式執行檔（train.py）相同的資料夾內

<figure><img src="../../.gitbook/assets/image (202).png" alt=""><figcaption></figcaption></figure>

## 3. 設定mini.yaml檔

1. 打開移動後的 「 mini.yaml 」 檔
2. 設定以下參數：

* <mark style="color:blue;">**name**</mark>：此核心名稱。
* <mark style="color:blue;">**token**</mark>：此用戶身分授權。
* <mark style="color:blue;">**worker**</mark>：此核心可以同時執行的任務數量。
* <mark style="color:blue;">**public：false**</mark>：是否將此核心對其他用戶公開。
* <mark style="color:blue;">**port**</mark>：此裝置與SeaDeep連接的端口。
* <mark style="color:blue;">**endpoint**</mark>：SeaDeep的API伺服器位置。
* <mark style="color:blue;">**training**</mark>：訓練項目。
  * <mark style="color:blue;">**command：**</mark><mark style="color:orange;">**"python"**</mark>：使用python執行。
  * <mark style="color:blue;">**args：**</mark><mark style="color:yellow;">**\[**</mark>**&#x20;**<mark style="color:orange;">**"train.py"**</mark>**&#x20;**<mark style="color:yellow;">**]**</mark>：要執行訓練的檔案名稱。
* <mark style="color:blue;">**inference**</mark>：推論項目。
  * <mark style="color:blue;">**command：**</mark><mark style="color:orange;">**"python"**</mark>：使用python執行。
  * <mark style="color:blue;">**args：**</mark><mark style="color:yellow;">**\[**</mark>**&#x20;**<mark style="color:orange;">**"infer.py"**</mark>**&#x20;**<mark style="color:yellow;">**]**</mark>：要執行推論的檔案名稱。

{% hint style="danger" %}
**port**：注意避免使用到與此電腦或SeaDeep其他核心相同的port。
{% endhint %}

<figure><img src="../../.gitbook/assets/image (19).png" alt=""><figcaption><p>設定mini.yaml檔</p></figcaption></figure>

## 4. 匯入train.py所需套件

### 4.1 匯入套件

1. 打開 「 train.py 」 。
2. 從mini\_sdk中import圖片左方的所有套件。

{% hint style="warning" %}
此為範例檔案，操作時需使用欲放上SeaDeep核心的檔案。
{% endhint %}

<figure><img src="../../.gitbook/assets/image (189).png" alt=""><figcaption><p>匯入套件</p></figcaption></figure>

### 4.2 重要套件說明

* set\_progress：設定當前進度。
* record\_task\_log：任務訓練的歷程紀錄。
* save\_task\_store\_file：上傳訓練結果
* upload\_task\_export\_file：上傳訓練好的模型、權重。

{% hint style="success" %}
SEA\_TASK\_ID可從範例檔案的127行取得，並透過141行程式顯示
{% endhint %}

<figure><img src="../../.gitbook/assets/image (191).png" alt=""><figcaption><p>重要套件說明</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption><p>set_progres：設定SeaDeep的進度條</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption><p>record_task_log：任務訓練的log歷程紀錄</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (12).png" alt=""><figcaption><p>save_task_store_file：儲存並上傳訓練結果</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption><p>upload_task_export_file：上傳訓練好的模型、權重</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption><p>SEA_TASK_ID取得方式</p></figcaption></figure>

## 5. 將檢查碼放入train.py

下滑找到以下code（圖片中第120行），於code下方放入**檢查碼**，以確認伺服器狀況。

```
if name == ‘main’：
```

{% hint style="success" %}
檢查碼位於範例檔案中的121行\~155行
{% endhint %}

<figure><img src="../../.gitbook/assets/image (23).png" alt=""><figcaption><p>放入檢查碼</p></figcaption></figure>

## 6. 設定預設訓練參數

於train.py內使用以下code設定SeaDeep訓練的預設參數，此數值將顯示於模型訓練時的 「 **模型參數** 」 一欄。

```
param.setdefault( 變數名稱, 預設值 )
```

{% hint style="success" %}
預設參數可設可不設
{% endhint %}

<figure><img src="../../.gitbook/assets/image (193).png" alt=""><figcaption><p>設定預設參數</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (195).png" alt=""><figcaption><p>模型訓練時的預設值</p></figcaption></figure>
