# finalProject

▶ 추가 및 수정, 삭제 기록
-- ~2021.01.24
[1] 수빈
 1. 입주민 Main View 간략하게 완성
 2. 입주민 Top 전체 드롭다운 되게 완성
 3. default.jsp 랑 default.html 작성 => 세션에 아이디 없으면 알아서 index.do / 있으면 main.do로 이동
 4. apart_Name, apart_No 뽑아오는 매퍼 및 service 작성

 [2] 한희
 1. 입주민 대시보드 메인뷰 작업 -usertop / 

 [3] 이나 작업일지 
 1. 행정관리자 기본 공지 등록 기능 구현, 
 2. 공지리스트 조회 구현,
 3. 공지 등록에서 일정공지 선택하면 일정관련 입력폼 생성 ,
 4. 일정공지 등록 구현, 

 [4] 영조
 1. 입주민 관리비 내역 조회
 2. 청구월에 해당하는 상세 내역 조회
 3. 테이블 호버, 선택 시 CSS적용
 백엔드 기능 구현 완성

 2. 관리자 관리비 지출내역 조회 뷰, 백엔드 진행 중

-- ~2021.01.25~01.26

 [1] 수빈
- user/chat/chat.jsp  : 채팅 화면 띄우기 => top에 연결 시켜놓음 => IndexController 수정 (띄우기용)
	=> mainInc / mainTop 채팅주소 수정

- 사이트 운영진은 APT / APT123 / ADMIN 으로 미리 데이터 넣어놓아야함

- 사이트 운영진 폴더 : admin / adminMaster (뷰 완성) - 백 해야 함

- Emailcontroller에 있는 aptRegister (비회원 뷰에서 신청하기 폼 ) 삭제
- (참고) MemberController 에 신청하기 view 나오는 메서드 있음
- 	→ 사이트 운영자에게 쪽지보내는 post방식 제출
	→ 아파트 쪽지함 VO : ApartmentToSuperVO
		매퍼 master.xml 추가   =  사이트 운영진 전용
- 아파트 신청 내역 조회 완료 - ajax사용

-com.it.apt.adminMaster model및 controller 생성
-EmailController 수정 (위에 자세히 적혀있음 ...)
-LoginController 수정 (=로그아웃처리 removeAttribute memVo)
-MemberController 에서 adminRegister_post 수정
- registerApt.jsp 수정 (아파트 신청 쪽지 보내기 .. )
- user chat폴더 추가, userbottom ( c:url 태그 수정) 수정

- 세션 vo 없을때 인터셉터 처리 (아직 권한 처리 전) = 서블릿컨텍스트 확인

[2] 한희
1. 건의게시판 등록,조회,수정,상세보기 기본적인 기능 구현 완료

[3] 이나
1. 일반 공지 / 일정 공지 수정    noticeBoard.xml
com.it.apt.adminLiving.model   NoticeBoardVO.java
   NoticeBoardDAO.java
   NoticeBoardDAOMyBatis.java
   NoticeBoardService.java
   NoticeBoardServiceImpl.java
com.it.apt.adminLiving.controller   AdminLivingController.java

2. 입주민 공지사항 목록조회 뷰페이지 작업    NoticeController.java

3. 생활지원센터 폴더 정리   
com.it.apt.living.controller   : AddController.java
CarController.java
NoticeController.javaviews/living/add/
addFacilityDetail.jsp
addFacilityList.jsp
applicationAdd.jsp"
   "views/living/car/
carRegister.jsp
views/living/noti/
aptSchedule.jsp
noticeDetail.jsp
noticeList.jsp"
   views/living/noti
livingCenter폴더 삭제   

[4] 영조
26일 작업분 yeongjo
1. 공통
mngcost.xml
com.it.apt.mngcost.controller/AdminMngcostController.java 수정

2. 입주민 관리비 납부내역 / 상세보기 보완
/mngcost/mngcostInquiry.jsp 수정

3. 관리자 월별 관리비 조회 / 청구
/admin/adminMngcost/adminMngcostRegister.jsp 수정
/admin/adminMngcost/adminMngcostOrder.jsp 생성

~~ 01.26~~ // 01.28 오후2시 쯤 Merge

[1] 수빈
1. apart.xml 수정
2. master.xml 수정
adminMaster.model 패키지 파일추가
apart.model - ApartAllVO - 추가
apart.model, controller 싹 다 수정

[2] 한희
1.관리자 공통메인뷰 뷰페이지 작업
1-1.adminTop에 서브메뉴 각 관리자 메뉴, 공통메뉴 추가
1-2.admin/adminAll 뷰페이지, 메인화면 아주 조금 추가
1-3.adminAll 컨트롤러 추가

2.smartEditor 적용
2-1.webapp 하위경로에 SmartEditor2 폴더 추가

3.건의게시판 등록, 수정, 목록 기능 구현
[views] 
폴더
admin/adminAll : 관리자 공통관리
ㄴadminAllMain.jsp : 공통관리메인뷰
webapp/SmartEditor2 : 스마트에디터
[java]
패키지
com.it.apt.adminAll.controller 
ㄴAdminAllController.java

[3] 이나
1. 공지/ 일정 수정(트랜잭션걸려있음) 및 삭제 완료
2. 참고로 adminLiving패키지경로 수정됨
3. noticeBoard.xml 수정

[4] 영조
form-repeater~.js 수정, 
yjAjax~.js 추가 - 카테고리, 관리비 뿌리는거


~~~ 01.28~~~~
[1] 수빈
subinJs.js 파일 추가
admin/adminMaster/zipcode.jsp 추가
	→ 사이트 운영진 완료!!

-adminTop : 소유주 및 시설 관리자 메뉴 추가 및 수정

-pom.xml에 poi 추가 

[2] 이나
0130 이나푸시
[ 공지리스트 페이징,검색 ]
NoticeBoardVO를 비롯한 notice.model 패키지 전부
NoticeBoardController.java
noticeBoard.xml
adminNotiList.jsp

[달력관련
com.it.apt.living.controller / NoticeController.java
리소스에 ynCalendar 폴더 전체
aptSchedule.jsp
ynCalendar.jsp

[ 부가시설 관련model]
AddCategoryVO.java
AddDAO.java
AddDAOMyBatis.java
AddFacilityInfoVO.java
AddService.java
AddServiceImpl.java

~~~~~~~~01.31
[이나]
1. 부가시설 목록 [관리자]  adminAddInfoList.jsp
2. 부가시설 등록 [관리자] adminAddInfoRegister.jsp
3. 부가시설 신청자목록[관리자] adminAddResidence.jsp
4. 부가시설 매퍼 add.xml 
5. 변경된 VO : AddFacilityInfoVO.java
6. 변경된달력 : aptScheduler.jsp / ynCalendar폴더안에 lib 안에 main.js , main.css

[한희]
1.건의게시판 상세보기 댓글 등록 및 조회 기능 구현-ajax이용
2. SUGGEST_VIEW 수정, SEARCH_AUTH_VIEW 추가
3. 관리자 대시보드 공통메인기능-입주민게시판 카테고리추가 조회 기능 구현

--접속한 회원의 권한 조회
CREATE OR REPLACE VIEW SEARCH_AUTH_VIEW
AS
SELECT M.MEMBER_NO, H.AUTH_CODE, A.AUTH_LEVEL
FROM MEMBER_INFO M JOIN HOUSEHOLD_INFO H
ON M.HOUSEHOLD_CODE = H.HOUSEHOLD_CODE
JOIN AUTHORITY A
ON A.AUTH_CODE = H.AUTH_CODE;

CREATE OR REPLACE VIEW SUGGEST_VIEW
AS
SELECT S.SUGG_BOARD_NO, C.SUGG_CTG_NAME, S.SUGG_TITLE, S.SUGG_CONTENT, S.SUGG_REGDATE, S.MEMBER_NO, S.APT_NO, M.MEMBER_NAME,
    A.ANSW_NO, A.ANSW_REGDATE
FROM SUGGEST_BOARD S JOIN SUGGEST_CATEGORY C
ON S.SUGG_CTG_NO = C.SUGG_CTG_NO
JOIN MEMBER_INFO M
ON S.MEMBER_NO = M.MEMBER_NO
LEFT JOIN SUGGEST_ANSWER A
ON S.SUGG_BOARD_NO = A.SUGG_BOARD_NO
ORDER BY SUGG_BOARD_NO DESC;


~~~~~

~~~~~~~~~~~~~~02.02
[1] 수빈
- 아파트 소유주 apartOwner폴더 추가 - 입주민, 관리자관리

[2] 한희
건의게시판 목록 페이징처리 CSS 변경
-건의게시판 댓글 수정, 삭제 기능 구현
-건의게시판 글 삭제 기능 구현
-건의게시판 댓글 및 글쓰기, 수정 시 유효성검사 완료
-관리자 로그인 시 건의게시판, 입주민게시판 체크박스 활성화(아직 기능구현X)
-관리자 대시보드 => 게시판 카테고리 등록 및 목록 기능 구현, 페이징CSS 수정
-입주민게시판 글쓰기 및 목록 기능 구현

-SearchVO 수정
-뷰 수정 및 추가

-입주민게시판 model 패키지 및 하위폴더 추가, 입주민게시판 mapper파일 추가

[3] 이나
0131-0202작업파일 내용

[1] ★푸시할 때 제외함, 충돌방짘ㅋ★
mainTop.jsp에 링크추가 : 129~131줄
 <li><a href="<c:url value='/living/noti/noticeList.do'/>">공지사항</a>
 <li><a href="<c:url value='/living/noti/aptScheduler.do'/>">아파트 일정</a>
 <li><a href="<c:url value='/living/add/addFacilityList.do'/>">부가 시설</a>


[2]
mainBottom.jsp에 링크추가 : 31줄
<li><i class="bx bx-chevron-right"></i> <a href="<c:url value='/admin/adminLiving/adminLiving.do'/>">김이나</a></li>

[3]
adminInc/adminTop.jsp에 링크추가 : 379 ~403  행정2 : 부가시설 관리
 <!-- 행정2 : 부가시설 관리 -->
                <li class=" nav-item"><a class="d-flex align-items-center" href="#"><span class="menu-title text-truncate" data-i18n="eCommerce">부가시설 관리</span></a>
                    <ul class="menu-content">
                        <!-- 행정2-1 : 부가시설 등록 -->
                        <li><a class="d-flex align-items-center" href="<c:url value='/admin/adminLiving/adminAdd/adminAddRegList.do'/>">
                        <i data-feather="circle"></i><span class="menu-item" data-i18n="Shop">시설 정보 등록</span></a>
                        </li>
                        <!-- 행정2-2 : 부가시설 수정 -->
                        <li><a class="d-flex align-items-center" href="<c:url value='/admin/adminLiving/adminAdd/adminAddEdit.do'/>">
                        <i data-feather="circle"></i><span class="menu-item" data-i18n="Details">시설 정보 수정</span></a>
                        </li>
                        <!-- 행정2-3 : 부가시설목록  -->
                        <li><a class="d-flex align-items-center" href="<c:url value='/admin/adminLiving/adminAdd/adminAddInfoList.do'/>">
                        <i data-feather="circle"></i><span class="menu-item" data-i18n="Wish List">부가 시설 목록 관리</span></a>
                        </li>
                        <!-- 행정2-4 : 부가시설 신청내역 -->
                        <li><a class="d-flex align-items-center" href="<c:url value='/admin/adminLiving/adminAdd/adminAddResidence.do'/>">
                        <i data-feather="circle"></i><span class="menu-item" data-i18n="Wish List">부가 시설 신청내역</span></a>
                        </li>
                        <!-- 행정2-5 : 부가시설 접수중단 목록(ADD_OUTDATE IS NOT NULL)-->
                        <li><a class="d-flex align-items-center" href="<c:url value='/admin/adminLiving/adminAdd/adminAddDel.do'/>">
                        <i data-feather="circle"></i><span class="menu-item" data-i18n="Wish List">부가 삭제 내역(신청 안받는 시설 목록)</span></a>
                        </li>
                    </ul>
                </li>



[4]
공지게시판 파일업로드 기능 추가
notice친구들 java파일, xml 전부 다 ,, 
★fileUpload.properties★ 파일에서 전체경로 각각apt껄로 변경함 , 각자의 물리 경로에서 해당 폴더 경로로 변경 필수===========================
file.upload.path=apt_fileUp
file.upload.path.test=D:\\JAVA\\lecture\\EEworkspace_list\\sts_ws\\HouseMuch\\src\\main\\webapp\\resources\\apt_fileUp
imageFile.upload.path=apt_imgUp
imageFile.upload.path.test=D:\\JAVA\\lecture\\EEworkspace_list\\sts_ws\\HouseMuch\\src\\main\\webapp\\resources\\apt_imgUp

file.upload.type=test
#file.upload.type=deploy

★여기세줄은 행정메뉴용으로 추가한것입니다, 프로젝트 외부경로로 설정한거라서 D없으심 C로만 바꿔주세요★
ROOT_FILEPATH = D:\\apt_LivingFile
ADD_FILEPATH = \\apt_addFile
NOTI_FILEPATH =\\apt_notiFile
★여기세줄은 행정메뉴용으로 추가한것입니다, 프로젝트 외부경로로 설정한거라서 D없으심 C로만 바꿔주세요★
=======================================================================================


[5]
부가시설 목록 조회 추가
add친구들 java파일, xml 전부 다 ,, 
file.upload.path=apt_fileUp

[6]
리소스에 aptAdmin_images/aptUser_images 폴더에 각각 이미지 새로 추가함 ,

[7] 
[입주민] 공지사항 목록, 부가시설 신청, 부가시설목록 : living폴더안에 있는 jsp파일들
[관리자] 공지사항 파일첨부 기능 추가로 뷰 수정 : adminLiving /  adminNoti 폴더 안에 있는 jsp파일들

  
---------------------2021-02-05 merge
[이나]
0202-0204작업파일

1. 공지사항 파일첨부 수정삭제기능 수정 + 입주민뷰
noticeBoard.xml
NoticeBoard  model전부다 
NoticeBoardController.java 
NoticeController.java
noticeDetail.jsp
noticeList.jsp

2. 부가시설 관련 뷰페이지 작업 및 링크연결
AdminAddController.java
AddController.java
add.xml, AddFacilityInfoVO.java
addFacilityDetail.jsp
addFacilityList.jsp
addOrder.jsp
addOrderList.jsp

3. 공과금조회 차트뷰페이지 작업
EnergyController.java
energyChart.jsp

4. 뷰페이지 관련 리소스 파일 ynResources폴더에 전부 추가

5. 뷰페이지 링크연결 
mainTop.jsp
adminTop.jsp


[수빈]
LoginController - 권한에 따라 들어가는 페이지 달라짐
회원가입처리 완료
입주민 정보 엑셀 업로드 및 DB에 바로 insert 처리

------------------------------------------------------
[수빈]
<02/10>
AdminOwnerController.java
ExcelCellRef.java
findId.jsp
findPwd.jsp
findPwdEmail.jsp
findResetPwd.jsp
LoginController.java
member.js
member.xml
member.xml
owner.xml
OwnerDAO.java
OwnerDAOMybatis.java
ownerResident.jsp
OwnerService.java
OwnerServiceImpl.java
registerMember.jsp
ResidentVO.java

<02/13>
AdminMasterController.java
AdminOwnerController.java
AdminAllVO.java
OwnerDAO.java
OwnerDAOMybatis.java
OwnerService.java
OwnerServiceImpl.java
HouseholdDAO.java
HouseholdDAOMybatis.java
HouseholdMemVo.java
HouseholdService.java
HouseholdServiceImpl.java
MemberController.java
household.xml
owner.xml
ownerManage.jsp
ownerResident.jsp
memberEdit.jsp
helpUploadforRes.png ++
form-repeater-bin.js ++
AdminOwnerController.java ++

<02/15>
AdminController.java
AdminOwnerController.java
ApartDAO.java
ApartDAOMybatis.java
ApartService.java
ApartServiceImpl.java
IndexController.java
MemberController.java
MemberDAO.java
MemberDAOMybatis.java
MemberService.java
MemberServiceImpl.java
apart.xml
household.xml
member.xml
adminEdit.jsp
adminOwnerMain.jsp
ownerResident.jsp
main.jsp
mainNotice.jsp
mainScheduler.jsp
registerMember.jsp
memberEdit.jsp
dot.JPG
mor.JPG
--
LoginController.java
adminTop.jsp
mainTop.jsp

<02/16>
AdminFacilityController.java
IndexController.java
facilityAddCost.jsp
facilityCompanyList.jsp
facilityCompanyReg.jsp
adminBottom.jsp
adminOwnerMain.jsp
ownerResident.jsp
main.jsp
userbottom.jsp

<02/17>
AdminFacilityController.java
CompanyCtgVO.jvav
CompanyDAO.java
CompanyDAOMybatis.java
CompanyService.java
CompanyServiceImpl.java
CompanyVO.java
company.xml
facilityAddCost.jsp
facilityCompanyDetail.jsp
facilityCompanyReg.jsp
adminMasterApt.jsp
adminMasterMsg.jsp
ownerResident.jsp

<02/18>
AdminFacilityController.java
AddCostVO.java
CompanyDAO.java
CompanyDAOMybatis.java
CompanyService.java
CompanyServiceImpl.java
CompanyVO.java
company.xml
AdminOwnerController.java
OwnerIMPVO.java
facilityAddCost.jsp
facilityCompanyDetail.jsp
facilityCompanyEdit.jsp
facilityCompanyList.jsp
facilityPayCost.jsp
ownerResident.jsp
payIMP.jsp
carRegister.jsp
bluebird.min.js
form-repeater-bin.js
html2canvas.min.js
jspdf.min.js

--
adminTop.jsp
mainTop.jsp 추가 수정- 머지 후 배포

<02/19>
AdminCarControoler.java
CarDAO.java
CarDAOMybatis.java
CarService.java
CarServiceImpl.java
CarVO.java
ApartVO.java
CarController.java
car.xml
adminCarResidence.jsp
adminCarVisit.jsp
carMainList.jsp
carRegister.jsp
dashCar.jsp
bin-chart.js

-- TOP 마무리

END ! 






