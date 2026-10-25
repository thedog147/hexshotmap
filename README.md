# HexCiv 截圖轉地圖工具

把 Google 地圖的「一般」與「衛星」截圖，轉成 HexCiv 戰棋地圖 JSON。全部在瀏覽器內運算，圖片不會上傳。

## 放上 GitHub Pages（手機網頁版也可以）
1. 在 GitHub 新增一個 repository（例如 `hexshot`），Public。
2. Add file → Upload files，上傳 `index.html`（可連同本 README），Commit。
3. Settings → Pages → Source 選 `Deploy from a branch`，Branch 選 `main` / `(root)`，Save。
4. 約一分鐘後，網址是 `https://你的帳號.github.io/hexshot/`，手機直接開啟，可加到主畫面。

## 使用流程
1. **圖片**：貼上 Google 地圖長按複製的中心座標，按「抓取底圖」，自動抓 OpenStreetMap 一般圖與 Esri 衛星圖，格線自動對準中心與公里（約 60 張圖磚）。也可改用上傳截圖。
2. **格線**：座標抓圖不用校準；若用上傳截圖，點「點比例尺兩端」輸入公里數，再用「⊞ 移格線」對準。
3. **分類**：按「自動分類」，切到「對照」（左一般、右衛星，拖白色圓點移動分隔線）檢查；「判色」可看像素判成什麼。
4. **編輯**：用畫筆、填滿、道路、出生區修正。山地請依衛星圖自己補。
5. **匯出**：下載 JSON，放到遊戲的 `maps/`。

## 格式
輸出與既有地圖相同：odd-r 偏移、`q = col - floor(row/2)`，`cells / spawn / dims`，城鎮 `popularity: 50`，水上的道路為 `BRIDGE`。

## 資料來源
底圖：© OpenStreetMap contributors；衛星影像 © Esri, Maxar, Earthstar Geographics。請勿連續大量重抓。

## 已知限制
- 顏色判斷會受地標文字、圖示影響；Google 配色不同時，可在「教我顏色」吸色。
- 山地無法可靠自動判斷。
- Google 地圖截圖請僅供教學使用，勿公開散布成品圖。
