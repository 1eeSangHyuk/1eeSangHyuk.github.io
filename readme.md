
--CSS 세세속성
border-[top|right|bottom|left]-[width|color|style]

CSS 작성 시에는 통합속성 > 세부속성 > 세세속성 순으로 작성

```CSS
선택자 {
    border: 1px solid blue;
    border-left: 2px dashed red;
    border-style: dotted;
    border-left-color: green;
}
```

### CSS 박스 크기 계산 방법
box-sizing : content-box | padding-box | border-box
설정하지 않은 경우 content-box이며, 그 밖에 border-box를 사용함
content-box 크기 : 크기+패딩+보더+마진
border-box 크기 : 크기+마진

```CSS
선택자 {
    width:200px; height:300px; padding:10px; border:20px solid black; margin:80px; box-sizing:border-box
}
/* 위 박스는 적용크기 기준이 content-box(기본값)
    실제폭 : 200+10*2+20*2+80 = 
    실제높이 : 300+10*2+20*2+80 = 
border-box 기준
    실제폭 : 200+80 = 
    실제높이 : 300+80 = 
    */
```

## 배치 속성
### 위치 속성
position - static | relative | absolute | fixed
static : 정적. 기본값으로 별도의 position 속성을 지정하지 않아도 static으로 됨.
relative : 상대적인 위치 설정시에 필요, 위치 좌표를 부모 기준으로 정할 경우 활용.
absolute : 절대적인 위치 설정시 필요, x좌표 위치와 y좌표 위치를 지정해야 함.
            위치값은 auto 또는 px단위 와 %단위 등으로 지정.
            left : 왼쪽 기준으로 부터의 위치
            right : 오른쪽 기준으로 부터의 위치
            top : 위쪽 기준으로 부터의 위치
            bottom : 아래쪽 기준으로 부터의 위치
        ※ x좌표 위치는 left나 right 중에서 하나만 기술하고, y좌표 위치는 top이나 bottom중에서 하나만 기술해야한다.
fixed : 화면에 고정된 위치를 설정할 때 필요하며, 스크롤시 fixed된 요소는 스크롤 되지 않고, 화면에 고정되어 있음.
        absolute와 마찬가지로 left/right, top/bottom의 위치를 설정해야 함.
    - static이나 relative일 경우는 margin으로 떨어진 거리를 지정하고, absolute이나 fixed일 경우는 left/right, top/bottom으로 위치를 설정

### 레이어 속성
z-index : position이 absolute이거나 fixed일 경우 여러 콘텐츠 박스를 겹칠 경우 어떤 콘텐츠 박스를 앞에 배치할지 층(레이어)를 설정하는 것으로 숫자 정수만으로 지정하며, 숫자 값이 큰 것이 위(앞)에 배치됨.

### 흐름 속성
float : left | right | both | none
    - position이 static이거나 relative일 경우 활용하는 배치 흐름 속성

### 흐름 해제 속성
clear : left | right | both | none
    - float 설정된 박스의 흐름을 해제시 사용하며, float이 left로 설정되면, clear도 left로 하면 흐름이 해제되며, left나 right 모두 해제시에는 both를 사용하여 흐름을 해제함.

