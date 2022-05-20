# TIL
배움의 기록

# 2022-05-19
- 자바형변환
- https://soobarkbar.tistory.com/57

# 2022-05-20
- 오라클 WITH 테이블 
WITH A AS
(
  SELECT SQL QUERY....
)
SELECT * FROM A;

원하는 데이터를 조회하여 가상테이블로 만든후 사용하는 것
WITH 테이블은 여러번 사용할 때 효과가 더 크며, 가상테이블은 메모리에 생성되므로 액세스 속도가 빠르며 조회후에는 자동으로 소멸된다.
