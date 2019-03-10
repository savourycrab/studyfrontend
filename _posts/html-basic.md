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
    - <div id="heading" style="font-size: 300%; padding: 10px;">시멘틱 마크업이란?</div>
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
{% highlight html %}
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
{% highlight html %}
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
{% highlight html %}
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
{% highlight html %}
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
{% highlight html %}
<p></p>
{% endhighlight %}
    - 제목
      - 6단계 까지 사용 가능
{% highlight html %}
<h1> 문서에서 단 한번만 사용(HTML5에서는 섹션<section> 콘텐츠 마다 사용 가능)
<h2>
<h3>
<h4>
<h5>
<h6>
{% endhighlight %}


# HTML 이미지 & 피규어 & 캡션
  - 주로 사용되는 이미지 포멧
    - jpg, gif, png, svg
      - jpg: 투명한 픽셀 허용 않함
      - png: 투명한 픽셀 처리를 허용하므로 로고, 다이어그램 등에 사용
      - git: 256비트 컬러, 단순한 그래픽 애니메이션에 사용(졸라맨)
      - svg: 벡터기반(방향성), 품질 손실없이 확대, 축소 가능(반응형웹에 적합)
 
  - <img> 테그 사용
    - html은 이미지를 embed하지 않고 연결해서 쓰는 형식임
    - figure: 전체 사진
    - caption: 각주
    - alt: 그림이 렌더링 되지 못할때 나타나는 대체텍스트 

  - img 사용 구조
{% highlight html %}
<figure>
    <img src="sbs-drama__do-you-want-to-kiss-first.png"
        alt= "SBS 드라마 <키스 먼저 할까요?>의 한 장면: 배우 김선아가 홀로 겨울바다를 걷는 중..">
    <!-- figure caption -->
    <figcaption>-이미지 출처:SBS <키스 먼저 할까요?> 방송화면 캡쳐-</figcaption> 
</figure>
{% endhighlight %}

  - img with height and width
{% highlight html %}
<figure>
    <img src="sbs-drama__do-you-want-to-kiss-first.png"
        alt= "SBS 드라마 <키스 먼저 할까요? width="" height="">의 한 장면: 배우 김선아가 홀로 겨울바다를 걷는 중..">
    <!-- figure caption -->
    <figcaption>-이미지 출처:SBS <키스 먼저 할까요?> 방송화면 캡쳐-</figcaption> 
</figure>
{% endhighlight %}

# HTML 유효성 검사 & 엔티티 코드
  - 웹 표준을 항상 따르기 어려움
  - 웹 표준 젠체를 암기하고 있기는 어렵기 때문
  - validator를 사용해 유효성 검사를 진행하고 권고에 따르는 것이 좋음

# mission for vaidation you should check the example with validator and resolve the problem
  - missions will be done in this weekend because i\'m not connecting internet

# HTML 순차/비순차 목록과 아이템

  - li(list): Item 요소
  - ol(ordered list): li요소를 순차로 표현
  - ul(unorderd list): li요소를 비순차로 표현
  - ol, ul요소는 li요소만을 포함할 수 있음, 같은 속성인 ol, ul요소를 포함할 수 없음

{% highlight html %}
<!--ordered list-->
<ol>
    <li></li>
    <li></li>
    <li></li>
<ol>

<!--unordered list -->
<ul>
    <li></li>
    <li></li>
    <li></li>
<ul>
{% endhighlight %}

# HTML 앵커 & 하이퍼링크
  - 페이지 내 이동 또는 다른 페이지로 이동
    - id, hyperlink
  - URI(Uniform resource locators)
    - 'scheme'(https://)'domain'(hahah.com)'path'(/ko-kr/web)
  - 경로(path)
    - 절대경로: 현재 html 문서 위치와 상관없이 전체 uri경로로 연결하는 형식(https://domain.com/html)
    - 상대경로: 현재 html 문서를 기준으로 연결하는 형식(../of/html)
    - 루트 상대경로: 현재 html 문서를 기준으로 최상위에 위치한 경로로부터 연결하는 형식(/path/of/html)
  - a 요소에 href 속성을 사용
    - 지정된 id를 가진 요소의 위치로 이동
    - 지정된 hyperlink 위치로 이동
      - target 속성에 _black를 사용하면 새 창으로 열림
  
  - id
{% highlight html %}
<a href="#hello">anchor</a>
<h2 id="hello">Hello</h2>
{% endhighlight %}

  - hyperlink
{% highlight html %}
<a href="https://domain.com/html">절대</a>
<a href="../of/html">상대</a>
<a href="/path/of/html">루트 상대</a>
{% endhighlight %}

  - outer hyperlink with image
{% highlight html %}
<img src="/path/of/image alt="">
<a href="https://domain.com/html">hello</a>
{% endhighlight %}

  - inner hyperlink with image
{% highlight html %}
<a href="https://domain.com/html">
    <img src="/path/of/image alt="">
    hello
</a>
{% endhighlight %}

  - hyperlink with new window 
{% highlight html %}
<a href="https://domain.com/html" target="_blank">new window</a>
{% endhighlight %}

  - hyperlink with email
{% highlight html %}
<a href="mailto:email@gmail.com" target="_blank">email</a>
{% endhighlight %}

# HTML 설명 목록
  - <dl>: 설명 목록
  - <dt>: 용어
  - <dd>: 용어 설명 

  - 설명 목록 구조
{% highlight html %}
<dl>
    <dt>hello</dt>
    <dd>
        <p></p>
        <a href=""></a>
    </dd>

    <dt>hello</dt>
    <dt>hello1</dt>
    <dd>
        <ul>
            <li><a href="" target="_blank"></a></li>
            <li></li>
        </ul>
    </dd>

    <dt></dt>
    <dd></dd>
    <dd></dd>
    <dd></dd>
</dl>
{% endhighlight %}

# HTML 인용구문 & 줄바꿈
  - <q>: 인라인 인용 요소
  - <blockquote>: 블록 인용 요소
  - <cite>: 창작물 참조 요(출처)
  - <br>: 줄바꿈 요소
    - 줄을 바꿀때만 사용
    - 두번 연속으로 사용하지 말도록함
      - 두번 사용하는 경우라면 단락(<p>)이 필용한 부분이 아닌지 확인 해볼것

  - <q>
{% highlight html %}
<q></q>
{% endhighlight %}

  - <blockquote>
{% highlight html %}
<blockquote>
    <p></p>
    <p></p>
    <p></p>
</blockquote>
{% endhighlight %}

  - <cite>
{% highlight html %}
<blockquote>
    <p>
        <q></q>
    </p>
    <p></p>
    <p></p>
    <cite></cite>
</blockquote>
{% endhighlight %}

  - <br>
{% highlight html %}
<blockquote>
    <p>
        <q></q>
    </p>
    <p></p>
    <p> <br> </p>
    <cite></cite>
</blockquote>
{% endhighlight %}

# HTML 어휘 요소들
  - Semantic, Non-semantic 요소가 모두 있음
  - Semantic
    - <storng>: 중요성 강조 요소(중첩가능)
    - <em>: 일반적인 내용상 강조 요소
  - Non-semantic
    - <b>: 단순 구분 목적으로 사용
    - <i>: 단순 구분 목적으로 사용됨, 기술적 용어, 관용구 등에 사용됨


# HTML 어휘 요소들
  -










