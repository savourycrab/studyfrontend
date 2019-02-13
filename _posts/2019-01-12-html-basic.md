---
title: "html-basic"
author: "savourycrab"
---

# HTML 개괄
  - HTML 동작
    - .html (text형태로 작성) -> 브라우저 (구조, 화면 등 렌더링 작업) -> 사용자에게 보여줌(view)
    - HTML 5 표준(5.2) - https://www.w3.org/TR/html
    - HTML, CSS 도서 추천(2019.02.10/일요일)
      - Do it! HTML5+CSS3 웹 표준의 정석
      - 모던 웹 디자인을 위한 HTML5+CSS3 입문
 
  - HTML 문서 파일과 웹 브라우저의 해석 & 시멘틱 마크업
    - 웹사이트 콘텐츠를 설명하는데 사용되는 마크업 언어
    - 콘텐츠의 의미를 설명하는데 유일한 목적이 있음
    - 구조 설계를 목표로 함
      - 비주얼 디자인( 모양, 색, 크기 등)이 목표가 아님
    - Row content -> me -> HTML markup -> browser -> WEB pag
    - 브라우저는 어떻게 동작하는가
      - https://d2.naver.com/helloworld/59361 

# 시멘틱 마크업(Semantic Makup)
  - 종종 POSH(Plain Old Semantic HTML)로도 불림
  - Non-semantic ^& Semantic
    - Non-Semantic - Contents에 heading(<h1></h1>, paragraph(<p></p>)과 같은 테그로 어떤 의미를 부여하지 않은 Row data contents를 말함
    - Semantic- Contents에 HTML 테그요소를 사용하여 의미를 부여한 상태( 주제다 본문이다 등등을 브라우져가 알 수 있도록)
    - 따라서, HTML은 기본적인 마크업 요소이지만 잘 구조화된 컨텐츠의 기초를 다지는데 매우 중요함
  - 현재의 시멘틱 마크업
    - <div id="heading" style="font-size: 300%; padding: 10px;">시멘틱 마크업이랑?</div>
      - 제목같아 보이지만 의미와 용도면에서 제목으로서의 기능이 없음
      - 몇가지 이슈가 생김
        - 최적화: 검색엔진을 최적화하는데 headings 요소 안에 있는 키워드가 매우 종요
        - 접근성: 스크린리더는 네비게이션 길잡이로 headings요소를 참고함
        - 개발: 적절한 시멘틱 요소를 사용하지 않게 될 때, 스크립트와 스타일 요소를 설정하는데 까다로움
      - <h1>시멘틱 마크업이란?</h1>
        - 시멘틱 마크업은 가능한 가벼워야 함
        - 중첩된 div요소와 스파게티 코드가 없어야 파일 사이즈가 작아지고 코딩이 쉬워짐
          - HTML, CSS, JS가 분리 되어 있어야 함
  - etc
    - 표준을 따라 markup하자
    - 시멘틱 HTML은 정확하고 접근이 용이한 컨텐츠의 데이타 구조를 형성
      - HTML5가 잘 지원하기 때문에 어떤 스크립트를 추가하지 않고도 가능한 접근이 용이하며 쓸모있게 데이터 구조를 만들어 낼 수 있음
    - CSS는 스타일 정보를 제공
      - 데이터 구조에 우리가 원하는대로 시각적인 효과를 더해줌
    - HTML5와 그 외 다른 것에 정의된 스크립팅 APIs와 베이스언어를 포함한 JS는 우리가 제작하는 사이트에 풍부한 기능 더해줌

# HTML 문서를 작성하는 기본 문법
  - 웹 페이지는 헤드(head>영역과 바디(body)영역으로 구성됨
    - <HEAD> : page title(웹 페이지의 제목으로 브라우저 탭에 표시됨), css links, other abstract things
    - <BODY> : headings, paragraphs, other things i can see
  - HTML 용어
    - 태그(tag, element)
      - 오픈 태그(open tag) - 여는 태그
      - 클로즈 태그(close tag) - 닫는 태그
      - 애트리뷰트(attribute) - 속성
      - 벨류(value) - 값
  - 기본 문법
    - <tagname attribute="value"> contents </tagname>
      - < a href="https://wikipedia.org">Link to Wikipedia</a>
      - 실습( html-basic-syntac.html)
{% highlight python %}
<html>
<head>
<meta charset="utf-8">
<title>HTML 문서 작성을 위한 기본 문법</title>
</head>
<body>
<p title="Development Tools">개발 도구(DevTools)</p>
</body>
</html>
{% endhighlight %}
      - tips
        - 크롬 개발도구 Elements에서 마크업된 내용을 확일 할 수 있음
        - 크롬 개발도구 console에서 document.charset 명령으로 브라우저 인코딩을 확인 할 수 있음

# 닫는 태그(close tag)가 없는 HTML요소(Empty Elements)
  - 컨텐츠를 감싸지 않은 요소
    - 컨텐츠를 감싸지 않아 비어있음
  - 컨텐츠를 감싸지 않기 때문에 닫는 태그가 필요 없음
  - 참고 
{% highlight python %}
<area>
<base>
<col>
<embed>
<hr>
<img>
<input>
<keygen> HTML 5.2 Draft removed
<link>
<meta>
<param>
<source>
<track>
<wbr>
{% endhighlight %}

# 문서유형정의(DTD: Document Type Definition) & 표준 모드
  - 브라우저의 렌더링 모드를 표준으로 작동하게 만들어 줌
  - 문서 유형 정의 방법
{% highlight python %}
<!DOCTYPE html>
<html>
<head>
</head>
<body>
</body>
</html>
{% endhighlight %}
    - 웹 표준 문서이자 모던 웹 브라우저를 지원하는 표준 문서임을 정의함
    - 지정하느냐 지정하지 않느냐에 따라 HTML 최종 결과물이 달라질 수 있음(표준, 비표준)
  - DTD는 반드시 HTML 문서 최 상의에 있어야 함
  - 부모자식 관계
    - <html>이 최상위 태그
    - <head>는 <html>의 first child
      - <body>는 <html>의 last child
      - <html>의 <head>와 <body> 사이(전방위)에는 어떤 태그도 넣을 수 없음
      - <head>와 <body>내부에 태그를 지정하면 <head> 또는 <body>의 child tag라 부를 수 있음
  - 표준과 비표준
    - doctype(DTD) 지정 유무에 따라 문서가 표준을 따를 것인지 비표준에 따를 것인지 나뉘게됨
    - doctype 지정 유무에 따라 브라우저는 아래와 같이 몇가지 모드로 동작함
      - 웹브라우저의 레이아웃 엔진이 지원하는 몇가지 모드
        - 호환 모드(quirks): w3c 표준 재정 이전에 제작된 웹사이트를 표현함(네스케이프 네비게이터 4 인터넷 익스프로러5의 비표준 동작들을 에뮬레이터함)
        - 유사 표준 모드(almost standards mode): 몇몇 호환모드만을 지원함
        - 표준 모드(standards mode): HTML과 CSS에 의해 웹 페이지 레이아웃이 결정됨
      - 각 엔진별 편차가 있기 때문에 필요할 때 검색해서 참고하자
        - Gecko: Firefox
        - WebKIT: Safari, Chrome

# 문서에 사용된 주 언어가 무엇인지 설정하는 lang 속성
  - <html> 루트 요소에 lang 속성을 사용하여 문서에 주로 사용된 언어를 설정할 수 있음
{% highlight python %}
<!doctype html>
<html lang="ko-KR">
<head>
</head>
<body>
</body>
</html>
{% endhighlight %}
  - 언어 코드는 ISO 639를 참고 할 것
    - https://ko.m.wikipedia.org/wiki/ISO_639
  - 장애인들이 사용하는 리더 등에서 이 정보를 기반으로 사용함

# 비주얼 디자인에서 제목(Headings>, 단락(Paragraph) 구조도출
  - 제목(Headings), 단락(Paragraph)를 도출하는 방법
  - 단락
{% highlight python %}
<p></p>
    - 제목
        - 6단계 까지 사용 가능
{% highlight python %}
{% endhighlight %}
<h1> 문서에서 단 한번만 사용(HTML5에서는 섹션 콘텐츠 마다 사용 가능)
<h2>
<h3>
<h4>
<h5>
<h6>
{% endhighlight %}









