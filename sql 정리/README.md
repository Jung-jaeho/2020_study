# order by

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
ORDER BY 3,1 DESC;

3번쨰열을 기준으로 오름차순으로 정렬한 상태에서 1번째 열을 기준으로 내림차순으로 정렬하는 쿼리입니다.


<출처> https://gomguard.tistory.com/93

