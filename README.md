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
- 구역을 구분하는 태그 : <div>, <span>
    - div 태그는 block display
    - span 태그는 inline display