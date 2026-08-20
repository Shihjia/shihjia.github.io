# shihjia.github.io — 個人 App 介紹網站

純靜態網站，放在 GitHub Pages。沒有建置流程、沒有相依套件——
**改完 HTML 推上去就生效**，不需要跑任何指令。

## 網址

| 頁面 | 網址 |
|---|---|
| 首頁（App 列表） | `https://shihjia.github.io/` |
| 順風耳 Earshot | `https://shihjia.github.io/earshot/` |

首頁的網址就是填進 **Play Console → 開發者帳號 → 公開個人資料 → 網站** 的那一個。

## 結構

```
.
├── index.html          首頁：簡介 + App 卡片列表
├── earshot/
│   └── index.html      順風耳介紹頁
├── assets/
│   ├── style.css       ← 所有頁面共用，不要複製第二份
│   └── earshot-icon.png
└── README.md
```

## 要加一支新的 App

1. 開一個資料夾，名字就是網址的一段（例如 `newapp/`）
2. 複製 `earshot/index.html` 改內容。**樣式表引用維持 `../assets/style.css`**
3. 圖示放 `assets/`，256×256 PNG 就夠（2 倍螢幕用）
4. 在 `index.html` 複製一張 `.app-card` 改成新 App 的，連到 `newapp/`

⚠️ **不要複製 `style.css` 去改。** 複製出來的樣式一定會慢慢長歪，
然後同一個站的兩頁看起來像兩個站。要改樣式就改那一份，全站一起變。

## 寫文案的兩條紅線

這些頁面是公開的，而且 Google Play 審查看得到：

1. **不寫真實姓名或可辨識的家庭細節。** 只寫「家人」。
2. **不做醫療宣稱。** 「為了看螢幕吃力的家人而做」是陳述動機，可以；
   「幫助某某疾病患者」「改善視力」是療效宣稱，會踩到 Play 的健康類政策。
   通篇用「唸出來」「聽訊息」，不用「輔助」「治療」「改善」。

## 待辦

- [ ] **順風耳上架後**，把 `earshot/index.html` 裡「即將在 Google Play 上架」
      那個灰色按鈕換成真的下載連結。HTML 裡有註解寫著要換成什麼。
      現在不放連結是因為上架前點下去會 404。

## 相關專案

- **順風耳 Earshot 的原始碼**：`C:\Project\MyEyes`（private repo `Shihjia/MyEyes`）
  上架流程與商店文案在它的 `docs/21-play-release.md`
- **順風耳的隱私權政策**：另一個 repo `Shihjia/earshot-privacy`，
  網址 `https://shihjia.github.io/earshot-privacy/`
  ⚠️ 那個網址是**寫死在 App 程式裡**的，不要為了整理而搬動它——
  搬了就得重新打包 App 才會生效
