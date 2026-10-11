# 深淵燈火｜互動式網頁小說

兩個《暗黑破壞神：永生不朽》玩家同屬氏族「深淵燈火」，遊戲裡的性別都與現實相反。讀者站在上帝視角，看竹科工程師林致遠（女死靈法師「薇歐拉」）與獵頭顧問沈若晴（男野蠻人「鐵拳老王」）一步步靠近真相。

目前收錄：第一章〈九點整，上線〉、第二章〈影盟之戰〉、第三章〈地獄骨夾〉、第四章〈新的職缺〉。

## 部署到 GitHub Pages

1. 在 GitHub 建立新的 repository（例如 `abyss-lantern`），設為 Public。
2. 把 `index.html`（以及這份 `README.md`）上傳到 repository 根目錄。
3. 進入 **Settings → Pages**，Source 選 **Deploy from a branch**，Branch 選 `main`、資料夾選 `/ (root)`，按 Save。
4. 約一分鐘後，網址會是 `https://<你的帳號>.github.io/<repository 名稱>/`。

整份作品是單一 HTML 檔，CSS、JavaScript、劇情資料全部內嵌，不需要任何建置步驟，也沒有外部圖片或字型。

## 存檔

進度與數值存在瀏覽器的 localStorage（每位讀者各自獨立）。注意：同一個 GitHub 帳號底下的所有 Pages 網站共用同一個網域，存檔鍵值都以 `abyss-lantern:` 開頭以避免衝突。

## 新增章節

劇情資料與程式邏輯分離，每一章是一段 `<script type="application/json" id="chapter-N">`。新增章節時：

1. 複製最後一章的 JSON 區塊，改 `id`、`no`、`title`，並設 `"carryFrom": "上一章的 id"`。
2. 在程式中的 `CHAPTER_IDS` 加入新的 `chapter-N`。
3. 節點格式與可用欄位，請見 `index.html` 中劇情資料上方的註解說明。
