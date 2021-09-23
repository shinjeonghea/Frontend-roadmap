# Browser & Browser의 동작 원리

:writing_hand: *write by shinjeonghea*

## 브라우저

- **웹 페이지, 이미지, 비디오 등의 콘텐츠를 수신, 전송 및 표현하는 소프트웨어**
- 주요 브라우저
  - Google Chrome - Webkit
  - Safari - Webkit
  - Mozilla Firefox(Escape) - Gecko
  - Microsoft Internet Explorer
  - Opera

<br>

## 브라우저의 주요 기능

- 사용자가 선택한 **자원을 서버에 요청(request)하고 응답(response)을 받아 화면에 표시한다.**
- 자원은 html 문서, pdf, image 등 다양한 형태이며, 자원의 주소는 uri에 의해 결정된다.
- html과 css 명세에 따라 html 파일을 해석해서 표시한다.
  - '명세'는 웹 표준화 기구인 W3C에서 정한다.

<BR>

## 브라우저의 구조

<img src="https://user-images.githubusercontent.com/58902042/104192414-22a99780-5462-11eb-86ec-8d08d7010c1d.PNG" width=500>

- **사용자 인터페이스**
  - 주소창, 즐겨찾기 등 사용자가 조작 가능한 영역
- **브라우저 엔진**
  - 사용자 인터페이스와 렌더링 엔진 사이의 동작 제어
  - *But, 위키피디아 영문버전에서는 브라우저 엔진과 렌더링 엔진을 따로 나누어서 설명하지 않는다.*
- **렌더링 엔진**
  - 요청된 자원을 화면에 표시
- **통신**
  - HTTP 요청과 같은 네트워크 호출
- **자바스크립트 해석기**
  - 자바스크립트를 해석하고 실행
- **UI 백엔드**
  - OS 사용자 인터페이스 방법을 활용하여 기본적인 위젯을 그림
  - But, 사용자 인터페이스와 기본적으로 따로 볼 이유는 없다. 
- **자료 저장소**
  - Local Storage, Indexed DB, 쿠키 등 브라우저 메모리를 활용하여 저장하는 영역

<br>

## 브라우저의 동작과정

<img src="https://user-images.githubusercontent.com/58902042/104191258-a19dd080-5460-11eb-8db3-c3da78012130.PNG" width=600>

1. 브라우저가 서버에 **요청을 전송** 한다.

2. 브라우저가 서버로 부터 HTML, CSS, JS, 이미지 파일등을 **응답받는다.**

3. HTML, CSS파일이 **렌더링 엔진** 의 HTML파서와 CSS 파서에 의해 **파싱** 된다(이 과정이 W3C 명세에 따라 해석되는 것).

4. 먼저 HTML 파싱 과정을 통해 DOM트리 구축, 그리고 CSS파싱을 통해 CSSOM트리를 생성한다.

5. 이 2가지를 연결하여 **렌더 트리** 로 결합된다.

   - 렌더 트리를 통해 **시각적 요소를 포함한 형태로 구성** 된 상태가 된다.

6. 이렇게 생성된 렌터 트리를 기반으로 **브라우저가 웹페이지를 표시** 한다.

   \+ 7. **자바스크립트의 경우** 는 자바스크립트 엔진이 처리한다.

   8. HTML 파서는 script 태그를 만나면 자바스크립트 코드를 실행하기위해 DOM 생성을 중지하고 **자바스크립트 엔진으로 제어 권한을 넘긴다.**
   9. 자바스크립트 엔진은 script의 내용을 파싱하고 실행한다.
   10. 자바스크립트 실행이 완료되면 다시 HTML 파서로 제어 권한을 넘겨서 DOM 생성을 재개한다.

<br>

### :bulb: 렌더링, 파싱, Trees에 대해 더 살펴보자

#### 1. 렌더링

- **렌더링 엔진은 요청 받은 내용을 브라우저 화면에 표시해준다.**

- **렌더링 엔진 종류**

  - 크롬, 사파리 - 웹킷(Webkit) 엔진 사용
  - 파이어 폭스 - 게코(Gecko) 엔진 사용

- **렌더링 주요 동작 과정**

  - 브라우저가 HTML, CSS, Javascript 등의 파일을 변환하여 화면에 픽셀 단위로 나타내기 위해 거쳐야하는 일련의 과정

  <img src="https://yilpe93.github.io/static/58dd63a5db0e6951536d1f080d54a9a0/d8f62/browser_03.png" width=500>

  1. DOM Tree 생성
  2. CSSOM 생성
  3. Render Tree(DOM+CSSOM) 생성
  4. Render Tree 배치
  5. Render Tree 그리기

#### 2. 파싱 

- **브라우저가 코드를 이해하고 사용할 수 있는 구조로 변환하는 것**

- 파싱 결과는 보통 문서 구조를 나타내는 Node Tree

- 파싱트리은 어휘 분석과 구문 분석을 통해 구축된다.

  <img src="https://user-images.githubusercontent.com/58902042/104293078-ef6a1580-5500-11eb-8119-c6ebe39c7136.png" width=100>

- 파싱을 통해, DOM 트리 생성


#### 3. DOM Tree

- **HTML의 내용과 속성을 Node로 갖고 각 Node의 관계를 나타내는 트리**

- HTML 의 문서를 구조화하여 스크립트 또는 프로그래밍 언어에서 접근 가능한 형태로 제공

- DOM 트리는 문서 마크업의 속성과 관계를 포함하지만,

  <img src="https://user-images.githubusercontent.com/58902042/104293974-fe04fc80-5501-11eb-854a-2cf63eef5952.png" width=300> <img src="https://user-images.githubusercontent.com/58902042/104294105-24c33300-5502-11eb-95f3-750d4d17a668.png" width=350>

  - 왼쪽의 마크업을 오른쪽의 DOM트리로 변환 가능

- 렌더링되어 그려질 때는 CSSOM 이 관여한다.

#### 4. CSSOM(CSS Object Model)

- DOM 생성과 마찬가지로 태그들을 토큰화, 토큰을 Node로 변환하여 CSSOM으로 변환한다.
- 브라우저가 모든 CSS를 파싱하고 처리할때까지 페이지가 화면에 그려지지 않는다.

#### 5. Render Tree

- 최종적으로 화면에 그려지는 내용이 된다.
- DOM + CSSOM, DOM의 Node에 일치하는 CSSOM 규칙을 찾아 연결한 트리
- 렌더링 트리에는 페이지를 렌더링하는데 필요한 가시적인 Node만 포함된다.
  - `display : none` 스타일이 지정된 Node 는 제외된다. 
  - `visibility : hidden` 스타일이 적용된 Node는 보이지는 않지만 공간을 차지하므로 렌더링 트리에 포함된다.

<br>

**:pushpin:더 자세히 알고싶다면 [브라우저는 어떻게 동작하는가?](https://d2.naver.com/helloworld/59361) 이 링크를 통해 확인하도록 하자.**

-----------

### :clipboard: [참조] Reference

- [브라우저란 무엇이며 어떻게 작동할까?](https://oneroomtable.tistory.com/entry/%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80%EC%9D%98-%EA%B0%9C%EB%85%90%EA%B3%BC-%EC%97%AD%ED%95%A0)
- [브라우저 동작 과정에 대해 알아보자(DOM, Parsing)](https://kim6394.tistory.com/217)
- [브라우저 동작 원리](https://poiemaweb.com/js-browser)
- [Jkun.io - 브라우저 동작 원리](https://yilpe93.github.io/Web/browser/)
