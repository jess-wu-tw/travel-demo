# 旅遊規劃

一個給朋友一起用的旅遊規劃網頁 App，單一個 HTML 檔、可即時共編。用來排行程、管理地點、以及公費分帳。

## 功能

- **旅程**：可建立多個旅程，每趟各自獨立。用「邀請連結」分享給旅伴，只有拿到連結的人看得到那一趟。
- **項目**：建立可重複使用的地點（景點／餐廳／飯店／機場／其他），含地址與備註，附 Google 地圖連結。
- **行程**：從項目挑選、排入日期與時間（24 小時制），可標記「不可異動（重要）」以淡黃底突顯；自動依日期分組、組內依時間排序；多天時提供日期篩選。
- **時區**：每筆行程可設當地時區，自動換算對應的台灣時間。
- **公費**：以「收支表」呈現，支援預收公積金、記錄公費支出、指定分攤成員、多幣別並換算台幣，並可結算「誰該付誰多少」。
- **登入**：使用 Google 登入，登入後可自訂顯示名稱；建立的項目／行程會標示建立者。
- **雲端共編**：資料透過 Firebase（Firestore）即時同步，同一趟的成員都能一起編輯。

## 技術

- 純前端單一 HTML 檔（HTML / CSS / 原生 JavaScript，無框架、無打包工具）
- Firebase Authentication（Google 登入）＋ Cloud Firestore（即時同步）
- 匯率換算使用免費的 open.er-api.com
- 部署於 Firebase Hosting

## 使用方式

**本機預覽**：用瀏覽器開啟 `travel-app.html` 即可預覽介面。
（註：Google 登入與雲端同步需在部署後的 https 網址才能運作，本機 `file://` 無法登入。）

**部署**：

```bash
firebase deploy --only hosting
```

部署後以 Firebase Hosting 網址開啟即可登入使用。

## 檔案

- `travel-app.html` — App 本體（所有程式都在這裡）
- `firebase.json`、`.firebaserc` — Firebase Hosting 部署設定
- `logo.png` — App 圖示
