# 🚀 NASA Battery Data Exploratory Data Analysis
* EDA for NASA Battery Data (DateSet1-B0005, B0006, B0007, B0018)

## 📙 Data Set
* NASA Ames Prognostics Center에서 공개하고 있는 자료를 활용
* source: https://ti.arc.nasa.gov/tech/dash/groups/pcoe/prognostic-data-repository/

## 🔖 Reference
* https://notebook.community/adrienBizeray/battery_skunkworks/nasa-battery-data-analysis
* https://www.kaggle.com/rajeevsharma993/battery-health-nasa-dataset
* https://www.koreascience.or.kr/article/JAKO202007163270634.pdf
* https://github.com/natskiu/Nasa-Battery

## 📝 연구 목적
* 사이클 당 배터리의 상태를 알아 볼 수 있는 주요 지표에 대한 평균 변화량 탐구
* NASA라는 공신력 있는 기관의 데이터를 통해 어느정도 표준적인 배터리 지표에 대한 사용량 트렌드를 얻기 위함

## 🎞 연구 가설
* 사이클 횟수가 증가할 수록 배터리 셀의 주요 지표 및 성능은 저하 될 것이다.
  * 이번 연구에서는 배터리 셀의 성능을 측정하는 주요 지표로 전압(voltage), 전류(current), 온도(temp)를 선정
* 배터리의 충/방전 정도에 따라 최종 사이클 이후 배터리 상태 변화량은 상이할 것이다.

## 🔍 주요용어
* SOH: State Of Health. 배터리의 이상적인 상태와 현재 배터리의 상태를 비교하여 나타낸 성능지수
* cycle: 만충 상태(charge-cut-off)에서 각 배터리의 방전 완료 조건(discharge-cut-off)에 도달 할 때까지의 구간
* DOD: Discharge Of Depth. 방전 깊이(구간). ex) dod 80 == 10% ~ 90%, dod 90 == 5% ~ 95%

## 🔋 연구결과(Result)
* 사이클 횟수가 증가할수록 배터리의 방전량 및 SOH는 감소했다.
* 통상적으로 SOH가 초기 상태의 70~80%가 될 때 배터리를 사용 할 수 없는 것으로 간주한다. 아래 그래프를 보게 되면 배터리 마다 SOH 한계에 도달하는 지점이 모두 다른데(60 ~ 120회 사이) 이는 각 배터리 셀의 dod의 차이라고 생각 할 수 있다.
* 따라서 dod는 배터리의 수명에 상당한 영향을 미치는 것을 알 수 있다.
* 또한 주요 지표 중 전압의 경우 사이클이 횟수가 증가 할 수록 cut-off 조건에 빠르게 도달 하는 것을 알 수 있다. 온도의 경우 최고 온도로 증가하는 기울기가 점차 가팔라 지는 것을 확인할 수 있다.
* 이는 배터리 셀이 가질 수 있는 전하량이 줄어든다는 것을 알 수 있다.
* 하지만 배터리 셀 데이터가 2008년도 데이터라는 점, 모든 데이터가 일정한 전류로 충방전을 진행해 도출 된 결과라는 것이 현실에 적용하기에는 한계점이 있다.

## 📊 주요 이미지
### 1 사이클 당 방전량 및 SOH 변화 트렌드(discharge and soh per cycles trend)
* source: https://github.com/RyuMyunggi/NASA-battery-dataset-eda/blob/main/eda_for_battery_field.ipynb

#### 1-1. 사이클 당 방전량(discharge per cycles)
  <img width="677" alt="스크린샷 2021-11-27 오후 9 29 57" src="https://user-images.githubusercontent.com/77147527/143681360-4b50b81f-2ca9-4ce3-9102-a92fd08d3ade.png">

#### 1-2. 사이클 당 SOH(soh per cycles)
  <img width="677" alt="스크린샷 2021-11-27 오후 9 31 03" src="https://user-images.githubusercontent.com/77147527/143681403-837adf07-d6b5-4883-9ab0-9560cfb55610.png">

### 2. 사이클 당 배터리 주요 지표의 변화 트렌드(battery field per cycles trend)
* source: https://github.com/RyuMyunggi/NASA-battery-dataset-eda/blob/main/eda_for_battery_field.ipynb

#### 2-1. 사이클 당 배터리 전압 변화 트렌드(battery voltage per cycles)
  <img width="674" alt="스크린샷 2021-11-27 오후 9 34 19" src="https://user-images.githubusercontent.com/77147527/143681510-a3b73c15-1243-4d5d-8cf2-655dcfcd575d.png">

#### 2-2. 사이클 당 전류 변화 트렌드(battery current per cycles)
  <img width="677" alt="스크린샷 2021-11-27 오후 9 34 35" src="https://user-images.githubusercontent.com/77147527/143681519-d32c219e-a0a4-44b4-8a99-62c1407091ca.png">

#### 2-3. 사이클 당 배터리 온도 변화 트렌드(bettery temp per cycles)
  <img width="673" alt="스크린샷 2021-11-27 오후 9 34 49" src="https://user-images.githubusercontent.com/77147527/143681528-72a47aa1-c461-4a2e-a4a4-7257e5292eec.png">

