# CSS코드 규칙

1. selector 작성(tag 지정) - property 작성(value값 작성)
2. CSS는 위에서부터 아래 순서로 적용되기 때문에 만약 한개의 태그에 다른 밸류값을 지정하면  
   가장 마지막에 지정한 value값이 적용된다.
3. block: div, header, section, main, footer, article 등등은 옆에 어떤것도 들어가지 않는다.
4. inline(in the same line)은 같은 줄 옆에 다른 요소가 추가될 수 있다
5. block 이 아닌 것들: span, a, image
6. 어떤 요소를 inline으로 설정할 경우 그 요소는 높이와 너비를 가질 수 없다.
7. \*{}는 전체를 의미한다.

## box의 요소

1. margin : box의 border(경계)의 바깥에 있는 공간이다.  
   (1) margin 값을 설정할 때 margin: 20px 15px과 같은 경우로 설정할 경우 첫번째 값인 20px은 수직 margin 값을, 두번째 값인 15px은 수평 margin값이다.  
   (2) margin 값을 설정할 때 margin: 20px 5px 12px 9px 과 같은 경우로 설정하면 위, 오른쪽, 아래, 왼쪽(시계방향)으로 값이 설정된다.  
   (3) collapsing margin: block과 block의 경계가 같을 때 두 block의 위 아래의 margin은 같이 취급된다.
   (4) margin은 inline에 적용될 때 좌,우에만 적용된다

2. padding: box의 경계로부터 '안쪽'에 있는 공간  
   (1) 값의 개수에 따라 적용되는 방향은 위의 margin과 동일하다  
   (2) 여러 div를 생성했을 때 id를 이용하여 div들을 구분할 수 있고, 각각 다른 속성을 적용시킬 수 있다.  
   (3) id에 속성을 적용 시킬 때는 #id {}로 표기  
   (4) padding은 span에도 적용된다.

3. Border는 box(block)의 경계이다.  
   (1) border는 보통 한 종류만 사용한다.  
   (2) border: 굵기, 스타일, 색상 순이다.  
   (3) border는 inline과 blcok 모두에 적용된다.

# class

class는 여러개의 속성들이 공용으로 사용할 수 있는 스타일 형식이고, 여러 개의 속성에 같은 스타일을 적용하고 싶을 때 사용한다.  
class는 .class로 사용한다  
class는 id와 달리 여러개를 지정해줄수 있다.

# inline-block

(1) block이 inline속성을 가지게 해주는 것
(2) 정해진 형식이 없기에 block사이에 공간이 생기며 깔끔하지 못하다.

# flexbox 사용 규칙

1. 자식 엘리먼트에는 어떤 것도 적지 않는다(부모 엘리먼트를 flex container로 만들어야 한다.
2. align-items : cross axis에서 작용(디폴트 값: 세로)
3. justify-content: main axis에서 작용(디폴트 값: 가로)  
   flex-container가 height를 가지지 않으면 align-items를 사용하더라도 바뀌지 않는다.
4. main axis, cross axis의 기본 값을 바꾸기 위해서는 flex-direction을 사용한다.
5. flex-direction 기본 값을 row이다.
6. 원하는 만큼 flex 컨테이너를 만들 수 있다.
7. flex wrap을 wrap로 설정하면 한 줄에 컨텐츠가 들어갈 수 있는 만큼만 보여주고 나머지는 다음줄로 넘김
8. no wrap일 경우 크기를 줄여서라도 한 줄로 표시

_height를 px로 해도 작동하지만, vh를 사용하면 화면 크기에 따라 height가 그 비율로 바뀌기에 기종마다 화면 비율이 달라도 그 비율에 맞게 설정할 수 있다._

# position

1. fixed  
   (1) position fixed를 사용하면 스크롤해도 항상 제자리에 머무른다.  
   (2) 처음 만들어진 자리에 고정되어있다. 하지만 top, left, right, bottom 중 하나만 수정해도 서로 다른 레이어에 위치하게되어 원래 위치가 무시된다. position fixed를 이용하면 가장 위에 위치하게 된다. (맨 앞)

2. relative  
   (1) 박스가 처음 위치한 곳을 기준으로 이동, top, botoom, left, right 속성을 주면 첫 위치를 기준으로 이동

3. absolute  
   가장 가까운 부모 엘리먼트에 position: relative를 추가하면 그 부모 기준으로 top, bottom, left, right 이동하고 아닐시엔 body를 기준으로 이동한다.

# pseudo selector

좀 더 세부적으로 엘리먼트를 선택해주는 것  
e.g div: last-child : div의 마지막 자식 요소 지정
span: nth-child(even), span:nth-child(2n), span: nth-child(2n+1)  
n allows you to do every other number

1. div span  
   : div 속 모든 span. span이 div의 direct children이 아니어도 작동
2. div > span  
   : span이 div의 direct children임을 의미한다. 이때는 direct children이 아니면 작동하지 않는다.
3. div + span  
   : div와 동등한 위치(형제)에 있는 span을 의미한다. 자식 요소도, 부모 요소도 아닌 것. 바로 다음 위치에 있는 형제만 적용된다.
4. div + ~  
   : 를 사용해 바로 뒤에 오는 형제 관계가 아닌 tag에도 스타일을 적용시킬 수 있다.
5. tag[attribute="value"]을 통해 스타일을 적용시킬 수 있다.
6. tag[attribute~="value"]으로 value를 포함하는 모든 tag에 스타일을 적용시킬 수 있다.

# States

active: 해당 요소를 마우스로 클릭했을 때 효과를 적용  
hover: 마우스가 해당 요소 위를 지나갈 때 효과를 적용  
focus: 키보드로 선택되었을 때 효과를 적용  
focus-within: 부모 요소에게 적용. 자신의 자식 요소 중 하나가 focused되었을 때 효과를 적용  
visited:: 방문한 사이트일 경우에 효과 적용

조건을 나열해 여러 상황 설정 가능  
ex) high-tag:hover low-tag:focus{

}
인 경우, 상위 요소위에 마우스 커서가 있고, 하위 요소가 focused 되었을 때 효과를 적용하게 된다.
