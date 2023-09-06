# css 기초 수업 #

## 230905 ##

#### 1. css 기초 ####

* **style sheet 언어.** HTML 문서의 레이아웃과 스타일을 적용 할 수 있다.

* **css 기본 구조**
`선택자(selector) { 속성 (property) : 값 (value); }` <- 기본 구조의 선언문

* **css 선언방식**
    * 외부 선언
    	* `<head>` 안에 `<link>`로 선언. 
    	* css 문서를 만들어 `<link rel="stylesheet" href="파일.css 경로">`로 연결
    * 내부 선언
    	* `<head>` 안에 `<style>`을 사용하여 작성
    	* `style` 태그 안은 CSS 영역.
    * 직접(인라인) 선언
    	* html `body` 안에 쓰인다. 제어가 어려워서 잘 사용하진 않음.
    	* `<a href="#" style="특성:값">`으로 작성

* **기본 선택자의 종류**
	* 타입(태그) : `h1`와 같이 태그 그대로 사용. HTML 태그를 지정하여 선언.
	* 아이디`#` : `#hanywyam`와 같이 `#`를 사용.
		* HTML 코드중 지정한 고유의 id 값. 하나의 html 문서 안에서 고유한 이름을 가지며 다른 id에 같은 이름을 쓸 수 없음.
   		* 요소에 대해 유일한 특성을 정의 할 때, 자바스크립트로 해당 요소를 조작할 때 사용.
	* 클래스`.` : `.hanywyam`와 같이 `.`을 사용. 하나의 페이지에 다양하게 사용 가능. 
		* html문서에 속성값을 두개 이상 가질 수 있다. 불특정 다수의 꾸밈을 줄 때 주로 사용.
		* 한 문서 안에서 같은 이름을 여러 번 사용할 수 있기 때문에 주로 꾸밈 값을 줄 때나 공통된 값 적용시 사용. 
		* 요즘은 특별한 일 없을때 대부분 클래스명을 사용하는 편
	* `!important` : 동일 요소에 적용되는 다른 규칙보다 우선 적용되며 기본 우선 순위가 무시.
		* style 뒤에 공백(space) 후 `!important` 를 추가
		* 꼭 필요한 경우에만 사용, 남용금지.

> css 선택자 mdn참고
> https://developer.mozilla.org/ko/docs/Learn/CSS/Building_blocks/Selectors

#### 2. 글자 색상 color ####

* **color 특성**
	* `color name: orange` ->color name으로 작성
	* `hex: #FF5F00` ->hex R(fc)G(00)B(ff) 6자리가 기본
	* `rgb: rgb(0,55,150)`  ->rgb(red,green,blue) 최대 255값까지 표현 
	* `rgba(50,100,250,0.7)` ->rgba(red,green,blue,alpha) 마지막 자리수는 백분율값으로 불투명도 0~1 사이의 값을 가짐.
	* `hsla(217, 97%, 47%,0.8)` ->color:hsla(색상hue, 채도saturation%, 명도lightness%, 불투명도alpha)

#### ​3. css 명령어 우선순위 ####

* **같은 이름 혹은 같은 종류의 선택자 혹은 같은 종류의 속성인 경우**
	* 위에서 아래로 순차적으로 적용되고, 마지막에 선언된 스타일이 우선 순위를 갖는다.

* **같은 선택자가 아닌 다른 종류 선택자인 경우**
	* !important > (직접,inline > ) #id(5) > .class(3) > type(1) 순으로 우선 순위를 갖는다.
	* 복합 선택자일때 각 점수를 합해 큰 값이 표현된다.

* **다른 종류의 선언문이며 같은 선택자인 경우**
	* (직접, inline > ) 내부선언 > 외부선언 순으로 우선 순위를 갖는다.

## 230906 ##

#### font 와 text ####

* **서체 사용시 주의사항**
	* 1. 정확한 서체명 작성( 띄어쓰기 인용부호 대소문자 등)
	* 2. 상대방의 컴퓨터에 서체가 없는 경우를 대비해 3-4개 서체를 추가 작성(fallback fonts)
	* 3. 바탕체 종류로 끝나는 경우 제일 마지막은 serif로 작성
	* 4. 돋움(고딕)체로 끝나는 경우 제일 마지막은 sans-serif로 작성
	* 5. 웹의 기본단위값 : px

* **폰트 사용 시 고려 사항**
	* 폰트 라이선스는 해결 되었는가?
	* 힌팅 폰트로 제작 되었는가?


* **font와 text의 여러 특성들**
* `font-family`: 서체 종류
	* 페이지에서 보여지는 폰트 스타일을 설정. 
	* 열리는 곳마다 저장된 폰트가 다를 수 있어 대체 글꼴을 함께 작성해준다.
	* 돋움, sans-serif 또는 바탕, serif 로 마지막에 글꼴을 정의해준다.

* `font-size`: 서체 크기
	* 웹 브라우저 공통 기본 서체 크기는 16px로 사용한다.

* `font-weight`: 서체 굵기
	* normal, bold, 100~900값으로 설정.

* `font-style`: 서체 스타일
	* normal, oblique, italic

* `text-transform`: 대소문자
	* 영문에서 대.소문자 관리. 한글은 대소문자가 없으니까 적용안됨.
	* `lowercase`: 전부다 소문자로 변경
	* `uppercase`: 전부다 대문자로 변경
	* `capitalize`: 모든 단어의 첫글자만 대문자로 변경

* `text-decoration`: 밑줄 및 취소선
	* `overline`: 글자 상단에 밑줄
	* `line-through`: 글자 중간에 밑줄. 취소선
	* `underline`: 글자 하단에 밑줄
	* `dashed`: 밑줄에 점선
	* `none`: 효과 전체 삭제

* `text-align`: 들여쓰기 / 내쓰기
	* `left`: 왼쪽
	* `right`: 오른쪽
	* `center`: 중앙
	* `justify`: 양 끝 기준 정렬. 문단의 양 끝을 일렬로 맞추고 맨 마지막 줄만 왼쪽으로 정렬. 글자보다는 이미지 정렬에 적합

* `text-shadow`: 서체 그림자
	* `text-shadow` 작성시 반드시 띄어쓰기를 해야하며 ,를 사용하지 않는다. 
	* x축 y축 번짐 색상 값 순으로 작성.
	* 자세한건 3_text-shadow.css 파일 확인

* `line-height`: 줄과 줄 사이 간격. 행간.
	* 보통 1.4~1.6배로 설정
	* `line-height: 30px;` ->웹의 기본 단위 값은 px이지만, 폰트사이즈가 변경될때 계속 고정되어 있는 값으로 나타나기때문에 행간에서는 px을 거의 사용하지 않음.
	* `line-height: 1.3em;`
	* `line-height: 1.6;` ->단위 값 없이 작성하면 배수의 값

* `letter-spacing`: 글자와 글자 사이 간격. 자간.
* `word-spacing`: 단어와 단어 사이 간격. 어간.