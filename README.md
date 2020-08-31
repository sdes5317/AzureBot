# AzureBot
練習實作一個Azure Bot


## Azure Bot服務架構說明(此文章於2020/08/26產生，實際使用可能因改版而無效)
* Azure Bot的框架本體是一個Web Api範本(WebHook)
* 把架設的Web Api連結設定在Bot服務後
* 當有訊息發送給Bot
* Azure會把訊息作為一個事件
* 轉發去這個Web Api

## Azure Bot申請概況
* 在選取Azure Bot範本時，有一個地方要先釐清，架設的Web Api要
  1. 架設在Azure AppService?
  2. 架設在自己的電腦?

* 這個部分會決定等一下選取的範本

## Azure Bot申請流程
1. 進入Azure 主控台
![主控台畫面](/picture/01.JPG)
2. 選擇Bot服務
![Bot服務1](/picture/02.JPG)
![Bot服務2](/picture/03.JPG)
3. * Web App Bot表示你要使用Azure AppService架設Web Api及使用Bot Channel的服務
   * Bot Channels Registration表示你只單純使用Bot Channel的服務
![Bot服務3](/picture/04.JPG)

#### Web App Bot
![Web App Bot](/picture/05.JPG)
* 這個選項會同時幫你建立**Bot**跟**AppService**
* 選這個有一個好處是他可以**幫你自動產生範本裡面附帶appId跟金鑰**
* 建議第一次使用這個選項，透過他自動產生範本功能
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

###### 產生範本
![Web App Bot設定頁面1](/picture/09.JPG)
###### 當Web Api網址有改變時
* 這裡預設會是Azure App Servcie的網址，也可以直接使用自己架設的Web Api網址
* 改變後要等幾分鐘才會生效
![Web App Bot設定頁面1](/picture/10.JPG)

#### Bot Channels Registration
![Web App Bot](/picture/06.JPG)
* 如果你已經熟悉Web App Bot，**差別**其實就是你要**自己去抓Bot範本並把AppId及金鑰貼在appsetting，且自己架設Web Api**
