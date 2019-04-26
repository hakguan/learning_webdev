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