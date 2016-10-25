#Git Command

終端機（或是 Bash）是一種只利用鍵盤輸入指令來操控電腦的方式。  
你可以重新命名檔案、開啟檔案、建立新資料夾、並在不同目錄（資料夾）之間切換，全都利用鍵盤輸入指令完成。

####程式庫Repository
| 指令|說明|
| ------| ------ | ------ |
| $ mkdir \<FOLDERNAME> | 建立一個新資料夾 (或稱做目錄) | 
| $ cd \<FOLDERNAME>    | 進入一個資料夾 (或稱做切換目錄) EX: cd /d =>到D槽 | 
| $ ls                  | 列出資料夾內容 | 
| $ ll                  | 列出資料夾詳細內容 | 
| $ less 檔名           |列出檔案內容|
| $ ls -al              |列出隱藏檔案|
| $ pwd                 |列出目前路徑|
| $ ctrl鍵+l            |清畫面|
| $ tab鍵               |可自動列出未打完的資料夾檔案名稱|

###Commit
.gitignore 則是要忽略的檔案清單，這是用來告訴 Git，當在做版本控制記錄的時候，不要理會這些檔案。例如，當某個檔案中包含密碼的時候，我們就不希望 Git 記錄它們下來。

|指令|說明|
| ------| ------ | ------ |
| $ git init            |為一個資料夾加上 Git 功能|
| $ git status          |檢查 程式庫repository 中的修改 現況status|
| $ git diff            |查看對檔案的修改|
| $ git add \<FILENAME> |準備 提交commit 對於一個檔案的修改到tracked區|
| $ git add .           |準備 提交commit 對於所有檔案的修改到tracked區|
| $ git commit -m "\<your commit message>" |提交commit(或儲存）您所準備好的修改並附上一個簡短的異動說明|
| $ touch \<FILENAME>   |產生檔案|
| $ git log |看commit內容|
| $ echo "\<FILENAME>" >> .gitignore       |將檔案列入忽略的檔案清單|
| $ git commit          |進入VI編輯訊息|

|VI狀態|進入鍵|說明|
| ------| ------ | ------ |
|VI輸入狀態|按i進入Insert|左下角顯示Insert|
|VI命令狀態|按ESC鍵|:wq 表示存檔離開|



###Remote Control 遠端
把電腦裡的程式庫repository 和 遠端remote的程式庫repository連結起來，並 推送push 電腦上的修改。     
每一個 遠端remote 都需要一個名字。而最主要、原始的那一個，通常都是叫做 origin。   
系統會預設一個名稱給最初的 分支branch，通常就會叫做 'master'。 

|指令|說明|
| ------| ------ | ------ |
| $ git remote add \<REMOTENAME> \       | 新增 遠端remote 連結  EX:$ git remote add origin \<URLFROMGITHUB> |
| $ git remote set-url \<REMOTENAME>     | 幫一個 遠端remote 設定位址|
| $ git pull \<REMOTENAME> \<BRANCHNAME> | 收取Pull 遠端remote 的程式 EX: $ git pull origin master|
| $ git remote -v                        | 看你有哪些 遠端remote 連結|
| $ git push \<REMOTENAME>               | 推送Push 電腦上的程式到 遠端remote  EX: $ git push origin master|

