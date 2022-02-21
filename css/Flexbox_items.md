# Flexbox_items
### flex container의 바로 하위에 있는 child 요소들은 자동으로 flexible items가 된다.
<img src="https://user-images.githubusercontent.com/89233243/154872816-8596f1e2-9304-43c2-852c-0abc75b5a591.png">  
이렇게 container 안에 있는 1, 2, 3 div들이 바로 flex items!  

flex item에도 여러가지 속성이 존재한다.
- `order`
- `flex-grow`
- `flex-shrink`
- `flex-basis`
- `flex`
- `align-self`
---
## order
`order`는 flex items들의 순서를 설정하는 속성이다. 즉, 코드에 제일 처음 적힌 flex-item이라도 뒤늦게 나오도록 순서를 설정할 수 있다는 것. order의 value는 반드시 숫자여야 하고, defalut값은 0이다.
```
<div style="order : 3">1</div>
<div style="order : 2">2</div>
<div style="order : 4">3</div>
<div style="order : 1">4</div>
```
div에 이렇게 order값을 주게 되면~
<img src="https://user-images.githubusercontent.com/89233243/154909597-30aa9abb-5669-4a95-b497-d6ccd7b8aa3d.png">

order값에 따라 순서가 바뀌게 됨!

---
## flex-grow
`flex-grow` 속성은 다른 flex item에 비해서 얼마나 상대적으로 늘어날 수 있는지를 설정하는 속성이다.
```
<div style="flex-grow : 1">1</div>
<div style="flex-grow : 1">2</div>
<div style="flex-grow : 2">3</div>
<div style="flex-grow : 5">4</div>
```
<img src="https://user-images.githubusercontent.com/89233243/154910069-ba015829-2f70-4e01-aad3-efa495b67d01.png">

다른 요소의 크기에 대해 상대적인 비율로 늘어나는 것이 포인트.

---
## flex-shrink
`flex-shrink` 속성은 다른 flex item에 비해서 얼마나 상대적으로 줄어들 수 있는지를 설정하는 속성이다.  
value는 반드시 숫자여야 하고, default value는 1임!
```
<div>1</div>
<div>2</div>
<div style="flex-shrink: 0">3</div>
<div>4</div>
<div>5</div>
<div>6</div>
<div>7</div>
<div>8</div>
<div>9</div>
<div>10</div>
```
<img src="https://user-images.githubusercontent.com/89233243/154910796-ef540d38-f507-4f08-a9be-69e07433dca0.png">

---
## flex-basis
`flex-basis`는 flex item의 초기 길이를 설정한다.
```
<div>1</div>
<div>2</div>
<div style="flex-basis: 200px">3</div>
<div>4</div>
```
<img src="https://user-images.githubusercontent.com/89233243/154911473-c419b635-5b1f-42a7-b27b-6c57967f5e90.png">

---
## flex
`flex-grow`, `flex-shrink`, `flex-basis`를 동시에 설정할 수 있는 단축 속성.

예) not growable(0), not shrinkable(0), 초기 길이가 200인 flex item  
`<div style="flex: 0 0 200px">3</div>`

---
## align-self
`align-self`는 flex container 안에 있는 item을 선택해서 container의 세로축을 기준으로 정렬할 수 있다. flex container에 설정한 `align-items` 속성보다 우선 적용됨.  

예) flex-container의 높이를 200px로 설정하고 3번 div만 center로 정렬한 경우
```
<div>1</div>
<div>2</div>
<div style="align-self: center">3</div>
<div>4</div>
```
<img src="https://user-images.githubusercontent.com/89233243/154913196-26aefaa3-96f2-4316-b346-ae406f530eeb.png">  

예) 2번 div는 flex-start, 3번 div는 flex-end로 정렬한 경우
```
<div>1</div>
<div style="align-self: flex-start">2</div>
<div style="align-self: flex-end">3</div>
<div>4</div>
```
<img src="https://user-images.githubusercontent.com/89233243/154913423-1e405da2-c270-4207-a16d-49223e884062.png">