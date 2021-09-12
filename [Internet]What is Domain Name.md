# Domain Name

:writing_hand: *write by shinjeonghea*


## 도메인 네임

- 인터넷 인프라의 핵심 부분이며, 인터넷에서 사용할 수 있는 **모든 웹 서버에 대해 사람이 읽을 수 있는 주소를 제공** 한다.
- 넓은 의미로는 네트워크상에서 컴퓨터를 식별하는 호스트 명
- 좁은 의미로는 도메인 레지스트리에 등록된 이름 

<br>

## 도메인 네임의 발생

- 인터넷에 연결된 모든 컴퓨터는 고유의 IP 주소를 통해 접근가능하다.

  <small> IP 주소: 인터넷에 연결되어있는 장치들을 각각 식별하기위해 사용하는 특수한 번호<small>

- 컴퓨터는 IP 주소를 쉽게 다루지만, 인간은 IP 주소를 기억하기 힘들고 시간에 따라 IP주소가 변할 수 있다.

- 따라서, 이러한 문제를 해결하기 위해 도메인 네임이라고 불리는 **인간이 읽기 쉬운 주소** 가 등장했다.

  - Ex_) IP : 220.95.233.172 / Domain Name : naver.com

<BR>

## 도메인 네임의 구조

<img src="https://user-images.githubusercontent.com/58902042/132996979-bdccc3c0-ccc9-4282-8438-258b31987111.gif" width=550>



- 도메인 네임은 점으로 몇개의 파트를 구분하고 오른쪽에서 왼쪽으로 읽는다.
- "." 또는 루트라고 불리는 도메인 이하로 **역트리 구조** 로 구성되어 있다.
- **TLD(Top-Level Domain)**
  - 가장 일반적인 정보를 제공한다.
  - 국가도메인(ccTLD)과 일반도메인(gTLD)가 있다.
    - 국가도메인은 인터넷상에서 국가는 나타내는 도메인으로 .kr, .jp, .cn, .us등 영문으로 구성된 국가도메인이 있고, 자국어 국가도메인도 있다.
    - 일반도메인은 .com(회사), .net(네트워크 관련기관), .org(비영리기관), .biz(사업) 등 등록인 특성에 따랏 사용할 수 있는 도메인 이다.

- **Label(or component)**
  - Label은 보통 TLD를 따른다.
  - 한 글자부터 완전한 문장까지 무엇이든 가능하다.
  - TLD 바로 앞에 있는 Label은 SLD(Sendary Level Domain)이라고도 부른다.
  - 도메인 이름의 "앞"부분은 제어할때 "하위 도메인"을 만들 수 있다.
    - Ex_) mozilla.org --> developer.mozila.org

<br>

**:pushpin: Domain Name에 대해 알아봤다면 다음은 [DNS](./[Internet]DNS%20and%20how%20it%20works.md) 를 알아보자.**


-----------

### :clipboard: [참조] Reference

- [MDN Web Docs-What is a domain name](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_domain_name)
- [생활코딩-도메인이란?](https://opentutorials.org/course/228/1450)
- [[Developer MI-NE]-Domain Nmae과 DNS이란?](https://minemanemo.tistory.com/80)
- [한국인터넷정보센터.한국](https://xn--3e0bx5euxnjje69i70af08bea817g.xn--3e0b707e/jsp/resources/domainInfo/domainInfo.jsp)

