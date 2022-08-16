# 티켓사조
![바탕화면](Images/184810334-a816ed71-3eb4-4f15-bc84-ca7898fe1de0.png)

팀명: 티켓 사조  
<img src= "Images/184799023-c1061898-d659-42ed-8f74-a01ffe5fd1b9.png" width=350px, height=400px, align='right'>

팀장: 김민식

팀원: 안원영, 장효준, 정세연

## 프로젝트 정보

### 1. 프로젝트 주제
Spring boot를 활용한 클래식 영화관 티켓팅 서비스 및 NCP AI 플랫폼을 활용한 고객편의기능 구현

### 2. 프로젝트 목적

1. 클라우드 환경 사용
2. 자리 예매 기능 구현
3. AI Platform(CLOVA OCR)을 활용한 영수증사지을 이용한 적립금 기능 구현
4. AI Platform(CLOVA CFR)을 활용한 닮은 꼴 배우 찾기 이벤트 페이지 구현
5. 네이버, 구글, 페이스북 등 다양한 로그인 API를 활용한 로그인 기능 구현

### 3. 프로젝트 기능 구현
1. 영화 좌석 선택 및 예약
2. AI를 활용한 영수증 인식 후 포인트 적립, 적립 내역 조회 기능
3. 로그인 API(OAuth) 사용해 로그인 및 회원가입 기능
4. 결제 API 기능 
5. 영화 필터 검색 기능
6. 성별, 나이 정보를 바탕으로 통계표 기능
7. 리뷰, 평점 기능
8. CLOVA Face Recognition(CFR)을 이용한 닮은 꼴 배루 찾지 이벤트 페이지 구현

### 4. 프로젝트 역할 분담 
| 이름 | 역할 |
|---------|--------|
| 김민식 |영화 상세 페이지(통계차트), 영화리스트 페이지, CHATBOT, Contact Us 페이지(구글맵, 문의사항 메일로 전송), CLOVA Face Recognition (CFR), Admin 페이지 (고객/영화/스케줄/쿠폰/포인트 관리, 예매내역 조회, 로그인, 회원가입)|
| 안원영 |로그인 API(**OAuth**), NCP AI CLOVA OCR* (쿠폰 or 적립), 리뷰 순위 페이지, 포인트 적립, 메인 페이지(서치 기능), Admin 페이지(메인 페이지에 차트), &nbsp; 쿠폰|
| 장효준 | 예매(좌석선택, 극장선택, 시간선택) , 결제 API, Admin 페이지(스케줄 관리)|
| 정세연 |회원가입, 일반 로그인, MyPage(나의 예매내역, 내 포인트 내역 조회, 내 쿠폰 내역 조회, 회원탈퇴, 회원정보변경, 비밀번호 변경)|

### 5. 프로젝트 개발 환경 및 수행 도구
![화면 캡처 2022-08-01 114948](Images/182062696-fb7c4078-a73f-46af-97bc-cb2e0dcefc03.png)

언어 | 웹 | 개발도구 | DataBase | 협업도구 | FrameWork
---- | ---- | ---- | ---- | ---- | ---- |
JAVA, SQL | HTML5,&nbsp; CSS3, JS, jQuery, Ajax, Bootstrap | Eclipse, NCP | Mysql | Zoom, Google Docs, Github, ERD Cloud,Padlet, Notion | Spring Boot, Mybatis

### 6. 데이터베이스 설계
ERD: [티켓사조](https://www.erdcloud.com/d/Gb6vzq6LdsJjFpduL)

![image](Images/184797326-65c2fdbf-d780-4300-92f2-82b4862eb04b.png)

### 7. UI 설계
![ui](Images/184812812-b5a0ff9e-75f3-4f1f-9a9f-d7f16a952bf0.png)

## 프로젝트 결과

### TicketSaJo(티켓사조) 관리자 사이트

### 1. 로그인 페이지

<p align="center"><img src="Images/adminlogin.gif"/></p>



- 관리자사이트 로그인 기능 구현
- DB에 관리자사이트 회원관련 데이터와 비교하여 로그인 가능
- 관리자사이트는 회원 정보가 담긴 Session값이 없으면 모든페이지 로그인 페이지로 Return
- 잘못된 로그인 정보 입력시 간단 확인 메시지 출력으로 유효성 검사

### 2. 회원가입 페이지

![aregister1-1](Images/aregister1-1.png)
- 관리자 페이지의 보안 강화를 위해 간단한 인증 절차 진행
- master에게 부여받은 코드를 전달받아 입력 해야 회원가입 가능
- 코드를 잘못 입력하면 '코드가 잘못되었습니다'라는 메시지 출력
![aregister1-2](Images/aregister1-2.png)
- 마스터인 회원정보에서만 코드보기 버튼 표시
- 마스터가 코드 확인후 전달 (코드는 주기적으로 변함)
- 코드 확인후 정확한 코드와 아이디 비밀번호 입력 시 회원가입 성공

### 3 .어드민 메인 페이지

![admin_main1](Images/admin_main1.png)

![admin_main2](Images/admin_main2.png)

- 관리자의 매출과 상관이 있는 오늘 사이트 방문자수와 오늘, 내일 개봉할 영화 수, 누적회원 수와 탈퇴 회원 수, 당일날 예매된 영화 수를 직관적으로 볼 수 있도록  수치화를 이용하여 간단하게 정보를 표시했다. 

- 먼저 chart 를 이용해 해당 페이지에 방문하는 사람 수를 통해 "7일간 방문한 사람수" 와 "누적 평균 방문 수" 를 볼 수 있는 그래프를 만들었습니다. 

- 당일 페이지 방문자 수는 cookie를 통해 집계하였고 데이터 베이스의 공간을 보다 효율적으로 사용할 수 있도록 mysql의 이벤트 스케쥴러를 이용하여 데이터를 관리하였습니다. 데이터는 하루마다 "당일 방문자 수" 를  "요일별 방문자 수 테이블 "로 저장하고 저장한 "당일 방문자 수 "는 초기화 될 수 있도록 하였습니다. 

### 4. 고객 관리 페이지

#### 4-1 고객 등록 페이지

<p align="center"><img src="Images/custadd.gif"/></p>

<p align="center"><img src="Images/custaddsuccess.gif"/></p>

- 고객 정보 입력, 등록
- 날짜는 숫자로 입력 ('-' 자동 생성, 날짜 범위 벗어나면 버튼 클릭시 alert로 다시 확인 메시지 출력)
- 아이디, 비밀번호 유효성 검사 (Ajax 데이터 보내서 데이터 유효성 검사), 간단하게 alert로 출력
- 성공시 성공페이지 출력

#### 4-2 고객 목록 페이지

<p align="center"><img src="Images/clist.gif"/></p>

- 고객 정보 나열 및 각 고객별 쿠폰목록 정보, 수정 삭제 기능 구현, 페이징 기능 구현
- 검색 기능 구현 (고객 관련 아무 정보나 서치 가능)
- 쿠폰함 클릭시 해당 아이디의 쿠폰 정보 나열, 삭제 가능
- 수정 삭제 버튼 클릭시 수정 및 삭제 가능

### 5. 영화 관리 페이지

#### 5-1 영화 등록

![addmoive](Images/addmoive.png)

![addmoive3-166053313953751](Images/addmoive3-166053313953751.png)

- 영화 정보 입력, 등록
- :zap: 영화 포스터 이미지 파일의 데이터는 관리자, 사용자 페이지에 모두 전송
- 즉시 사용자 페이지에도 적용 
- 날짜는 숫자로 입력 ('-' 자동 생성, 날짜 범위 벗어나면 버튼 클릭시 alert로 다시 확인 메시지 출력)
- 성공시 성공페이지 출력

#### 5-2 영화 목록 페이지

<p align="center"><img src="Images/amlist.gif"/></p>

- 영화 정보 나열 및 각 영화별 리뷰 정보, 수정 삭제 기능 구현, 페이징 기능 구현
- 검색 기능 구현 (영화 관련 아무 정보나 서치 가능)
- 리뷰 관리 클릭시 해당 영화의 리뷰 목록 확인, 삭제 가능
- 수정 삭제 버튼 클릭시 수정 및 삭제 가능

### 6. 장르 관리 페이지

#### 6-1 장르 추가

![addgenre](Images/addgenre.png)

- 장르 정보 입력, 등록
- 상위 장르는 데이터베이스의 상위 장르들을 나열 그 중 SELECT만 가능하도록 구현

#### 6-2 장르 목록![genrelist](Images/genrelist.png)

![genrelist1](Images/genrelist1.png)

- 장르 정보 나열 및 각 장르별 수정 삭제 기능 구현
- 수정 삭제 버튼 클릭시 수정 및 삭제 가능

### 7. 쿠폰 관리 페이지

#### 7-1 쿠폰 추가

![addcoupon](Images/addcoupon.png)

- 쿠폰 정보 입력, 등록
- 날짜는 숫자로 입력 ('-' 자동 생성, 날짜 범위 벗어나면 버튼 클릭시 alert로 다시 확인 메시지 출력)

#### 7-2 쿠폰 목록

![couponlist](Images/couponlist.png)

![couponlist1](Images/couponlist1.png)

- 쿠폰 정보 나열 및 각 쿠폰별 수정 삭제 기능 구현
- 수정 삭제 버튼 클릭시 수정 및 삭제 가능

### 8. 스케줄 관리 페이지

#### 8-1 스케줄 표시

<p align="center"><img src="Images/list_calendar.gif"/></p>

- 오픈소스 라이브러리 Fullcalendar를 사용하여 스케줄을 구현하였습니다.

- 캘린더의 해당날짜에 등록된 스케줄이 표시됩니다.

- 데이터는 Ajax로 데이터베이스에서 받아오며 데이터 형식은 JSON으로 정제하였습니다.

- 스케줄을 클릭하면 스케줄을 수정할 수 있는 상세페이지로 이동합니다.

- 리스트 버튼을 누르면 스케줄을 리스트 형식으로 열람할 수 있습니다.

#### 8-2 스케줄 등록

<p align="center"><img src="Images/sadd.gif"/></p>

- 캘린더에서 날짜를 선택했을 경우 상영날짜에 선택한 날짜가 자동입력됩니다.

- 리스트에서 스케줄 추가 버튼을 클릭 했을 경우 날짜는 빈칸입니다.

- 상영관과 상영영화, 상영날짜를 입하여 다음 버튼을 클릭하면 상세 스케줄 등록 페이지로 이동합니다.

#### 8-3 상세 스케줄 등록

![dsadds](Images/dsadds.gif)

- 상세 스케줄 등록은 회차와 시작시간을 입력합니다.

- 시작시간은 숫자 입력시 자동으로 포맷이 마춰지며 24:00를 넘을 수 없습니다.

- 시작시간을 입력하면 자동으로 끝나는 시간이 입력됩니다.

- 끝나는 시간은 영화 테이블의 runningtime 정보를 불러와 10자리 수에서 올림 처리하여 시작시간에서 더합니다.

- 예를 들어 시작시간이 09:30이고 영화의 runningtime이 112분이라면 120분으로 올림되어 끝나는 시간은 11:30입니다.

- 회차와 시작시간을 입력하고 ADD를 눌러야 등록상태가 됩니다.  추가 버튼을 눌렀을 때 등록상태가 된 정보만 등록됩니다.

- 등록상태가 된 회차는 다른 칸의 회차 선택창에서 나타나지 않습니다.

#### 8-4 스케줄 상세 및 수정

![sdelete2](Images/sdelete2.gif)

- 스케줄 캘린더에서 스케줄을 클릭하거나 스케줄 리스트에서 상세보기를 클릭했을 때 스케줄 상세를 볼 수 있습니다.


- 스케줄 상세에서 해당 스케줄의 영화 타이틀, 상영관, 상영날짜, 회차, 상영시간과 좌석 현황을 열람할 수 있습니다.

- 스케줄 수정과 삭제를 할 수 있습니다.

### 9. 예매내역 조회 페이지

![reservation](Images/reservation.png)

![reservation1](Images/reservation1.png)

- 예매된 전체 내역을 조회하는 페이지를 구현
- 예매 상세 버튼을 클릭하면 해당 예약건의 상세 정보가 출력(좌석, 상영 회차 등)


## 개인 Project 구상 * 기획 * 개발

[22.06.29 Fianl-Project 브레인 스토밍 ](%E1%84%8F%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A2%E1%84%89%E1%85%B5%E1%86%A8%20%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%92%E1%85%AA%E1%84%80%E1%85%AA%E1%86%AB%20%E1%84%90%E1%85%B5%E1%84%8F%E1%85%A6%E1%86%BA%E1%84%90%E1%85%B5%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20(%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%92%E1%85%A2%E1%86%BC%E1%84%8C%E1%85%AE%E1%86%BC)%205312ea98a9ef47848084dbadc15f798a/22%2006%2029%20Fianl-Project%20%E1%84%87%E1%85%B3%E1%84%85%E1%85%A6%E1%84%8B%E1%85%B5%E1%86%AB%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A9%E1%84%86%E1%85%B5%E1%86%BC%20b98452bc0af74afd835fa6bf8d34e5e2.md)

[22.06.30 Fianl-Project 브레인 스토밍 ](%E1%84%8F%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A2%E1%84%89%E1%85%B5%E1%86%A8%20%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%92%E1%85%AA%E1%84%80%E1%85%AA%E1%86%AB%20%E1%84%90%E1%85%B5%E1%84%8F%E1%85%A6%E1%86%BA%E1%84%90%E1%85%B5%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20(%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%92%E1%85%A2%E1%86%BC%E1%84%8C%E1%85%AE%E1%86%BC)%205312ea98a9ef47848084dbadc15f798a/22%2006%2030%20Fianl-Project%20%E1%84%87%E1%85%B3%E1%84%85%E1%85%A6%E1%84%8B%E1%85%B5%E1%86%AB%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A9%E1%84%86%E1%85%B5%E1%86%BC%20abc6e7955a5544a988e48eec545c32cf.md)

[22.07.01 Fianl-Project 브레인 스토밍 ](%E1%84%8F%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A2%E1%84%89%E1%85%B5%E1%86%A8%20%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%92%E1%85%AA%E1%84%80%E1%85%AA%E1%86%AB%20%E1%84%90%E1%85%B5%E1%84%8F%E1%85%A6%E1%86%BA%E1%84%90%E1%85%B5%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20(%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%92%E1%85%A2%E1%86%BC%E1%84%8C%E1%85%AE%E1%86%BC)%205312ea98a9ef47848084dbadc15f798a/22%2007%2001%20Fianl-Project%20%E1%84%87%E1%85%B3%E1%84%85%E1%85%A6%E1%84%8B%E1%85%B5%E1%86%AB%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A9%E1%84%86%E1%85%B5%E1%86%BC%207a72bf721ef54315927b774b57edf40d.md)

[22.07.02 Fianl-Project 브레인 스토밍 ](%E1%84%8F%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A2%E1%84%89%E1%85%B5%E1%86%A8%20%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%92%E1%85%AA%E1%84%80%E1%85%AA%E1%86%AB%20%E1%84%90%E1%85%B5%E1%84%8F%E1%85%A6%E1%86%BA%E1%84%90%E1%85%B5%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20(%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%92%E1%85%A2%E1%86%BC%E1%84%8C%E1%85%AE%E1%86%BC)%205312ea98a9ef47848084dbadc15f798a/22%2007%2002%20Fianl-Project%20%E1%84%87%E1%85%B3%E1%84%85%E1%85%A6%E1%84%8B%E1%85%B5%E1%86%AB%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A9%E1%84%86%E1%85%B5%E1%86%BC%200c36e71b783747a1a8bdf2560d8f8e99.md)

[22.07.05 Fianl-Project 기획 ](%E1%84%8F%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A2%E1%84%89%E1%85%B5%E1%86%A8%20%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%92%E1%85%AA%E1%84%80%E1%85%AA%E1%86%AB%20%E1%84%90%E1%85%B5%E1%84%8F%E1%85%A6%E1%86%BA%E1%84%90%E1%85%B5%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20(%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%92%E1%85%A2%E1%86%BC%E1%84%8C%E1%85%AE%E1%86%BC)%205312ea98a9ef47848084dbadc15f798a/22%2007%2005%20Fianl-Project%20%E1%84%80%E1%85%B5%E1%84%92%E1%85%AC%E1%86%A8%2016258b58906b4fbab9e6dd1b5769fd5c.md)

[22.07.06 Fianl-Project 기획 ](%E1%84%8F%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A2%E1%84%89%E1%85%B5%E1%86%A8%20%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%92%E1%85%AA%E1%84%80%E1%85%AA%E1%86%AB%20%E1%84%90%E1%85%B5%E1%84%8F%E1%85%A6%E1%86%BA%E1%84%90%E1%85%B5%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20(%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%92%E1%85%A2%E1%86%BC%E1%84%8C%E1%85%AE%E1%86%BC)%205312ea98a9ef47848084dbadc15f798a/22%2007%2006%20Fianl-Project%20%E1%84%80%E1%85%B5%E1%84%92%E1%85%AC%E1%86%A8%20f5e617d0db9444f39747c6d54013155e.md)

[22.07.07 Fianl-Project 기획 ](%E1%84%8F%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A2%E1%84%89%E1%85%B5%E1%86%A8%20%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%92%E1%85%AA%E1%84%80%E1%85%AA%E1%86%AB%20%E1%84%90%E1%85%B5%E1%84%8F%E1%85%A6%E1%86%BA%E1%84%90%E1%85%B5%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20(%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%92%E1%85%A2%E1%86%BC%E1%84%8C%E1%85%AE%E1%86%BC)%205312ea98a9ef47848084dbadc15f798a/22%2007%2007%20Fianl-Project%20%E1%84%80%E1%85%B5%E1%84%92%E1%85%AC%E1%86%A8%202a657f69b6604e1795677485595659ad.md)

[22.07.11 Fianl-Project 개발](%E1%84%8F%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A2%E1%84%89%E1%85%B5%E1%86%A8%20%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%92%E1%85%AA%E1%84%80%E1%85%AA%E1%86%AB%20%E1%84%90%E1%85%B5%E1%84%8F%E1%85%A6%E1%86%BA%E1%84%90%E1%85%B5%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20(%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%92%E1%85%A2%E1%86%BC%E1%84%8C%E1%85%AE%E1%86%BC)%205312ea98a9ef47848084dbadc15f798a/22%2007%2011%20Fianl-Project%20%E1%84%80%E1%85%A2%E1%84%87%E1%85%A1%E1%86%AF%209a45a15ac2ad4e65a93faf32d55df557.md)

[22.07.12 Fianl-Project 개발](%E1%84%8F%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A2%E1%84%89%E1%85%B5%E1%86%A8%20%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%92%E1%85%AA%E1%84%80%E1%85%AA%E1%86%AB%20%E1%84%90%E1%85%B5%E1%84%8F%E1%85%A6%E1%86%BA%E1%84%90%E1%85%B5%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20(%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%92%E1%85%A2%E1%86%BC%E1%84%8C%E1%85%AE%E1%86%BC)%205312ea98a9ef47848084dbadc15f798a/22%2007%2012%20Fianl-Project%20%E1%84%80%E1%85%A2%E1%84%87%E1%85%A1%E1%86%AF%209f5837db2d22435094580f64be59ba83.md)

[22.07.13 Fianl-Project 개발](%E1%84%8F%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A2%E1%84%89%E1%85%B5%E1%86%A8%20%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%92%E1%85%AA%E1%84%80%E1%85%AA%E1%86%AB%20%E1%84%90%E1%85%B5%E1%84%8F%E1%85%A6%E1%86%BA%E1%84%90%E1%85%B5%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20(%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%92%E1%85%A2%E1%86%BC%E1%84%8C%E1%85%AE%E1%86%BC)%205312ea98a9ef47848084dbadc15f798a/22%2007%2013%20Fianl-Project%20%E1%84%80%E1%85%A2%E1%84%87%E1%85%A1%E1%86%AF%20973adbae0f6f481b9c72ce5abb97ad20.md)

[22.07.14~26 Fianl-Project 개인 개발](%E1%84%8F%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A2%E1%84%89%E1%85%B5%E1%86%A8%20%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%92%E1%85%AA%E1%84%80%E1%85%AA%E1%86%AB%20%E1%84%90%E1%85%B5%E1%84%8F%E1%85%A6%E1%86%BA%E1%84%90%E1%85%B5%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20(%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%92%E1%85%A2%E1%86%BC%E1%84%8C%E1%85%AE%E1%86%BC)%205312ea98a9ef47848084dbadc15f798a/22%2007%2014~26%20Fianl-Project%20%E1%84%80%E1%85%A2%E1%84%8B%E1%85%B5%E1%86%AB%20%E1%84%80%E1%85%A2%E1%84%87%E1%85%A1%E1%86%AF%20fc97fd6b8bee4f74a0c5e9bcb8f00a47.md)

[22.07.27 Fianl-Project 중간 발표](%E1%84%8F%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A2%E1%84%89%E1%85%B5%E1%86%A8%20%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%92%E1%85%AA%E1%84%80%E1%85%AA%E1%86%AB%20%E1%84%90%E1%85%B5%E1%84%8F%E1%85%A6%E1%86%BA%E1%84%90%E1%85%B5%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20(%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%92%E1%85%A2%E1%86%BC%E1%84%8C%E1%85%AE%E1%86%BC)%205312ea98a9ef47848084dbadc15f798a/22%2007%2027%20Fianl-Project%20%E1%84%8C%E1%85%AE%E1%86%BC%E1%84%80%E1%85%A1%E1%86%AB%20%E1%84%87%E1%85%A1%E1%86%AF%E1%84%91%E1%85%AD%204474808c18b2492b8dd8c7447b3ec536.md)

[22.07.27~ Fianl-Project 개인 개발](%E1%84%8F%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A2%E1%84%89%E1%85%B5%E1%86%A8%20%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%92%E1%85%AA%E1%84%80%E1%85%AA%E1%86%AB%20%E1%84%90%E1%85%B5%E1%84%8F%E1%85%A6%E1%86%BA%E1%84%90%E1%85%B5%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20(%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%92%E1%85%A2%E1%86%BC%E1%84%8C%E1%85%AE%E1%86%BC)%205312ea98a9ef47848084dbadc15f798a/22%2007%2027~%20Fianl-Project%20%E1%84%80%E1%85%A2%E1%84%8B%E1%85%B5%E1%86%AB%20%E1%84%80%E1%85%A2%E1%84%87%E1%85%A1%E1%86%AF%2068d360fd2857453a86db09389ee39914.md)

## 프로젝트 관련 자료

- 제안 요청서 (RFP)
  
    [RFP1.0.hwp](%E1%84%8F%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A2%E1%84%89%E1%85%B5%E1%86%A8%20%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%92%E1%85%AA%E1%84%80%E1%85%AA%E1%86%AB%20%E1%84%90%E1%85%B5%E1%84%8F%E1%85%A6%E1%86%BA%E1%84%90%E1%85%B5%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20(%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%92%E1%85%A2%E1%86%BC%E1%84%8C%E1%85%AE%E1%86%BC)%205312ea98a9ef47848084dbadc15f798a/RFP1.0.hwp)
    
- 요구사항 정의서

[요구사항.xlsx](https://docs.google.com/spreadsheets/d/1zxziyQmYhLGoes65Drm3nR-ITSRQ8t1O/edit?usp=drive_web&ouid=105051611234612731581&rtpof=true)

- ERD

[티켓사줘](https://www.erdcloud.com/d/Gb6vzq6LdsJjFpduL)

- UI설계

[https://docs.google.com/presentation/d/176k--5z45jnKjw7wpXgmnHfMEYfp_1rr/edit#slide=id.p1](https://docs.google.com/presentation/d/176k--5z45jnKjw7wpXgmnHfMEYfp_1rr/edit#slide=id.p1)

[Ticket_SaJo DML.sql](%E1%84%8F%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A2%E1%84%89%E1%85%B5%E1%86%A8%20%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%92%E1%85%AA%E1%84%80%E1%85%AA%E1%86%AB%20%E1%84%90%E1%85%B5%E1%84%8F%E1%85%A6%E1%86%BA%E1%84%90%E1%85%B5%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20(%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%92%E1%85%A2%E1%86%BC%E1%84%8C%E1%85%AE%E1%86%BC)%205312ea98a9ef47848084dbadc15f798a/Ticket_SaJo_DML.sql)

[Ticket_SaJo DDL.sql](%E1%84%8F%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A2%E1%84%89%E1%85%B5%E1%86%A8%20%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%92%E1%85%AA%E1%84%80%E1%85%AA%E1%86%AB%20%E1%84%90%E1%85%B5%E1%84%8F%E1%85%A6%E1%86%BA%E1%84%90%E1%85%B5%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20(%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%92%E1%85%A2%E1%86%BC%E1%84%8C%E1%85%AE%E1%86%BC)%205312ea98a9ef47848084dbadc15f798a/Ticket_SaJo_DDL.sql)
