# 保險商品網站

用於網路投保使用者體驗研究的靜態網站，包含商品總覽及 10 個商品頁面。保留既有版面、內嵌圖片、保費試算、研究情境與字級設定；不需要安裝套件或執行建置。

## 上傳 GitHub 並發布網站

1. 解壓縮 `insurance-website-github.zip`，開啟其中的 `insurance-website` 資料夾。
2. 登入 GitHub，右上角「＋」→「New repository」。名稱可用 `insurance-website`，選擇 **Public**，勾選 **Add a README file**，再按 **Create repository**。Public 表示程式碼和網站公開可見。
3. 在新建的 repository 點 **Add file → Upload files**。
4. 將資料夾裡的所有檔案拖進上傳區，按 **Commit changes**。請上傳解壓後的檔案，不是 ZIP 或最外層資料夾；完成後應能直接在 repository 首頁看到 `index.html`。README 可用本包版本覆蓋。
5. 點 **Settings → Pages**，在 **Build and deployment** 下將 **Source** 設為 **Deploy from a branch**。
6. 將 **Branch** 選為 **main**、資料夾選 **/ (root)**，按 **Save**。
7. 等待部署完成，回到 Pages 頁面按 **Visit site**。網址通常為 `https://你的帳號.github.io/insurance-website/`。repository 若用其他名稱，網址最後一段也會不同。

Mac 顯示隱藏檔可按 Command + Shift + .，將 `.nojekyll`、`.gitignore` 一起上傳。此網站沒有需經 Jekyll 處理的內容；`.nojekyll` 用來明確指定直接發布靜態檔案。

## 情境網址

在網站網址最後加上參數即可指定研究情境：

| 參數 | 情境 |
| --- | --- |
| `?c=1` | Why × 純文字 |
| `?c=2` | Why × 圖片 |
| `?c=3` | How × 純文字 |
| `?c=4` | How × 圖片 |

例如：`https://你的帳號.github.io/insurance-website/?c=1`。
字級參數可追加為 `?c=1&font=large`，支援 `normal`、`large`、`xlarge`。瀏覽器會記住情境與字級；正式分派情境時請使用含 `c` 的明確網址。

## 本機預覽與後續更新

直接開啟 `index.html` 即可預覽。若電腦有 Python，也可在此資料夾執行 `python3 -m http.server 8000`，再開啟 `http://localhost:8000/`。

後續修改 HTML 後，在 GitHub 使用 **Add file → Upload files** 上傳同名檔案，提交後會重新部署。若出現 404，先確認 `index.html` 位於 repository 根目錄、Pages 使用 `main / (root)`，並查看 **Actions** 的部署是否完成。

這是研究模擬網站，沒有真實承保、付款或伺服器端資料收集功能。原有設定與試算狀態保存在各使用者瀏覽器；GitHub Pages 不會自動彙整受試者操作或眼動資料。

## 檔案

`index.html` 是正式首頁；`商品_…_新模板.html` 是各商品頁面；`首頁_商品總覽.html` 保留為舊入口並自動轉往首頁。圖片已內嵌於 HTML，無需另傳圖片資料夾。

官方說明：[設定 GitHub Pages 發布來源](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
