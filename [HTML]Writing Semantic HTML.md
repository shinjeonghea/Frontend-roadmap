# Writing Semantic HTML

:writing_hand: *write by shinjeonghea*

## 시맨틱(semantic) HTML

- 의미론적 HTML
- **각 요소의 의미를 브라우저와 개발자 모두에게 알 수 있게 정보를 제공하는 HTML**

<br>

## non-semantic elements VS semantic elements

<img src="https://user-images.githubusercontent.com/58902042/134606059-6c817db9-f69e-4890-9e0c-9426fa02bafc.png" width=350> 

**시맨틱하지 않은 **

- `<div>` 와 `<span>` 등
- 태그에 포함되는 내용에 대한 어떤한 정보도 제공하지 못한다.

**시맨틱한**

- `<form>` 과 `<table>` 등
- 태그에 포함되는 내용에 대한 정보를 예측할 수 있다.

**왜 예측해야하는가?**

- 검색엔진에서 웹사이트 정보를 수집하여 웹사이트의 키워드에 대응하는 인덱스를 만들기 위해 웹사이트의 HTML을 수집한다. 
- 그 과정에서 Semantic elements를 해석하게 되는데 만약 Semantic elements가 없다면 HTML에서 중요한 요소를 파악하는 과정에서 문제가 생긴다.

<BR>

## Semantic HTML 장점

1. **Accessibility**
   - 모바일 사용자나 장애가 있는 사용자의 접근성을 향상
   - 브라우저나 스크린 리더가 코드를 더 쉽게 인터프린터 가능
2. **SEO**
   - Semantic HTML은 SEO(Search Engine Optimization)을 향상
   - SEO가 좋을수록 검색 엔진이 웹 사이트를 빠르게 식별 가능, 중요한 정보에 가중치 부여
3. **Easy to Understand**
   - 웹 사이트 소스코드의 가독성을 향상

<br>

## Semantic elements

| Tag        | 설명                                                      |
| ---------- | --------------------------------------------------------- |
| section    | 문서들의 섹션 정의                                        |
| article    | 본문                                                      |
| header     | 화면 상단에 위치하는 사이트, 문서의 전체적인 정보 정의    |
| footer     | 화면의 하단에 위치하는 사이트, 문서의 전체적인 정보 정의  |
| nav        | 문서의 네비게이션 항목 정의                               |
| aside      | 광고와 같이 페이지의 내용과는 관계가 적은 내용들          |
| main       | 문서에서 가장 중심이 되는 컨텐츠 정의                     |
| figure     | 삽화나 다이어그램과 같은 부가적인 요소 정의               |
| figcaption | 일반적으로 figure 태그안에 포함, 캡션을 달아주기위한 용도 |
| details    | 기본적으로 화면에 표시되지 않는 정보들을 정의             |
| mark       | 참조나 하이라이트 표시를 필요로 하는 문자를 정의          |
| time       | 시간을 정의                                               |

1. **\<section>**

   ~~~html
   <section>
   	<h1>WWF</h1>
   	<p>The World Wide Fund for Nature (WWF) is....</p>
   </section>
   ~~~

   - 내용의 주제에 따른 그룹핑 역할
   - `<article>` 를 포함하거나 포함될 수 있다.
     - 일반적으로는 `<article>` 를 포함한다.

2. **\<article>**

   ~~~html
   <article>
   	<h1>What Does WWF Do?</h1>
   	<p>WWF's mission is to stop the degradation of our planet's natural environment,
   and build a future in which humans live in harmony with nature.</p>
   </article>
   ~~~

   - 독립된 내용, 웹 사이트로부터 독립적으로 읽을 수 있어야 한다.
   - ex_) 포럼, 블로그 포스트, 신문 기사
   - `<section>` 을 포함하거나 포함될 수 있다.

3. **\<header>**

   ~~~html
   <article>
       <header>
           <h1>What Does WWF Do?</h1>
           <p>WWF's mission:</p>
       </header>
       <p>WWF's mission is to stop the degradation of our planet's natural environment,
       and build a future in which humans live in harmony with nature.</p>
   </article>
   ~~~

   - 문서나 섹션의 머릿말, 서두의 내용을 위해 사용
   - 한 문서에 여러개의 `<header>` 사용 가능

4. **\<footer>**

   ~~~html
   <footer>
       <p>Posted by: Hege Refsnes</p>
       <p>Contact information: <a href="mailto:someone@example.com">
       someone@example.com</a>.</p>
   </footer>
   ~~~

   - 문서나 섹션의 꼬릿말 의미
   - 항상 포함된 요소에 대한 정보를 담고 있어야한다.
     - 주로 문서의 저자, 저작권 정보, 사용법을 위한 링크, 연락처 정보 등
   -  하나의 문서에서 여러개의 `<footer>` 사용 가능
     - 하나의 문서에 한번만 사용되지만, `<section>` 이나 `<article>` 내에서 또 사용 가능

5. **\<nav>**

   ~~~HTML
   <nav>
       <a href="/html/">HTML</a> 
       <a href="/css/">CSS</a> 
       <a href="/js/">JavaScript</a> 
       <a href="/jquery/">jQuery</a>
   </nav>
   ~~~

   - 네비게이션 링크의 집합을 의미 / 중요한 블록의 네이게이션 링크를 위한 것
   - 모든 문서의 링크가 `<nav>` 에 있어야하는 것은 아니다.
   - 브라우저가 네비게이션 영역을 인식하여, 검색엔진 색인에 도움을 줄 수 있다.

6. **\<aside>**

   ~~~html
   <article>
     <p>The first World Series was played between Pittsburgh and Boston in 1903 and was a nine-game series.</p>
   </article>
   <aside>
     <p>
      Babe Ruth once stated, “Heroes get remembered, but legends never die.”
     </p>
   </aside>
   ~~~

   - 부가적인 정보를 전달할 때 주로 사용
   - `<article>` 과 `<section>` 태그와 주로 사용
   - 사이드바, 배너광고, 위젯 등으로 이용

7. **\<main>**

   ~~~html
   <main>
     <article>
       <h3>Baseball</h3>
       <p>
         The first game of baseball was played in Cooperstown, New York in the summer of 1839.
       </p>
     </article>
   </main>
   ~~~

   - `header` 와 `footer` 태그와 분리되어 웹 페이지의 가장 핵심적인 내용 포함
   - `div` 대신 사용함으로써 브라우저가 중요한 부분을 빠르게 파악하도록 한다.

8. **\<figure> 과 \<figcaption>**

   ~~~html
   <figure>
       <img src="pic_trulli.jpg" alt="Trulli">
       <figcaption>Fig1. - Trulli, Puglia, Italy.</figcaption>
   </figure>
   ~~~

   - ` <figure>` 태그는 이미지나 비디오, 코드 같은 미디어 포함
   - 이때, 미디어에 시각적 설명을 추가하기 위해 `<figcaption>` 사용

<BR>

**:pushpin: Sematic HTML을 사용하므로써 개선되는 [Accessibility](./%5BHTML%5DAccessibility.md) 과 [SEO](./%5BHTML%5DSEO%20Basics.md) 가 무엇인지 더 알아보자.**

-----------

### :clipboard: [참조] Reference

- [4. Writing Semantic HTML](https://velog.io/@ssoon_d/4.-Writing-Semantic-HTML)
- [Semantic HTML(시맨틱 HTML) 이란?](https://eunsukimme.github.io/html/2019/12/18/Semantic-Web/)
- [[빠리의 택시 운전사] - [HTML]시맨틱(Semantic) HTML을 짜보자](https://geonlee.tistory.com/96)

