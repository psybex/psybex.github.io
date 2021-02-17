---
title : "오라클 객체 정보 문자열 조회 쿼리"
category : 
    - Database
tag :
    - Database
    - Oracle
    - Tip
toc : true
---

## 오라클 자주 사용하는 조회 쿼리

현재 사용자가 접속한 DB의
객체 정보를 저장한 테이블
ALL_SOURCE

|Column name|Type|Description|
|---|---|---|
|OWNER|VARCHAR2 (30) NOT NULL|Object owner.|
|NAME|	VARCHAR2 (30) NOT NULL|Object name.|
|TYPE|VARCHAR2 (12) NOT NULL|Object type (such as PROCEDURE, FUNCTION, PACKAGE).|
|LINE|	TT_INTEGER NOT NULL|Line number of this line of source.|
|TEXT|VARCHAR2 (4000) NOT INLINE|Text source of the stored object.|
||||

<br>
<br>

```

/*
PAKAGE BODY에서
'HEAT_NO'텍스트 와
LIKE 조건에 해당하는
객체 정보를 조회
*/

SELECT *
  FROM ALL_SOURCE
 WHERE TYPE = 'PACKAGE BODY'
   AND TEXT LIKE '%HEAT_NO%'
;

```
