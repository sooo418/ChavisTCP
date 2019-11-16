## Chavis 구조 소개

### **프로젝트 동작방식**

[![img](https://camo.githubusercontent.com/3ca4f3ab0adeb14d8f35db57d8e4daff2022e455/68747470733a2f2f706f737466696c65732e707374617469632e6e65742f4d6a41784f5445774d5468664d6a55322f4d4441784e5463784d7a59314e444d7a4f44497a2e4b6b75332d34336a6d452d48495f3548424133785f5731524c655835495f376b38566d5f394953696d4a55672e7a3042334c5738354f77586e444d4f6f4a39746d55516252307737306f5376305271314956304955664959672e504e472e656864776e6430322f696d6167652e706e673f747970653d77373733)](https://blog.naver.com/PostView.nhn?blogId=ehdwnd02&logNo=221681605957&categoryNo=26&parentCategoryNo=0&viewDate=&currentPage=1&postListTopCurrentPage=1&from=postView&userTopListOpen=true&userTopListCount=5&userTopListManageOpen=false&userTopListCurrentPage=1#)

동작 방식은 위의 그림처럼 서버, 자동차(CAN장비,LattePanda), 사용자app, 정비소app으로 구성되어 서로 통신을 하며 동작합니다.

### **프로젝트 구성도**

[![img](https://camo.githubusercontent.com/8f07748199ba98f6d944b026fb2b0bc6386f9741/68747470733a2f2f706f737466696c65732e707374617469632e6e65742f4d6a41784f5445774d5468664d6a49332f4d4441784e5463784d7a59314d7a41334e7a45332e4642646f396a6d52466f4c4556354f6e365f506e384c356536453677534e36335950675963454478436a63672e324c64797474384a4e684d39717a3534515842454c6d705a54745477746d5679494d35484d6b372d323377672e504e472e656864776e6430322f696d6167652e706e673f747970653d77373733)](https://blog.naver.com/PostView.nhn?blogId=ehdwnd02&logNo=221681605957&categoryNo=26&parentCategoryNo=0&viewDate=&currentPage=1&postListTopCurrentPage=1&from=postView&userTopListOpen=true&userTopListCount=5&userTopListManageOpen=false&userTopListCurrentPage=1#)

구성도를 보면 구성요소들이 어떤 방식으로 통신하는지 어떤 구성요소들이 있는지 알 수 있도록 표시했다.

서버는 TCP통신의 서버와 HTTP통신의 서버 둘로 나눴습니다.

### **프로젝트 DB구조**

[![img](https://camo.githubusercontent.com/4ae276bc100482857293a3013ef9074eaa8dbd83/68747470733a2f2f706f737466696c65732e707374617469632e6e65742f4d6a41784f5445774d5468664d5459782f4d4441784e5463784d7a63334f5459794e7a55332e793152542d636130375158494836674b55754e4e493374503249324b754b4c6e472d3945686c56612d3267672e6a517472675f4f484534314a2d4e676a6d33515a697333317a44635f416a6637773746564b317248676d59672e504e472e656864776e6430322f696d6167652e706e673f747970653d77373733)](https://blog.naver.com/PostView.nhn?blogId=ehdwnd02&logNo=221681605957&categoryNo=26&parentCategoryNo=0&viewDate=&currentPage=1&postListTopCurrentPage=1&from=postView&userTopListOpen=true&userTopListCount=5&userTopListManageOpen=false&userTopListCurrentPage=1#)

위의 그림과 같이 6개의 DB Table을 사용하였습니다.



## Chavis TCP Server 소개

Charvis TCP Server는 차량 데이터를 관리하며 차량 데이터를 기반으로 차량의 부속품들의 교체 시기가 되었을 때 사용자앱에 알림을 보내줍니다.

TCP소켓을 사용하여 정비사 및 사용자 용 앱, ServerLattePanda와 정해진 프로토콜을 통해 데이터를 주고 받습니다.

정비사용 앱으로 사용자에게 허가된 경우에만 원격키를 사용하여 TCP서버로 차량의 문을 여는 메시지를 보내고 TCP 서버는 적절한 차량의 문을 여는 메시지를 보내어 차량의 문을 열 수 있습니다.

