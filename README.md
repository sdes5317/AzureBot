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
![主控台畫面](/picture/01.jpg)
2. 選擇Bot服務
![Bot服務1](/picture/02.jpg)
![Bot服務2](/picture/03.jpg)
3. * Web App Bot表示你要使用Azure AppService架設Web Api及使用Bot Channel的服務
   * Bot Channels Registration表示你只單純使用Bot Channel的服務
![Bot服務3](/picture/04.jpg)

#### Web App Bot
![Web App Bot](/picture/05.jpg)
* 這個選項會同時幫你建立**Bot**跟**AppService**
* 選這個有一個好處是他可以**幫你自動產生範本裡面附帶appId跟金鑰**

#### Bot Channels Registration
![Web App Bot](/picture/06.jpg)
* 如果你已經熟悉Web App Bot，**差別**其實就是你要**自己去抓Bot範本並把AppId及金鑰貼在appsetting，且自己架設Web Api**
