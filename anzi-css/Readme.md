```
- H1 은 Document 상에 1개만 있는 것이 좋다.
- 자식 속성은 부모 속성을 바로 상속을 받는다.
- Document는 기본적으로 갖고 있는 margin 을 갖고 있다.
  따라서 필요시 기본적으로 갖고 있는 margin 을 제거한다.
  body {
    margin: 0px;
  }
```
# 2. style tag에서 요소를 선택하는 방법
```
- tag : tag name
- class name : . + class name
- id : # + tag id
```

# 3. CSS 설명
```
- font-family : 여러개의 폰트를 사용할수 있고, 기능은 첫번째가 먼저 제공이되고,
                없으면 그 다음, 그 다음.. 이렇게 적용된다.
- color : font-color 인데... color 로 사용된다.
- font-size : font의 크인데, body에 해당 속성을 선언하면,
              font-size가 선어되어 있지 않은 자식 태그는 영향을 받는다.
- line-height : px 단위지만 px가 없이 사용되면 font-size 의 영향을 받게된다.
                ex) font-size: 30px;
                    line-height: 1;
                이렇게 지정하면 font-size의 정적 line-height가 적용된다.
                즉, line-height: 1; 이면 font-size와 동일한 크기로 적용된다.
- font-weight : css 에서는 medium 이 없기때문에 500 이 해당 역할을 한다.
- opacity 에서 %를 입력할때는 20 / 100 = 0.2 를 입력한다.
- nth-child(N) : 가상 선택자
                 부모안에 모든 요소 중 N번째 요소
  A:nth-of-type(N) : 부모안에 A라는 요소 중 N번째 요소
  :first-child : 부모안에 모든 요소 중 첫번째 요소
  :last-child : 부모안에 모든 요소 중 마지막 요소
  A:first-of-type : 부모안에 A라는 요소 중 첫번째 요소
  A:last-of-type : 부모안에 A라는 요소 중 마지막 요소
- border 는 기본적으로 (outer)로써 밖으로 커진다, inner 안쪽으로 커지게 하고 싶다면, box-sizing 의 border-box라는 속성을 이용한다.
- div 기본 속성은 width는 100% 이다.
- position 속성
  static (default) : left, right, top, bottom 의 속성이 무시된다.
  relative : 상대적으로 left, top을 변경.
  absolute :
    * 좌표가 부모가 가로막지만 않는다면, 그냥 문서상에 그 좌표를 사용한다. 즉, left, top 값을 갖는다.
    * 스크롤이 생성이 되면 겹치는 부분이 따라 올라간다.
  fixed : 스크롤이 생기면 겹치는 부분이 문서상의 그대로 좌표를 유지한다.
  * position에 static 이 아닌 relative, absolute, fixed 속성을 사용하게 되면, left, right, top, bottom 을 사용할 수있게 된다.
- overflow : 스크롤을 감춘다.
  overflow: hidden (x, y) 모두 감춤
  overflow-x
  overflow-y
- div 는 기본적으로 block 속성을 갖고 있다.
- span 는 기본적으로 inline 속성을 갖고 있다.
  inline 속성은 left, right 는 적용되지만 top, bottom은 적용되지 않는다.
- div, span의 기본적인 속성은 display 를 통해서 변경이 가능하다.
- display
  display: block;
  display: inline;
- transition
  1s : 1초, 1ms
  transition은 홀로 동작할 수 없고, hover, active를 통해서만 가능하다.
- List 표현 태그
  ol : Ordered List
  ul : Unordered List
- Image 활용 방법
  img 태그 사용
  style 을 이용하여 background-img
- background-size: cover 는 이미지를 영역으로 채우지만 이미지가 잘린다, 해서 background-position: center로 이동시켜 한쪽으로 이미지가 잘리는 것을 막고, 골고루 잘리도록 한다.

- white-space 속성
  normal (default) : nowrap
- 축약 (padding, margin)
  padding = padding-top, padding-bottom, padding-left, padding-right
  padding = 상하, 좌우 / 상좌, 상우, 하우, 하좌
- flex
  * 특성은 item의 width에 맞게 조정한다.
  * flex의 width에 맞게 조정되는 것을 막는 속성은 flex-shrink: 0; 이 있다.
  display: flex; 가로 정렬하는데 매우 유용하다.
   > jsstify-conetnt : 가로
   > jsstify-conetnt: flex-start, flex-end, center
   > jsstify-conetnt: space-around, space-between, space-evenly
   > align-items : 세로
   > align-items : center, flex-start, flex-end
  flex-direction : 세로 정렬하는데 매우 유용하다.
   > column, column-reverse, row, row-reverse
- pseudo element
  :before, :after
  주로 마우스 오버시, 클릭시 에 많이 사용
  ex) .item::after {
        content: "";
        width: 100%;
        height: 100%;
        position: absolute;
        left: 0;
        top: 0;
      }

      .item:hover:after {
        background-color: rgba(0, 0, 0, 0.12);
      }

      .item:active:active {
        background-color: rgba(0, 0, 0, 0.2);
      }
    물론, pseudo 속성 없이 hover, active를 사용할수도 있지만, 테크닉으로 알아두면 됨
- 가급적이면 용도에 맞는 태그를 사용하자.
  <header>  등
- height 를 %로 해주면 부모의 값을 상속받아 사용하는데, 부모에 height 가 없으면 0 된다.

- inline-block의 단점은 font에 영향을 받는다.
- 따라서 부모 속성에서 font-size:0 으로 해주면 해결이 되지만.. 찝찝함.
- grid
  display: grid;
  grid-template-columns: 컬럼 + width
  grid-template-columns: 숫자 + fr 비율별로 사용 가능
  fr : fraction 은 자기가 벌어질수 있는 범위 만큼 벌어진다.
- 형제 요소에 선택하기
  ~ 표시를 하면 형제 요소에 적용이 가능하다.
  ex) .search form:hover ~ .test
- class name을 여러개 줄수 있는데 공백을 추가하여 css 를 여러개 선언하여 사용
  <div class="item mouse-effect">
```

# 4. CSS 애니메이션
```
- tansition의 단점
  사용되는 제약이 있다. 따라서 이 제약을 넘어서기 위해서는 animation 속성을 이용한다.
- animation은 길이를 갖는다.
- animation은 from ~ to를 갖는데, duration 동안 from ~ to를 갖고, 이게 없어지면 끝난다.
  즉, from : background-color: yellow;
      to : background-color: green;
      animation-duration: 1s;
      background-color: red;
  하면 1초동안 yellow -> green 으로 변하고, background-color가 지정이 되어 있지 않으므로 사라진다.
  단. animation-fill-mode 를 이용하면 to의 내용에서 머문다.
- transform
- Z 축을 표현하고 싶다면 부모요소에 perspective를 반드시 선언해야 한다.
- translate는 CPU 와 GPU를 사용하는데, GPU를 사용안한때도 있지만, translate3d를 사용하면 무조건 GPU를 사용하기때문에 조금더 부드러운 효과를 볼수 있다.

- animation 축약을 겹쳐서 사용하면 제일 마지막의 값으로 덮어 쓰여지지만, 각각을 하면 해당 하는 값만 덮어쓰여진다.

```