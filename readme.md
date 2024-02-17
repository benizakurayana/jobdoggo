# 尋職犬 JobDoggo 🐕
## 專案範圍
目標使用者：本專案選擇「不積極的求職者」作為目標使用者

功能範圍：104人力銀行求職相關功能之擴充及改善

「不積極的求職者」定義如下，我們將求職者分為：
1.	積極的求職者：看到適合的職缺立即投履歷，需要快速辨別適合的職缺，已關閉的職缺即無用處
2.	不積極的求職者：在職中或自身狀況尚未能投入職場，為之後的求職做準備，想了解有哪些產業、公司、職缺、需要什麼技能和經歷，對於有興趣的公司或職缺可以等待


## 現況
求職者可以使用的104功能：
- 登入104會員後可以使用
   - 儲存公司
      - 有開放中職缺的公司：有「儲存公司」、「新工作通知」按鈕
	  - 已無開放中職缺的公司：只有「新工作通知」按鈕，按了會自動加入儲存公司。仍可看到「公司介紹」、「主要商品」、「福利制度」區塊
	  - 儲存公司清單自訂分類最多10個
	    - 按下儲存公司按鈕時不能選分類，會先被放到未分類 
      - 儲存公司清單每筆只保留1年
  - 儲存工作
     - 若職缺已關閉，無法再看到該職缺頁面，即使在關閉前已加入儲存工作或已應徵，也只能在清單看到職缺和公司名稱
     - 儲存工作清單自訂分類最多10個
       - 按下儲存工作按鈕時不能選分類，會先被放到未分類
     - 儲存工作清單每筆只保留1年
  - 應徵紀錄
    - 清單每筆只保留60天
  - 專屬工作
    - 智慧推薦、面試機會高、設定的條件(最多5組條件)

- 未登入104會員即可使用
   - 找工作(搜尋功能)
     - 經簡易測試，登入和未登入情況下搜尋同一關鍵字，結果略有不同
   - 相似工作 

## 使用者需求
  - 104介面之內
    - 按下儲存工作按鈕時可以同時選擇分類
    - 職缺搜尋結果及相似工作搜尋結果
      - 不要顯示特定公司或職缺(104封鎖的公司最多只能設定10個)
      - 在列表檢視可以看到產業別、薪資、員工人數、是否遠端
      - 可以用員工人數排序
  - 104介面之外
    - 應徵紀錄、儲存工作、專屬工作、搜尋結果、相似工作清單中的職缺資訊另外儲存起來
    - 儲存職缺時，每次操作都可以選擇是否同時儲存到104的儲存工作清單(據說儲存的工作會影響104演算法)
    - 刪除職缺時，也同時從104的儲存工作清單刪除
    - 對另外儲存起來的職缺資訊選擇想要看到的欄位，隨心所欲的篩選、排序，並可連結到職缺頁面或應徵頁面
    - 產生統計分析報表

## 可行性
- 爬蟲程式
  - 請參考[benizakurayana的這個專案](https://github.com/benizakurayana/scraper-job-bank-posts)，已初步確認如何抓取已應徵、搜尋結果、相似工作清單中的職缺資訊
  - 備註：上述專案使用Python編寫，但本專案初步規劃後端部分使用Java Spring MVC framework；上述專案未使用資料庫，但本專案初步規劃使用FireStore
- Chrome/Edge Extension(瀏覽器擴充功能)
  - 請參考[benizakurayana的這個專案](https://github.com/benizakurayana/job-data-extractor)，已初步確認如何編寫及測試一個Chrome/Edge Extension
  - 備註：上述專案使用JavaScript編寫，但本專案初步規劃使用Vue編寫Extension自己的頁面；上述專案直接在JavaScript使用FireStore的API進行操作，但本專案初步規劃將資料庫操作相關程式碼放在後端
