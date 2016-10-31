#Git Command

終端機（或是 Bash）是一種只利用鍵盤輸入指令來操控電腦的方式。  
你可以重新命名檔案、開啟檔案、建立新資料夾、並在不同目錄（資料夾）之間切換，全都利用鍵盤輸入指令完成。

####程式庫Repository
| 指令|說明|
| ------| ------ | 
| $ mkdir \<FOLDERNAME> | 建立一個新資料夾 (或稱做目錄) | 
| $ cd \<FOLDERNAME>    | 進入一個資料夾 (或稱做切換目錄) EX: cd /d =>到D槽 | 
| $ ls                  | 列出資料夾內容 | 
| $ ll                  | 列出資料夾詳細內容 | 
| $ less 檔名           |列出檔案內容|
| $ ls -al              |列出隱藏檔案|
| $ pwd                 |列出目前路徑|
| $ ctrl鍵+l            |清畫面|
| $ tab鍵               |可自動列出未打完的資料夾檔案名稱|

####Commit
在你的 程式庫repository 中建立一個新檔案，新增一些內容到那個檔案並且將那些修改 提交commit 到 Git 中。
.gitignore 則是要忽略的檔案清單，這是用來告訴 Git，當在做版本控制記錄的時候，不要理會這些檔案。例如，當某個檔案中包含密碼的時候，我們就不希望 Git 記錄它們下來。

|指令|說明|
| ------| ------ |
| $ touch \<FILENAME>   |產生檔案|
| $ rm \<FILENAME>      |刪除檔案|
| $ git init            |為一個資料夾加上 Git 功能|
| $ git status          |檢查 程式庫repository 中的修改 現況status|
| $ git diff            |查看對檔案的修改|
| $ git add \<FILENAME> |準備 提交commit 對於一個檔案的修改到tracked區|
| $ git add .           |準備 提交commit 對於所有檔案的修改到tracked區|
| $ echo "\<FILENAME>" >> .gitignore       |將檔案列入忽略的檔案清單|
| $ git commit -m "\<your commit message>" |不用進VI,在命令列提交commit(或儲存）您所準備好的修改並附上一個簡短的異動說明|
| $ git log             |看commit內容|
| $ git commit          |進入VI編輯訊息|
| $ vi \<FILENAME>      |進入該檔案的VI編輯訊息|
| $ vi .git/config      |進入.git中的設定檔的VI編輯訊息|

|VI狀態|進入鍵|說明|
| ------| ------ | ------ |
|VI輸入狀態|按i進入Insert|左下角顯示Insert|
|VI命令狀態|按ESC鍵|:wq 表示存檔離開|
|VI命令狀態|按ESC鍵|:q! 表示不存檔離開|
|VI命令狀態|按ESC鍵|游標放在指定行,按dd表示可刪除一行|

####Remote Control 遠端
把電腦裡的程式庫repository 和 遠端remote的程式庫repository連結起來，並 推送push 電腦上的修改。     
每一個 遠端remote 都需要一個名字。而最主要、原始的那一個，通常都是叫做 origin。   
系統會預設一個名稱給最初的 分支branch，通常就會叫做 'master'。 

|指令|說明|
| ------| ------ | 
| $ git remote add \<REMOTENAME> URL or SSH     | 新增 遠端remote 連結  EX:$ git remote add origin \<URLFROMGITHUB> |
| $ git pull \<REMOTENAME> \<BRANCHNAME>        | 收取Pull 遠端remote 的程式 EX: $ git pull origin master|
| $ git remote -v                               | 檢視現有的 遠端remote 連結connections|
| $ git push \<REMOTENAME> \<BRANCHNAME>        | 推送Push 電腦上的程式到 遠端remote  EX: $ git push origin master|
| $ git push \<REMOTENAME> --delete \<BRANCHNAME>  |刪除 遠端remote 分支branch|

####Branch
Git 程式庫repositories 用 分支branches 來隔離進度。    
當需要跟其他人一起進行專案時，在你完成負責的部份之前，經常需要利用 分支branch 來保護你對程式所做的修改。    
如此，你就可以讓主要的 'master' 分支branch 保持穩定，不被未完成的修改影響。等到你完成在 分支branch 上的修改，就可以把它 合併merge 回 'master' 分支branch。

|指令|說明|
| ------| ------ |
| $ git status                        |看目前正在哪個 分支branch|
| $ git branch                        |列出所有的 分支branches|
| $ git branch \<BRANCHNAME>          |新增 分支branch|
| $ git branch -D \<BRANCHNAME>       |刪除 分支branch|
| $ git branch -H \<BRANCHNAME>       |列出分支branch相關指令參數|
| $ git branch -m \<NEWBRANCHNAME>    |重新命名目前所在的 分支branch|
| $ git checkout -b \<BRANCHNAME>     |新增並切換到新的 分支branch|
| $ git checkout \<BRANCHNAME>        |切換到另一個 分支branch|

####Merge 
在本機上 合併Merge 你的 分支branch，刪除舊的 分支branch，從 上游upstream 獲得更新來獲得最終勝利！

|指令|說明|
| ------| ------ |
| $ git merge \<BRANCHNAME>                        |Merge 分支branch 到目前的 分支branch|

####Reset
回復檔案狀態。
遇到多個檔案要Comit，可以回復檔案到Staged狀態，再合併多個檔在同一個Comit。

|指令|說明|
| ------| ------ |
| $ git reset \<COMIT編號或其前4碼>         | 放棄 add，但保留修改=unstaged區|
| $ git reset --hard \<COMIT編號或其前4碼>  | 放棄所有修改，回到上個 commit 完成後的狀態|
| $ git reset --soft \<COMIT編號或其前4碼>  | 回復到 commit 提交前的狀態=staged區|

