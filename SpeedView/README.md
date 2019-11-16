## 차량 인포테이먼트 앱 소개(SpeedView API)

![img](https://postfiles.pstatic.net/MjAxOTEwMThfMjY2/MDAxNTcxMzgwNjI4OTc0.gpp7QrX91kP80WfVH8wgFZG1L5e1WsT68H3SGRZoDVcg.DiRqECC3DU0ErjMs-aCYUxRDUPROHtxx0GaLcQ9EMIwg.PNG.ehdwnd02/image.png?type=w773)

차량 데이터의 변동을 시각적으로 볼 수 있도록 API를 활용하여 만들었다.

실제 UDP 통신으로 받는 코드는 SpeedView\app\src\main\java\com\github\anastr\speedview\Server.java 파일이고 SpeedView\app\src\main\java\com\github\anastr\speedview\MainActivity.java 파일에서 Server class를 이용하여 정해진 API method를 사용하여 데이터의 변동을 화면에 표시해준다.

