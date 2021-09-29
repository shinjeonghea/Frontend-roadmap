# Forms and Validations

:writing_hand: *write by shinjeonghea*

## form

- 사용자와 웹 사이트 또는 어플리케이션이 **서로 상호 작용** 하게하는 중요한 기술 중 하나
- 사용자가 **웹 사이트에 데이터를 전송하는 것을 허용**
- 일반적으로 데이터는 웹 서버로 전송되지만 웹 페이지가 데이터를사용하기 위해서 사용 가능
- 하나 이상의 위젯으로 만들어진다.
  - 텍스트 필드
  - 셀렉 박스
  - 버튼
  - 체크박스
- 위젯들은 위젯을 설명하는 라벨과 함께 사용된다.

<br>

## form 태그 동작방법

**form은 입력된 데이터를 한번에 서버로 전송, 전송된 데이터는 웹 서버가 처리하고 결과에 따른 웹 페이지를 보여준다.**

<img src="https://user-images.githubusercontent.com/58902042/135186598-e5c1b176-27cc-42d8-94f0-04051b2b58f8.png" width=500>

1. form이 있는 웹 페이지를 방문
2. form 내용을 입력
3. form 안에 있는 모든 데이터를 웹 서버로 요청
4. 웹 서버는 받은 form 데이터를 처리하기 위해 웹 프로그램으로 요청
5. 웹 프로그램이 form 데이터 처리
6. 처리결과에 따른 새로운 html 페이지를 웹 서버에 전송
7. 웹 서버는 받은 html 페이지를 브러우저에 전송
8. 브라우저는 받은 html 페이지를 보여줌

<br>

## form 태그 속성

form 속성을 이용하여 전송할 위치와 방법을 정한다.

- action : form을 전송할 서버 쪽 스크립트 파일을 지정

- name : form을 식별하기 위한 이름을 지정

- accept-charset : form 전송에 사용할 문자 인코딩 지정

- target : action에서 지정한 스크립트 파일을 현재 창이 아닌 다른 위치에 열도록 지정

- method :  폼을 서버에 전송할 http 메소드를 지정

  ~~~html
  <form action="/my-handling-form-page" accept-charset="utf-8" name="message" method="post">
      <div>
          <label for="name">Name:</label>
          <input type="text" id="name" />
      </div>
      <div>
          <label for="mail">E-mail:</label>
          <input type="email" id="mail" />
      </div>
      <div>
          <label for="msg">Message:</label>
          <textarea id="msg"></textarea>
      </div>
  </form>
  ~~~

### 1-1. Method 속성

- Method의 속성은 GET과 POST

- **브라우저에서 form 데이터를 가져와 서버로 보내는 똑같은 기능을 수행하지만, 방식이 다름**

  **GET 방식** 

  <img src="https://user-images.githubusercontent.com/58902042/135188989-152a6f4a-5585-49ac-bd55-2f0767bf8563.PNG" width=500>

  - URL에 form 데이터를 추가하여 서버로 전달하는 방식
  - 지정된 리소스에서 데이터를 요청하는 경우 사용(Read)
  - GET 방식의 HTTP 요청은 브라우저에 의해 캐시되어 저장
  - 쿼리 문자열에 포함되어 전송되므로, 길이의 제한 존재
  - 데이터가 노출되고, 길이 제한이 존재하여 보안성에 취약

  **POST 방식**

  <img src="https://user-images.githubusercontent.com/58902042/135188984-17084918-0219-4638-ab5f-a73489b2b173.PNG" width=500>

  - form 데이터를 별도로 첨부하여 서버로 전달하는 방식
  - 지정된 리소스에서 데이터를 처리하는 경우 사용(Write, Update, Delete)
  - POST방식의 HTTP 요청은 브라우저에 의해 캐시되지 않으믈, 브라우저 히스토리에도 남지 않음
  - 쿼리 문자열과 별도로 전송, 따라서 데이터 길이에 제한 없음
  - GET 방식보다 보안성이 높음

<br>

## form 구성 태그

#### 1. \<fieldset>, \<legend> 태그

- \<fieldset> 태그 : form 태그 안에 관련있는 form 요소들을 그룹화

- \<legend> 태그 : \<fieldset> 태그 하위에 사용하여 그룹화한 요소들의 목적에 맞는 이름 지정

  <img src="https://user-images.githubusercontent.com/58902042/135191432-4a333d11-0bf4-4100-8e59-80dc0e63ca59.png" width=200>

  ~~~html
  <html>
      <head>
      </head>
      <body>
          <form action=# accept-charset="utf-8" name ="info" method="get">
              <fieldset style="width:150">
                  <legend>개인 정보 입력</legend>
                  이름 :
                  <input type="text" name="name"/><br><br>
                  나이 :
                  <input type="text" name="age"/><br><br>
              </fieldset>
              <br>
              <fieldset style="width:180px; height:180px">
                  <legend>여가 활동</legend>
                  취미 :
                  <input type="text" name="hobby"/><br><br>
                  특기 :
                  <input type="text" name="specialty"/><br><br>
              </fieldset>
          </form>
      </body>
  </html>
  ~~~

#### 2. \<input> 태그

- 사용자가 다양하게 form 태그에 입력할 수 있는 공간을 생성

- input 태그 속성

  - type : 태그의 모양 변경 / text, radio, checkbox, password, button, submit 등을 지정
  - name : 태그 이름 지정
  - readonly : 태그를 읽기전용으로 설정
  - maxlength : 해당 태그 최대 글자 수 지정
  - required : 해당 태그를 필수 태그로 지정 / 필수 태그를 입력하지 않고 submit 버튼을 누르면 에러 발생
  - autofocus : 웹 페이지가 로딩되면 이 속성을 지정한 태그가 포커스로 이동
  - placeholder :  태그에 입력할 값에 대한 힌트 지정
  - pattern :  정규표현식을 사용하여 특정범위 내의 유효한 값을 입력받을 때 사용

  <img src="https://user-images.githubusercontent.com/58902042/135193120-bfe4fdce-6e8c-40cc-866e-26374eb35bbc.png" width=300>

  ~~~html
  <html>
      <head></head>
      <body>
          <form action="#" accept-charset="utf-8" name="person_info" method="get">
              <fieldset style="width:150">
                  <legend>개인 정보 입력</legend>
                  이름 : <input type="text" name="name" required="required"/><br><br>
                  주민번호 :  <input type="text" name="security_number"
                      pattern="\d{6}-\d{7}"
                      title="123456-1234567 형식으로 입력해주세요"/><br><br>
                  아이디 :<input type="text" name="id"/><br><br>
                  패스워드 :<input type="password" name="password"/><br><br>
                  
                  성별 : 남<input type="radio" name="gender"/>
                  여<input type="radio" name="gender"/><br><br>
  
                  관심사 : 연예<input type="checkbox" name="checkbox1"/>
                  		스포츠<input type="checkbox" name="checkbox2"/>
                 			IT<input type="checkbox" name="checkbox3"/><br><br>
  
                  <input type="submit" value="submit"/>
                  <input type="reset" value="reset"/><br><br>
              </fieldset>
          </form>
      </body>
  <html>
  ~~~

#### 3. \<select>, \<optgroup>, \<option>

- \<select>태그 : 항목 선택 태그

  - 속성
  - size : 한번에 표시할 항목의 수 
  - multiple : 다중 선택 허용 지정

- \<optgroup>태그 : \<select> 하위 태그 / \<select> 태그 안의 목록들을 그룹화

  - 속성
  - label : 그룹의 이름 설정

- \<option>태그 : \<optgroup>하위 태그 / 목록을 나타내는 태그

  <img src="https://user-images.githubusercontent.com/58902042/135193907-c0478eac-c254-4511-ac15-4f9a31502318.png" width=250>

  ~~~html
  <html>
      <head></head>
  
      <body >
          <form action="#" accept-charset="utf-8" name="person_info" method="get">
              <fieldset style="width:250">
                  <legend>개인 정보 입력</legend>
                  지역선택 (size, multiple속성 추가)<br>
                  <select name="city2" size="5" multiple="multiple">
                      <option value="seongnam-si">성남시</option>
                      <option value="suwon-si">수원시</option>
                      <option value="yongin-si">용인시</option>
                      <option value="anyang-si">안양시</option>
                      <option value="gwacheon-si">과천시</option>
                      <option value="hanam-si">과천시</option>
                  </select>
                  <br><br>
                  지역선택 (optgroup 태그 포함)<br>
                  <select name="city1">
                      <optgroup label="서울">
                          <option value="songpa-gu">송파구</option>
                          <option value="gangnam-gu">강남구</option>
                          <option value="seocho-gu">서초구</option>
                          <option value="junggu-gu">중구</option>
                      </optgroup>
  
                      <optgroup label="경기도">
                          <option value="seongnam-si">성남시</option>
                          <option value="suwon-si">수원시</option>
                          <option value="yongin-si">용인시</option>
                          <option value="anyang-si">안양시</option>
                      </optgroup>
                  </select>
                  <br><br>
                  <input type="submit" value="submit"/>
                  <input type="reset" value="reset"/><br><br>
              </fieldset>
          </form>
      </body>
  </html>
  ~~~

#### 4. \<textarea>태그

- 여러 줄을 입력받는 태그

- \<textarea> 태그 속성

  - rows : 줄의 크기
  - cols : 한 줄에 입력될 크기

  <img src="https://user-images.githubusercontent.com/58902042/135194408-a136bef7-af83-4903-b389-9dda39850f55.png" width=300>

  ~~~html
  <html>
      <head></head>
  
      <body >
          <form action="#" accept-charset="utf-8" name="person_info" method="get">
              <fieldset style="width:250">
                  <legend>개인 정보 입력</legend>
                  가입 인사<br>
                  <textarea name="comment" cols="50" rows="5" placeholder="가입인사를 남겨주세요."></textarea>
                  <br><br>
                  <input type="submit" value="submit"/>
                  <input type="reset" value="reset"/><br><br>
              </fieldset>
          </form>
      </body>
  </html>
  ~~~

**:pushpin: HTML에서 더 많은 form 구성 태그들을 알고싶다면 [여기](https://www.w3schools.com/html/html_forms.asp) 를 클릭해보자.**

<br>

## 웹 표준 유효성 검사

- 웹 사이트가 **W3C에서 지정한 웹 표준을 얼마나 지켰는지 체크하고 수정** 하기 위한 검사
- 어느 정도 표준이 지켜졌으며 어던 오류가 발생하고 어떤 **해결방안이 있는지 알려주는 검사**

<BR>

## 웹 표준 유효성 검사 방법

W3C 웹표준 유효성검사도구 : http://validator.w3.org/ 에서 가능

**1. Validate by URL** : 웹페이지의 URL을 입력하면 해당 경로의 페이지를 검사
**2. Validate by File Upload** : 로컬상의 HTML파일을 업로드 해서 유효성 검사
**3. Validate by Direct Input** : 직접 HTML 코드를 Input Text 창에 입력해 유효성 검사

<BR>

## 유효성 검사를 하는 이유

- 웹표준이 잘 되어있는지 여부를 확인
  - 현재 사이트에서 웹표준이 맞지 않는 부분을 검출하여 웹표준을 높이는데 도움
- 웹표준 유효성 인증마크를 부착할 수 있다.
  - 웹표준 검사결과가 완벽하다면 인증마크를 붙일 수 있다.
  - 홈페이지가 웸표준을 준수했다는 것을 가시적으로 나타낼 수 있다.

-----------

### :clipboard: [참조] Reference

- [HTML Classes](https://www.w3schools.com/html/html_classes.asp)[MDN-나의 첫 HTML 폼](https://developer.mozilla.org/ko/docs/Learn/Forms/Your_first_form)
- [넥스트리 - HTML:폼(form) 이해](https://www.nextree.co.kr/p8428/)
- [TCP SCHOOL - \<form> 태그의 method 속성](http://tcpschool.com/html-tag-attrs/form-method)
- [Oh오마이사이트](https://ohmysite.co.kr/web_common_sense.html?article_num=34&OTSKIN=layout_ptr.php&PB_1429088248=8&PB_1491885899=8&design_file=web_common_sense_v.php)
