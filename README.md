# CafeInfoYou
📆 **프로젝트 진행기간 : 2023/01/26 ~ 2023/02/04**<br>
🔷**역할 : 프론트엔드, 팀 리더**

## 메인 화면
<p align="center">
  <br>
  <img width="1227" height="600" alt="메인 화면" src="https://user-images.githubusercontent.com/62414262/227697470-ec1307ec-58fe-433b-af5a-a15a1e342920.png">
  <br>
</p>

## 프로젝트 소개

<p align="justify">
카페 추천 사이트 <br>
지역을 입력하면 카페를 추천해주고 리뷰순, 대형, 디저트 카페를 특정하여 찾을 수 있다
</p>


![ezgif com-optimize](https://user-images.githubusercontent.com/62414262/227705718-6563aec0-2e18-47d5-b7d4-f311616fec91.gif)

<br>

## 기술 스택


| Frontend | Backend |
| :--------: | :--------: |
|  <img src="https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E" alt="JavaScript">  <img src="https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB" alt="React">  <img src="https://img.shields.io/badge/redux-%23593d88.svg?style=for-the-badge&logo=redux&logoColor=white" alt="Redux"> <img src="https://img.shields.io/badge/MUI-%230081CB.svg?style=for-the-badge&logo=mui&logoColor=white" alt="MUI"> <img src="https://img.shields.io/badge/NAVER Search API-green?style=for-the-badge&logo=Naver&logoColor=white"> <img src="https://img.shields.io/badge/KAKAO SEARCH API-F7DF1E?style=for-the-badge&logo=Kakao&logoColor=black"> |   <img src="https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white" alt="NodeJS">  <img src="https://img.shields.io/badge/express.js-%23404d59.svg?style=for-the-badge&logo=express&logoColor=%2361DAFB" alt="ExpressJS"> 
 

<br>

## 구현 기능

### 필터 UI
- Material UI의 CheckBox를 사용해 필터 UI 구현, 속성으로 색상 커스텀
- 필터 UI가 가로로 나타나게 하기 위해 기존에 MUI에서 제공하는 FormControlLabel을 FormGroup으로 묶지 않고 사용하는 방법으로 해결,
Form 관련 속성을 이해하고 사용할 수 있다

### 필터 기능
- 필터 체크 유무는 Redux를 통해 상태 관리하여 검색 컴포넌트에서 사용 가능하게 했다
- 네이버 검색 API를 프론트 쪽에서 요청하면 CORS 문제가 일어나기 때문에 백엔드 서버를 따로 구성해서 요청하는 방식으로 해결함
- 네이버 검색 API는 1초에 10번의 트래픽만 가능하게 허용해놨는데 너무 많은 요청을 보낼 시
에러가 나는 문제를 해결하기 위해 setTimeout을 통해 시간 간격을 두고 처리하도록 했다
- 필터검색 처리시에 중복 체크를 구현하기 위해 검색 방법을 두 가지로 분류함
  - 대형 / 디저트
    - 카카오 맵API로 검색 요청시에 검색어에 “대형 카페” or “디저트 카페” 추가해 검색
  - 리뷰순
    - 1차로 대형 또는 디저트가 들어간 검색어로 나온 카페 리스트를 
    네이버 검색 API를 이용해 리뷰순으로 정렬해준다
   
<br>

## 배운 점 & 아쉬운 점
- 프론트에서 API 요청을 보내면 CORS 문제가 있어 백엔드 서버가 필요한 것을 새로 알게 되었다
- 대형과 디저트를 검색어에 추가하는 방식으로 구현하니 카카오 맵 API에서 대형 디저트 카페는 검색이 불가해 대형과 디저트를 중복 체크 할 수 없는 점
- 스터디 카페, 모임 장소등도 카페로 분류되어 있어 추천 리스트에 나오는 점, 소분류도 카카오 map api에서 분류하도록 구현하면 정확도가 높아질것 같다

