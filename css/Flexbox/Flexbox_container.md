# Flexbox_container

### Flexbox model을 사용하려면 먼저 flex container가 있어야 한다!  

<img src="https://user-images.githubusercontent.com/89233243/154872816-8596f1e2-9304-43c2-852c-0abc75b5a591.png">  

```
<head>
  <style>
    .flex-container {
      display : flex;
      background-color: aquamarine;
    }
    .flex-container div{
      background-color: aliceblue;
      margin : 10px;
      padding : 20px;
      font-size : 30px;
    }
  </style>
</head>
<body>
  <div class="flex-container">
    <div>1</div>
    <div>2</div>
    <div>3</div>
  </div>
</body>
```

❗ Flexible Layout은 display property를 유연하게 세팅하기 위해 반드시 부모 요소를 가지고 있다(=flex container).  
flex container의 바로 하위에 있는 child 요소들은 자동으로 flexible items가 된다.

>display property : 요소의 display 속성  

위의 사진을 예시로 보자면 바깥의 연두색 부분이 flex container, 안의 div가 flexible items.

즉, 다시 말하자면 자유롭게 배치하고 싶은 요소들을 감싸고 있는 container에 `display : flex;` 속성을 부여해야 한다는 뜻!!!  


# Flex Container

flex container에는 여러가지 속성이 존재한다.
- `flex-direction`
- `flex-wrap`
- `flex-flow`
- `justify-content`
- `align-items`
- `align-content`
---
## flex-direction
flex-direction은 flex itmes 요소를 flex-container 안에서 어떤 방향으로 쌓을 것인지 결정하는 속성. 총 4가지 종류가 있다.
- `flex-direction : column;`   
 요소를 flex-container에 수직으로 쌓음(위에서 아래)
- `flex-direction : column-reverse;`  
 요소를 flex-container에 수직으로 쌓지만 아래에서 위 방향
<img src="https://user-images.githubusercontent.com/89233243/154874478-3ecafebf-c6ef-4642-bd8b-56e83755588d.png">
- `flex-direction : row;`  
flex items를 container 안에 수평으로 쌓음 (좌에서 우)
- `flex-direction : row-reverse;`  
 요소를 수평으로 쌓지만 우측에서 좌측 방향
<img src="https://user-images.githubusercontent.com/89233243/154874509-71d622d7-2ff6-48fc-ab90-38f7f44e0bd1.png">

---
## flex-wrap
flex-wrap은 flex items들을 감쌀 것인지, 아닌지 결정하는 속성. 총 3가지 종류가 있다.
- `flex-wrap : nowrap;` (default)  
 요소가 flex-container를 벗어나도 감싸지 않음. 즉, 요소가 container를 벗어나버림.
<img src="https://user-images.githubusercontent.com/89233243/154875080-22c0bb6a-b40d-4c47-aeed-0786e44253a3.png">
- `flex-wrap : wrap;`  
필요한 경우 flex items들을 줄바꿈하도록 지정. 요소가 container를 벗어나려고 하면 자동으로 줄바꿈 되면서 모든 items들을 container 안에 존재하도록 함.
<img src="https://user-images.githubusercontent.com/89233243/154875148-21167758-5434-4b24-ae29-9e7ae3635c39.png">
- `flex-wrap : wrap-reverse;`  
wrap과 똑같은 속성이지만 요소의 순서가 역정렬됨.
<img src="https://user-images.githubusercontent.com/89233243/154875184-bfc65422-979b-4e3a-8ded-7ce7c288f71e.png">

---
## flex-flow
flex-direction과 flex-wrap 속성을 동시에 사용하기 위한 단축 속성.  
사용 예시 : `flex-flow : row wrap;`

---
## justify-content
flex items들을 정렬할 때 사용되는 속성. (가로축 기준)
- `justify-content : flex-start;` (default)  
container가 시작하는 지점을 기준으로 flex items들을 정렬.
<img src="https://user-images.githubusercontent.com/89233243/154876920-be95f25a-46e7-4bce-a3fb-7c6381ca7bdc.png">
- `justify-content : flex-end;`  
container가 끝나는 지점을 기준으로 flex items들을 정렬.
<img src="https://user-images.githubusercontent.com/89233243/154876969-44d5a24a-7843-44e3-88f2-171d51e4d97b.png">
- `justify-content : center;`  
container의 가운데에 flex items들을 정렬.
<img src="https://user-images.githubusercontent.com/89233243/154877005-a1bc4fc7-3e30-458c-82f4-7ff434e9a146.png">
- `justify-content : space-between;`
flex item과 flex item의 사이에 공백 존재.
<img src="https://user-images.githubusercontent.com/89233243/154877051-b7c2695e-782c-4613-88a0-549dab545c8f.png">
- `justify-content : space-around;`
flex item의 이전, 사이, 이후에 공백 존재.
<img src="https://user-images.githubusercontent.com/89233243/154877081-aa35235f-7da3-404a-befb-574c1827d223.png">
space-around는 1번 div 좌측에 있는 공간이 1번 div 우측에도 있고, 2번 div 앞에도 있다고 보면 됨.

---
## align-items
flex items들을 정렬할 때 사용되는 속성. (세로축 기준)
- `align-items : flex-start;`  
container의 위를 기준으로 flex items들을 정렬.
<img src="https://user-images.githubusercontent.com/89233243/154904276-7f5fab7e-7103-4ac1-bb11-5df5c7cd152c.png">
- `align-items : flex-end;`
container의 바닥을 기준으로 flex items들을 정렬.
<img src="https://user-images.githubusercontent.com/89233243/154904380-8796fdd4-ba02-4dc7-928b-7553b0a80cd6.png">
- `align-items : center;`
container의 중간을 기준으로 flex items들을 정렬.
<img src="https://user-images.githubusercontent.com/89233243/154904521-29f95435-80d8-456f-a477-8d3c26aa0b25.png">
- `align-items : stretch;` (default)
container 크기에 맞춰서 flex items들도 늘어남!
<img src="https://user-images.githubusercontent.com/89233243/154904629-3544c035-d95f-405e-9a2a-a380201064df.png">
- `align-items : baseline;`  
text의 baseline을 기준으로 flex items들이 정렬됨. (각 요소의 폰트 사이즈를 다르게 설정해보면 한눈에 알 수 있음)
<img src="https://user-images.githubusercontent.com/89233243/154905032-e8c32b60-164d-4545-bfe0-38f952bdbc5d.png">

❗ `justify-content : center;`와 `align-items : center;`를 이용하면 flex items들을 container의 정중앙으로 쉽게 보내버릴 수 있음~~ (perfect centering)
<img src="https://user-images.githubusercontent.com/89233243/154905398-ca2549a4-eb04-44a0-a56a-eab78bc72364.png">

---
## align-content
align-items가 flex-items를 정렬한다면 align-content는 flex-items들이 속한 라인을 중심으로 정렬한다.
- `align-content : space-between;`
flex-items들이 속한 라인 사이에 동일한 여백을 비워두고 정렬한다.
<img src="https://user-images.githubusercontent.com/89233243/154906357-f87b8d48-32d3-4d6e-806f-2d4d278469a3.png">
- `align-content : space-around;`
flex-items들이 속한 라인의 위, 아래 모두에 동일한 여백을 비워두고 정렬한다.
<img src="https://user-images.githubusercontent.com/89233243/154906568-39bcb1c8-b6a0-45b7-b953-6faa0e2e68b2.png">
- `align-content : stretch;` (default)
line 사이에 여백이 존재하지 않도록 flex-items들을 쫙쫙 늘려줌.
<img src="https://user-images.githubusercontent.com/89233243/154906785-bb430737-c296-4f79-a115-62a1fa22e48c.png">
- `align-content : center;`  
container의 중간을 기준으로 flex line을 정렬
<img src="https://user-images.githubusercontent.com/89233243/154906926-dffc8072-688f-43a4-8da5-9546e289cc32.png">
- `align-content : flex-start;`  
container의 위(천장)를 기준으로 flex line을 정렬
<img src="https://user-images.githubusercontent.com/89233243/154907127-24b3bd40-af89-44a0-bfba-ff1c0c2f4b53.png">
- `align-content : flex-end;`  
container의 아래(바닥)를 기준으로 flex line을 정렬
<img src="https://user-images.githubusercontent.com/89233243/154907159-2781ef8c-c3c9-43da-b5f4-013af2434202.png">


출처 : https://www.w3schools.com/css/css3_flexbox_container.asp