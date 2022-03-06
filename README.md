# 🎮 오버워치 캐릭터 선택

오버워치 캐릭터 선택 예제를 단계별로 제작하며<br>
공부했던 요소를 되짚어보는 복습용 자료입니다.

꼭 🔽 아래 내용을 복습하고 추가적인 실습 🔽 을 진행해봅시다.

<br>
<br>

## Emmet을 활용해 구조 반복하기

자동 완성 기능을 활용해 반복되는 구조를 빠르게 완성할 수 있습니다. <br>
에밋은 CSS 문법을 기반으로 이루어지는 단축키이므로 주요한 CSS 문법은 미리 익혀둡시다

예) `.클래스 선택자` `>자식 선택자`

```html
<!-- 반복되는 구조 -->
<div class="hero">
  <div class="image"></div>
</div>

<!-- 32번 반복하는 에밋 -->
.hero*32>.image
```

- `*32` : *는 `곱셈 연산자`로, 반복하는 기능을 수행합니다. 
- `>` : >은  `자식 선택자`로 뒤에 오는 요소가 자식 요소임을 의미합니다. 

<br>
<br>

## img 태그 class 속성 적용 실수

자주 발생하는 실수로, `class = "이름"`을 제대로 적용하였는지 확인해야 합니다.

CSS에서 선택자가 제대로 작동하지 않을 수 있기 때문입니다. <br>
만약 스타일이 제대로 작동되지 않는다면, 해당 실수를 의심해봅시다

<br>
<br>

## flex를 이용한 정렬

> flex를 이용하면, 하위 요소(item)들을 수평정렬할 수 있습니다 <br>

```css
.container .heros {
  display: flex;
  flex-wrap: wrap;
}
```

<br>

### 부모 요소에 적용

`display: flex` 필수! container(부모)를 flex 속성으로 변환시킵니다. 

`flex-wrap: wrap` flex를 사용하면 수평정렬되면서 기존 요소의 width가 줄어들게 되는데<br>
wrap을 사용하면 요소의 기본 width를 유지하는 대신 줄바꿈 처리됩니다.

`justify-content: center` item들을 주축(가로)으로 가운데 정렬합니다. 

`align-items: center` item들을 교차축(세로)로 가운데 정렬합니다. 

<br>

### 자식 요소에 적용

`order: 1` 배치 순서 - 숫자가 적을수록 먼저 배치됩니다.

`flex-grow: 비율` item의 총너비(content + 여백)의 증가비율을 설정합니다. 

`flex-shrink: 비율` item의 총너비(content + 여백)의 감소비율을 설정합니다.

`flex-basis: 1px` item의 너비를 설정합니다. 

<br>
<br>

## 전환 - transition

> transition 속성을 활용하면, 상태 전환에 필요한 다양한 옵션을 추가할 수 있습니다


```css
.transition{ property duration; }

/* 추가 */
.transition{ property duration timing-function delay; }

/* 예시 */
.transition {
  transform .1s;
}
```

`속성` : 전환 옵션을 적용할 대상(속성)을 정합니다

`지속 시간` : 해당 속성으로 몇 초에 걸쳐 전환될 것인지를 결정합니다. 

<br>
<br>

## 변환 - transform

> transform 속성을 활용하면, `위치` `크기` `회전` `기울임` `원근감` 등을 기존의 상태에서 변화시킬 수 있습니다. 

`transform: 변환함수1 변환함수2;` 형태로 사용하며, 다양한 변환 속성 또는 변환함수를 띄어쓰기( )를 이용해 이어서 사용할 수 있습니다

<br>

### 변환 함수

- `translate(x, y)` 기존의 위치에서 x축, y축으로 얼마만큼 이동할 것인지를 정할 수 있습니다. (위치 관련 함수)

  `translateX(x)` `translateY(y)` 로 상세한 위치 이동을 표시해야 합니다. 

- `scale(배수)` 기존의 크기에서 몇 배 커질 것인가를 결정합니다. (크기 관련 함수)

- `rotate(15deg)` _각도deg_ 만큼 회전합니다.

- `skewX(x)` `skewY(y)` 요소를 기울입니다.

<br>

### 3차원 변환 속성
- `perspective: 거리px` 거리가 작을 수록 원근감이 크게 느껴집니다

- `backface-visiblity: hidden` 뒤집었을 때(rotate) 뒤집어진 면(backface)이 보이지 않게 합니다. 

<br>
<br>

## max, min - width, height

> max-width를 활용하면 반응형 특성을 유지하되, 요소의 왜곡현상을 방지할 수 있습니다. 