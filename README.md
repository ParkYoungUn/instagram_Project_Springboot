# SpringBoot를 활용한 instagram clone project
------------------------------------------------------------

### instagram clone Demo
* [인스타그램 클론코딩 데모 사이트 이동하기](http://insta.yi.or.kr)
	* 사용자 이름: test
	* 비밀번호: test
* [인스타그램 클론코딩 데모 영상보기](https://youtu.be/ptLInn3zmcI)

### project 개발 기간 및 인원
* 개발기간
	* 2020/09/26 ~ 2020/11/5
* 인원
	* 3명

## DB & 사용기술
![DB](https://user-images.githubusercontent.com/50615738/103171278-572c2980-488e-11eb-9ebc-9cdf7bf6930b.png)
![skill](https://user-images.githubusercontent.com/50615738/103171459-ca826b00-488f-11eb-8a8a-3eb1b44fac8c.png)

## 회원가입/로그인
![image10](https://user-images.githubusercontent.com/50615738/103172132-a8d7b280-4894-11eb-9989-8a81023dba10.png)
#### 회원가입 / 로그인
	* Spring Security를 활용한 User Authentication 관리
	* 회원가입(email, 사용자이름 중복체크)
	* 로그인(비밀번호 및 사용자 이름 체크)
	* 로그아웃
	* 비밀번호 암호화 및 세션 유지 관리
	* Client Session을 통한 로그인 유저 정보 활용

## 로그인 처리 / 비밀번호 변경
![image52](https://user-images.githubusercontent.com/50615738/103172212-3f0bd880-4895-11eb-9532-38be81ba729c.png)
![image51](https://user-images.githubusercontent.com/50615738/103172218-51861200-4895-11eb-907f-c77ab17f5f52.png)
#### 로그인 처리 / 비밀번호 변경
* 로그인 처리
	* Back-End 내에서 유저정보 비교 후 유효하지 않으면 Exception 처리 되도록 구현됨
* 비밀번호 변경
	* BCryptPasswordEncoder를 통해 기존 비밀번호와 입력받은 비밀번호 비교
	* 새 비밀번호는 2번 입력하도록 하여 일치 여부 확인
	* 기존 비밀번호 입력 실패 시 CustomException 예외 발생
	* 새 비밀번호 일치 여부에 따라 유효하지 않으면 불일치 문구 출력
	* 새 비밀번호 불일치 시 알림창 생성

## Feed(메인 페이지)
![image54](https://user-images.githubusercontent.com/50615738/103172330-0f110500-4896-11eb-844e-e5153d8dda04.png)
![image56](https://user-images.githubusercontent.com/50615738/103172338-1a643080-4896-11eb-95fe-d46cc32f0be3.png)
#### Feed
* 단독게시물 화면내에서 게시물 삭제 가능
* 게시글 작성자만 게시물을 삭제할 수 있도록 권한을 부여함
* 회원님을 위한 추천 기능(5명의 유저를 랜덤으로 추천)

## Explore
![image58](https://user-images.githubusercontent.com/50615738/103172418-93638800-4896-11eb-8d03-11d8140b3386.png)
#### [팔로우] 하지 않은 사람들의 전체 게시물
* 해당 게시물 마우스 오버 시 좋아요, 댓글 수를 보여줌.
* 특정 게시물 클릭 시 해당 Board 페이지로 이동

## 프로필/사진업로드
![image60](https://user-images.githubusercontent.com/50615738/103172447-e0475e80-4896-11eb-8bc7-e2cad70d372a.png)
![image62](https://user-images.githubusercontent.com/50615738/103172451-eccbb700-4896-11eb-8726-a37cc14bb6f8.png)
#### 프로필/사진업로드
* 사진등록 버튼 클릭 시 사진업로드 되도록 구현.
* 프로필편집 버튼 클릭 시 유저 정보 수정가능(사용자이름, 비밀번호 제외) 
* 해당 게시물 마우스 오버 시 좋아요,  댓글 수를 보여줌, 클릭 시 해당 게시글 페이지로 이동

## 검색
![image64](https://user-images.githubusercontent.com/50615738/103172508-68c5ff00-4897-11eb-9be8-b2314afebd22.png)
#### 검색
* 검색창에 키워드 입력 또는 해시태그 클릭 시 키워드에 맞는 게시글을 보여줌

## 팔로워 리스트 / 팔로우 리스트
![image65](https://user-images.githubusercontent.com/50615738/103172578-cc502c80-4897-11eb-9cd4-f11df2993336.png)
![image66](https://user-images.githubusercontent.com/50615738/103172580-ce19f000-4897-11eb-981e-abf0613a80fa.png)
#### 팔로워 / 팔로우
* 팔로워(follower) : 내 소식을 듣는 사람
* 팔로잉(following) : 내가 소식을 듣는 사람
	* [팔로워 리스트] [팔로우 리스트] 클릭 시 모달창을 통해 보여줌 
	(해당유저의 기준에 맞게 [팔로우] [팔로우취소] 버튼을 보여줌)
	특정유저를 클릭해서 해당 유저 페이지로 이동 가능

## 실시간 알림
![image68](https://user-images.githubusercontent.com/50615738/103172677-6ca65100-4898-11eb-9bc7-1c262c10ed7a.png)
#### BootStrap-Notify
* pring Websocket(sockJs, stomp)를 활용해 팔로우, 좋아요, 댓글 알림을 실시간으로 보여줍니다.
* 알림 클릭시 해당 회원 프로필 또는 해당 게시물로 이동

## 알림
![image71](https://user-images.githubusercontent.com/50615738/103172712-b42cdd00-4898-11eb-90c5-1809a4b1597e.png)
* 최근 내역 5개를 보여줌

## Direct-Message(채팅)
![image72](https://user-images.githubusercontent.com/50615738/103172739-de7e9a80-4898-11eb-840c-0540752510fe.png)
#### Direct-Message
* Left Section
	* 전체 유저 목록 및 유저 검색 목록 (클릭하여 채팅할 유저를 선택)
* Right Section
	* 선택된 유저와의 채팅 기록 및 채팅 
