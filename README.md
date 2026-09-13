# Markdown Editor

純前端的 Markdown 編輯器，即時預覽、多分頁，並可直接讀寫本機檔案。不需安裝、不需建置、沒有後端，也不需要網路。

## 快速開始

```bash
git clone https://github.com/terry-groot/markdown-editor-js.git
cd markdown-editor-js
```

用瀏覽器開啟 `index.html` 即可（雙擊，或拖進瀏覽器視窗）。

## 功能

- **即時預覽** — 左右分割視窗，中間的分隔線可拖曳調整比例（20%–80%）
- **多分頁** — 同時開啟多個檔案，分頁可雙擊重新命名；分頁狀態會存進 `localStorage`，關掉瀏覽器再打開仍在
- **本機檔案讀寫** — 透過 File System Access API 直接存回原檔，檔案 handle 存在 IndexedDB，下次開啟不必重新授權
- **格式工具列** — 粗體、斜體、刪除線、H1–H3、清單、待辦清單、連結、圖片、行內程式碼、程式碼區塊、引言、分隔線、表格
- **語法高亮** — 程式碼區塊由 highlight.js 上色，並跟隨亮/暗主題切換
- **亮/暗主題** — 偏好存在 `localStorage`
- **GFM 支援** — 表格、刪除線、待辦清單、自動換行

## 快捷鍵

| 快捷鍵 | 動作 |
|---|---|
| `Ctrl/Cmd + B` | 粗體 |
| `Ctrl/Cmd + I` | 斜體 |
| `Ctrl/Cmd + K` | 插入連結 |
| `Ctrl/Cmd + N` | 新分頁 |
| `Ctrl/Cmd + W` | 關閉分頁 |
| `Ctrl/Cmd + O` | 開啟檔案 |
| `Ctrl/Cmd + S` | 儲存 |
| `Ctrl/Cmd + Shift + S` | 另存新檔 |
| `F5` | 從磁碟重新載入 |
| `Tab` | 縮排 4 個空白 |

## 瀏覽器支援

直接存回原檔的功能需要 [File System Access API](https://developer.mozilla.org/en-US/docs/Web/API/File_System_Access_API)：

| 瀏覽器 | 開啟／儲存 |
|---|---|
| Chrome / Edge / Opera | 完整支援，可直接覆寫原檔 |
| Firefox / Safari | 降級為上傳檔案 + 下載檔案 |

## 相依套件

已放在 `vendor/` 內，**完全離線可用**，不依賴 CDN：

- [marked](https://github.com/markedjs/marked) 12.0.2 — Markdown 解析
- [highlight.js](https://highlightjs.org/) 11.9.0 — 程式碼語法高亮（common 語言版，含 36 種語言）

`index.html` 以相對路徑引用 `vendor/`，搬移時請整個資料夾一起搬。
