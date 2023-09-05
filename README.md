# css 기초 수업 #

## 230905 ##

#### 1. css 기초 ####

* style sheet 언어. HTML 문서의 레이아웃과 스타일을 적용 할 수 있다.

* css 기본 구조 
`선택자(selector) { 속성 (property) : 값 (value); }` <- 기본 구조의 선언문

* css 선언방식
    * 외부 선언
    	* `<head>` 안에 `<link>`로 선언. 
	* css 문서를 만들어 `<link rel="stylesheet" href="파일.css 경로">`로 연결
 * 내부 선언
		* `<head>` 안에 `<style>`을 사용하여 작성
		* `style` 태그 안은 CSS 영역.
	* 직접(인라인) 선언
		* html `body` 안에 쓰인다. 제어가 어려워서 잘 사용하진 않음.
		* `<a href="#" style="특성:값">`으로 작성
* 기본 선택자의 종류
	* 타입(태그) : `h1`와 같이 태그 그대로 사용. HTML 태그를 지정하여 선언.
	* 아이디`#` : `#hanywyam`와 같이 `#`를 사용. HTML 코드중 지정한 고유의 id 값. 하나의 html 문서 안에서 고유한 이름을 가지며 다른 id에 같은 이름을 쓸 수 없음. 요소에 대해 유일한 특성을 정의 할 때, 자바스크립트로 해당 요소를 조작할 때 사용.
	* 클래스`.` : `.hanywyam`와 같이 `.`을 사용. 하나의 페이지에 다양하게 사용 가능. 
		* html문서에 속성값을 두개 이상 가질 수 있다. 불특정 다수의 꾸밈을 줄 때 주로 사용.
		* 한 문서 안에서 같은 이름을 여러 번 사용할 수 있기 때문에 주로 꾸밈 값을 줄 때나 공통된 값 적용시 사용. 
		* 요즘은 특별한 일 없을때 대부분 클래스명을 사용하는 편
	* `!important` : 동일 요소에 적용되는 다른 규칙보다 우선 적용되며 기본 우선 순위가 무시.
		* style 뒤에 공백(space) 후 `!important` 를 추가
		* 꼭 필요한 경우에만 사용, 남용금지.

> css 선택자 mdn참고 https://developer.mozilla.org/ko/docs/Learn/CSS/Building_blocks/Selectors

#### 2. 글자 색상 color ####

* color 특성
	* `color name: orange` ->color name으로 작성
	* `hex: #FF5F00` ->hex R(fc)G(00)B(ff) 6자리가 기본
	* `rgb: rgb(0,55,150)`  ->rgb(red,green,blue) 최대 255값까지 표현 
	* `rgba(50,100,250,0.7)` ->rgba(red,green,blue,alpha) 마지막 자리수는 백분율값으로 불투명도 0~1 사이의 값을 가짐.
	* `hsla(217, 97%, 47%,0.8)` ->color:hsla(색상hue, 채도saturation%, 명도lightness%, 불투명도alpha)

#### ​3. css 명령어 우선순위 ####

* 같은 이름 혹은 같은 종류의 선택자 혹은 같은 종류의 속성인 경우
	* 위에서 아래로 순차적으로 적용되고, 마지막에 선언된 스타일이 우선 순위를 갖는다.

* 같은 선택자가 아닌 다른 종류 선택자인 경우
	* !important > (직접,inline > ) #id(5) > .class(3) > type(1) 순으로 우선 순위를 갖는다.
	* 복합 선택자일때 각 점수를 합해 큰 값이 표현된다.

* 다른 종류의 선언문이며 같은 선택자인 경우
	* (직접, inline > ) 내부선언 > 외부선언 순으로 우선 순위를 갖는다.
