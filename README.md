# 二大差旅費

保六總隊第二大隊國內差旅申報規定與審查工作台。

公開網站：<https://yenlab-code.github.io/second-battalion-travel/>

## 使用

下載整個專案後開啟 `index.html`。單一 HTML 已包含規定摘要、保六內規全文及64頁彙編文字；PDF原件連結需要保留 `sources` 資料夾。官方票價外部查詢需要網路。

## 內容

- 單欄初核流程：常用門檻、分案型、來回交通費、住宿與雜費依序處理。
- 六步審查提醒、送件勾選表及規定快查集中在另一頁。
- 29則白話規定，每則附實際例子與依據，明確區分內規、中央規定與待主計確認事項。
- 兩條常用行程、去回程分開計算、自駕來回里程試算、大眾運輸分段加總及 CSV 匯出。
- 交通費工作表內提供臺鐵、北捷、臺北公車及臺中公車官方查詢入口，查價後可直接返回填寫。
- 住宿與雜費單日初核、115年3月彙編全文搜尋。

介面採米白點狀背景、珊瑚色按鈕、薄荷綠與淡藍提示，並以小狗、小貓作為主題角色。重要內容採單欄向下閱讀；官方臺鐵、北捷、臺北公車及臺中公車查詢入口放在交通費步驟內，方便查價後返回填寫。

法規查核日：2026-09-23。保六內規為使用者提供的114年1月1日生效版本；無法由公開網路證明沒有後續內部函示。未判明之「火車票價」車種、接駁、自駕限制及免附憑證事宜已標示待主計確認。

## 維護

編輯 `tools/build.py` 的規則卡與 `tools/template.html` 的畫面、計算邏輯，再執行：

```text
python -m pip install pypdf
python tools/build.py
node tools/check.cjs
```

`index.html` 是生成後的正式成品；發布時應同時部署 `index.html` 和 `sources/`。不要把 `tools/` 或其他研究中間檔當作公開網站路徑。

後續使用者要求修改時：修改、核對法規與相關計算、更新版本說明、驗證畫面，提交此儲存庫並同步更新 GitHub Pages。**不設每月自動法規更新，也不自行改動核銷標準。**

## 存取與發布

GitHub儲存庫：`yenlab-code/second-battalion-travel`（公開）。網站由 GitHub Pages 從 `main` 分支根目錄發布。

所有計算在瀏覽器執行，工作表不會上傳。輸入內容於重新整理後清除。網站和儲存庫皆為公開內容；HTML中的 `noindex` 只降低搜尋引擎索引機會，**不限制任何人存取**。

## 來源

- [國內出差旅費報支要點](https://law.dgbas.gov.tw/LawContent.aspx?id=FL017585)
- [國內訓練或講習補助要點](https://law.dgbas.gov.tw/LawContent.aspx?id=FL017586)
- [115年3月解釋彙編公告](https://www.dgbas.gov.tw/News_Content.aspx?n=1522&s=235980)
- [臺北市主計處官方轉載](https://dbas.gov.taipei/News_Content_table.aspx?n=6B0F6BAEC6193B30&s=37827FFE07E4E8AD&sms=82A923F4592F0FA8)
- [北捷票價資料](https://data.gov.tw/dataset/128418)；資料提供者臺北大眾捷運股份有限公司，政府資料開放授權條款第1版。
- 保六警主字第1130005692號函（使用者提供，詳 `sources/internal-114.pdf`）。

一般參考用途；不是核准文件，也不取代主計與機關權責認定。
