# Git

是一個分散式版本控制軟體，最初由林納斯·托瓦茲（Linus Torvalds）創作，於2005年以GPL釋出。

一個版本控制系統 Version Control System (VCS)，通常有以下功能:

1. 建立 Repository (儲存庫)，用來保存程式碼。
2. 方便散佈程式給團隊，有效率協同開發。
3. 記錄誰改變什麼、在什麼時候、因為什麼原因。
4. Branch(分支)，可因不同情境分開開發。
5. Tag(標籤) 重要里程碑，以便參照。

####圖形操作介面的Git程式
Git GUI, SmartGit, Source Tree, TortoiseGit

####Git雲端檔案庫
GitHub, Bitbucket, GitLab


####Git工作流程

當開發者要建立一個開發專案時，要為這個專案建立一個目錄，以及使用git init指令建立一個這個專案的儲存庫（Repository ）。這個目錄可稱為是這個專案的工作目錄（Working Directory），開發專案所有的檔案都儲存在這個目錄下，而執行與專案相關的Git指令，也都是在工作目錄下執行。  
而下達建立儲存庫的指令後，則是會在這個工作目錄下建立一個.git資料目錄，來儲存所有版本變更需要的資訊。
另外，Git還會在.git目錄下建立一個名稱為index的索引檔案，作為記錄專案所有檔案的處理狀態。

![Git工作流程](http://static4.ithome.com.tw/sites/default/files/images/708-%E5%B0%81%E9%9D%A2-P29-600-1.png)

####開發分版觀念：Master、Branch和Merge

主幹（Master）與分支（Branch）是稱呼專案的主要版本和分支版本。  
Branch也是一個建立分支的Git指令，可將某個歷史版本複製一份，獨立成為另一個新的分支版本，  
而合併（Merge）指令剛好相反，則是把兩個不同的分支版本，合併到其中一個分支上。

####專案分版手法：Clone和Fork

複製（Clone）指令是把專案在遠端儲存庫上的所有內容複製到本地，建立起本機儲存庫及工作目錄，而叉（Fork）則是把別人專案的遠端儲存庫內容複製一份到自己的遠端儲存庫，黃保翕生動的形容：「就像是在餐桌上用叉子把盤子上的一塊肉叉到自己的盤子上。」

####資料同步指令：Push、Pull、Pull Request
執行推（Push）指令，可以把自己目前本機端儲存庫的相關檔案，上傳到遠端儲存庫，  
而拉（Pull）指令則把遠端儲存庫的最新版本下載至自己的本機端，並將遠端分支合併到本地分支，不過，Pull並不像Clone指令會下載完整專案各版本內容。  
Pull Request則是更主動地要求第三方開發者納入自己開發的程式，將本地端儲存庫上的程式碼，整併到對方的儲存庫上。

***
>參考網站:
- Git達人教你搞懂GitHub基礎觀念 <http://www.ithome.com.tw/news/95283>
- ihower 的 Git 教室<https://ihower.tw/git/>
- 好麻煩部落客<http://gogojimmy.net/2012/01/17/how-to-use-git-1-git-basic/>
- Git-it <http://jlord.us/git-it/index-zhtw.html>
- Git <https://zlargon.gitbooks.io/git-tutorial/content/>
