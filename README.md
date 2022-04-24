<h2> Spring-JPA01 </h2>

<h3>사용 기술</h3> 

Spring Boot, JPA, H2 DB


<h3> 웹사이트 기능 </h3>

 - 사용자 회원가입
 - 상품 등록, 재고 확인
 - 상품 주문
 - 주문 조회, 취소

<h3> API 서버 </h3>

 - @GetMapping("api/members") <br>
 회원 정보 조회 <br>

 - @PostMapping("/api/members") <br>
 회원 가입 <br>

 - @PutMapping("/api/members/{id}")<br>
 회원 정보 수정 <br>
