線上文件編輯器
這是一個基於 HTML、CSS 和 JavaScript 的輕量級線上文件編輯器，具備基本的文字格式化功能，並整合了 Gemini API 以提供智慧化的內容摘要和寫作輔助功能。

功能特色
文件上傳與下載：

支援上傳 .txt, .html, .htm, .css, .js, .json, .xml, .md 等純文字相關文件。

下載時會根據原始檔案類型（例如 .html）保留富文字格式，其他文件則下載為純文字。

基本文字格式化：

粗體、斜體、底線。

字體大小調整。

字體顏色選擇。

文字對齊（左對齊、置中、右對齊）。

編輯歷史管理：

支援多步「撤銷」和「重做」操作。

Gemini API 整合：

摘要內容： 利用 AI 快速生成文件內容的簡潔摘要。

繼續寫作： 根據現有內容的風格和語氣，讓 AI 智慧地續寫文字。

響應式設計： 介面簡潔、現代，並適應不同螢幕尺寸。

純前端實現： 無需後端伺服器即可運行，方便部署。

專案結構
本專案由單一的 index.html 檔案構成，其中包含了所有的 HTML 結構、CSS 樣式（透過 Tailwind CSS CDN 和內聯樣式）以及 JavaScript 邏輯。

.
└── index.html

如何運行
由於這是一個純前端應用程式，您有多種方式來運行它：

1. 本地運行
將 index.html 檔案保存到您的電腦。

使用任何現代瀏覽器（如 Chrome, Firefox, Edge, Safari）直接打開 index.html 檔案。

2. 部署到 GitHub Pages
在 GitHub 上創建一個新的儲存庫（例如 my-document-editor）。

將 index.html 檔案上傳到該儲存庫的根目錄。

進入儲存庫的「Settings」（設定）->「Pages」（頁面）。

在「Source」（來源）部分，選擇您的主要分支（通常是 main 或 master）和根目錄 (/) 作為發布來源。

保存設定後，GitHub Pages 會自動部署您的網站，並提供一個公開的 URL（通常是 您的GitHub用戶名.github.io/您的儲存庫名稱/）。

3. 部署到 Cloudflare Pages
確保您的專案已託管在 GitHub、GitLab 或 Bitbucket 上。

登入您的 Cloudflare 帳戶，進入「Pages」儀表板。

點擊「Create a project」（建立專案）並選擇「Connect to Git」（連接到 Git）。

授權 Cloudflare 訪問您的 Git 儲存庫，並選擇包含此編輯器專案的儲存庫。

在建置設定中：

Build command (建置指令): 留空 (因為是純 HTML 檔案，無需建置)

Build output directory (建置輸出目錄): 留空 或 填寫 . (點，表示根目錄)

點擊「Deploy site」（部署網站）。Cloudflare Pages 將自動從您的 Git 儲存庫中獲取檔案並部署您的網站。

Gemini API 設定
本應用程式使用 Gemini API 進行內容摘要和寫作續寫。

程式碼中的 const apiKey = ""; 會在 Canvas 環境中自動填充。

如果您在其他環境中運行，您需要從 Google AI Studio 獲取自己的 Gemini API 金鑰，並將其填入 apiKey 變數中。請注意保護您的 API 金鑰，不要將其公開暴露在客戶端程式碼中。

使用說明
上傳文件： 點擊「上傳文件」按鈕，選擇您電腦中的文字檔案（.txt, .html 等）。

編輯內容： 在編輯器區域中直接輸入或修改文字。您可以使用工具列上的按鈕進行文字格式化。

撤銷/重做： 使用「撤銷」和「重做」按鈕來管理您的編輯歷史。

摘要內容： 點擊「✨ 摘要內容」按鈕，AI 將為您總結編輯器中的文字。

繼續寫作： 點擊「✨ 繼續寫作」按鈕，AI 將根據現有內容為您生成續寫。

下載文件： 點擊「下載文件」按鈕，編輯器中的內容將會下載到您的裝置。檔案的副檔名會盡可能與上傳時的類型保持一致（例如 .html 會下載為 .html，其他則為 .txt 或原始副檔名）。

限制
此編輯器主要設計用於處理純文字或簡單 HTML 內容。

它無法直接編輯複雜的二進位文件格式，例如 .docx (Microsoft Word) 或 .pages (Apple Pages)。如果您需要編輯這些文件，請將其內容複製並貼到編輯器中。下載時，這些內容將保存為純文字。

在下載非 HTML 檔案時，所有富文字格式（如粗體、斜體、顏色）都將丟失，因為它們會被保存為純文字。

Gemini API 的使用可能會有速率限制和費用，請查閱 Google AI Studio 文件 以獲取最新資訊。

希望您喜歡這個文件編輯器！如果您有任何問題或建議，歡迎提出。
