# Unreal4_Project

### 언리얼 엔진의 스킬 향상을 위해 진행한 프로젝트 입니다.
***
## 1. 큐브 이동 시뮬레이션
- Quiz_0
  - 지정된 위치에 큐브가 도착하면 자동으로 다음 위치로 이동

![Quiz_0](https://github.com/nunnunnana/Unreal4_Project/assets/99165741/0f74f14b-7bdb-4a96-a2ee-7a7cc4fe11d2)

- 블루프린트 코드

Quiz_0_Cube_Actor
>https://blueprintue.com/blueprint/sekq4uq0/

- <개발>
  - quiz_actor에 큐브가 이동할 Scene Component 4개를 배치
  - Scene Component Target_list에 넣고 초기 인덱스를 0으로 설정
  - 만약 Is_Move가 True이면 Cube에 Y축을 계속 더하고 Next_Target과 Cube의 위치가 동일해지면  인덱스에 +1을 해 다음 타겟을 바꿔준다.
  - 인덱스가 Target Lengh와 같아지면 인덱스를 0으로 설정
  - Qube를 인덱스 n번째의 Scene Component에 Attach하고 인덱스에 +1을 해서 Next_Target을 바꿔준다.
  - 만약 인덱스가 Target Lengh보다 커지면 인덱스를 0으로 설정



---
- Quiz_1
  - Quiz_0 에서 스페이스를 누르면 다음 타깃으로 넘어가는 기능 추가


- 블루프린트 코드

Quiz_1_Cube_Actor
>https://blueprintue.com/blueprint/k4xn_fx-/

Quiz_1_Pawn
>https://blueprintue.com/blueprint/afy4vdvh/

- <개발>
  - Pawn에서 스페이스를 누르면 Qube 액터에 Next 이벤트 호출
  - Cube 액터에 Next 이벤트가 호출되면 Is_Move 변수를 True로 변경
  - Tick 이벤트에서 Is_Move가 True면 Cube 이동 후 Is_Move 변수를 False로 변경



---
- Quiz_2
  - 위젯의 버튼을 클릭하면 해당 위치로 이동하는 기능 추가
  - 위젯에 슬라이드를 추가한 후 큐브의 이동 속도 조절 기능 추가
 
![Quiz_2](https://github.com/nunnunnana/Unreal4_Project/assets/99165741/21a4a925-75f1-4186-b916-d903ec15e32d)

- 블루프린트 코드

Quiz_2_Cube_Actor
>https://blueprintue.com/blueprint/keccg8dj/

Quiz_2_Widget
>https://blueprintue.com/blueprint/5spq9cwf/

Quiz_2_Pawn
>https://blueprintue.com/blueprint/1rgd172y/

- <개발>
  - Pawn에서 시작시 위젯 생성
  - 위젯에서 GetActorOfClass로 Cube 액터를 찾아서 변수 설정 후 위젯 입력에 따라서 Cube 액터 이벤트 호출
  - Target은 배열로 만들고 시작할 때 인덱스 설정
  - Cube 액터에서 위젯에 입력 받은 Index가 Target_Lengh보다 작고 Current_Target이 현재 Target index가 아닐때
  현재 Target을 Current Target 으로 바꾸고 Current_Target의 위치와 Cube의 위치를 빼고 정규화해서 방향 벡터를 구함
  - Cube 액터에 Tick 이벤트에서 현재 위치와 Current_Target의 거리가 5 이하이면 Direction 방향으로 Move_Speed만큼 이동

 


***
## 2. 충돌 후 색 변경 시뮬레이션
- Quiz_3
  - 카메라와 충돌하면 위젯의 색상과 큐브의 색상 변경 

![Quiz_3](https://github.com/nunnunnana/Unreal4_Project/assets/99165741/d25fac35-e7b6-4a1e-9e79-bd9f13c72da2)

- 블루프린트 코드

Quiz_1_Cube_Actor
>https://blueprintue.com/blueprint/k4xn_fx-/

Quiz_1_Pawn
>https://blueprintue.com/blueprint/afy4vdvh/

- <개발>
  - Pawn에 Sphere Collision을 생성한 후 Collision과 오버랩되면 타겟 액터의 색과 위젯의 색을 변경
  - Cube 액터에 Next 이벤트가 호출되면 Is_Move 변수를 True로 변경
  - Tick 이벤트에서 Is_Move가 True면 Cube 이동 후 Is_Move 변수를 False로 변경


---
- Quiz_3_1
  - 마우스를 클릭하면 십자선 위치에 지정된 색상을 가진 Sphere 생성
  - 같은 위치에 한 번 더 클릭하면 Sphere 크기 증가

![Quiz_3_1](https://github.com/nunnunnana/Unreal4_Project/assets/99165741/d516ce35-ebeb-4dc3-a439-dff3c12369af)

<img src="https://github.com/nunnunnana/Unreal4_Project/assets/99165741/950968a0-0c4e-4930-ba5c-ab36d7e7867b.png" width="1200" height="700"/>

키보드 숫자 1, 2, 3, 4로 색상 변경하고 마우스 클릭하면 LineTrace에 검출된 Actor에 선택한 색상의 Sphere를 생성

만약 같은 색상에 Sphere이면 크기 증가



---
- Quiz_4
  - 카메라에 있는 Sphere와 오버랩된 액터는 흰색으로 변경
  - Sphere와 가장 가까운 액터는 검은색으로 변경
  - End Overlap 된 액터는 원래 색으로 돌아옴

![Quiz_4](https://github.com/nunnunnana/Unreal4_Project/assets/99165741/391e2da1-5796-421a-a902-3f73eee37ec0)

<img src="https://github.com/nunnunnana/Unreal4_Project/assets/99165741/aa7179ef-bf1c-4c1f-82ae-6b3f4e0c35c0.png" width="1200" height="300"/>

Pawn에 Sphere Collision을 생성한 후 Collision과 오버랩된 액터를 전부 흰색으로 변경

오버랩된 액터중에 가장 가까운 액터를 찾아 검정색으로 변환
