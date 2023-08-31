# Unreal4_Project

언리얼 엔진의 스킬 향상을 위해 진행한 프로젝트 입니다.
***
## 1. 큐브 이동 시뮬레이션
![Quiz_0](https://github.com/nunnunnana/Unreal4_Project/assets/99165741/0f74f14b-7bdb-4a96-a2ee-7a7cc4fe11d2)
- Quiz_0

<img src="https://github.com/nunnunnana/Unreal4_Project/assets/99165741/d3731af0-cc1b-4380-a9b5-b2c5ba7c0865.png" width="400" height="300"/>


<img src="https://github.com/nunnunnana/Unreal4_Project/assets/99165741/9ae5693e-d651-4431-ba84-da5486b07bab.png" width="400" height="200"/>


quiz_actor에 큐브가 이동할 Scene Component 4개를 배치

<img src="https://github.com/nunnunnana/Unreal4_Project/assets/99165741/0c2a3728-968d-4b31-8acc-307d1d5cbc3c.png" width="400" height="200"/>

Scene Component Target_list에 넣고 초기 인덱스를 0으로 설정

<img src="https://github.com/nunnunnana/Unreal4_Project/assets/99165741/a47915d1-e140-41ec-9bb7-c6958337fa4d.png" width="400" height="200"/>

만약 Is_Move가 True이면 Cube에 Y축을 계속 더하고 Next_Target과 Cube의 위치가 동일해지면  인덱스에 +1을 해 다음 타겟을 바꿔준다.

인덱스가 Target Lengh와 같아지면 인덱스를 0으로 설정

<img src="https://github.com/nunnunnana/Unreal4_Project/assets/99165741/9506d2ab-a9bf-4063-ac00-722b54b76a43.png" width="400" height="200"/>

Qube를 인덱스 n번째의 Scene Component에 Attach하고 인덱스에 +1을 해서 Next_Target을 바꿔준다.

만약 인덱스가 Target Lengh보다 커지면 인덱스를 0으로 설정

---
- Quiz_1
  - Quiz_0 에서 스페이스를 누르면 다음 타깃으로 넘어가는 기능 추가
  - BasePawn 액터 생성 
<img src="https://github.com/nunnunnana/Unreal4_Project/assets/99165741/ceda7b47-6bdf-4638-8769-e5666cd9e8a6.png" width="800" height="400"/>

---
- Quiz_2
  -  
![Quiz_2](https://github.com/nunnunnana/Unreal4_Project/assets/99165741/21a4a925-75f1-4186-b916-d903ec15e32d)
