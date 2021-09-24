# HTML basics

:writing_hand: *write by shinjeonghea*

## HTML

- **H**yper **T**ext **M**arkup **L**anguage의 약자<br><sub>markup : 어떤 정보를 태그라고 하는 형식을 통해서 정의한다는 뜻</sub>

- **콘텐츠의 구조를 정하는 마크업 언어이다.**

- HTML은 콘텐츠의 다른 부분을 둘러싸거나 감싸는데 사용하는 일련의 **요소(elements)** 로 구성되어 특정 방식으로 나타나거나 특정 방식으로 작동한다.

- 둘러싸는 **태그(tags)** 는 단어나 이미지를 다른 곳으로 하이퍼링크할 수 있고, 글꼴을 바꾸거나 글의 크기를 키우거나 줄이는 작업을 할 수 있다.

<br>

## HTML 요소의 구조

### - 구성

<img src="https://user-images.githubusercontent.com/58902042/134470628-2ce1fbc4-4f36-4b8f-b92e-8c400b8461b8.png" width=600> 

**1. 여는 태그**

- 여는 꺾쇠 괄호와 닫는 꺾쇠 괄호로 묶인 요소 이름으로 구성(위 사진의 경우\<P>)

- 요소가 시작되거나, 적용되는 위치를 표시

**2. 닫는 태그**

- 여는 태그에 추가적으로 '/'가 포함
- 요소가 끝나는 위치를 표시
- 여는 태그가 있다면 반드시 닫는 태그가 존재해야함

**3. 내용**

- 텍스트를 나타내는 요소의 내용

**4. 요소**

- 여는 태그, 닫는 태그 및 내용의 구성

### - 태그의 속성

<img src="https://user-images.githubusercontent.com/58902042/134472256-a4d8bf60-18bd-45d6-9134-793e8573af21.png" width=700> 

- 태그의 부가적인 정보
- 속성의 구성
  - 요소이름(or 요소에 이미 속성이 존재하는 경우 이전 속성)과의 공백
  - 속성 이름 뒤에 '=' (위 사진에서는 class가 속성 이름)
  - 여닫는 따옴표로 묶인 속성 값 (위 사진에서는 editor-note가 속성 값)

### - 요소의 중첩

~~~html
<p>My cat is <strong>very</strong> grumpy.</p>
~~~

- 요소안에 다른 요소 넣는 것
- 먼저 연 태그를 나중에 닫아야한다
  - 위의 경우\<p>를 먼저 열었기때문에 \<strong>을 먼저 닫고 \</p>를 나중에 닫았다.

### - 빈 요소

~~~html
<img src="images/firefox-icon.png" alt="My test image">
~~~

- 요소에 내용이 존재하지 않는 것
- 위의 경우, 닫는 태그\</img>가 존재하지 않는다. 

 <br>

## HTML 요소의 종류

**이미지**

~~~html
<img src="images/firefox-icon.png" alt="My test image">
~~~

- 이미지를 나타내는 요소
- 속성 
  - src - 이미지 파일의 경로
  - alt - 이미지에 대한 설명문

**제목**

~~~html
<h1>My main title</h1>
<h2>My top level heading</h2>
<h3>My subheading</h3>
<h4>My sub-subheading</h4>
~~~

- 특정부분을 제목 또는 하위 제목으로 구체화
- HTML은 \<h1> ~ \<h6>까지의 단계를 가진다.

**문단**

~~~html
<p>This is a single paragraph</p>
~~~

- 문자의 문단을 포함하기 위한 요소
- 일반적인 문자내용을 나타낼 때 사용한다.

**목록**

- 목록의 항목들은 **\<li> (목록항목)** 요소 안에 놓인다

1. **순서 없는 목록**

   ~~~html
   <ul>
     <li>technologists</li>
     <li>thinkers</li>
     <li>builders</li>
   </ul>
   ~~~

   - \<ul> 요소로 둘러쌓여 있다.
   - 쇼핑 목록과 같이 항목의 순서에 관계없는 목록을 위한 것

2. **순서 있는 목록**

   ~~~html
   <ol>
     <li>wash your hands</li>
     <li>cut a carrot</li>
     <li>fry potatoes </li>
   </ol>
   ~~~

   - \<ol> 요소로 둘러쌓여 있다.
   - 조리법처럼 항목의 순서가 중요한 목록을 위한 것

**연결**

~~~html
<a href="https://www.mozilla.org/en-US/about/manifesto/">Mozilla Manifesto</a>
~~~

- 단어를 웹에 연결하는 링크로 만들어 준다.
- 속성
  - href - 연결하고자 하는 웹의 주소와 연결

<br>

## HTML 문서 구조

~~~html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My test page</title>
  </head>
  <body>
    <img src="images/firefox-icon.png" alt="My test image">
  </body>
</html>
~~~

**HTML 페이지를 구성하는 HTML 요소들**

- **\<!DOCTYPE html>**
  - 문서유형/필수 서문
  - 기본적으로 문서가 올바르게 작동하는지 확인하는 링크 역할
- **\<html> \</html>**
  - 루트 요소
  - 전체 페이지의 모든 내용을 래핑
- **\<head> \</head>**
  - 페이지 뷰어에게 표시하는 콘텐츠가 아닌 HTML페이지에 포함하려는 모든 항목에 대한 컨테이너 역할
  - 검색 결과에 표시되는 키워드 및 페이지 설명, CSS 등
- **\<meta charset="utf-8">**
  - 문서에서 사용해야 하는 문자 집합을 UTF-8로 설정
  - 기본적으로 사용자가 넣는 모든 텍스트 콘텐츠 처리 가능
- **\<title> \</title>**
  - 페이지가 로드되는 브라우저 탭에 제목 설정
  - 책갈피/즐겨찾기에서의 페이지 설명
- **\<body> \</body>**
  - 웹 사용자가 페이지를 방문할 때 표시되는 모든 컨텐츠
  - 텍스트, 이미지, 비디오, 게임, 재생 가능한 오디오 등

-----------

### :clipboard: [참조] Reference

- [MDN - HTML 기본](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics)
- [생활코딩 - HTML이란?](https://opentutorials.org/course/1594/10)

