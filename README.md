# mysql-

# mysql 에서 json data 저장 , select 하기 
``` mysql


select JSON_EXTRACT( 셀렉트할 테이블 컬럼, '$.셀렉트할 json key 값' ) from 셀렉트할 테이블 where JSON_EXTRACT( 셀렉트할 테이블 컬럼 , '$.셀렉트할 json key 값' ) = "검색하려는 json key 값";

```
