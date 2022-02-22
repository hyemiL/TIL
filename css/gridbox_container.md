# Gridbox_container
<img src="https://user-images.githubusercontent.com/89233243/155151129-90e3be4b-855d-48f9-a9fa-0de872ca01e2.png">
위의 레이아웃은 6개의 컬럼과 3줄로 이루어진 grid rayout!  

```
<style>
.item1 { grid-area: header; }
.item2 { grid-area: menu; }
.item3 { grid-area: main; }
.item4 { grid-area: right; }
.item5 { grid-area: footer; }

.grid-container {
  display: grid;
  grid-template-areas:
    'header header header header header header'
    'menu main main main right right'
    'menu footer footer footer footer footer';
  gap: 10px;
  background-color: #2196F3;
  padding: 10px;
}

.grid-container > div {
  background-color: rgba(255, 255, 255, 0.8);
  text-align: center;
  padding: 20px 0;
  font-size: 30px;
}
</style>
<body>
<div class="grid-container">
  <div class="item1">Header</div>
  <div class="item2">Menu</div>
  <div class="item3">Main</div>  
  <div class="item4">Right</div>
  <div class="item5">Footer</div>
</div>
</body>

```
---
### Grid Layout
CSS의 Grid 레이아웃은 행과 열을 베이스로 하는 격자 레이아웃 시스템.  
웹페이지의 디자인을 float나 positioning 없이 쉽게 할 수 있도록 도와준다.  
grid layout은 부모 요소와 하나 또는 그 이상의 자식 요소들로 구성되어 있다. 또한 반드시 부모 요소의 display 속성이 grid 혹은 inline-grid로 지정되어야 한다.  

- `display : grid;`  
block 속성의 grid container를 만들 때 사용.
<img src="https://user-images.githubusercontent.com/89233243/155152816-6a80f345-4651-42ee-96b7-1a1c9d8ba82d.png">

- `display : inline-grid;`  
inline 속성의 grid container를 만들 때 사용.
<img src="https://user-images.githubusercontent.com/89233243/155153056-bf8d7001-242b-4a99-ae24-2133379cf7aa.png">

grid container의 직계 하위에 있는 자식 요소는 자동으로 grid items가 된다.

---

## Grid Columns
grid items의 세로줄을 columns라고 칭한다.
<img src="https://user-images.githubusercontent.com/89233243/155153432-4f21dca6-d5e5-4d47-befa-10788ff086bd.png">

---

## Grid Rows
grid items의 가로줄을 rows라고 칭한다.
<img src="https://user-images.githubusercontent.com/89233243/155153615-16d97cfc-b271-483a-84a6-24723f74c328.png">

---

## Grid Gaps
각각의 컬럼과 로우 사이의 공간을 'gaps'라고 칭한다.
<img src="https://user-images.githubusercontent.com/89233243/155153917-a5402e50-8178-424f-a448-bad14673691a.png">

이 gap의 사이즈는 `column-gap`, `row-gap`, `gap` 세 가지 속성 중 하나를 통해 설정할 수 있다.

- `column-gap : 50px;`
<img src="https://user-images.githubusercontent.com/89233243/155154280-4099c34f-4f21-40ba-a478-426793c48dc9.png">
컬럼과 컬럼 사이의 갭이 50px 생겨남.

- `row-gap : 50px;`
<img src="https://user-images.githubusercontent.com/89233243/155154435-cfec791e-b7f6-4d19-a7eb-c1221cb1ae69.png">
로우와 로우 사이의 갭이 50px 생겨남.

- `gap : 50px 100px;`
<img src="https://user-images.githubusercontent.com/89233243/155154739-e5751bbc-e6dc-4b51-b7eb-6f4ff5e154bb.png">
로우와 컬럼을 축약해서 바로 쓸 수도 있음. (`row-gap`, `column-gap` 순서)

- `gap : 50px;`
<img src="https://user-images.githubusercontent.com/89233243/155154982-7afd28b6-44e0-4b3b-96ec-4c1850e793fe.png">
로우와 컬럼에 동시에 같은 값 적용도 가능.

---
## Grid Lines
컬럼과 컬럼 사이에 있는 라인들을 column lines,  
로우와 로우 사이에 있는 라인들을 row lines라고 부른다.
<img src="https://user-images.githubusercontent.com/89233243/155155325-0a07fb31-4fbe-4fac-93c4-1c2932a64df9.png">

Grid container에 grid items를 배치할 때 line number를 참조할 수 있음.

예를 들어, 그리드 아이템을 컬럼 라인 1부터 배치하고, 컬럼 라인 3에서 끝낼 때의 경우
```
.grid-container {
  display: grid;
  grid-template-columns: auto auto auto;
  gap: 10px;
  background-color: #2196F3;
  padding: 10px;
}
.item1 {
  grid-column-start: 1;
  grid-column-end: 3;
}
```
처럼 설정할 수 있음.


<img src="https://user-images.githubusercontent.com/89233243/155156608-58564de5-aa57-4276-95ee-053a3eafcce8.png">  
이렇게 1번 item이 1번 컬럼 라인부터 3번 컬럼 라인에 걸쳐 생성됨.

반대로 row line 1부터 3까지 배치할 경우
```
.item1 {
  grid-row-start: 1;
  grid-row-end: 3;
}
```
<img src="https://user-images.githubusercontent.com/89233243/155157246-0dba4685-93f5-4839-8f0f-b84d2b153f72.png">
처럼 레이아웃을 짤 수 있음.

출처 : https://www.w3schools.com/css/css_grid.asp