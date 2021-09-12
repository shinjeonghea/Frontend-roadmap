# DNS& DNS의 동작 원리

:writing_hand: *write by shinjeonghea*

**:pushpin: DNS를 알기전에 [Domain Name](https://github.com/shinjeonghea/GC-Study/blob/main/%5BInternet%5DWhat%20is%20Domain%20Name.md)에 대한 내용을 먼저 보도록 하자. **

<br>

## DNS

- **Domain Name System의 약자**
- **Domain Name을 IP로 변환하여 컴퓨터가 서로 통신할 수 있게 하는 시스템**
- 전화번호부와 같은 기능을 한다는 예시가 많다.

<BR>

## DNS 서버

- DNS안에서 각자의 역할을 하는 서버
- IP 주소를 특정 Domain Name과 같다고 저장하고, 사용자들이 Domain Name을 검색했을 때 IP 주소로 연결되도록 한다.



## DNS 동작 과정 - 1

<img src="https://gentlysallim.com/wp-content/uploads/2021/03/210111_02.jpg" width="350">

1. 브라우저를 통해 유저가 Nesite.com을 검색한다.
2. DNS 서버로 도메인 주소가 전달한다.
3. 서버는 내부에서 도메인 주소로 "Nesite.com = 12.123.123.123" 찾아낸다.
4. 브라우저에 12.123.123.123 IP 주소를 가진 호스팅 서버로 가도록 지시한다.

5. 호스팅 서버가 브라우저의 요청을 받고 웹 사이트를 출력하여 보이게 한다.

<BR>

##### 실제로는 도메인의 수가 너무 많기 때문에, DNS 서버 종류를 계층화해서 단계적으로 처리한다.

<BR>

## DNS 서버 종류

<img src="https://gentlysallim.com/wp-content/uploads/2021/03/210111_03.jpg" width=600>

- **Root DNS Server**

  - ICANN이 직접 관리하는 절대 서버

  - TLD DNS 서버 IP들을 저장해두고 안내하는 역할을 한다.

    <small>ICANN : 국가, 단체 또는 ISP에게 IP 주소 공간을 할당 및 관리하고 TLD의 신규 등록 및 관리 업무를 수행하는 국제 인터넷 주소 관리 기관<small>

- **TLD DNS Server**

  - 도메인 등록 기관(Registry)이 관리하는 서버
  - Authoritative DNS 서버 주소를 저장해두고 안내하는 역할을 한다.
    -  어떤 도메인 묶음이 어떤 Authoritative DNS Server에 속하는지 아는 이유는 도메인 판매 업체(Registrar)의 DNS 설정이 변경되면 도메인 등록 기관(Registry)으로 전달이 되기 때문이다.

- **Authoritative DNS Server** 

  - 실제 개인 도메인과 IP 주소의 관계가 기록/저장/변경되는 서버
  - 그래서 권한의 의미인 Authoritative가 붙였다.
  - 일반적으로 **도메인/호스팅 업체의 ‘네임서버’**를 말하지만, 개인 DNS 서버 구축을 한 경우에도 여기에 해당한다.

- **Recursive DNS Server **

  - 인터넷 사용자가 가장 먼저 접근하는 DNS 서버
  - 위 3개의 DNS 서버를 매번 거친다면 비효율적이므로, 한 번 거친 후 얻은 데이터를 일정 기간(TTL/Time to Live) 동안 **캐시라는 형태로 저장해 두는 서버**
  - 직접 도메인과 IP 주소의 관계를 기록/저장/변경하지는 않고 캐시만을 보관하기 때문에, Authoritative와 비교되는 의미로 반복의 Recursive를 붙였다.
    - 대표적으로 KT/LG/SK와 같은 **ISP(통신사) DNS 서버**가 있고, 브라우저 우회 용도로 많이 쓰는 구글 DNS, 클라우드플레어와 같은 Public DNS 서버가 있다.

- 브라우저는 캐시가 저장된 Recursive 서버를 사용하고, 실제 네임서버를 설정하는 곳은 Authoritative 서버

<br>

## DNS 동작 과정 - 2

<img src="https://gentlysallim.com/wp-content/uploads/2021/03/210111_03_2.jpg" width=600>

1. 브라우저에서 Nestie.com을 검색한다.
2. 브라우저는 사용하고 있는 통신사 DNS 서버에게 도메인 네임에 해당하는 IP 주소를 요청한다.
3. ISP 서버에서 캐시 데이터가 없다면, 루트 DNS 서버에 위치를 요청한다.
4. 루트 DNS 서버는 도메인의 TLD를 보고(여기서는 .com) 최상위 도메인을 관리하는 TLD DNS 서버 주소로 안내한다.
5. ISP 서버는 TLD DNS 서버에게 다시 주소를 요청한다.
6. TLD DNS 서버는 도메인 네임과 관계를 맺는 IP 주소를 가진 Authoritative DNS 서버 주소(여기서는 가비아 DNS 서버)로 안내한다.
7. ISP 서버가 가비아 DNS 서버에 다시 주소를 요청한다.
8. 가비아 서버는 "Nesite.com = 12.123.123.123"이라는 정보를 확인하고 IP를  ISP 서버에 넘겨준다.
9. 동시에, ISP 서버는 해당 정보를 캐시로 기록한다.
10. ISP 서버는 브라우저에게 12.123.123.123 IP 주소를 안내한다.
11. 호스팅 서버는 브라우저가 받은 IP 주소에 대한 웹사이트의 출력을 요청받고 보이게 한다.

<BR>

**:pushpin: 동작원리에서 계속 언급되었던 [호스팅 서버](./[Internet]What is hosting.md) 란 무엇일까?**

<BR>

-----------

##### :clipboard: [참조] Reference

- [AWS- DNS란 무엇입니까?](https://aws.amazon.com/ko/route53/what-is-dns/)
- [Kyun2da.dev- DNS란 무엇인가?](https://kyun2da.dev/CS/dns%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80/)
- [g's - DNS란 뭐고, 네임서버란 뭔지 개념 정리](https://gentlysallim.com/dns%eb%9e%80-%eb%ad%90%ea%b3%a0-%eb%84%a4%ec%9e%84%ec%84%9c%eb%b2%84%eb%9e%80-%eb%ad%94%ec%a7%80-%ea%b0%9c%eb%85%90%ec%a0%95%eb%a6%ac/)

- [해시넷 - ICANN](http://wiki.hash.kr/index.php/ICANN)