## 회원 등록
curl -X POST "http://localhost:8083/api/Member/" -H "accept: */*" -H "Content-Type: application/json" -d "{\"email\":\"scant10@gmail.com\",\"id\":\"jenny\",\"name\":\"제니\",\"passWord\":\"1111\"}"

## 첫번째 도서 등록
curl -X POST "http://localhost:8082/api/book/" -H "accept: */*" -H "Content-Type: application/json" -d "{\"author\":\"한정헌\",\"classfication\":\"LITERATURE\",\"description\":\"고전 소설\",\"isbn\":\"1232141214\",\"location\":\"JEONGJA\",\"publicationDate\":\"2023-02-11\",\"source\":\"SUPPLY\",\"title\":\"누구를 위하여 종을 울리나?\"}"

## 회원의 도서 카드 등록
curl -X POST "http://localhost:8081/api/RentalCard/" -H "accept: */*" -H "Content-Type: application/json" -d "{\"userId\":\"jenny\",\"userNm\":\"제니\"}"

## 첫번째 도서 대여
curl -X POST "http://localhost:8081/api/RentalCard/rent" -H "accept: */*" -H "Content-Type: application/json" -d "{\"itemId\":1,\"itemTitle\":\"누구를 위하여 종을 울리나?\",\"userId\":\"jenny\",\"userNm\":\"제니\"}"

## 첫번째 도서 상태 확인
curl -X GET "http://localhost:8082/api/book/1" -H "accept: */*" 

## 회원포인트 확인
curl -X GET "http://localhost:8083/api/Member/1" -H "accept: */*"

## 베스트도서 확인
curl -X GET "http://localhost:8084/api/books" -H "accept: */*" 

## 첫번째 도서 반납
curl -X POST "http://localhost:8081/api/RentalCard/return" -H "accept: */*" -H "Content-Type: application/json" -d "{\"itemId\":1,\"itemTitle\":\"누구를 위하여 종을 울리나?\",\"userId\":\"jenny\",\"userNm\":\"제니\"}"


## 두번째 도서 등록
curl -X POST "http://localhost:8082/api/book" -H "accept: */*" -H "Content-Type: application/json" -d "{\"author\":\"최재천\",\"classfication\":\"LITERATURE\",\"description\":\"최재천의 인생공부\",\"isbn\":\"1232141214\",\"location\":\"JEONGJA\",\"publicationDate\":\"2023-01-11\",\"source\":\"SUPPLY\",\"title\":\"최재천의공부\"}"

## 두번째 도서 대여
curl -X POST "http://localhost:8081/api/RentalCard/rent" -H "accept: */*" -H "Content-Type: application/json" -d "{\"itemId\":2,\"itemTitle\":\"최재천의공부\",\"userId\":\"jenny\",\"userNm\":\"제니\"}"

## 두번째 도서 상태 확인
curl -X GET "http://localhost:8082/api/book/2" -H "accept: */*" 

## 두번째 도서 연체 처리
curl -X POST "http://localhost:8081/api/RentalCard/overdue" -H "accept: */*" -H "Content-Type: application/json" -d "{\"itemId\":2,\"itemTitle\":\"최재천의공부\",\"userId\":\"jenny\",\"userNm\":\"제니\"}"

## 두번째 도서 상태 확인
curl -X GET "http://localhost:8082/api/book/2" -H "accept: */*" 

## 두번째 연체 도서 반납
curl -X POST "http://localhost:8081/api/RentalCard/return" -H "accept: */*" -H "Content-Type: application/json" -d "{\"itemId\":2,\"itemTitle\":\"최재천의공부\",\"userId\":\"jenny\",\"userNm\":\"제니\"}"

## 회원 상태 확인
curl -X GET "http://localhost:8083/api/Member/1" -H "accept: */*"

## 회원 대여 정지 해제
curl -X POST "http://localhost:8081/api/RentalCard/clearoverdue" -H "accept: */*" -H "Content-Type: application/json" -d "{\"userId\":\"jenny\",\"userNm\":\"제니\",\"point\":10}"
