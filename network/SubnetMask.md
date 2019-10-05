# **Subnet Mask**

## 작성자
[![tdm1223](https://avatars1.githubusercontent.com/u/21440957?s=100&v=4)](https://github.com/tdm1223)
[![rlatjdwo555](https://avatars0.githubusercontent.com/u/28692938?s=100&v=4)](https://github.com/rlatjdwo555)
[![Stupid07](https://avatars1.githubusercontent.com/u/35564566?s=100&v=4)](https://github.com/Stupid07)

## Subnetting ?
- 기존의 class로 분리하는 IP 주소 체계에서, **네트워크 부분**과 **호스트 부분**으로 IP 영역대를 분리하게 된다.
- 분할하는 이유는 브로드캐스트에서 성능저하가 발생하기 때문이다.
- 네트워크 부분이 같다면 같은 네트워크에 포함되어있는 호스트이고, 이 네트워크 부분을 서브넷 마스크를 통해 구분하게 된다.

## Subnet ?
- 특정 지역에서 관리되는 IP 영역을 몇개의 영역으로 나누어서 관리하는 것

## Subnet Mask ?
- 특정 IP와 비트수를 이용해 네트워크 영역을 구분하게 된다.
``` 
네트워크 영역 : 128.2.1.0/23
IP : 128.2.1.0
Subnet Mask : 255.255.254.0 (1을 왼쪽부터 23개)
IP를 비트로 표현
-> 10000000 00000010 00000001 00000000
Subnet Mask를 비트로 표현
-> 11111111 11111111 11111110 00000000
두개의 영역을 논리곱 연산
-> 10000000 00000010 00000000 00000000
의 IP가 형성되고 
10000000 00000010 0000000 네트워크 부분
0 00000000 ~ 1 11111111 호스트 부분
뒤의 9비트의 모든 경우의수가 해당 서브넷 네트워크 영역에 포함된다.
```

## 사용 예제
- 네트워크 영역이 128.2.1.0/23로 구분되어 있을 때, 브로드 캐스트를 하면 해당 호스트 부분 최소값부터 최대값까지에 뿌려지게된다.
- 라우팅 테이블에서 128.2.1.0/23은 3번 포트로 전달하도록 되어있다면 128.2.1.192 가 목적지인 패킷은 3번 포트의 영역에 해당되므로 3번 포트로 포워딩 하게 된다.

## Link
- [나무위키](https://namu.wiki/w/%EC%84%9C%EB%B8%8C%EB%84%B7%20%EB%A7%88%EC%8A%A4%ED%81%AC)