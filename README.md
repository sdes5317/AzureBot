# AzureBot
練習實作一個Azure Bot


## Azure Bot服務架構說明(此文章於2020/08/26產生，實際使用可能因改版而無效)
* Azure Bot的框架本體是一個Web Api範本(WebHook)
* 把架設的Web Api連結設定在Bot服務後
* 當有訊息發送給Bot
* Azure會把訊息作為一個事件
* 轉發去這個Web Api


## Azure Bot申請流程
1. 進入Azure 主控台
![主控台畫面](/picture/01.JPG)
2. 選擇Bot服務
![Bot服務1](/picture/02.JPG)
![Bot服務2](/picture/03.JPG)
3. * Web App Bot表示你要使用Bot Channel的服務，並且透過Azure AppService架設Web Api
   * Bot Channels Registration表示你只單純使用Bot Channel的服務(代表你會有自己的Web Api Server)

![Bot服務3](/picture/04.JPG)

# Web App Bot
![Web App Bot](/picture/05.JPG)

* 這個選項實際上會在你的Azure同時幫你建立**Bot**跟**AppService**兩個方案
* 選這個有一個好處是他可以**幫你自動產生範本裡面附帶appId跟金鑰**
* 建議第一次使用這個選項，透過他自動產生範本功能


###### 設定頁面
![Web App Bot設定頁面1](/picture/07.JPG)
![Web App Bot設定頁面1](/picture/08.JPG)

1. **Bot控制代碼**:唯一識別碼，這裡可直接輸入專案名稱
2. 訂閱帳戶:這裡以學術帳號示範，如果是一般帳號可能要綁信用卡
3. 資源群組:如果之前沒有的話在這裡要建一個
4. 位置:沒特殊需求就選亞洲
5. **定價層:這裡要特別注意，要選F0，否則是會產生額外費用的**
6. **應用程式名稱**:這個名稱會當作你建立的AppService網域
7. 機器人範本:依照需求選擇範本(這次使用的是Echo Bot)
8. **App Service方案/位置:這裡也要特別注意，如果你使用他自動幫你新建的，預設他會幫你選S1，記得建完後要去這個方案改回F0，否則也會有額外的費用**
9. Application Insights:預設
10. Application Insights位置:預設
11. Microsoft應用程式ID和密碼:預設
12. 設定完上面的參數建立後，可依下列流程完成Hello World，** 產生範本-> 開啟範本並架設-> 使用ngrok取得實體ip-> 設定Api網址-> 在teams中啟用bot **

###### 產生範本
![Web App Bot設定頁面1](/picture/09.JPG)

###### 設定Api網址
* 假設使用ngrok，每次改變都要重新設置
* 這裡預設會是Azure App Servcie的網址，也可以直接使用產生的範本，自己架設的Web Api網址
* 改變後要等幾分鐘才會生效
![Web App Bot設定頁面1](/picture/10.JPG)

###### 在teams中啟用bot
![在teams中啟用bot1](/picture/11.JPG)
![在teams中啟用bot2](/picture/12.JPG)
![在teams中啟用bot3](/picture/13.JPG)
* 最後一步點擊teams圖標後，會問你要不要開起teams，開啟後自動把bot加入對話，這時候bot會收到OnConversationUpdateActivityAsync事件
# Bot Channels Registration
![Web App Bot](/picture/06.JPG)
* 這個方案只負責幫你把用戶訊息轉發到你的Bot Web Api
* 如果你已經熟悉Web App Bot，**差別**其實就是你要**自己去抓Bot範本並把AppId及金鑰貼在appsetting，且自己架設Web Api**
