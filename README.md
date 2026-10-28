# 崇正 AI 影片工作台（GitHub Pages 網頁）

**線上入口：** https://staney41011.github.io/chongzheng-video-studio/

公開儲存庫只保存靜態 HTML / CSS / JavaScript。**任何使用者都可以打開網站，但私人剪輯任務、Google Drive 和後端 API 需工作台密碼與個人授權才能使用**。

## 目前網站流程

1. 輸入管理密碼，按「檢查 AI / Drive 連線」確認是否已設置。
2. 首次使用按「連接 Google Drive」，完成自己的 Google OAuth 授權。
3. 選擇活動類型、Reels / Shorts / YouTube、影片長度、風格、字幕、音樂，再貼 Google Drive 資料夾。
4. 按「儲存並讓 AI 分析素材」：後端分析真實照片及影片抽樣影格，提出依據素材的 Prompt、鏡頭順序、時間碼與敘事字幕；若需要逐字字幕，使用 Whisper 分析原始音訊。
5. 網站顯示素材抽樣影格、AI 摘要、Prompt 與建議分鏡。使用者確認後啟動 Modal 影片渲染，成品回存 Google Drive。
6. 修改 Prompt 會要求 AI 再次分析與更新分鏡，不會僅改文字卻沿用舊剪輯計畫。

## 仍需完成的授權

後端整合已進入首次實作與測試階段；因 GitHub Secrets 尚缺 Google OAuth Client ID、Client Secret、Gemini API Key，**目前不能宣稱已經端到端實測完成**。詳細設定方式在私人後端 Repo 的 README。

## 隱私與成本

- GitHub Pages 本身沒有任何 OAuth client secret、Gemini API Key、Google refresh token 或影音素材。
- Modal API 使用 EDITOR_KEY 授權、Google refresh token 加密保存於私人 Modal Volume。
- 需要確認有權向第三方 Gemini 提供所選影像素材；網站提供確認框。
- Modal 和 Gemini 都可能依實際用量收費。
- 高階音樂、長影片的完整逐格理解、多國語翻譯與完整影片產品化仍需要額外開發及正式驗證。

**私人後端：** staney41011/chongzheng-cloud-video（僅授權帳號可查看）。
