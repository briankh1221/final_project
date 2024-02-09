# LOTUS: 중고 거래 웹사이트
>
> K-Digital Training 
> (더조은 아카데미 - 빅데이터 분석 (with 파이썬)과 엘라스틱 서치를 활용한 자바(Java) 웹 개발자 양성 과정)
>
> 권지현, 고훈 파이널 프로젝트 레포지토리 입니다

# 프로젝트 소개

> - **이용자가 손쉽게 중고 물품을 구매 및 판매할 수 있는 플랫폼입니다.**
> - **다른 중고 사이트의 정보를 한눈에 볼 수 있어 이용자는 합리적인 가격으로 원하는 물품을 구매할 수 있습니다.**
> - **이용자는 간편한 절차를 통해 자신의 중고 물품을 손쉽게 판매할 수 있습니다.**
>
> - **SpringBoot와 Spring Data JPA를 사용해 기본적인 REST API를 구현하였고 AWS, S3 등을 이용해 서버를 배포할 예정입니다.**
>
> 
> #### 개발 기간 및 인원
> 24.01.16 ~ 24.03.09 (8주) / 프론트, 백엔드 2명(권지현, 고훈)


# 목차
>
> 1. [ERD](#ERD)
> 2. [아키텍처](#아키텍처)
> 3. [기술 스택](#기술-스택)
> 4. [주요 기능](#주요-기능)
>   + 공통 : [회원가입, 로그인](#회원가입-로그인) | [상품 목록 및 상품 상세 조회](#상품-목록-및-상품-상세-조회)
>   + 사용자 : [장바구니 관리](#장바구니-관리) | [주문 내역 관리](#주문-내역-관리) | [리뷰 관리](#리뷰-관리)
>   + 관리자 : [상품 및 상품 카테고리 관리](#상품-및-상품-카테고리-관리) | [옵션 카테고리 및 옵션 관리](#옵션-카테고리-및-옵션-관리) | [주문 수락 및 주문 상태 관리](#주문-수락-및-주문-상태-관리)
> 5. [api 명세](#api-명세)
> 6. [형상 관리 - Notion, Jira](#형상-관리)
> 7. [팀 문화](#팀-문화)

# 주요 기능

### 요약

<table align="center"><!-- 팀원 표 -->
  <tr>
   <th>
    공통
   </th>
   <th>
    사용자
   </th>
   <th >
    관리자
   </th>
   </tr>
  <tr>
   <td align="left" width="350px" class="공통">
    - 회원가입, 로그인
    <br/>
     - 채팅 (메시지 보내기)
    <br/>
    - 중고 물품 판매 등록 및 중고 물품 상세 페이지 조회
    <br/>
    - 리뷰 게시판 등록 및 리뷰 게시판 상세 페이지 조회
   </td>
   <td align="left" width="350px" class="사용자">
    - 장바구니 관리
    <br/>
    - 주문 내역 관리
    <br/>
    - 리뷰 관리
   </td>
   <td align="left" width="350px" class="관리자">
    - 상품 및 상품 카테고리 관리
    <br/>
    - 옵션 및 옵션 카테고리 관리
    <br/>
    - 주문 수락 및 주문 상태 관리
   </td>
  </tr>
</table>

## [ 공통 기능 ]

### 회원가입, 로그인
- 사용자는 이메일, 비밀번호, 닉네임, 휴대전화번호를 이용해 회원가입할 수 있다.
- 관리자는 이메일, 비밀번호, 관리자 인증코드, 실명을 이용해 회원가입할 수 있다.
- 회원가입 시 사용한 이메일과 비밀번호를 이용해 로그인할 수 있다.

### 상품 목록 및 상품 상세 조회
- 상품 카테고리 별 상품 목록을 조회할 수 있다.
  - 판매중인 상품과 매진된 상품이 전부 조회되며, 카테고리 별 상품이 아닌 전체 상품 목록 조회는 불가능하다.
- 베스트 상품 목록
  - 주문량이 많은 순서대로 5개의 상품들이 조회된다.
- 상품의 상세 정보를 조회할 수 있다. 상세정보에는 상품의 정보와 추가할 수 있는 옵션이 포함되어 있다.


## [ 사용자 기능 ]

### 장바구니 관리
- 장바구니에 상품을 추가한 후, 상품의 수량을 조절하거나 상품을 삭제할 수 있다.

### 주문 관리
- 결제를 하면 장바구니에 담겨있는 모든 상품이 주문 내역으로 생성된다.
- 기본적으로 3개월간의 주문 내역이 조회되고, 기간을 설정할 시 설정한 기간동안의 내역이 조회된다.
- 본인의 모든 주문 내역을 조회할 수 있다.
- 주문한 상품들의 조리가 시작된 후 시간이 얼마나 경과되었는지 조회할 수 있다.
- 관리자가 주문을 수락하기 이전에는 사용자가 주문을 취소할 수 있다.


### 리뷰 관리
- 본인이 주문한 상품에 대해 리뷰 내용, 별점(1~5점), 사진 1장으로 리뷰를 등록할 수 있다.


## [ 관리자 기능 ]

### 상품 및 상품 카테고리 관리

- 상품을 등록할 수 있다.(상품 사진은 1장만 등록할 수 있다.)
- 등록한 상품의 정보를 수정, 삭제할 수 있다.
- 상품 전체 목록을 조회할 수 있고, 상품 하나의 정보도 조회할 수 있다.
- 상품의 재고 현황을 변경할 수 있다. => 상품의 품절 여부를 변경할 수 있다. ??

- 상품 카테고리를 등록할 수 있고, 등록한 상품 카테고리를 수정, 삭제할 수 있다.
- 상품 카테고리 전체 목록을 조회할 수 있고, 상품 카테고리 하나의 정보도 조회할 수 있다.

### 옵션 및 옵션 카테고리 관리
- 옵션 및 옵션 카테고리를 등록할 수 있고, 등록한 옵션을 수정, 삭제할 수 있다.
- 옵션 및 옵션 카테고리의 전체 목록을 조회할 수 있고, 하나의 정보도 조회할 수 있다

### 주문 관리
- 주문이 어떻게 진행되고 있는지 확인할 수 있도록 주문의 상태를 변경할 수 있다.
- 주문이 들어오면 예상 조리 시간을 선택해야 한다.
- 주문이 들어오면 주문을 수락하거나 거절할 수 있다.

# API 명세

| Domain       | URL                                                                        | Http Method                 | description       | 접근 권한 |
|:-------------|:---------------------------------------------------------------------------|:----------------------------|:------------------|:------|
| **auth**     | /auth/signup                                                                    | `POST`                 | 사용자 회원가입          | USER |
|              | /auth/signup/admin                                                              | `POST`                 | 관리자 회원가입          | ADMIN |
|              | /auth/signin                                                                    | `POST`                 | 사용자/관리자 로그인       | -     |
| **admin**    | /admin/product/{productId}                                                 | `GET` `PUT` `DELETE`        | 관리자 상품 조회, 수정, 삭제 | ADMIN  |
|              | /admin/category/{categorytId}                                              | `GET` `PUT` `DELETE`        | 관리자 카테고리 항목 관리 | ADMIN  |
|              | /admin/qna/{productId}                                                     | `GET` `PUT` `DELETE`        | 관리자 질문 게시판 관리 | ADMIN |
|              | /admin/review/{productId}                                                  | `GET` `PUT` `DELETE`        | 관리자 리뷰 관리 | ADMIN  |
| **Prouduct** | /product/category-list/{categoryId}                                        | `GET`                       | 카테고리 별 상품 목록 조회   | USER |
|              | /product/best-list                                                         | `GET`                       | 베스트 상품 목록 조회      | USER |
|              | /product/recent-list                                                       | `GET`                       | 최신 상품 목록 조회          | USER |
|              | /user/product                                                              | `POST`                      | 상품 등록             | USER |
|              | /product/{productId}                                                       | `GET` `PUT` `DELETE`        | 상품 조회, 수정, 삭제     | USER |
|              | /user/product-list                                                         | `GET`                       | 사용자 등록 상품 목록     | USER |
| **favorite** | /user/favorite                                                             | `POST`                      | 찜 등록      | USER |
|              | /user/favorite                                                             | `GET` `PUT` `DELETE`        | 찜 상품 조회, 수정, 삭제     | USER |
| **qna**      | /user/qna                                                                  | `POST`                      | qna 작성     | USER |
|              | /user/qna                                                                  | `GET` `PUT` `DELETE`        | qna 조회, 등록, 삭제     | USER |
| **review**   | /user/review                                                               | `POST`                      | 리뷰 작성    | USER |
|              | /user/review                                                               | `GET` `PUT` `DELETE`        | 리뷰 조회, 수정, 삭제     | USER |
| **message**  | /user/message                                                              | `GET` `POST`                | 채팅 조회, 작성     | USER |

# 임시 아키텍쳐

![전체 아키텍쳐 임시](https://github.com/briankh1221/final_project/assets/129491967/6d48dd94-d156-4e88-9702-ab1fa3efaabe
)

# ERD
[👉 ERD Cloud에서 직접 보기](https://www.erdcloud.com/d/pTHTfhADbwpA9mggo)

![ERD](https://github.com/briankh1221/final_project/assets/145642491/bf9f35f2-41ed-428a-abfd-be44aba59cdb)

