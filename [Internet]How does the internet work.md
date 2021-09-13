# 인터넷의 동작 원리

:writing_hand: *write by shinjoenghea*


## 인터넷

- **컴퓨터로 연결하여 TCP/IP라는 통신 프로토콜을 이용해 정보를 주고받는 컴퓨터 네트워크**
- Vint Cef와 Bob Kahn의 설계로 시작되었으며, 미국 국방 연구 프로젝트인 ARPANET의 실험 결과로 탄생했다.
- 인터넷은 **수 많은 독립적으로 운영되는 네트워크로 구성**되어 있으며, 패킷 라우팅 방법 또는 네트워크의 일부를 구축할 장소, 사용자들간의 상호작용까지 완전히 분산되어, 결정하는 **중앙 통제가 존재하지 않는다**.

<BR>

## 인터넷의 작동 방식

  1. 도메인 이름을 입력하면 브라우저가 **해당 IP주소를 DNS서버에 요청** 한다.
  2. DNS서버에서는 도메인 이름에 해당하는 **IP주소를 반환** 한다.
  3. IP주소를 받은 후 브라우저는 해당 요청을 각 서버로 전달한다.
  4. 서버가 특정 웹사이트에 대한 접속 요청을 받으면 **패킷단위로 데이터의 흐름이 시작된다.**<br>
      &nbsp; &nbsp;<sub>패킷 : 통신망을 통해 전송하기 쉽도록 자른 데이터의 전송 단위)</sub>
  5. 데이터는 **광섬유 케이블** 을 통해 디지털 형식(광펄스 형식)으로 전송된다.<br>
     (참고 : 광섬유 케이블은 항상 땅 밑에 위치해 있다.)
  6. 광섬유 케이블의 빛 신호는 **라우터를 통해 전기 신호로 변환** 된다.
  7. 이더넷 케이블을 사용하여 **노트북에 전기 신호를 전송** 한다.

<BR>

## 인터넷의 변화

*앞으로 소개하는 예시에서의 '연결'은 유선과 무선에 차이가 없다*

#### 1. 단순한 네트워크

**1) 1:1 연결**

- 두 대의 컴퓨터가 통신이 필요할 때, 우리는 다른 컴퓨터와 물리적으로 (보통 이더넷 케이블, 일반적으로 우리가 말하는 '랜선') 또는 무선으로 (WIFI or Bluetooth) 연결되어야 한다.
- 모든 현대 컴퓨터들은 이러한 연결 중 하나를 이용하여 연결해야만 통신할 수 있다.
- 네트워크는 두 대의 컴퓨터로 제한되지 않는다.


![img](https://media.vlpt.us/images/doomchit_3/post/0adb405a-6fab-48e2-b4d0-762c255b9d9c/1.png)



**2) N:N 연결**

- 네트워크 연결은 2대의 컴퓨터로 제한되지 않는다. 이와 같은 방식으로 원하는 만큼 컴퓨터를 연결할 수 있다. 
- 하지만 이렇게 계속해서 연결할 경우 빠르게 복잡성이 늘어난다.
- Ex_) 10대의 컴퓨터를 연결하려는 경우라면 컴퓨터당 9개의 플러그와 45개의 케이블이 필요하다.

![img](https://media.vlpt.us/images/doomchit_3/post/347572a8-3b5b-4b72-89fb-40091d17df10/2.png)



**3) 라우터의 연결**

- 위의 문제를 해결하기 위해 사용하는 것이 **라우터(Router)** 이다. <br>
  &nbsp; &nbsp; <sub>라우터 : 네트워크와 네트워크 간의 경로를 설정하고 가장 빠른 길로 트래픽을 이끌어주는 네트워크 장치</sub>

- 위의 그림과 같이 라우터를 시스템에 추가하면 10대의 컴퓨터 네트워크에는 10개의 케이블만이 필요하다.

![img](https://media.vlpt.us/images/doomchit_3/post/6334de99-3d4d-427d-a31b-74b485650f3d/3.png)



####  2. 네트워크 속의 네트워크(모뎀과 ISP의 연결)

- 그렇다면 수 십억 대의 컴퓨터를 연결하려면 라우터에 그만큼의 플러그로 연결해야 할까?
  일단, 라우터 자체로도 그렇게 확장할 수 없을 것이다. 그렇다면 어떻게 해야할까?
- 라우터 또한 컴퓨터라는 점을 기억하자.
- 따라서 두 대 이상의 라우터도 연결할 수 있다

![img](https://media.vlpt.us/images/doomchit_3/post/300c095e-770e-4091-bdb7-b17d14c1b691/4.png)

- 즉, 컴퓨터를 라우터에 연결하고, 라우터에서 라우터로 연결함으로써 연결을 무한히 확장할 수 있다.

![img](https://media.vlpt.us/images/doomchit_3/post/4676dc11-face-4266-92f2-68f51c38bbe0/internet-schema-5.png)

- 이러한 네트워크는 우리가 인터넷이라고 부르는 것과 유사하지만 놓치고 있는 한가지가 있다. 

- 바로, 물리적 한계이다.

- 상대적으로 많은 컴퓨터에 적은 케이블을 통해 연결이 가능하지만, 아주 먼 곳까지 계속해서 라우터를 유선 케이블로 연결 하는 것은 비효율적이다.

- 이 문제를 해결하기 위해 전력 및 전화와 같이 이미 집에 연결된 케이블인 **전화선** 을 이용하기로 했다.

- 네트워크와 전화시설을 연결하기 위해선, **모뎀(MODEM, MOdulator and DEModulator)** 이라는 특수 장비가 필요하다.<br>
  &nbsp; &nbsp;  <sub>모뎀 : 네트워크 정보를 전화시설에서 처리할 수 있는 정보로 변환해주는 장비, 그 반대의 경우도 마찬가지 이다.</sub>

![img](https://media.vlpt.us/images/doomchit_3/post/37085ff4-19f0-4c3b-9ac2-58a520cf52c6/6.png)



- 모뎀을 통해 우리의 네트워크는 전화 시설에 연결된다. 

- 하지만, 아직까지 컴퓨터가 보낸 메시지가 도달해야 할 컴퓨터(혹은 네트워크)까지 도달하지 않은 상태다.

- 이 메시지가 전달되려면 **인터넷 서비스 제공 업체(ISP, Internet Service Provider)** 에 연결되어야 한다.<br>
   &nbsp; &nbsp;<sub>ISP :  함께 연결되는 몇몇 특수한 라우터를 관리하고 다른 ISP의 라우터에도 액세스할 수 있는 회사 / 우리나라에는 SK텔레콤, KT, LG유플러스 등이 있다.</sub>

- 따라서 우리 네트워크의 메시지는 ISP 네트워크의 네트워크를 통해 대상 네트워크로 전달된다. 인터넷은 아래 그림과 같이 이러한 전체 네트워크 인프라로 구성된다.

![img](https://media.vlpt.us/images/doomchit_3/post/63e641a9-59db-4130-9e96-d97ede4aa3b8/7.png)

<BR>

:pushpin: 인터넷 작동원리에서 언급되었던 광케이블과 같은 데이터를 전송하는 방식에 대해 알고싶다면 이 [링크](https://youtu.be/ZhEf7e4kopM) 를 통해 확인하자.

:pushpin: 인터넷 작동원리에서 언급된 [Domain Name](./[Internet]What%20is%20Domain%20Name.md)과 [DNS]([Internet]DNS%20and%20how%20it%20works.md)에 대해서 알아보도록 하자.

-----------

### :clipboard: [참조] Reference

- [roadmap.sh - How does the internet work?](https://roadmap.sh/guides/what-is-internet)
- [[Internet] 인터넷? 개념잡기 작동원리-IMBETPY](https://velog.io/@doomchit_3/Internet-internet-what-how-IMBETPY)
- [위키백과-인터넷](https://ko.wikipedia.org/wiki/%EC%9D%B8%ED%84%B0%EB%84%B7)
- [[나를 위한 기록]-인터넷은 어떻게 작동될까요?](https://iamhyuki.github.io/internet/%EC%9D%B8%ED%84%B0%EB%84%B7%EC%9D%80-%EC%96%B4%EB%96%BB%EA%B2%8C-%EB%8F%99%EC%9E%91%ED%95%98%EB%8A%94%EA%B0%80/)
- [Elliot-[네트워크 용어] 라우터란?(Router)](https://puzzle-puzzle.tistory.com/entry/네트워크-용어-라우터란-Router)

