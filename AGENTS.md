# AGENTS.md — 課文背誦小教室專案

> 這份檔案是給 AI 助手（Codex CLI、Claude Code 等）讀的常駐指令。
> 在這個專案目錄底下做任何事之前，請先讀完並遵守。

---

## 專案是什麼

這是一個**單檔 HTML 課文背誦工具**集合，給**台灣小五生**背誦中文詩、散文、文言文用。

每一課產出**一個獨立的 `.html` 檔**，內含五個互動模式（故事、逐句學習、遮蔽測試、打亂問答、闖關計時），可離線使用、可傳給家長。

目前已有：
- [index.html](index.html) — 白居易《長恨歌》（二）
- [ocean-killer-memorization.html](ocean-killer-memorization.html) — 〈海洋的殺手〉

---

## 必讀文件（按順序）

任何修改、新增課文之前，**先讀這兩份**：

1. [MEMORIZATION_METHOD.md](MEMORIZATION_METHOD.md) — 設計方法論：背後的記憶科學、五個互動模式的存在理由、視覺與技術約束、品質檢查清單。
2. [PROMPT_TEMPLATE.md](PROMPT_TEMPLATE.md) — 給 LLM 的指令模板（含 `{{...}}` 佔位符）+ 已填好的《長恨歌》範例 + 散文補充說明。

這兩份是專案的「規格書」，不是參考資料。**所有設計決策都要對得回去**。

---

## 鐵則（不可妥協）

違反任一條都算 bug，請當場修：

### 技術
- **單一 HTML 檔**：所有 CSS、JS、圖片 base64 全部內嵌在 `<style>` 與 `<script>` 與 `<img src="data:...">`。
- **絕對不用 CDN**：不引用 Google Fonts、jsdelivr、unpkg、cdnjs 任何外部資源。
- **絕對不用框架**：禁用 React、Vue、jQuery、Tailwind CSS、Bootstrap、Alpine、Svelte 等。**純 vanilla JS + 純手寫 CSS**。
- **mobile-first**：手機是主要使用情境，桌面是加分。
- **localStorage 進度持久化**：key 開頭用 `memorization-{{課文識別碼}}-`，避免不同課文互相覆蓋。

### 內容結構（核心五模式必備）
- 故事模式 / 逐句（段）學習 / 遮蔽測試（3 段難度）/ 打亂順序問答 / 15 分鐘闖關計時。
- 散文長文可加：首頁、關鍵詞骨架、家長陪背。
- 任何新模式都要說得出對應哪條記憶科學原理（提取練習、間隔練習、雙重編碼、降低認知負荷）。

### 視覺
- 字級下限：課文本身手機 ≥ 24px、桌面 ≥ 32px；按鈕高度 ≥ 42px。
- 字體：襯線 `Noto Serif TC` 系列、無襯線 `Noto Sans TC` 系列，**用 system font fallback，不從網路載**。
- 主題色**依課文情境選**，**不要套用其他課文的色票**。米白底 + 深褐字是底色，強調色與輔助色隨課文情境換（古典→朱紅金、海洋→海藍珊瑚、田園→抹茶木褐 等）。

---

## ui-ux-pro-max skill 的使用提醒

本機已安裝 `ui-ux-pro-max` skill（位於 `~/.codex/skills/ui-ux-pro-max/`），會自動提升 UI 品味。
但這個 skill **預設偏向 Tailwind CSS**。本專案禁用 Tailwind — 在生 HTML 時請明確指定：

> **vanilla CSS only, no Tailwind, no CDN, all styles inline in `<style>` tag.**

並用本專案的「米白 + 課文情境色」取代 skill 預設的色票傾向。

---

## 工作流程（新增一課時）

1. 跟使用者一起決定：課文標題、體裁、單位數（句數或段數）、主題色票。
2. 為每個單位準備：原文、關鍵詞 + 解釋、白話、記憶提示、4 字標籤、圖片描述。
3. 設計因果鏈／脈絡鏈、Quiz 的語意問題（不照原文順序）。
4. **複製 `PROMPT_TEMPLATE.md` 內的指令模板**、填空。
5. 產出單檔 HTML。
6. 對照 `MEMORIZATION_METHOD.md` 的「品質檢查清單」逐項驗收。
7. 命名：主課文存 `index.html`，其他課文存 `{{識別碼}}.html`。

---

## 工作流程（修現有課文 bug 時）

1. 先在瀏覽器開該課文 HTML，重現問題。
2. 找到對應的 `<section id="...">` / JS function。
3. 修完後，**五個模式全部點過一輪**（不只測剛改的地方）。
4. 手機尺寸（DevTools 切到 iPhone）也要看過。
5. localStorage 進度載入要照常運作。

---

## 不要做的事

- **不要** 把方法論從 MD 抄進 HTML 註解 — MD 是真相來源，HTML 是產物。
- **不要** 在沒問過使用者前重構既有課文 HTML — 它們已經在用。
- **不要** 為了「乾淨」就刪掉看起來重複的 CSS — 兩課的視覺刻意不同。
- **不要** 加套件、加建置流程、加 npm scripts — 這個專案的精髓就是「雙擊 HTML 就能用」。
- **不要** 把圖片改成外部連結 — 必須 base64 內嵌。
- **不要** 自作主張開新檔（README、CHANGELOG、tests 等），除非使用者明確要求。

---

## 對話語言

使用者母語是繁體中文。回應用**繁體中文**，技術名詞可保留英文。
