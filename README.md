# mysql-

# mysql 에서 json data select 하기 
``` mysql

select JSON_EXTRACT( json데이터가 있는 셀렉트할 테이블 컬럼, '$.셀렉트할 json key 값' ) from 셀렉트할 테이블 where JSON_EXTRACT( json데이터가 있는 셀렉트할 테이블 컬럼 , '$.셀렉트할 json key 값' ) = "검색하려는 json key 값";

```
# mysql 에서 json data select 할때 , Array 를 select 할때 
![array](https://user-images.githubusercontent.com/69393030/145916327-9f794c52-89d0-49fe-8e7b-85fb2820f3db.PNG)

이런식으로 array 가 있으면 이렇게 접근할 수 있다.

select JSON_EXTRACT( json데이터가 있는 셀렉트할 테이블 컬럼, '$.셀렉트할 json key[0]' ) from 조회할 테이블명  
select JSON_EXTRACT( json데이터가 있는 셀렉트할 테이블 컬럼, '$.셀렉트할 json key[1]' ) from 조회할 테이블명 

select JSON_EXTRACT( json데이터가 있는 셀렉트할 테이블 컬럼, '$.셀렉트할 json key[2]' ) from 조회할 테이블명 

# mysql 에서 json data select 시 , 원하는 index 의 array 의 값을 find 할때 

``` mysql 
 select JSON_EXTRACT( json데이터가 있는 셀렉트할 테이블 컬럼, '$.셀렉트할 json key[0]' ) from 셀렉트할 테이블 where JSON_EXTRACT( json데이터가 있는 셀렉트할 테이블 컬럼, '$.셀렉트할 json key 값[0]' ) = 42;


```
이때 number (숫자)의 경우 , '42' 가 아닌 싱글쿼트를 제거한 42 를 사용하도록한다.

# 화살표 -> (Arrow notation) 표기 법으로 filter 하여 , json data 를 find 하기

``` mysql

SELECT json데이터가 있는 셀렉트할 테이블 컬럼
FROM 셀렉트할 테이블
WHERE value -> "$.셀렉트할 json key" = 'SKT'

```
