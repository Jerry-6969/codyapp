# Codyapp 🐾

Cody（美國短毛貓，2024-02-26 生）的電子病歷本 + 照護儀表板。

單一 `index.html`、vanilla JavaScript、無後端，部署於 GitHub Pages。

## 功能（v1）

- **飲食紀錄**：主食乾糧設定（含換糧事件）、罐頭與零食記錄（產品庫一鍵快選、蛋白質標記、賞臉評分、「取代最後一餐」）
- **症狀紀錄**：嘔吐（含內容物分類）／軟便／拒食／皮膚搔癢／其他，嚴重程度分級
- **照護提醒**：剪指甲、洗耳朵、刷牙、驅蟲藥，記錄後計時歸零，主畫面顯示「已 N 天」與紅黃綠狀態，可自訂項目與週期
- **醫療紀錄**：就診原因、診斷、處置用藥、檢驗指數（同一指數跨次就診自動畫趨勢圖）、下次回診倒數
- **體重追蹤**：快速記錄與趨勢折線圖
- **看診模式**：一鍵產生近 30 天摘要（症狀時間軸、飲食清單、體重曲線、驅蟲與主食狀態、上次就診），可列印/存 PDF
- **雙人同步**：localStorage 離線可用 + Google Drive 共用資料夾同步（追加式合併、id 去重、timestamp 較新者勝），另有 JSON 匯出/匯入備援
- **相簿**：v1 為佔位，v2 實作 Drive photos/ 照片牆

## Google Drive 同步設定

1. Google Cloud Console 建立專案並啟用 Drive API
2. 建立 OAuth 用戶端 ID（網頁應用程式），授權來源加入 GitHub Pages 網址
3. OAuth 同意畫面加入 Jerry 與 Phoebe 為測試使用者
4. Jerry 在 Drive 建共用資料夾分享給 Phoebe（編輯權限）
5. 兩人各自在 app「設定」頁填入相同 Client ID 與資料夾 ID，按「登入並同步」

資料存於共用資料夾中的 `cody-data.json`；本機快取 key 為 `codyapp-data`。
