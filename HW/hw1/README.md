# 資料結構作業一

## 程式作業一 - ackerman.cpp

#### 流程說明
先宣告兩整數型別變數，用於儲存輸入資料及運算用，
接著利用while loop持續讀取數字，利用scanf規定格式為兩數字以一空格隔開，一次讀取兩數，
緊接輸出經 **Ackerman函式** 計算之值，
如此重複迴圈直至讀到EOF為止。

#### Ackerman函式
在Ackerman函式中，根據題意在m和n各等於0, 以及其餘狀況各有其函式運算方式共三種，
前兩情況利用兩個if判斷式給定其回傳值，
函式結尾，亦即前兩判斷式皆未符合時，則回傳其餘狀況對應值，也因此構成函式遞迴。




## 程式作業二 - powerset.cpp

#### 流程說明
首先宣告一字串及字串型別的vector，
分別用於儲存輸入內容及其經 **splitString函式** 轉換之vector，
接著利用while loop持續讀取單行資料(getline)，
轉換為vector陣列後，先印出一空集合(空集合為所有集合的子集合)，再利用 **powerset函式** 印出所有子集合，
如此重複迴圈直至讀到EOF為止。

#### splitString函式
用於將空格隔開之所有內容分離，
利用string::find()函式及兩位置變數依序找到空格位置，並利用string::substr()分割字串，
同時一一push_back至一空vector陣列中。
函式結尾的判斷式是由於字串結尾非空格時，會忽略最後一筆資料，因此補充之。

#### powerset函式
參數含欲找尋之子集合大小，利用 **subset函式** 窮舉該大小的子集合，
並以遞迴方式，逐次增加欲找尋之子集合大小，直至與輸入之集合大小相等時返回

#### subset函式
每次進入函式時會攜帶一未完成的子集合，以及兩參數(目前找尋至原集合第幾項、還需幾項可完成子集合)，
並依序執行兩動作:
1. 將當前項加入未完成子集合，檢查數量是否已滿，是則輸出，否則繼續前往下一項。
2. 忽略當前項，直接前往下一項。

因此由原本空的子集合，以及設定集合目標大小，可藉此方法(每項均跑過被包含及不包含的可能性)，達到窮舉的目的。
此函式將會於子集合已滿或剩餘項不足時返回。

