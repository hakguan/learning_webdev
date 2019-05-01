# learning_webdev
Learning Web Development with HTML, CSS and JS
These are what I learned, not for teaching

1. HTML *(HyperText Markup Language)*
2. CSS *(Cascading Style Sheets)*
3. JavaScript 

# 관련 내용
## 1. Web 개발에 유용한 사이트 및 도구
- Chrome 개발자 도구
- [Google 검색](https://google.com)
- [w3schools](https://www.w3schools.com)
  - HTML, CSS 관련 튜토리얼 및 관련 지식(태그 등) 확인 가능
  - Python, PHP, SQL, jQuery, Java 등도 제공
- [Stack Overflow](https://stackoverflow.com) (가장 큰 개발자 커뮤니티)
- [JSFiddle](https://jsfiddle.net)
  - HTML, CSS, JS를 테스트해볼 수 있는 기능 제공
  - Stack overflow에 질문할 때 코드를 JSFiddle에서 작성하고 저장한 후에 링크를 공유하면 보다 쉽게 질문을 이해시킬 수 있음 
## 2. HTML / CSS
- Optional Tags를 꼭 사용해야 하는가?
  - 정리(organization)의 목적으로 사용할 수 있으나의견은 분분함
  - [구글 HTML/CSS 스타일 가이드](https://google.github.io/styleguide/htmlcssguide.html#Optional_Tags)에서는 옵셔널 태그를 생략하는 것을 권장함
- class와 id의 차이점?
  - 하나의 파일에서 중복하여 사용될 수 있는가(class는 중복사용 가능, id는 중복 불가능)
    - class (가능)
        ```html
        <p class="big-text">paragraph 1</p>
        <p class="big-text">paragraph 2</p>
        ```
    - id (불가능)
        ```html
        <p id="best-text">paragraph 1</p>
        <p id="best-text">paragraph 2</p>
        ```
  - 또한 class는 한번에 여러개를 사용할 수 있지만, id는 한번에 한개만 적용 가능
    - class (가능)
        ```html
        <p class="big blue">paragraph 1</p>
        ```
    - id (불가능)
        ```html
        <p id="best first">paragraph 1</p>
        ```
  - 따라서, 여러 요소를 스타일링 하고 싶을 땐 class, 한 요소만 스타일링 하고 싶을 땐 id를 사용한다고 기억
- html 문서에 style을 입히는 방법
    1. 외부 CSS파일 + \<link> 태그 ***(가장 선호됨)***
        ```html
        <link href="css/style.css" rel="stylesheet">
        ```
    2. html 문서 내에 \<style> 태그 사용
        ```html
        <head>
            <style>
                body {
                    color: blue;
                }
            </style>
        </head>
        ```
    3. html 문서의 각 태그 내에서 style 속성 사용
        ```html
        <h1 style="color: red; font-size: 72px;">Heading 1</h1>
        ```
- color를 표현하는 방법
    1. 색 이름
    2. rgb 값
    3. hex
    ```Html
    <!--예시(순서대로 표기방법)-->
    <style>
        h1 {
            color: blue;
            color: rgb(34, 50, 90);
            color: #61F96B;
        }
    </style>
    ```
- text에 적용할 수 있는 텍스트 스타일링 속성
    ```Css
    h1 {
        font-size: 32px;
        font-weight: 700; 
    /*- 굵기를 표현하는 속성으로 100~900 사이의 값을 가짐(100단위)
    - 브라우저마다 지원하는 값이 다를 수 있음*/
        text-align: left;
    /*left, center, right*/
        text-decoration: unterline;
    /*none, underline, overline, line-through*/
    }
    ```
- 텍스트 font 크기
    1. 절대적크기(absolute) : px, pt
        - pt는 px의 1.33배 (워드 프로그램 등에서 사용, 웹에서 잘 사용하지는 않음)
    2. 상대적크기(relative) : em, %
        - 1em은 100%와 같음
        - %의 경우 부모 요소의 폰트 크기를 기준으로 함(바로 상위의 부모 요소)
- 폰트 설정 방법
    1. 사용자 컴퓨터에 설치되어 있는 폰트 사용
       - 폰트의 유형 : serif, sans-serif, monospace, cursive, fantasy
       ```Html
       <style>
           h1 {
               /*폰트에 띄어쓰기가 있는 경우 "" 안에 넣어줘야 함*/
               font-family: "Times New Roman", Times, serif;
               /*--브라우저에서 위의 순서대로 폰트를 찾아서 사용하도록 함(사용자의 컴퓨터에 설치되어 있지 않은경우 다음 안으로 넘어감*/
           }
       </style>
       ```
    2. 웹폰트 사용
        - [Google 폰트 사용](https://fonts.google.com)
        ```Html
        <head>
            <link href="https://fonts.googleapis.com/css?family=Roboto+Condensed|Source+Sans+Pro" rel="stylesheet">
        </head>
        <style>
            h1 {
                font-family: 'Roboto Condensed', sans-serif;
            }
            h2 {
                font-family: 'Source Sans Pro', sans-serif;
            }
        </style>
        ```
        - [Google 폰트 earlt access](https://fonts.google.com/earlyaccess)
            - Korean을 검색해서 한글 지원 폰트 사용 가능(정식버전에서도 한글을 지원하는 폰트 찾을 수 있음)
    3. 파일로 제공되는 폰트 사용
        - 폰트 파일을 프로젝트 폴더 내에 넣고 경로 지정
        ```Css
        @font-face {
            src: url("../fonts/BMHANNAPro.ttf");
            font-family: "Hanna";
        }

        p {
            font-family: "Hanna";
        }
        ```
- 구역을 구분하는 태그 : \<div>, \<span>
    - div 태그는 block display
    - span 태그는 inline display
- Box model
![box model](/box_model/images/box-model-intro.png)
    - contents
    - padding
    - border
      - soild, dotted, dashed 등
      - input 태그 등의 경우 기본적으로 태두리가 설정되어 있으나, 없애고 싶을 때는 두 가지 방법이 있음
        1. border: none;
        2. border: 0;
    ```Html
    <style>
        h2 {
            border: 3px dashed green;
            /*가장 일반적*/
        }
        .p1 {
            border-style: solid;
            border-color: #4d9fff;
            border-width: 5px;
        }
        h1 {
            border-top: 3px dotted #4d9fff;
            /*각 면을 다르게 정의하고 싶을 때*/
        }
        p {
            border-radius: 10px; /*둥근 모서리*/
            /*border-top-left-radius, top-right, bottom-left, bottom-right로 각각 설정가능*/
            box-shadow: 10px 10px 50px 10px red/*가로위치, 세로위치, 흐림정도 크기 색*/
            /*none; 기본값*/
        }
    </style>
    ```
    - margin
    - width, height
      - 최대(max), 최소(min) 값도 설정할 수 있음
      - max 설정으로 넘친 내용의 경우 overflow로 처리할 수 있음
      - overflow: visible(기본값), hidden, scroll, auto
    - box 꾸미기
      - background color / image
        ```Html
        <style>
        p {
            background-color: rgb(232, 95, 20); /*박스 배경색*/
            /*transparent; 는 배경색을 투명하게 해줌(기본값)*/       
        }
        body {
            background-color: gray; /*페이지 배경색*/
        }
        div {
            background-image: url("../images/beach.jpg")
            background-repeat: no-repeat;
            /*
            no-repeat: 반복하지 않음
            repeat-x: 가로 반복
            repeat-y: 세로 반복
            repeat: 가로 및 세로 반복
            space: 반복할 수 있는 만큼 반복한 뒤, 남는 공간은 이미 간 여백으로 배분
            round: 반복할 수 있는 만큼 반복한 뒤, 남는 공간은 이미지 확대를 통해 배분
            */
            background-size: cover; 
            /*
            px, %로 값 지정(%의 경우 부모 요소의 width, height에 맞춰 출력)
            auto: 원래 이미지 사이즈대로 출력
            cover: 화면을 꽉 채우면서 사진 비율 유지(box 크기에 따라 잘릴 수 있음)
            contain: 가로 및 세로 중 먼저 채워지는 쪽에 맞춰 출력
            */
            background-position: center center;
            /*
            배경 이미지의 위치를 정해주는 속성으로 배경의 위치 및 배경이 잘리는 경우 기준 점을 설정해주는 효과
            1. left/right/center top/bottom/center 로 지정
            2. %로 지정(left, top을 기준으로)
            3. px로 지정(left, top을 기준으로)
            */
        }
        </style>
        ```
      - box-shadow
        ```Html
        <style>
        /*기본값: none;*/
        /*위치 설정*/
        p {
            box-shadow: 50px 40px; /*가로위치 세로위치*/
            /*그림자 색 추기(기본값 black)*/
            box-shadow: 50px 40px #4d9ff;
            /*흐림정도(blur, 기본값 0px)*/
            box-shadow: 50px 40px 10px #4d9ff; /*가로 세로 blur 색*/
            /*그림자 크기(spread)*/
            box-shadow: 50px 40px 10px 20px #4d9ff; /*가로 세로 blur spread 색*/
        }
        </style>
        ```
      - box-sizing
        - padding, border를 포함해서 width, height에 맞추고 싶을 때 사용
        ```Html
        <style>
        h1 {
            width: 300px;
            height: 200px;
            padding: 35px;
            border: 5px solid red;
            box-sizing: border-box; /*기본값: content-box*/
            /*
            box-sizing을 사용하지 않을 경우 총 box의 크기는 
            너비 = width + padding * 2 + border * 2
            높이 = height + padding * 2 + border * 2
            */
        }
        </style>
        ```
- ***CSS 선택자 정리***
    - [관련문서](https://github.com/hakguan/learning_webdev/tree/master/css_selector)
    - 태그 이름
    - 클래스/아이디
    - 자식(children)
    - 직속 자식(direct children)
    - 복수 선택
    - 여러 조건
    - Pseudo-class(가상 클래스)
    - 마우스 오버(hover)
- CSS 상속
    - 상속되는 속성들
      1. color
      2. font-familiy / size / weight
      3. line-height
      4. list-style
      5. text-align
      6. visivility
    - 위의 속성들을 대부분의 경우 상속되지만 예외적인 경우도 존재함
        - \<a> 태그의 경우 color 속성이 상속되지 않음
    ```Css
    .div2 {
        color: green;
    }
    .div2 a {
        color: inherit;
    /* color 속성을 inherit으로 지정하면 강제로 부모 속성값을 상속받을 수 있음 */
    }
- CSS 우선순위
    - 같은 요소를 가리키지만 선택자가 다른 경우 명시도(Speciticity) 점수에 따라 우선순위가 결정됨
      1. Inline Styles
      2. IDs
      3. Classes, attributes, pseudo-classes
      4. Elements, pseudo-elements
    - 각 요소의 개수를 순서대로 1000, 100, 10, 1 자리로 반환하여 명시도 점수를 계산할 수 있음
    ```Css
    ul li:first-child #link {
       color: green;
    }
    /* 13점 */
    ul li:first-child a {
        color: orange;
    /* 112점 */
    }
    ```
- CSS의 단위
    - px, em, rem
    - [참고 사이트](https://webdesign.tutsplus.com/ko/tutorials/comprehensive-guide-when-to-use-em-vs-rem--cms-23984)
- display 속성
    - inline, block, inline-block, list-item, table, flex, none, ...
    - 각 HTML 요소는 이 중 하나의 속성을 가지고 있음
    - 대표적으로 inline(\<span>, \<b>, \<img> 등), block(\<div>, \<h1>, \<p> 등)이 있음
    -  본래 가지고 있는 속성을 바꿔줄 수 있음
    ```Css
    i {
        display: block;
    }
    /*<i> 태그는 inline 속성이나 block 속성을 지정해 줄 수 있음*/
    div {
        display: inline;
    }
    /*<div> 태그는 block 속성이나 inline 속성을 지정해 줄 수 있음*/
    ```
    1. inline
       - 다른 요소들과 같은 줄에 머무르려고 하는 성향과, 필요한 만큼의 가로길이만 차지하는 성향이 있음
       - span, a, b, i, img, button 등의 요소는 기본 display 값이 inline임
       - \<img>는 대체요소(replaced element)라고 불리는 inline요소로, 가로 및 세로 길이를 지정할 수 있는 inline 요소임
         - image와 text가 한 줄에 있을 경우 vertical-align을 사용(top, middle, bottom)하면 그림의 위, 중간, 아래를 기준으로 정렬됨
    2. block
       - 다른 요소들과 독단적인 줄에 가려고 하는 성향과, 최대한 많은 가로 길이를 차지하는 성향이 있음
       - div, h1, h2..., p, nav, ul, li 등의 요소는 기본 display 값이 block임
    3. inline-block
       - inline 요소는 가로와 세로 길이가 auto로 내용에 따라 달라져 width, height를 설정할 수 없음
       - inline-block으로 display를 설정하면 inline의 성향을 유지하면서 width와 height를 설정할 수 있음
    4. flex
    5. list-item
    6. none
- Baseline
    - inline으로 정렬된 항목의 경우 baseline에 맞춰 정렬됨
    - text의 경우 box가 아닌 text를 기준으로 baseline이 설정됨
    - image의 경우 image의 최하단이 baseline으로 설정됨
    - inline-block의 경우 inline-block에 포함된 요소 중 가장 아래 요소의 baseline이 inline-block의 baseline으로 설정됨
      - inline-block에 요소가 없는 경우 box를 기준으로 baseline에 설정됨
      - box의 크기보다 contents의 크기가 클 경우 overflow 속성에 따라 baseline이 바뀜(visible인 경우 일반적인 경우와 동일하고, scroll인 경우 box를 기준으로 설정됨)
- Vertical-align
    - vertical-algin 속성은 inline 또는 inline-block 요소에 적용됨
    - vertical-align의 기본값은 baseline으로 설정되어 있음
      - 기준이 되는 baseline은 부모 속성의 baseline임
    - vertical-align: top;을 할 경우, 같은 line에 있는 요소들 중 가장 높이 있는 요소에 맞춰지면서 baseline이 바뀔 수 있음
      - baseline은 vertical-align의 조건들을 충족시키면서 줄의 높이를 최소화시키는 곳에 위치함
    - vertical-align: middle;을 할 경우, 부모 태그의 가운데와 맞춰짐
    - *세로 가운데 정렬*
    - [참고 사이트](https://www.w3schools.com/css/css3_flexbox.asp)