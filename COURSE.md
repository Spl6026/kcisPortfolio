# 個人作品集製作課程

每堂課：10 分鐘看老師示範，20 分鐘自己修改，5 分鐘在瀏覽器檢查，5 分鐘 commit、push 並看 GitHub Pages。第一次設定 Pages 如果來不及，回家再完成；本機檢查仍可照做。

## 第 1 週：HTML 內容

1. 找到 `site/index.html` 中的 `<h1>` 與 `<p>`，改成自己的作品集標題與個人介紹。
2. 在 `<main>` 裡新增一個 `<section>`，放一個 `<h2>` 與兩段 `<p>`。
3. 新增 `<ul>` 和至少三個 `<li>`，列出本學期想展示的內容。
4. 新增一個 `<a href="https://example.com/">參考網站</a>`，把網址改為適合的公開資料；點擊確認連結可開啟。

檢查：標題、介紹、清單都出現在頁面；打開開發者工具的 Console 沒有找不到檔案的訊息。

## 第 2 週：CSS 外觀

先用行內 CSS 修改一個元素，觀察 `style` 裡的屬性和值。

```html
<p style="color: blue; font-size: 20px;">我正在學習網頁設計。</p>
```

`color` 設定文字顏色，`font-size` 設定字體大小。每一組屬性和值用冒號連接，結尾用分號。`style` 屬性的內容放在引號內。

1. 在自己的介紹段落加入 `style`，修改 `color`、`font-size` 與 `background-color`，存檔後重新整理。
2. 將同樣的外觀套用到第二段文字，觀察重複的設定。
3. 在 HTML 為兩段文字加入 `class="intro"`，將共用樣式移到 `site/style.css`，再刪除這兩段的 `style`。

```html
<p class="intro">我正在學習網頁設計。</p>
```

```css
.intro {
  color: blue;
  font-size: 20px;
}
```

HTML 中的 `<link rel="stylesheet" href="style.css">` 會載入 CSS 檔。`.intro` 選取使用這個 class 的元素，`p` 則選取所有段落。

4. 在 `.intro` 加上 `padding: 16px;`、`margin: 16px 0;` 與 `background-color: lightgray;`，比較區塊內部空間與區塊間距。

檢查時確認兩段介紹套用相同樣式，並能指出設定來自哪個 CSS 選取器。同一屬性同時寫在行內樣式與一般 CSS 規則時，行內樣式通常會優先套用。

### 本週 CSS 說明

| 寫法 | 用途與效果 |
|---|---|
| `color: blue` | 將文字設為藍色，也可以填入 `#2459a6` 這類色碼。 |
| `background-color: lightgray` | 將元素的背景設為淺灰色。 |
| `font-size: 20px` | 將文字大小設為 20 個 CSS 像素。`px` 是常用的長度單位。 |
| `padding: 16px` | 在內容與邊框之間，四邊各留 16px 的內距。 |
| `margin: 16px 0` | 上下外距為 16px，左右外距為 0。兩個值依序表示上下與左右。 |
| `font-family: Arial, "Microsoft JhengHei", sans-serif` | 依序選擇電腦可用的字體，最後使用系統的無襯線字體。含空白的字體名稱以引號包住。 |
| `line-height: 1.6` | 行高為字體大小的 1.6 倍，讓多行文字更容易閱讀。 |

`body` 選取整個頁面的本文元素。範本在這裡設定字體與行高，多數內層文字會繼承這些設定。CSS 的大括號包住樣式宣告，`/* 文字 */` 是註解。

先保留背景色，只改 `padding`，觀察背景內的空間如何變大。接著只改 `margin`，觀察元素與其他內容之間的距離。

## 第 3 週：卡片排版

1. 在 `id="projects"` 的作品區內，將原有作品內容整理成下方結構。每張卡片包含作品名稱、製作內容與學習心得。

```html
<div class="project-list">
  <div class="card">
    <h3>我的第一個作品</h3>
    <p>介紹作品內容與學習心得。</p>
  </div>
  <div class="card">
    <h3>我的第二個作品</h3>
    <p>介紹作品內容與學習心得。</p>
  </div>
</div>
```

2. 在 CSS 新增 `.card` 規則，試著設定 `border: 1px solid gray;`、`padding: 16px;` 與 `border-radius: 8px;`。
3. 在 CSS 新增 `.project-list` 規則，加入 `display: flex; flex-wrap: wrap; gap: 1rem;`。若卡片太窄，為 `.project-list .card` 加上 `flex: 1 1 240px;`。

檢查：放大或縮小瀏覽器視窗，卡片不會重疊或超出畫面。

### 卡片與 Flex 說明

| 寫法 | 用途與效果 |
|---|---|
| `.card` | 選取所有 `class` 包含 `card` 的元素。 |
| `border: 1px solid gray` | 加上寬度 1px、實線、灰色的邊框。三個值依序為寬度、線條樣式與顏色。 |
| `border-radius: 8px` | 將邊框四角設為 8px 的圓角。 |
| `display: flex` | 將容器內的直接子元素以 Flex 排版，預設沿水平方向排列。 |
| `flex-wrap: wrap` | 一列放不下時，允許子元素換到下一列。 |
| `gap: 1rem` | 子元素之間保留間距。`rem` 以根元素的字體大小為單位，預設通常 1rem 約為 16px。 |
| `.project-list .card` | 選取 `.project-list` 裡面的 `.card`。中間的空格表示後代元素。 |
| `flex: 1 1 240px` | 三個值依序是放大比例、縮小比例與基準尺寸。每張卡片以 240px 為排版起點，會分配剩餘空間，也允許縮小。 |

`display`、`flex-wrap` 與 `gap` 寫在容器 `.project-list`，`flex` 寫在裡面的卡片。卡片的實際寬度也會受內容、padding 與 border 影響。縮窄視窗，觀察卡片何時換行。

## 第 4 週：語意與圖片

`section` 用來組織有標題的主題區段，例如「關於我」與「作品」。只為排版包住卡片時使用 `div`。

1. 指出頁面中的 `<header>`、`<main>`、`<section>`、`<footer>` 各放什麼內容。
2. 可以在一個區塊中放入範本圖片：`<img src="sample.svg" alt="藍色方格圖示">`。若換成自己的圖片，將檔案放在 `site/`，並用文字說明它的內容或功能。
3. 在 CSS 加上 `img { max-width: 100%; height: auto; }`，讓圖片配合可用寬度縮放。再用瀏覽器的窄視窗檢查文字、圖片與連結是否容易閱讀。

檢查：圖片載入成功；看不到圖片時，替代文字仍能傳達資訊。圖片沒有意義時可以省略圖片，不必硬加。

### 圖片 CSS 說明

`img` 選取頁面上的圖片。`max-width: 100%` 限制圖片寬度最多為所在容器可用寬度的 100%，較大的圖片會縮小。`height: auto` 讓高度依圖片比例調整，避免變形。

把瀏覽器視窗縮窄，確認圖片會隨容器縮小。`alt` 是 HTML 屬性，用文字描述圖片內容，顯示外觀則由 CSS 設定。

## 第 5 週：整理作品

1. 整理自己的個人介紹與作品，刪除範本中的示例文字，保留自己的介紹、清單和至少一個有用的連結。
2. 請同學用手機寬度試看，記錄一個看不清或找不到的地方。
3. 修改後再次確認標題、對比與間距。

檢查：同學不用解釋也知道這個頁面的主題。

## 第 6 週：發佈與展示

1. 本機開啟 `site/index.html`，檢查所有連結與圖片。
2. `git status` 確認修改，commit 並 push 到自己的 repo。
3. 在 GitHub **Actions** 看 `Publish site` 是否成功；打開 **Settings → Pages** 提供的網址，確認線上內容是最新版。
4. 用一分鐘介紹你的主題，以及你如何發現並修正一個問題。

如果 Actions 失敗，開啟失敗步驟查看錯誤訊息，並確認 Settings → Pages 的 Source 已設為 GitHub Actions，再請老師協助。

## CSS 查詢網站

查詢屬性時，可以在 W3Schools CSS 教學中找到 `margin`、`border`、`display` 等主題。先閱讀範例，再用 **Try it Yourself** 修改數值並查看效果，最後回到自己的網頁套用。

[W3Schools CSS 教學](https://www.w3schools.com/css/)
