---
title: "css-basic"
author: "savourycrab"
---

# CSS Style
  - Inline style
    - 태그 엘리먼트에 직접 CSS를 지정하는 형식
    - 추 후 수정 등이 어려워 사용하지 않는게 좋음
{% highlight html %}
<!doctype html>

<html>
<head>
    <meta charset="utf-8" />
    <title>Inline Style</title>
</head>
<body>
    <p style='color:#ff0a00'>이 문장은 인라인 스타일이 적용되었습니다.</p>
    <p>이 문장은 일반 문장입니다.</p>

</body>
</html>
{% endhighlight %}

  - External style
    - 동일한 태그에 적용할 CSS를 지정하거나, 식별자를 지정하여 CSS를 지정하는 형식
    - Inline style과 같이 HTML파일 내에 작성하지만 태그 밖에 따로 형식을 지정해 사용
{% highlight html %}
<!doctype html>

<html>
<head>
    <meta charset="utf-8" />
    <title>Internal Style Sheet</title>
<style type="text/css">
    p {color:#ff0a00; font-size:30px; } <!-- 글자색을 #ff0a00 으로, 글자크기를 30px로 지정-->
</style>
</head>
<body>
    <p>내부 스타일 시트가 적용된 문장입니다.</p>
    <p>모든 p에 적용됩니다.</p>
</body>
</html>
{% endhighlight %}

  - Outer style
    - External style과 같이 태그 또는 식별자로 구분하여 CSS를 지정하는 형식
    - External style과 달리 CSS파일을 따로 만들어 Import 해서 사용함
{% highlight html %}
- Index.html
--------------------------------------------------------------
<!doctype html>

<html>

<head>

<meta charset="utf-8" />

<title>sub</title>

<link rel="stylesheet" type="text/css" href="style.css" >

</head>

<body>

         <h1>외부 스타일 시트가 적용된 문장.</h1>

         <h2>서브 페이지</h2>

         </body>

         </html>
--------------------------------------------------------------

- Style.css
--------------------------------------------------------------
    h1 {
         color:#ff0a00;
         border:3px solid blue;
         width:600px;
         padding:10px;
    }

    h2 { 
        color:green;
    }
--------------------------------------------------------------
{% endhighlight %}

# CSS 식별자
  - 












