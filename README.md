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
	* transparent 색 없음. 색상의 기본값 표시. 투명.

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

* `text-indent`: 들여쓰기/ 내쓰기. 들여쓰기보다는 내쓰기를 주로 많이 쓰인다.
	* `text-indent: 100px;` 첫 문장만 들여쓰기
	* `text-indent: -120px;` 첫 문장만 내쓰기. 웹 문서 바깥쪽으로 이동.

* `text-align`: 문자 정렬
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

## 230907 ##

#### font 와 text2 ####

상속값 vs 직접 입력된 값이 있을 때
-> 직접 적용된 값이 우선으로 스타일이 적용되지 않는다.

#### 1. 마우스 이벤트: `<a>` 태그 스타일 주기 #### 

* `:`, `::`
	* 가상 선택자로 다양한 종류가 있으며 주로 실제하는 요소와 함께 작성.
	* 예) 의사 클래스, 의사 요소, 수열 선택자...
	* :link, :visited, :hover, :focus, :checked ...
	* 최근 만들어진 스타일은 `::` 두개를 사용하는 경우가 많다.

```css
    a:link{ 링크 상태일 때 (기본)
      color: aquamarine;
    }
    a:visited{ 방문했을 때
      color: yellow;
    }
    a:hover{ 마우스를 위에 올렸을 때
      text-decoration: line-through;
      color: #FF3Fa4;
    }
    a:active{ 클릭했을 때
      background-color: orange;
      color: #fff;
    }
    [required]:focus{ 포커스(커서가 보이는 상태)되었을 때
      background-color: #ffcc70;
    }
```
* 모든 이벤트에 효과를 나타낼 수 있지만, 이렇게 사용하진 않는다.
* 주로 사용하는 방법.

```css
    a{
      color:inherit; /* 상속 */
      text-decoration: none;
    }
    a:hover{
      background-color: orange;
      color: #fff;
    }
```
* `inherit`을 이용해 위의 설정값을 상속하여 기본 스타일을 삭제한다.

#### 2. `<form>` 요소 스타일 주기 #### 
* form 관련 요소들은 기본 스타일이 존재하기 때문에 변경하고자 하는 요소에 직접 적용

#### 3. 배운 내용을 활용하여 Ex #### 

#### 4. 인라인 세로 정렬 `vertical-align` #### 
* 서체 및 인라인 요소 세로 정렬 기준
* 글씨와 이미지 및 input의 정렬 상태가 맞지 않는다면, 이미지 요소 및 input에 `vertical-align`적용
	* `top` :현재 요소와 자손들 모두 top 기준. 단, 텍스트는 행간이 존재하기 때문에 상단 여백이 남는다.
	* `baseline` :기본값
	* `bottom` :현재 요소와 자손들 모두 bottom 기준
	* `middle` :부모 기준(baseline 기준으로 글자 높이의 반)

#### 5. 가로 세로 영역 제어 `width`, `height` #### 
1. 블록 요소(p, div, h1, header, main, article, form, ul...)
 - 가로 값의 경우 부모 요소의 가로 값을 받음
 - 일반적인 흐름에서는 블록 요소 옆에 다른 요소가 올 수 없음
 - 자식으로 블록, 인라인 요소 등 대부분이 올 수 있음
 - 세로 값의 경우 자식 요소의 높이 값을 그대로 가져 옴
 - `width`, `height`로 제어 가능

2. 인라인요소(span, img, a, em, input, strong...)
 - 가로 값의 경우 자식(컨텐츠)의 값을 가져 옴
 - 인라인 요소 옆에 다른 인라인 요소가 올 수 있음
 - 자식으로 인라인 요소만 올 수 있음
 - 세로 값의 경우 자식 요소의 높이 값을 그대로 가져옴
 - `width`, `height`로 제어 불가능

* 고정 너비
	* px을 이용해 너비를 설정. 고정값.
	* `width: 500px; height: 300px;`
* 가변 너비 
		* % 를 이용해 페이지 내 백분율 단위로 표현. 페이지 사이즈에 따라 변한다.
		* 요즘은 사용하는 디바이스가 다양하기 때문에 더 많이 씀.
	* `width: 70%;`
	* `height: 50%;`
		* % :상대단위. width-> 부모를 기준으로 100분의 70. height-> 부모를 기준으로 100분의 50.
		* 세로 %는 부모의 높이 값이 정의되어 있는 경우에만 적용 됨. 기본값일 때는 적용되지 않는다.

## 230908 ##

* **박스 모델: 실제 콘텐츠 영역. 박스와 콘텐츠 영역 사이의 여백인 패딩(padding), 박스의 테두리(border), 그리고 여러 박스 모델 간의 여백인 마진(margin) 등의 요소로 구성되어 있다.**
- 박스 영역의 값 적용 순서는 top-right-bottom-left 시계방향 순 이다.
```
		`top`
	┌──────────────────┐
	│     margin       │
	│ ┌──────────────┐ │
	│ │   border     │ │
	│ │ ┌──────────┐ │ │
`left`	│ │ │          │ │ │	`right`
	│ │ │ padding  │ │ │
	│ │ │          │ │ │
	│ │ └──────────┘ │ │  
	│ └──────────────┘ │
	└──────────────────┘
		`bottom`
```

## 1. 테두리 border ##
- 방향 지정 없이 입력 가능.
- 방향을 따로 입력하면 입력한 영역에만 스타일이 나타난다.
	- `border-width` 테두리 굵기
		- `border-top-width: 10px;`
		- `border-bottom-width: 3px;`
		- `border-right-width: 2px;`
		- `border-left-width: 2px;`
	- `border-style` 테두리 스타일
		- `solid` : 기본선. 한줄.
		- `dotted` : 도트선. 점선으로 점으로 표현.
		- `double` : 이중선. 두줄. 3px 이상에서만 보임.
		- `dashed` : 대쉬선. 점선으로 선으로 표현.
		- `groove` : 입체선.
	- `border-color` 테두리 색상.
- 축약형: 값의 순서에 상관없이 띄어쓰기로 한번에 입력하여 표현가능.
	- `border: 8px ridge #ffbb5c;`
- 축약형으로 네 방향의 값을 다르게 줄 수 있다.
	- `border-top: tomato 4px dotted;`
	- `border-right: #342db7 2px solid;`
	- `border-bottom: #9d44c0 6px double;`
- override: 적용 성격을 이용해 간결하게 작성할 수도 있다.
ex1
```css
.box{
      border-top: #342db7 3px solid;
      border-right: #342db7 3px solid;
      border-left: #342db7 3px solid;
      border-bottom: #342db7 5px double;
}
```
ex2
```css
.box{
border: 6px solid #000;
border-bottom-style: double;
}
```
- ex1과 ex2는 같은 값이다.

- **`border` vs `otuline`**
- `border`와 달리, `outline`은 요소의 바깥 부분에 그려지고, 요소가 가지는 실제 크기에 영향을 주지 않음. 
- 다른 요소의 영역을 침범할 우려가 있어서 잘 사용하지 않는다.
```css
.box{
      outline-style: solid;
      outline-width: 4px;
      outline-color: #ffbb5c;
/* 축약형 */
      outline: solid 4px #ffbb5c;
}
```

#### 2. 둥근 모서리 border-radius ####
- top-left, top-right, bottom-right, bottom-left순으로 각모서리마다 다른값을 줄 수 있다.
	- `border-radius: 50px 20px 50px 20px;`
- 서로 마주보고 있는 값을 한자리로 인식해서 적용.
	- `border-radius: 50px 20px;`
- 영역 밖으로 내용이 넘칠 때는 `overflow`를 이용해 숨길 수 있다.
	- `overflow: hidden;`

#### 3. 안쪽 여백 padding ####
- 패딩(padding)이란, 콘텐츠 영역과 테두리 사이의 여백을 말한다.
- top right bottom left 순으로 시계방향의 값을 가진다.
	- `padding: 40px 20px 40px 20px;`
- top+bottom=40px, right+left=20px 서로 마주보고 있는 값을 같이 작성 가능.
	- `padding: 40px 20px;`
- right+left=20px 서로 마주보고 있는 값. 같으면 생략해도 적용된다.
	- `padding: 30px 20px 40px;`
- 모두 같을때 하나의 값으로 작성 가능.
	- `padding: 50px;`
```css
.box{

      padding: 50px;
      padding-right: 10px;      /* override */

      padding: 50px 10px 50px 50px;       /* 용량면에서는 기본 작성이 더 효율적 */
}
```

#### 4. 바깥 여백 margin ####
- 마진(margin)이란 기준 요소의 바깥 여백을 말한다.
- top right bottom left 순으로 시계방향의 값을 가진다.
	- `margin: 10px 20px 30px 40px;`
- 서로 마주보고 있는 값을 같이 작성 가능.
	- `margin: 50px 20px;`
- right+left=20px 서로 마주보고 있는 값. 같으면 생략해도 적용된다.
	- `margin: 30px 20px 40px;`
- 모두 같을때 하나의 값으로 작성 가능.
	- `margin: 50px;`
- body에도 기본 margin값이 설정되어 있다. 
- 단, 다른 박스는 padding에만 이미지나 배경색이 적용되는데, body의 경우 예외적으로 padding+margin까지 이미지나 배경색이 적용된다.
- **마진 상쇄 현상** :일반적인 흐름일 때, top과 bottom이 만낫을때 둘 중 큰 값이 적용됨.
    단, 플루트 포지션 그리드..와 같은 상황에서는 적용되지 않음.
- 인접형제 요소 및 부모요소의 margin-bottom과 marigin-top의 마진값이 만났을 때 둘 중 큰 값이 적용.
- 단, float, flex, overflow, position등의 값이 적용된 경우는 발생하지 않음.
	- 1. 형제 관계 요소의 margin-bottom과 margin-top이 만나면 둘 중 큰 값이 적용.
	- 2. 부모 자식 관계 요소에서 margin-top의 값이 같이 들어간 경우 둘 중 큰 값이 적용.


#### 5. 블럭 요소 중앙 정렬 ####
1. 요소의 가로 값이 필요.
2. 일반적인 흐름에서는 left+right값은 항상 auto로 설정.
```css
.box{
      margin: 0 auto 0 auto;      /* top right bottom left */
      margin: 20px auto;          /* top+bottom=20, right+left=auto */
      margin: auto;               /* 일반적인 상황의 auto=>가로 중앙 정렬만, 세로 중앙 정렬은 하지 않는다. */
      margin: auto 0;            /* 세로는 오토가 먹지 않아서 값이 변하지 않음 */
      margin: 20px auto 0;       /* top right+left bottom */
    }
```
- "한 줄인 경우" 세로(위아래) 중앙 정렬 방법
	- `height`와 `line-height`의 값을 동일하게 적용
	- 영역에서 글이 두 줄 이상, 폰트 사이즈의 크기가 큰 경우는 잘 안됨.
```css
.wrapper .site{
  background-color: aqua;
  border-bottom: 1px solid #fff;
  height: 40px;
  line-height: 40px;
}
```

## 230911 ##

0. margin+paddingEx

#### 1. 넘치는 컨텐츠 제어 overflow ####
- 고정된 크기를 가진 부모요소에서 컨텐츠가 넘칠 때 스크롤바 표시 여부 결정
	- `overflow: visible;` 기본값. 이미 갖고 있는 값. 한정된 영역에서 컨텐츠가 넘치면 무조건 보여짐.
	- `overflow: hidden;` 한정된 영역에서 컨텐츠가 넘치면 무조건 숨김. 많이사용★
	- `overflow: auto;` 한정된 영역에서 컨텐츠가 넘치면 자동으로 스크롤이 생기고 넘치지 않으면 스크롤이 생기지 않음.  많이사용★
	- `overflow: scroll;` 한정된 영역에서 컨텐츠가 넘치든 넘치지 않든 무조건 스크롤이 생김.
	- `overflow: inherit;` 상속. 상속은 현재 부모나 조상 요소에 overflow가 적용된 게 없으면 상속 받지 못함.
- overflow X축 컨트롤
```css
.box{
  overflow-y: hidden;  /* 1. 일단 y축 없애줌 */

/* 2. 글자의 띄어쓰기 기준으로 줄바꿈 처리 */
  white-space: wrap;   /* 기본값. */
  white-space: nowrap; /* br요소로 직접 줄바꿈 시키는 것 외엔 자동 줄바꿈 되지 않음 */
}
- overflow Y축 컨트롤
```css
.box7{
  overflow-y: scroll;  /* 무조건 스크롤 */
  overflow-y: hidden;  /* 넘치면 숨기기 */
  overflow-y: auto;    /* 넘치면 스크롤 */
}
```

2. overflowEx

#### 3. 요소 성격 변경 display+visibility+opacity ####
- `display` 블록 레벨 요소를 인라인 요소로 바꾸거나 인라인 레벨 요소를 블록 레벨 요소로 바꿀 수 있다.
	- `inline` 블럭요소를 인라인 요소로 변경. 요소의 기본 성격 변경. 상속X. 해당하는 요소에만 적용.
	- `block` 인라인요소를 블럭요소로 변경.
	- `inline-block` 
		- 인라인, 블록 성격 모두 가짐
		- 인라인처럼 띄어쓰기, 줄바꿈 인식
		- 인라인처럼 line-height 값을 가짐
		- 블록처럼 width, height 값을 가짐
		- 가로 중앙 정렬의 경우 인라인, 블록 적용 방식 다 가능.
		- 다만, 띄어쓰기가 있어 인라인 방식으로 정렬하는 것이 좀 더 편함.
	- `none` 브라우저 영역에서 사라짐. 코드 창에서만 확인 가능하며 레이아웃에 영향을 줌.
- `visibility: hidden;` 브라우저 영역은 남으나 컨텐츠가 보이지 않음. visible=보임, hidden=숨김
- `opacity`: 불투명도 조절. 자식에게까지 영향을 줌. 0~1사이 값
```css
    .menu1 .opacity{
      opacity: 0.542;
      /* 불투명도 조절. 자식에게까지 영향을 줌. 0~1사이 값 */
    }
```

4. displayEx1
5. displayEx2


## 230912 ##
﻿
#### 박스 모델: 요소의 실제 크기 계산법 ####
1. 요소의 실제크기1
2. 요소의 실제크기2
3. box-sizing
4. box-sizingEx

#### 어절 기준 줄바꿈 제어(띄어쓰기 기준) ####
- `word-break: normal;` 기본값.
- `word-break: break-all;` 어절에 맞춰 줄바꿈. 단, 영어 한정.
- `word-break: keep-all;` 어절을 유지하며 줄바꿈. 한글에 적합.



## 230913 ##

#### 1. 리스트 스타일 축약형 ####
* ul의 앞머리 스타일을 변경.
* 지우거나 다른 아이콘(영문, 라틴, 동그라미, 네모 등)으로 변경 가능.
* `ul`에 스타일을 주거나 `li`에도 사용 가능.
```css
    ul{
      width: 300px;
      /* 잘 사용하진 않음.
      list-style-type: lower-greek;
      list-style-position: inside;
       */
       list-style: inside square;       /* 축약형. 띄어쓰기로 구분. */
       list-style: none;                /* 가장 많이 사용. 
       특히, 메뉴를 만들 때 가장 많이 쓴다. li에도 넣을수 있음. */
    }
```

#### 2. 테이블 스타일 ####
- 셀 숨김(감추기), 셀과 셀 사이 간격 조절. 셀 테두리 값 조절.

- table은 자신만의 고정값이 있어서 부모에게 상속받지 못한다.
- 페이지에서 중앙정렬하고 싶을 때는 width값 없이 마진값으로만 해야함.
- 셀과 셀 사이의 간격. 테이블 요소에만 적용되는 전용 속성.
	- `border-spacing: 50px;`
	- `border-spacing: 10px 50px;`      /*  X축 Y축 순으로 적용.  */
- 셀과 셀의 겹치는 셀 조정.
	- `border-spacing: 0;` 먼저 사이 간격 값 0으로 초기화.
	- `border-collapse: separate;` 기본값. 겹치는 셀 테두리 값 그대로 둠.
	- `border-collapse: collapse;` 겹치는 셀 테두리 값 제어

3. 폼 스타일 연습
﻿
0_1 테이블 스타일 연습1 - 숙제
0_2 테이블 스타일 연습2 - 숙제
0_3 테이블 스타일 연습3 - 숙제



## 230914 ##

#### 1. accent-color 속성 ####
- `form`에 들어가는 `input`값에는 기본적인 color 스타일 적용이 안된다.
- input type=checkbox, radio, range, progress 컨트롤 값 제어.
`accent-color: 색상;`

> ﻿﻿모든 브라우저에서 CSS code 사용 가능한지 확인하는 site https://caniuse.com/
> ﻿최신 기술의 경우 적용이 안되는 경우가 있어서 확인 필요.

#### 2. :before :after ####
- 해당 요소로 작성한 내용은 드래그가 되지 않는다.
- 구분선을 넣거나, 아이콘을 넣어 버튼으로 사용한다?
- 값으로 작성되는 "부분"은 텍스트 컨텐츠의 영역으로 코드값이 적용되지 않는다.
- `content` 생략 불가능. ""로 내용을 비워둘 순 있지만, 값은 절대 뺄 수없다. 무조건 작성.
	- `:before`, `::before`
		- 기준 요소 안의 컨텐츠 영역 앞쪽에 적용. 의사 요소
	- `:after`, `::after`
		- 기준 요소 안의 컨텐츠 영역 뒤쪽에 적용.

#### 3. em ####
- 알파벳 M을 기준으로 만들어진 단위
- 부모의 `font-size`를 기준으로 값 설정
- 브라우저 기본 폰트 사이즈: 16px
- 1em = 16px, 2em = 32px
- '나'를 감싸고 있는 부모를 기준으로 설정되는 상대적인 사이즈값이 계산된다.
- 브라우저마다 상대적인 값으로 표현된다.
- 다만, 값이 계속 상속되는 상대적인 값으로 제어가 까다롭다.

#### 4. rem ####
rem 단위값은 root, 즉 최상위 요소 html의 font-size를 기준으로 설정한다.
```css
    html {    /* <- rem 기준. 최상위 root 요소 */
      font-size: 24px;
    }
    body {    /* body는 html의 자식 요소. body 값에 font-size를 넣어도 rem에 적용되지 않는다. */
      font-size: 20px;
    }
```
