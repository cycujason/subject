## Summer Schedule
周別/工作者	蕭祥維	劉家勳	謝祈璿	備註欄	備註欄2
- 7/5~7/11	簡單編輯介面加入	登入系統編寫及測試(登入介面含DB)，用JS試	編寫或改寫hedgedoc的文字編輯功能	部屬使用heroku?	ckeditor showdown express,node server
- 7/12~7/18	簡單編輯介面加入	登入系統編寫及測試(登入介面含DB)	加入real-time模組	即時系統模組，MARKDOWN編輯模組
- 7/19~7/25	歡迎畫面	管理介面	筆記文字及圖像儲存連接DB		
- 7/26~8/1	第一次整合測試	第一次整合測試	第一次整合測試	可能第一次進度meeting	
- 8/2~8/8	圖像編輯視窗設計&&協力網站美化	網站美化設計	內文搜索模組初試		
- 8/9~8/15	圖像編輯視窗設計&&協力網站美化	網站美化設計	內文搜尋結果優化		
- 8/16~8/22	圖像與筆記整合&&協力網站美化	網站美化設計	內文搜尋功能完成		
- 8/23~8/29	第二次整合測試	第二次整合測試	第二次整合測試	可能第二次進度meeting	
- 8/30~9/5	緩衝周	緩衝周	緩衝周		
- 9/6~9/12	總驗收及程式檢查	總驗收及程式檢查	總驗收及程式檢查
### Teacher notes
預期的驗收項目：
- 7/17 主畫面(註冊登入、文字編輯)介面設計，資料庫讀寫模組
- 7/31 文字及圖像管理， 用戶操作及後台管理介面 (於會議展示)
- 8/14 圖像編輯模組  ，內文搜尋模組
- 8/28 圖文整合系統雛型  (於會議展示)
- 9/11 實驗程序規劃，系統執行效率最佳化、操作介面美化
- 9/25 專題報告初稿，專題競賽情境展示 (於會議展示)
---
# 老師留言
- Try to rename the repository name and add more material, such as your project goal.
- Ref to the repository at https://github.com/FelixWuYH/BSprojectICE
- 基於防疫不便到校，改以預約線上討論(週三除外)，相關資訊(如網址)或檔案可備份於倉庫或雲端資料夾，以便查閱。1/26
# 寒假進度
目前討論先更改專題方向，改以電影或影視作品的推薦，依舊以neo4j做知識庫後進行推薦

一樣照neo4j對電影資料做分析與關係建圖，建立知識庫後進行推薦，推薦的手法會用content-based


110/1/23  22:20

參考資料:

https://grouplens.org/datasets/movielens/latest/

https://codertw.com/%E7%A8%8B%E5%BC%8F%E8%AA%9E%E8%A8%80/751750/

先從網路抓資料集，嘗試建立知識庫，先對各項資料抽取屬性建圖，考慮是否需要另外爬蟲抓取其他資料，如IMDB等

先抓movielens or kaggle dataset 的資料

尋找評分方式，計量方法，推薦的用法

考慮是否增加其他視覺化統計資料

110/1/24  17:34


決定點與點關係，整理movielens的資料，用程式的辦法整理匯入資料(資料量大，先大略瀏覽資料屬性)

嘗試使用其他資料庫看看其效能或結果是否會比neo4j更合適(試驗)

110/1/25  22:30


建立初步嘗試雛形

因為資料量大，先改用small資料

討論查詢後相關資料給使用者看(EX:網址，供使用者自由選擇是否前往查看更多資訊)

110/1/27 16:10


TMDB 網站有API https://www.themoviedb.org/documentation/api/wrappers-libraries

先嘗試mysql和python的連接和把圖建完，找尋合適的使用方式與應用

110/1/28 17:38


MySQL
遇到的問題：MySQL的建置，發生無法匯入CSV的問題。
解決辨法：
先改ProgramData\MySQL\MySQL Server 8.0\my.ini中的參數。
加上secure_file_priv=''
後將CSV放入同目錄下的Data\test\ test為資料庫的名稱，即可解決。

問題：MySQL沒有建立連線。
解法：打開服務，找到MySQL80，右鍵打開就可以建立連線。

01/29/2021 02:12

  
  
  
Netflix部分的研究:  

官方API已下架  

https://partnerhelp.netflixstudios.com/hc/en-us/sections/205641408-API-Developer-s-Toolkit  

有另外找到一個有netflix影視較大量且有較新的資料的網站:  

https://unogs.com/  

內容各個影視的id parameter如:  

絕命毒師(Breaking Bad)  

在netflix url為--->https://www.netflix.com/tw/title/70143836  

在unogs為---->https://unogs.com/title/70143836  

可見一組parameter對應一部影視，不過在netflix上可能會有國家地區的限制，能看到的不同。  

unogs有一個官方API  

https://rapidapi.com/unogs/api/unogs  

有免費的方法，不過一天只能推100個request，超過即要每一次request付費一次，且要先綁定繳費信用卡才能使用API。  

其他的python package有:  

https://pypi.org/project/netflix/(github:https://github.com/efe/netflix)  

https://pypi.org/project/pyflix2/  

都有嘗試寫來抓抓看資料，但前者一直回傳noneType的物件，可能遭到netflix方面的封禁  

後者因為他要有啟動碼但取得啟動碼的網站已消失(status code :404)  

有想過直接用爬蟲對unogs.com來取的資訊，也有真的去試著爬回來，但unogs的服務條款有寫:  

You must not conduct any systematic or automated data collection activities on or in relation to this website without unogs.com's express written consent.  

This includes:  


scraping  

data mining  

data extraction  

data harvesting.....  

目前還能抓影視資料回來，有可能之後會被封禁也不一定。  


有搜尋到一些整理好的parameter資料集，但內容經實驗查詢後多數連結不適用或可能早已下架  

-->利用wiki來獲取資料  


維基部分的研究:  
我們簡單試過api，主要是以網址後面加上action、format等參數來得到相關資訊。弄得跟爬蟲有點像  
https://ithelp.ithome.com.tw/articles/10196319  
https://www.mediawiki.org/wiki/API:Search  


spotify部分的研究:  
官方有developer的社群，在使用過程中感覺比起netflix友善許多  
目前嘗試使用的是python的方式:  
https://spotipy.readthedocs.io/en/2.16.1/#api-reference(github:https://github.com/plamere/spotipy)  
利用其套件加上官方developer社群中dashboard可建立一個應用資料庫，取得api的key，進而使用spotipy  
能透過設定scope設定存取權  
https://developer.spotify.com/documentation/general/guides/scopes/  
其中也有參考:  
https://medium.com/%E6%B5%B7%E5%A4%A7-ios-app-%E7%A8%8B%E5%BC%8F%E8%A8%AD%E8%A8%88/%E4%B8%B2%E6%8E%A5%E5%A4%9A%E7%A8%AE-api-%E8%A3%BD%E4%BD%9Clady-gaga-app-spotify%E7%AF%87-2d39c52da7e4  


2021/2/10 22:10  
  
 想法:   

**資工系 多人即時筆記功能+作業及線上考試提醒功能(行事曆、待辦事項)+課程資料整合(from網路或修過課的好心人)**  

多人筆記系統可參考HackMD並加入圖像工具列，像OneNote那樣(加入字體顏色、大小、螢光標記功能)，因為HackMD markdown語法需要時間學習，使用圖像較好操作。  
保留HackMD多人筆記、放入程式碼、加入圖片、繪製甘特圖、UML、撰寫數學式及表格等等。  

因為我們常常忘記繳交作業和i-learning的考試時間，所以我們想做一個能提醒我們的功能，**從i-learning擷取行事曆**，或是能透過手動增添條目，在一個時間內提醒使用者要記得做事，可以加上倒數計時器，像是i-learning上的考試，可以在前三天、前一天、最後幾個小時做倒數，就不用擔心沒有做到考試了！  

課程資料整合可以放入課本的電子書、投影片、參考資料、考古等等，讓其他人可以在上面收穫更多資訊。  

可以是以課程分類資料夾，在其中開放共筆記事本，及放置資源，共筆可以設置管理者或是科目資料夾可直接設定管理者，在主目錄可設定一個"考研組合"或"三年級組合"等等，讓使用者不必慢慢找可直接得到該條目底下的所有課程並進入找取相關資料，各科目也可在其中放置課業守護的line連結讓使用者可快速找到發問處(若有的話)，使用者也可設定我的#最愛，讓使用者更迅速或專注在某筆記或科目上。  

對共筆可設置喜歡的類似評分系統，讓大家知道筆記的熱門度，或是直接以年份管理，另外整理考研的時間置頂讓大家知道或提醒大家。  

2021/02/19

## 老師提問
1. 資料的應用範疇：允許的筆記類型有哪些需求？理工科如數理、程設，文科如語文、商管，各自列出後再歸納篩選較重要的。
2. 系統的核心特色：知識圖如何表示和運用，擷取或輸入資料的形式決定前者，後者則依循上列需求去思考各種可能。輔以維基百科或其他相關外部資源是選項之一。
3. 系統平台和介面：選定雲端平台及操作介面的搭配，後端資料庫或AI分析的支援是重要考量之一。

3/3 使用 :https://hackmd.io/@TMDproject/H1VCLGcGO



2021/3/18  
為了改善進度停滯現況，我們決定每周固定時間討論與更新內容  
每周六下午15:00~17:30固定上Discord討論並由組長彙整每周進度，並在其中提出每人所遇見的問題加以討論。   
其餘時間可視情況加開討論或私下約討論個別進度  
週六晚上23:59前組長更新Github上相關內容  
並使用issue追蹤相關問題  

經過討論，目前分工如下:  
蕭祥維--heroku後端之實驗與相關支援元件對於實作之測試，看是否能確實符合需求，若不符要尋找其他方案  
劉家勳--CodiMD程式之參考，嘗試建立共筆功能  
謝祈璿--測試並實作搜尋系統內容  

期中之前的目標:  
建立共筆系統之雛形，能放上最基本的共筆功能至server端運行  

期末之前的目標:  
能在共筆系統內加入搜尋並有分類管理功能  

目前構想:  
分類管理是能對各種不同的檔案進行系統化處理，使使用者能快速對想要的筆記做分類與歸納  
搜尋是希望能導入語言處理，產生摘要或關鍵字，實現日常對話式搜尋問答與產生標籤提供搜尋

---
### 2021/3/19
* 使用issues提問或整理討論內容，不只大家可以一起參與討論，透過自動發信通知，也可以直接回信。https://github.com/cycujason/neo4j-recommendation-system/issues
* CodiMD看起來是首要目標，盡快(1-2週內)整理一份簡介，廣泛優先於深入，以供三位進一步討論可用素材及分工。 https://hackmd.io/@docs/hackmd-vs-codimd

(3/20) 周六  
非常簡單ver的分析CodiMD之結構---  
bin => heroku連接及部署資料  
contribute => developer certificate of origin  
deployments => docker build  
lib =>偏後端與後臺運作的功能  
locales =>語言參數檔(純粹是各種語言的切換)  
public => 看起來是前端功能及介面設定  
test =>猜測是對功能做測試  
utils => string.js，字串正則表達式替換(目前不太確定用途)  


app.js有建立連線及開始使用的內容  
底下是參數檔，及使用webpack對前端進行封裝的程式  

CodiMD使用的是socket.io的realtime功能(open source資源)  
使用的是Node.js的環境  
根據內部檔案和內容，有用到"docker"(研究重點)且部署是用到heroku  
看來我們要去學學javascript及CSS，HTML的語法(應該不難)  


(3/27) 週六  
研究部署所需環境變數，嘗試一次部署致heroku(失敗)  
以及研究slug size問題  
需要調整內部的參數與內容  
考慮移除GOOGLE，DROPBOX，FACEBOOK，TWITTER，MATTERMAOST的API接口  
保留GITHUB，GITLAB接口  
希望能保留GITHUB部分的功能  
登入方式希望單純而暫時不提供過多登入選項  
先暫時不更動CODI語法功能  
修改程式時可從修改cofig.json對初步修改  

heroku部分的application error待解決  
可能的錯誤點，state changed from starting to crashed  
解決的可能辦法，在Config Vars填上GITHUB、GITLAB接口  


(4/2)周五 (4/3) 週六  
基本上Codimd的功能包含之前談過的圖表與數學式  
及留言區塊(可改製作成超連結分類)  
但閹割掉了一些Markdown語法的功能  
像是Tag，但這部分應該影響不大(跟筆記撰寫方式與格式有關)  
Codi本身原本是HackMD的社群版本  
所以保有許多Hack有的功能  
但沒有共同管理，分類管理，及一個比較好的檢索查找方式(應該可以是內文分析的切入點)  
也沒有團隊管理的部分  
版本控管也只看的到變更內容而看不到變更者  
變成非常簡單的單純共筆功能  
官方好像有說codi是建議在3-5人的共同編輯(果真是小型社群版本)  
其他在config中的許多API是登入方式的接口  
到時看要不要單純留下EMAIL登入(或留著也不一定。增加itouch?客製?)  
其中bitbucket不是登入方式是一個"代碼控管庫"(git的位置?)  
確定codi開發是用socket .io(應該會沿用，若pusher沒有比較好或修改接口太繁複就沿用)  
題外話:(codi 的 document 部分沿用hack的 document 要自己切換視角，雖然本是同根生的東西)  

這兩周有嘗試架起原版的codi，想說順便認識一下heroku平台(官方有預設弄好的heroku build的 method)，但遇到了一些問題:  
若用官方之辦法能建立成功但appliction error，可能是程式設定的問題  
若用線下自己推的方式會有lost模組發生  
看過一些stack overflow論壇和教學目前還沒找到真正的解決辦法  
還在多方嘗試中，有想過先試試本地docker和mysql架，但還是想先用heroku試試  
