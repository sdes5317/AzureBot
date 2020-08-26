# AzureBot
練習實作一個Azure Bot


##Azure Bot服務架構說明(此文章於2020/08/26產生，實際使用可能因改版而無效)
Azure Bot的框架本體是一個Web Api範本(WebHook)
把架設的Web Api連結設定在Bot服務後
當有訊息發送給Bot
Azure會把訊息作為一個事件
轉發去這個Web Api

##Azure Bot申請概況
在選取Azure Bot範本時，有一個地方要先釐清
架設的Web Api要
1.架設在Azure AppService
2.架設在自己的電腦

這個部分會決定等一下選取的範本


