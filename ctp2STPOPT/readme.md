# CTP程序接入华鑫证券STP奇点股票期权柜台

openctp已经发布了华鑫证券STP奇点股票期权柜台的CTP兼容接口，以CTP接口对STPOPT接口进行封装，使得CTP程序无需任何修改，只是更换一下CTP动态库，就可以接入华鑫证券股票期权柜台ETF期权等商品。

openctp的动态库（dll、so等文件）只是对华鑫证券接口的简单封装，不是经过openctp的模拟服务器进行转发，而是直接调用华鑫证券的dll与柜台进行交互，所以登录用户名、密码均为华鑫证券柜台用户名、密码，模拟账户申请需至华鑫证券官网申请，该接入方式同样支持实盘。

当前版本基于的华鑫证券股票期权接口版本：API_C++_交易_v1.3.3_20220908。

## 接入方式
下载openctp相应CTP版本的dll，交易dll有两个文件，thosttraderapi_se.dll为openctp的封装dll，fastsptraderapi.dll为华鑫证券发布的接口dll，行情也同样是有两个，交易与行情的dll互相独立，可以只接交易或只接行情。

行情的dll请至openctp的华鑫证券股票接口目录下载，华鑫证券的股票、两融、期权柜台均使用同一套行情接口，这里不重复发布。

华鑫证券股票期权的7x24测试环境：

行情前置地址：tcp://210.14.72.16:9402

交易前置地址：tcp://210.14.72.17:15500

华鑫证券N视界模拟平台是跟simnow类似的证券模拟平台，采用与CTP类似的开放式API，更多信息请至官网了解：http://www.n-sight.com.cn/

[CTP开源客户端TextTrader](https://github.com/krenx1983/TextTrader)的接入效果：
![M8$B1FGSOB 3A) T7%PUP P](https://user-images.githubusercontent.com/83346523/128633288-e70f2af9-7106-46a8-bda1-4859c61adf5b.png)
![KLU1WTF~M{{K2VGA28TX VL](https://user-images.githubusercontent.com/83346523/128633135-5173ffa0-762f-40a6-8cbd-74eae4105e06.png)
![$`}{JD~M_S {C4Y9T@O`LQ6](https://user-images.githubusercontent.com/83346523/128633324-471c81f8-8b56-47bb-a9f7-c52c7a1843c6.png)
![Q8U5YDF$4)VSBLX9A5W%U6N](https://user-images.githubusercontent.com/83346523/128633163-c7b532d9-6cbd-4abf-83fa-e9b34d59c112.png)
![F}X6O 2{E83J4OF8XJ)~4AV](https://user-images.githubusercontent.com/83346523/128633183-cf372e87-fa11-40cb-a34d-bc9c562b2bf7.png)
![)Y96T659_YW Y_QZHBUW@}Q](https://user-images.githubusercontent.com/83346523/128633169-94942480-c4bf-4e98-b554-2c3496c0956e.png)