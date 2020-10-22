
# SELECT 연습



order by

Select 문을 사용할때 출력되는 결과물은 테이블에 입력된 순서대로 출력되는 것이 기본입니다. 하지만 우리는 가끔은 내림차순으로 혹은 오름차순으로 정렬된 데이터들이 필요할 떄가 있습니다. 이때 사용하는 것이 ORDER BY절입니다.
ORDER BY 절은 항상 SELECT 문의 맨 마지막에 위치합니다.

ex>

SELECT *
FROM table_name
ORDER BY column_name(ASC,DESC)

ASC는 오름차순이고 DESC는 내림차순입니다.

ORDER BY 같은 경우에는 열의 이름 뿐 아니라 ALIAS를 입력해도 무방합니다. 이는 ORDER BY가 퀴리문 중에 가장 나중에 실행되는 쿼리문이기 때문입니다. 또한 열의 숫자위치로 정렬하는 것도 가능하며 여러 열을 기준으로 정렬하는 것이 또한 가능합니다.

기본형태
SELECT * FROM table_name ORDER BY column_name;

ALIAS 사용
SELECT sal+ comm AS TOTAL FROM emp ORDER BY TOTAL;

열의 숫자를 사용
SELECT * FROM table_name ORDER BY 3;
3번째 열을 기준으로 정렬하는 쿼리입니다.

여러 열을 기준으로 사용
SELECT *
FROM table_name
ORDER BY 3,1 DESC;  (지금은 리미트를 한다.)

<한개만 뽑을때>
-- 코드를 입력하세요
SELECT NAME 
FROM ANIMAL_INS
ORDER BY DATETIME
LIMIT 1;


3번쨰열을 기준으로 오름차순으로 정렬한 상태에서 1번째 열을 기준으로 내림차순으로 정렬하는 쿼리입니다.



<sum,MIN,MAX>

1번

SELECT MAX(DATETIME) AS 시간
FROM ANIMAL_INS;

SELECT DATETIME AS 시간
FROM ANIMAL_INS
ORDER BY DATETIME DESC
LIMIT 1;


2번
SELECT MIN(DATETIME) AS 시간
FROM ANIMAL_INS;

SELECT DATETIME AS 시간
FROM ANIMAL_INS
ORDER BY DATETIME
LIMIT 1;

3번
-- 코드를 입력하세요
SELECT COUNT(DATETIME) as count
FROM ANIMAL_INS;

4번
중복제거 하는 방법

  SELECT DISTINCT ID, NAME
   FROM TABLE;

    SELECT count(DISTINCT NAME) as count
    FROM ANIMAL_INS

오라클(ORACLE)에서 데이터 조회 시 데이터 중복을 제거하기 위해서는 대표적으로 2가지 방법이 있다. distinct 키워드를 사용하여 중복을 제거하는 방법과, group by 절을 사용하여 데이터 중복을 제거하는 방법이다.
두가지 방법 모두 장단점이 존재한다. 
distinct 키워드를 사용하여 데이터 중복을 제거할때는 select절에 distinct 키워드만 명시하면 되므로 쿼리문이 복잡하지 않고 간결하다. 그러나 distinct를 사용시 temp tablespace에 임시로 저장하고 작업하는 방식이라 시스템에 부하를 줄 수 있다.
group by절을 이용하여 데이터 중복을 제거할때는 select절의 컬럼을 group by절에도 동일하게 명시를 해야하는 부담감이 있지만 distinct에 비하여 조금 빠른감이 있다.

-중복제거
SELECT DISTINCT (컬럼명) FROM 테이블명

-중복된 데이터 제거 후 COUNT
SELECT COUNT(DISTINCT (컬럼명)) FROM 테이블명

-중복찾기
SELECT 컬럼명 FROM 테이블명 GROUP BY 컬럼명 HAVING COUNT (컬럼명) > 1

<출처> https://gomguard.tistory.com/93

