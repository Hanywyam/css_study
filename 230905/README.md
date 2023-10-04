1. [1_cssBasic.html](https://hanywyam.github.io/css_study/230905/1_cssBasic.html)
2. [2_color.html](https://hanywyam.github.io/css_study/230905/2_color.html)
3. [3_css우선순위.html] (https://hanywyam.github.io/css_study/230905/3_css우선순위.html)

1. 아이디 선택자
- #box
- `#`를 이용한다. id값 선택자. (5)

2. 클래스 선택자
- `.box`
- `.`을 이용한다. class값 선택자. (3)

3. 타입(태그) 선택자
- `body`
- html에 쓰는 태그를 그대로 이용한다. (1)

4. 종속 선택자
- `h2.bg`
- 두 선택자를 붙여 사용한다.
- 앞의 선택자 안에서 뒤에 선택자까지 갖고 있는 선택자

5. 하위 선택자
- `h2 .bg`
- 두 선택자 사이를 띄어 사용한다.
- 기준 선택자 하위에 포함된 선택자

6. 복합 선택자
- `p.deco > strong`
- 두 선택자 사이를 띄어 사용한다.
- 종속 선택자 자식으로 타입(strong)선택자를 선택

7. 가상 선택자
- `a:hover`
- `:` 또는 `::`를 이용한다.
- 다양한 종류가 있으며 실제하는 요소(태그)와 함께 작성한다.

8. 속성 선택자
- `input[type="text"]`
- 요소[속성='값'] 으로 사용.
- 요소들 중에 속성의 값을 갖고 있는 선택자
- input 요소들 중에 type값이 text인 선택자

9. 일반 형제 선택자
- 선택자 ~ 선택자
- 선택자 사이에 `~`을 이용. 선택자 사이는 띄어쓴다.
- 기준 요소 뒤에 오는 "모든" 형제 관계 선택자에 적용한다.

10. 인접 형제 선택자
- 선택자 + 선택자
- 선택자 사이에 `+`를 이용. 선택자 사이는 띄어쓴다.
- 기준 요소 바로 뒤에 오는 형제 관계 선택자, 단 한개만 적용한다.

11. 수열 선택자, 의사 클래스
- `:first-child {}` 같은 부모를 둔 자식들 중 첫번째 자식
	- `.box p:first-child` :같은 부모를 둔 자식들 중 처음 나오는 요소가 p인 경우 적용
- `:last-child {}` 같은 부모를 둔 자식들 중 마지막 자식
	- `.box p:last-child` :가장 마지막에 나오는 자식이 p여야지만 적용
- `:nth-child(n) {}` 같은 부모를 둔 자식들 중 n번째 자식
	- `.box p:nth-child(6)` :자식들 중 6번째 위치에 p가 있으면 적용
- `:first-of-type {}` 같은 부모를 둔 자식들 중 '같은 타입'의 첫번째 자식
	- `.container div:first-of-type` :같은 부모를 둔 자식들 중 같은 타입의 첫번째 div에 적용
- `:last-of-type {}` 같은 부모를 둔 자식들 중 '같은 타입'의 마지막 자식
	- `.box div:last-of-type` :각 부모 안에서 같은 타입의 자식들 둥 마지막 div에 적용
- `:nth-of-type(n) {}` 같은 부모를 둔 자식들 중 '같은 타입'의 n번째 자식
	- `.box div:nth-of-type(2)` :자식들 중 같은 타입의 2번째 div
- `()`안에 적용하는 값
	- (even) 짝수
	- (odd) 홀수
	- (3n+1) 3개를 기준으로 첫번쨰
	- (3n) 3번째

수열 선택자 기출변형
```css
/* 3~11까지 선택 */
    .wrapper :nth-child(n+3):nth-child(-n+11) {
      border:3px solid #000;
    }
    /* 5~11까지 선택하되 2개 중 첫번째에 적용 */
    .wrapper :nth-child(2n+5):nth-child(-n+11) {
      color:teal;
    }
```