# MovieTheaters_py
영화예매표 키오스크 구현

*** 영화 필수 정보 ***
-영화 이름
-영화 상영관
-영화 상영 기간
-영화 상영 시간
-영화 관람 가능 연령
-영화 가격
-예매한 인원의 정보 <- 영화관 선호도 구하기에 필요한 정보
  1. age0~80 2. gender(male, female)
-totalmoney : 총 벌어들은 금액 수 <- 결제 할 때마다 추가
-countpeople : 총 영화를 본 인원 수 


*******while문으로 시작

timestamp를 받아서 거기에 따라 영화 종류 선정


1. 영화 종류 선정 ( 종류별로 예매비용 다르게할것)
프리미엄 : 일반 상영관보다 50% 더 부가세
여기서 관리자계정 접속가능여부
1-1) 예외처리 : 현재 시간보다 일찍 시작한 영화는 예매 불가 
1-2) 날짜까지 입력받아서 기간별로 볼 수 있는 영화


while(True)로 시작
2. 좌석고르기(x1,x2 입력 받고 (x1,x2) 위치 좌석은 x표로 예매됨을 표시
  1. 1) 조조 2) 심야 3) 일반 -> 조조 20% / 심야 10%
  2. 1) 단체신가요 ?
	yes : 몇장 구매하실래요?
		좌석 고르고 제대로 고르면 False로 변경
		인원 수 만큼 countpeople에 더하기
	3-1 . 예외처리 ) 이미 예매된 좌석은 예매된 좌석이라 안내문구 출력하고 다시 while문 처음으로 돌아감.
	3-2 . 예외처리 ) 없는좌석 고르면 없는좌석이라 표시해두고 다시 while문 처음으로 돌아감.
			단체 전용 신상 정보 : "단체 몇명" 만 표시
			단체 결제	
	no : 좌석 고르고 제대로 고르면 False로 변경
		countpeople+1
	3-1 . 예외처리 ) 이미 예매된 좌석은 예매된 좌석이라 안내문구 출력하고 다시 while문 처음으로 돌아감.
	3-2 . 예외처리 ) 없는좌석 고르면 없는좌석이라 표시해두고 다시 while문 처음으로 돌아감.
		신상 정보 입력 후 결제

while(True)로 시작
 +2 ) 신상정보는 생년월일 + 뒷자리 맨첫번째 입력받고, 현재 연도에서 차감 후, 나이 계산. ( 맨첫번째 1,3 : 남자 2,4 여자)
제대로 입력 받으면 False로 바꿔서 반복문 안돌게 조정
나이, 성별에 따라 age, gender에 더하기
	예외처리 ) 관람 가능 연령대 범위를 벗어난 경우, 
	input = 신상정보
	while(잘못되면):
	input=신상정보


 +2 예외처리 ) 119 이상의 나이가 계산되면 
	생년월일이 잘못 입력되었습니다.
		신상정보 입력으로 다시 되돌아감
     예외처리 ) 존재하는 날짜인지 판별
이스터에그 : 오늘 생일이면  Happy birthday ! 출력

4. 돈 입력받기. 카드밖에안됨 ( 카드잔액은 충분하다고 가정 )
예매비는 ~~~원 입니다
totalmoney에 예매비 더하기

5. 영화표 출력
출력해야할 요소 (2차원 배열로)
[오늘날짜, 영화 종류, 좌석, 시간]
단체예매일 경우
[오늘날짜, 영화 종류, 예매한 모든 좌석, 시간]

6. 시간남으면 팝콘까지하자(카드밖에안됨)

관리자계정

0) 로그인해야됨
	로그인 ID 변수 입력받은 후, 사용자가 입력한 ID와 같으면 접속
	password도 똑같이.
1) 1. 오늘 번 돈의 액수 : totalmoney 출력
   2. 무슨 영화를 몇명이 예매했는지 : countpeople 
   3. 영화관 선호도 ( 전체 관람객 수를 영화 예매 수로 나눈 값 )
   3_1 성별 간의 선호도. 전체를 특정성별로 나눈 값
   4. 구입한 사람의 신상정보 : 10대이하 부터 10살 단위로, 80대 이상으로 끊어치기
	age10, age20 이런느낌으로 변수 받고 출력
   
