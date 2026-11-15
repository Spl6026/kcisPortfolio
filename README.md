# Portfolio 個人作品集

用六週完成自己的個人介紹與作品集。你會學習 HTML、CSS，並透過 GitHub Pages 發布網站。

## 建立自己的作品集

1. 在老師提供的範本 repo 點選 **Use this template → Create a new repository**。
2. Owner 選自己的帳號，Repository name 填入 `portfolio`，選擇 Public 後建立。
3. 在新 repo 的 **Settings → Pages → Build and deployment**，將 Source 選為 **GitHub Actions**。
4. 將自己的 repo clone 到電腦，並在 VS Code 開啟。請把下方的 `YOUR-NAME` 換成自己的 GitHub 帳號。

```bash
git clone https://github.com/YOUR-NAME/portfolio.git
```

在 VS Code 選擇 **File → Open Folder**，開啟剛下載的 `portfolio` 資料夾。

## 修改與預覽

- `site/index.html` 放個人介紹、作品文字、連結與圖片。
- `site/style.css` 設定顏色、字體、間距與排版。
- `site/sample.svg` 是圖片練習用的素材。

修改後先存檔，再用瀏覽器開啟 `site/index.html`。之後每次修改，重新整理瀏覽器就能查看結果。

課程步驟見 [個人作品集製作課程](COURSE.md)。

## 發布更新

在 VS Code 的終端機執行下列指令，將作品儲存到自己的 GitHub repo。

```bash
git add site
git commit -m "Update my portfolio"
git push
```

到 GitHub 的 **Actions** 頁面查看 `Publish site`。執行成功後，在 **Settings → Pages** 開啟網站，網址通常是 `https://YOUR-NAME.github.io/portfolio/`。

首次發布可在 Pages 設定完成後，到 **Actions → Publish site → Run workflow** 手動執行。後續推送到 `main` 分支會自動發布。

從範本建立 repo 時，第一次 Actions 可能會在 Pages 設定完成前執行。若部署失敗並出現 Pages 尚未啟用的錯誤，請先在自己 repo 的 **Settings → Pages** 將 Source 設為 **GitHub Actions**，再到 **Actions → Publish site → Run workflow** 選擇 `main` 執行。每個從範本建立的 repo 都需要各自完成 Pages 設定。

教室電腦重開機後，先啟動課堂工具包，再重新 clone 自己的 repo。下課前確認已 push，才能在下次上課接續進度。

## 六週進度

| 週次 | 內容 | 完成目標 |
|---|---|---|
| 1 | HTML 標題、段落、清單、連結 | 寫好個人介紹 |
| 2 | 行內 style、class、獨立 CSS 檔 | 調整顏色、字體與間距 |
| 3 | 盒模型、Flex 排版 | 建立作品卡片 |
| 4 | 區塊結構、圖片與手機畫面 | 加入圖片並檢查版面 |
| 5 | 內容整理與同學試用 | 完成自己的作品集 |
| 6 | 檢查、發布與展示 | 分享線上網站 |

網站會公開，請自行決定要展示的姓名與聯絡方式。若用於履歷，可以放上願意公開的電話或 Email。圖片請使用自己拍攝或取得授權的素材，密碼、API 金鑰與未經同意的他人個資請勿放入 repo。

## CSS 參考資料

講義附有各週 CSS 屬性說明。查詢更多屬性與範例可使用 [W3Schools CSS 教學](https://www.w3schools.com/css/)。
