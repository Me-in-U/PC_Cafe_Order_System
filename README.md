# 🖥️ PC방 상품 주문 관리 시스템

## 📌 개요
단일 HTML/JS/CSS 파일로 구현된 **PC방 상품 주문 및 회원/관리자 관리 시스템**입니다.  
`jQuery` 기반으로 동작하며, 로그인/회원가입, 상품 장바구니 주문, 관리자 기능(회원 관리/주문 관리/상품 관리)을 지원합니다.  
서버나 DB 없이 메모리 배열로 데이터가 관리되며, 브라우저에서 바로 실행 가능합니다.

---

## 🚀 주요 기능

### 1. 🔐 로그인 / 회원가입
- **아이디 규칙**: 5~21자, 영문자 최소 1자 포함, 영문/숫자/밑줄(_) 허용  
- **비밀번호 규칙**: 10~16자, 영문/숫자/특수문자(!@*`/?_) 각 1자 이상 포함  
- **회원가입**: 중복 아이디 방지, 성공 시 로그인 화면으로 유도  
- **관리자 기본 계정**: ID: `admin`, PW: `admin`

### 2. 👑 관리자 기능
관리자 계정 로그인 시 관리자 페이지 진입  
- **📋 회원 관리**: 현재 가입된 유저 목록 표시 (본인 제외), 표시 항목: 아이디 / 비밀번호 / 관리자 여부 / 기능  
  - 회원 탈퇴 (관리자는 탈퇴 불가, 탈퇴 시 주문내역도 함께 삭제)  
  - 권한 변경 (일반 ↔ 관리자)  
- **📦 주문 내역 관리**: 전체 회원의 주문 내역 확인 가능 (아이디 / 주문내역 / 총 가격 / 주문일시)  
- **🛠 상품 추가 / 제거**: 카테고리(🍜식사 / 🍪간식 / 🍹음료 / 🔗기타)별 관리 가능  
  - 상품 추가: 이름 / 가격 입력 후 추가  
  - 상품 제거: 카테고리 및 상품 선택 후 제거  

### 3. 🙋 일반 사용자 기능
일반 사용자 로그인 시 유저 페이지 진입  
- **🛒 상품 보기 / 장바구니**: 카테고리 버튼으로 상품 탐색, 상품 카드 클릭 시 장바구니 추가  
  - 장바구니 표시 항목: 번호 / 상품명 / 가격  
  - 기능: 개별 삭제(x), 전체 비우기, 주문하기(최소 1개 이상 필요)  
- **📑 주문 내역**: 로그인한 사용자 본인의 주문 내역 확인 (주문내역 / 총 가격 / 주문일시)  

---

## 📂 데이터 구조 (JavaScript 객체 기반)

```js
function User(id, pw, admin = false) {
  this.id = id;
  this.pw = pw;
  this.admin = admin; // true → 관리자
}

function Item(item_name, item_price) {
  this.item_name = item_name;
  this.item_price = item_price;
}

function history(id, cart_data, total_price, time) {
  this.id = id;
  this.cart_data = cart_data;   // Item 배열
  this.total_price = total_price;
  this.time = time;             // Date 객체
}
````
## 🖼️ 화면 구성 (스크린샷 예시)

- 로그인
![스크린샷 2024-03-17 000220](https://github.com/BOJ-ios/PC_Cafe_Order_System/assets/44316764/de13b91e-da30-45f5-9a85-d4ae68c4835a)

- 관리자 페이지 (회원정보)
![스크린샷 2024-03-17 000227](https://github.com/BOJ-ios/PC_Cafe_Order_System/assets/44316764/86418775-f487-4b5f-b8be-b3cab1dcb79b)

- 관리자 페이지 (주문내역)
![스크린샷 2024-03-17 000235](https://github.com/BOJ-ios/PC_Cafe_Order_System/assets/44316764/2ed3814d-b711-4166-9b6a-c90f3f35099b)

- 관리자 페이지 (상품 추가/제거)
![스크린샷 2024-03-17 000238](https://github.com/BOJ-ios/PC_Cafe_Order_System/assets/44316764/702b430e-2642-48d7-9ad3-fa473c31a105)

- 유저 페이지 (상품 보기)
![스크린샷 2024-03-17 000327](https://github.com/BOJ-ios/PC_Cafe_Order_System/assets/44316764/8abf4cdb-c2b0-4942-9e9e-eca448b76587)

- 유저 페이지 (상품 보기2)
![스크린샷 2024-03-17 000337](https://github.com/BOJ-ios/PC_Cafe_Order_System/assets/44316764/d5906577-6930-4cad-a11a-869bf5aa3a27)

- 유저 페이지 (주문내역)
![스크린샷 2024-03-17 000343](https://github.com/BOJ-ios/PC_Cafe_Order_System/assets/44316764/e4663560-6f4b-413b-94f3-161971b5cc1a)

---

## ⚙️ 기술 스택

- Frontend: HTML5, CSS3, jQuery (3.7.0 + Migrate 3.4.1)
- Backend: 없음 (순수 클라이언트 실행)
- DB: 없음 (데이터는 새로고침 시 초기화됨)

---

## 🧪 실행 방법

1. 저장소 clone 또는 HTML 파일 다운로드

2. 브라우저에서 index.html 실행

3. admin / admin 계정으로 관리자 로그인, 또는 회원가입 후 사용자 로그인


