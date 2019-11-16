### [Can Protocol] => ServerLattePanda, CarLattePanda

### [chavis] => TCP 서버

### [SpeedView] => 차량 인포테이먼트 앱



## Chavis CAN통신 소개

라떼판다를 이용하여 CAN장비를 연결 후 두 개의 CAN장비를 연결하여 '커넥티드 카'라고 가정하여 Serial통신을 진행하였습니다.



### TCP Server(TCP서버)

[![img](https://blogfiles.pstatic.net/MjAxOTEwMThfMTY1/MDAxNTcxMzc4MzE4MDI2.6hZouwYqzo0wfoxfBjfJmlW4qz4kvpD314WqhEZNm6Ag.AkleAA1lIqlO0vVPzm0mbM5NP9q0t88-uazuBvMqLzgg.PNG.ehdwnd02/image.png?type=w1)](https://blog.naver.com/PostView.nhn?blogId=ehdwnd02&logNo=221681723144&categoryNo=0&parentCategoryNo=0&viewDate=&currentPage=1&postListTopCurrentPage=1&from=postView&userTopListOpen=true&userTopListCount=5&userTopListManageOpen=false&userTopListCurrentPage=1#)

TCP Server의 JavaFX로 "TCP 서버 시작" 버튼을 클릭하여 서버를 구동하고 ServerLattePanda의 JavaFX에서 "COM포트, TCP 서버 연결" 버튼을 클릭하고 CarLattePanda의 JavaFX에서 "COM포트 연결" 버튼을 클릭하여야 해당 이미지처럼 JavaFX에 메시지들이 출력됩니다.



### ServerLattePanda(서버와 통신하는 차량의 최상위 ECU)

[![img](https://blogfiles.pstatic.net/MjAxOTEwMThfOTIg/MDAxNTcxMzc4MzU0ODI1.SG-SpZYZlq1u_XramP9s7hdUv3fL73yYBaRnJ1B0qx4g.kPzepJSB1YQJHlFape2ionkYTmjLUewZdV_bb0RvU_wg.PNG.ehdwnd02/image.png?type=w1)](https://blog.naver.com/PostView.nhn?blogId=ehdwnd02&logNo=221681723144&categoryNo=0&parentCategoryNo=0&viewDate=&currentPage=1&postListTopCurrentPage=1&from=postView&userTopListOpen=true&userTopListCount=5&userTopListManageOpen=false&userTopListCurrentPage=1#)

ServerLattePanda의 JavaFX로 "COM포트, TCP 서버 연결" 버튼을 클릭해 서버와 COM포트 연결하고 CarLattePanda의 JavaFX에서 "COM포트 연결" 버튼을 클릭하여야 위의 이미지처럼 JavaFX에 메시지들이 출력됩니다.



[![img](https://blogfiles.pstatic.net/MjAxOTEwMThfMzkg/MDAxNTcxMzc4MzY0ODg2.SUEAabcweVY_QEmPwOSMZHaZIQn2rkGSCs3LYG5PW9kg.7VynaFgYONp04Ijwxg6Xx0WIBXjcGSG3ov1NAZEUa8Qg.PNG.ehdwnd02/image.png?type=w1)](https://blog.naver.com/PostView.nhn?blogId=ehdwnd02&logNo=221681723144&categoryNo=0&parentCategoryNo=0&viewDate=&currentPage=1&postListTopCurrentPage=1&from=postView&userTopListOpen=true&userTopListCount=5&userTopListManageOpen=false&userTopListCurrentPage=1#)

CarLattePanda에서 "주행 시작" 버튼을 클릭시 위의 이미지처럼 메시지를 연속적으로 받게된다. ECU에서는 받은 메시지를 서버는 TCP소켓으로 차량인포테이먼트 앱에는 UDP통신으로 데이터를 지속적으로 보내줍니다.



### CarLattePanda(차량을 제어하는 ECU)

[![img](https://blogfiles.pstatic.net/MjAxOTEwMThfNCAg/MDAxNTcxMzc4MzcyMzI3.1qKVFeTgpzvvTsWWS1ZMLZ9eht2P5oynMV5Db2Gx_lAg.av1mx7FN7yQOrY0zrW3ZNh21rXMCp2M8RSRLYCljuMwg.PNG.ehdwnd02/image.png?type=w1)](https://blog.naver.com/PostView.nhn?blogId=ehdwnd02&logNo=221681723144&categoryNo=0&parentCategoryNo=0&viewDate=&currentPage=1&postListTopCurrentPage=1&from=postView&userTopListOpen=true&userTopListCount=5&userTopListManageOpen=false&userTopListCurrentPage=1#)

CarLattePanda의 JavaFX로 서버와 ServerLattePanda가 모두 작동중일 때 "COM포트 연결" 버튼을 눌러 모든 준비 동작이 끝나야만 합니다.

[![img](https://blogfiles.pstatic.net/MjAxOTEwMThfMjM2/MDAxNTcxMzc4MzgwMDU5.yui8D1xw6ZDrnH7cEziN-4puRgn-qhijfnTcz_HFoqwg.1-KsFn3AgnboY6ht06eR_cQbT48CzFsUm7YekjQksyAg.PNG.ehdwnd02/image.png?type=w1)](https://blog.naver.com/PostView.nhn?blogId=ehdwnd02&logNo=221681723144&categoryNo=0&parentCategoryNo=0&viewDate=&currentPage=1&postListTopCurrentPage=1&from=postView&userTopListOpen=true&userTopListCount=5&userTopListManageOpen=false&userTopListCurrentPage=1#)

"주행 시작" 버튼을 눌러 Thread를 하나 실행시켜 데이터를 지속적으로 ServerLattePanda쪽에 메시지를 보내준다. "주행 중지" 버튼을 눌러 Thread를 중지시킬 수 있습니다.

[![img](https://blogfiles.pstatic.net/MjAxOTEwMThfMjkg/MDAxNTcxMzc4MzkyMjQ3.pSAfeXCTcXLWxsOpb7JHZ8632vIbNeskavslaofd2fgg.saiUE4Carf3r8Ko9V4fTb4REd00zk7nmBaXedEYDBpQg.PNG.ehdwnd02/image.png?type=w1)](https://blog.naver.com/PostView.nhn?blogId=ehdwnd02&logNo=221681723144&categoryNo=0&parentCategoryNo=0&viewDate=&currentPage=1&postListTopCurrentPage=1&from=postView&userTopListOpen=true&userTopListCount=5&userTopListManageOpen=false&userTopListCurrentPage=1#)

위의 이미지는 실제 차량으로 하는 프로젝트가 아니기 때문에 JavaFX에 메시지를 띄워준 것이다. 정비사용 앱에서 정비를 할 때 차문을 여는 버튼을 하나 만들었는데 해당 버튼을 클릭시 서버로 메시지를 보내 서버에서는 차량(CarLattePande)에게 차문을 열도록 메시지를 보내 구현했습니다.



### 차량인포테이먼트 화면(차량의 현재 정보를 실시간으로 확인할 수 있는 앱)

[![img](https://blogfiles.pstatic.net/MjAxOTEwMThfMjY2/MDAxNTcxMzgwNjI4OTc0.gpp7QrX91kP80WfVH8wgFZG1L5e1WsT68H3SGRZoDVcg.DiRqECC3DU0ErjMs-aCYUxRDUPROHtxx0GaLcQ9EMIwg.PNG.ehdwnd02/image.png?type=w1)](https://blog.naver.com/PostView.nhn?blogId=ehdwnd02&logNo=221681723144&categoryNo=0&parentCategoryNo=0&viewDate=&currentPage=1&postListTopCurrentPage=1&from=postView&userTopListOpen=true&userTopListCount=5&userTopListManageOpen=false&userTopListCurrentPage=1#)

ServerLattePanda로부터 UDP 통신으로 데이터를 받아 데이터의 변동을 시각화시켜 사람이 보기 쉽도록 만든 APP입니다.

