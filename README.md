## SearchMetro-BackEnd

지하철역의 여러 정보를 한눈에 볼 수 있는 웹사이트인 SearchMetro의 Back-end 코드입니다. 

## 📖 사용한 공공데이터
- 서울시 지하철 실시간 도착정보
- 서울시 지하철역 정보 검색 (역명)
- 서울시 지하철 호선별 첫차와 막차 정보(전철역코드,외부코드)
- 서울시 지하철 역사 편의시설 현황 (JSON 파일)
- 서울교통공사 역주소 및 전화번호 (JSON 파일)

## 🖥 라우트 소개

- 메인페이지 (/)
  <ul>
    <li>get : DB에서 유저 검색 후 북마크 정보 클라이언트에 전달</li>
    <li>post : token 검증 후 유효기간이 됐다면 DB에서 RefreshToken 가져온 후 검증하여 token 재발급</li>
    <li>delete : DB에서 유저 검색 후 북마크 정보 삭제</li>
  </ul>
- 검색 (/search)
  <ul>
      <li>get : Open API 정보 가져온 후 클라이언트에 전달</li>
      <li>post : 북마크 추가 혹은 삭제</li>
  </ul>
- 첫차와 막차 정보 (/search/FirstAndLast)
  <ul>
      <li>get : 클라이언트에서 선택한 조건에 따라 첫차와 막차 정보 가져온 후 전달</li>
  </ul>
- 별점 (/search/rating)
  <ul>
      <li>get : DB에서 별점 정보 가져온 후 평균값과 함께 클라이언트에 전달</li>
      <li>post : DB에 별점 정보가 없는 역일 경우 별점 DB 추가, 아니라면 클라이언트의 별점 점수 DB에 추가</li>
  </ul>
- 게시글 (/search/comment)
  <ul>
      <li>get : DB의 게시글 정보 클라이언트에 전달</li>
      <li>post : 클라이언트에서 가져온 정보로 DB의 게시글 정보 추가</li>
      <li>patch : 게시글 추천</li>
      <li>delete : 작성자나 관리자일 경우 게시글 DB에서 삭제</li>
  </ul>
- 로그인 (/login)
  <ul>
      <li>post : 이메일, 비밀번호 검증 후 token과 RefreshToken(DB에 저장) 발급</li>
  </ul>
- 마이페이지 (/search/comment)
  <ul>
      <li>get : DB에서 유저 정보 검색 후 클라이언트에 전달</li>
      <li>patch : 닉네임 또는 비밀번호 변경</li>
      <li>delete : 회원탈퇴 (사용자 회원탈퇴와 관리자 회원삭제가 같이)</li>
  </ul>
- 관리자 페이지 (/search/comment/admin)
  <ul>
      <li>get : DB에서 전체 유저 정보 검색 후 클라이언트에 전달</li>
  </ul>
- 회원가입 (/signup)
  <ul>
      <li>post: 비밀번호 암호화 후 회원정보 DB에 추가</li>
  </ul>
- 에러 (/error)
  <ul>
      <li>post: 클라이언트의 에러 정보 콘솔에 출력</li>
  </ul>

## 📚 기술 스택
<img src="https://img.shields.io/badge/node.js-339933?style=for-the-badge&logo=Node.js&logoColor=white">  <img src="https://img.shields.io/badge/express-000000?style=for-the-badge&logo=express&logoColor=white">  <img src="https://img.shields.io/badge/mongoDB-47A248?style=for-the-badge&logo=MongoDB&logoColor=white">

## 👨‍💻 개발자
KIM HEESIK (cka8701@gmail.com)
