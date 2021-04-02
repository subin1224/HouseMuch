# HouseMuch

![image](https://user-images.githubusercontent.com/76253952/112454851-73ac0500-8d9c-11eb-9b7d-73376a8f89a9.png)

![image](https://user-images.githubusercontent.com/76253952/112454876-7e669a00-8d9c-11eb-9908-8f4f18e5173e.png)

![image](https://user-images.githubusercontent.com/76253952/112455373-ff259600-8d9c-11eb-8ab3-ea1d7b24ad4b.png)

![image](https://user-images.githubusercontent.com/76253952/112455413-09e02b00-8d9d-11eb-9c4d-e80efc23bbee.png)

![image](https://user-images.githubusercontent.com/76253952/112455454-14022980-8d9d-11eb-972f-c415c34792ef.png)

![image](https://user-images.githubusercontent.com/76253952/112455487-1bc1ce00-8d9d-11eb-9615-30cfec3b28b0.png)

# 🔎 구현 목록

## **비회원**

1. Javax.mail 을 이용해 사이트 이용 문의를 사이트 관리자에게 이메일을 보낼 수 있습니다.
2. 사이트 관리자에게 사이트 이용 신청을 보낼 수 있습니다.
3. 회원가입 을 할 수 있습니다. 이때, BCrypt 를 이용해 비밀번호 암호화를 적용합니다.
4. Javax.mail 을 통해 보낸 인증번호로 아이디와 비밀번호 찾기를 할 수 있습니다. 
5. Kakaomap API 를 통해 사이트 제작 회사의 위치를 확인 할 수 있습니다.

## 입주민

1. 첫 홈페이지에 코로나 오픈 API를 이용해 국내 코로나 확진자 현황을 조회할 수 있습니다.
2. 회원정보를 수정(이름, 비밀번호, 이메일 수정 가능) 및 탈퇴 할 수 있습니다.
3. 해당 세대의 차량과 해당 세대를 방문한 차량들을 등록 및 조회를 할 수 있습니다.

## 사이트 운영자

1. 비회원이 보낸 사이트 신규 이용 신청 내역을 조회 및 삭제 할 수 있습니다.
2. 사이트를 이용하는 아파트를 등록, 수정, 삭제 및 조회가 가능합니다.

## 시설 관리자

1. 계약한 보수 업체의 목록들을 조회 할 수 있으며, 보수 업체 계약 내용을 SmartEditor를 이용해 등록, 수정, 삭제 또한 가능합니다.
2. 계약한 보수 업체와의 세부사항 은 JSPDF를 이용해 프린트, pdf출력이 가능합니다.
3. 계약 내용 외에 추가적으로 유지보수 비용이 발생하면 해당 비용을 아파트 소유주에게 청구할 수 있습니다.
4. 해당 아파트에 등록한 모든 세대 차량 및 방문차량을 chart.js를 통해 월별로 간단하게 조회 할 수 있습니다.

## 아파트 소유주

1. Excel poi 를 통해 엑셀 파일에 담겨져있는 입주민들의 정보를 한번에 두개의 table에 insert 할 수 있습니다.이때, 입주민 등록과 동시에 회원가입에 필요한 세대코드를 발급합니다. 
2. 아파트 관리자의 세대코드를 발급합니다. 이때 부여할 각 권한을 조절 할 수 있습니다.
3. 시설 관리자에게 전달 받은 추가 유지보수 비용을 Import 를 통해 결제 할 수 있습니다.

---

## 🔗Link

[HouseMuch_Subin.pptx](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1780602e-2415-4609-989e-8e149fa53cb8/HouseMuch_Subin.pptx)

- [http://3.131.225.119:8080/HouseMuch/](http://3.131.225.119:8080/HouseMuch/)
- [https://github.com/subin1224/finalProject](https://github.com/subin1224/finalProject)
