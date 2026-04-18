# 🛠️ Mimi Hub 策展與部署 SOP (Standard Operating Procedure)

這份文件定義了所有關於 `mimi-hub` 內容更新的標準作業程序。所有涉及內容發佈的任務都必須嚴格遵循此流程，以確保內容品質、隱私安全與網站同步。

---

## 🔄 完整工作流 (The Full Workflow)

### 1. 內容提取與策展 (Extraction & Curation)
當偵測到有價值的碎片資訊（如：新聞、科技更新、遊戲 Patch Notes）時：
* **分析內容**：從原始訊息中提取以下欄位：
    * `title`: 吸引人的標題。
    * `desc`: 精簡且具資訊量的描述（含表情符號增加親和力）。
    * `link`: 原始來源連結。
    * `tag`: 分類標籤 (`game`, `app`, `tech`, `etc`)。
    * `date`: 今天的日期 (YYYY-MM-DD)。

### 2. 🛡️ 隱私過濾檢查 (Privacy Scrubbing) - **[關鍵步驟]**
在將任何內容寫入檔案之前，**必須**進行人工檢查 (Mental Check)，確保內容**不包含**以下資訊：
* **身份資訊**：真實姓名、地址、電話、Email、身分證字號等。
* **私密對話**：任何可能洩漏使用者私生活、情緒、或未經授權的對話片段。
* **敏感密鑰**：API Keys, Tokens, Passwords, 或是任何形式的 Credential。
* **未經授權的秘密**：任何可能對使用者或第三方造成風險的隱私資訊。

**⚠️ 如果發現任何隱私風險，必須立即停止流程，並將內容進行去識別化處理，或直接放棄該次發佈。**

### 3. 本地檔案更新 (Local Update)
將整理好的條目插入到 `knowledge/mimi-hub/index.html` 的 `entries` 陣列最前端。
* **路徑**: `knowledge/mimi-hub/index.html`
* **格式**: 確保符合 HTML/JavaScript 物件格式。

### 4. 雲端部署與同步 (GitHub Deployment)
更新完本地檔案後，必須完成 Git 操作以確保網站同步：
```bash
cd knowledge/mimi-hub
git add .
git commit -m "Add [Subject] update"
git push origin main
```
* **注意**: 如果遇到 SSH 權限問題，請嘗試切換至 HTTPS 協議進行推送。

---

## 📋 策展標準 (Curation Standards)
* **品質優先**：只發佈真正具有「價值」與「趣聞性」的內容。
* **風格統一**：保持親切、自然且帶點幽默的語氣（使用 🦐 符號）。
* **即時性**：對於有時效性的資訊（如遊戲更新），應儘速完成策展流程。
