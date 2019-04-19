#### Q1. 각 부서별(dept_id)로 평균 급여(avg(salary))를 구하되 평균 급여가 2000 이상(avg(salary)>=2000)인 부서만 나타내시오
```
select dept_id 부서이름,avg(salary) 평균급여
 from s_emp

group by dept_id

having avg(salary) >= 2000 
-- 그룹함수 조건은 where 절이 아닌 having에 넣는다
;
```

#### Q2. 각 부서내에서(dept_id) 각 직책별(title)로 몇명의 인원(count(*))이 있는지 나타내시오
```
select title, count(*) from s_emp--1. 몇명있는지 출력

group by title--3. 직책별로 그룹화

order by title
;
```

#### Q3. 직원(S_EMP) 테이블에서 이름을 사전순으로 정렬하여 5개의 데이터만 나타내시오.

```
select name 연봉킹이름, salary 연봉

from (
	select name, salary from s_emp 
	order by 2 desc	) -- 정렬먼저

where rownum < 6;
```

#### Q4. 관리자별(manager_id)별(이름)로 담당하고 있는 직원의 수(count())를 나타내시오.
```
SELECT e2.name, e1.manager_id, count(*) 

FROM s_emp e1, s_emp e2

where e1.manager_id = e2.id

group by e2.name,e1.manager_id

order by e1.manager_id;
```
####  5. OUTER JOIN

> **사용법 :** WHERE e.id **(+)** = c.sales_rep_id  -- LEFT OUTER JOIN

 - LEFT OUTER, RIGHT OUTER, FULL OUTER
 - 데이터가 부족한 쪽으로 '(+)'를 붙이면 된다.

```
> 담당 직원이 배정되지 않은 고객을 찾는 경우

SELECT e.name 사원명, e.id, c.name 고객명 

FROM s_emp e, s_customer c

WHERE e.id (+) = c.sales_rep_id  -- LEFT OUTER JOIN
--WHERE e.id = c.sales_rep_id (+) -- RIGHT OUTER JOIN

ORDER BY 2;
```

#### Q6. 각 직책별(title)로 급여의 총합(sum(salary))을 구하되 직책이 부장인 사람은 제외하시오, 단, 급여 총합이 8000만원 이상인 직책만 나타내며, 급여 총합에 대한 오름차순으로 정렬하시오
```
select title, sum(salary) from s_emp--1. 급여의 총합 - (sum(salary))

where title not like '%부장' -- 부장인 사람은 제외

group by title--2. 직책별로 - (title)

having sum(salary) >= 8000--3. 급여 총합이 8000만원 이상

order by 2 asc;--4. 오름차순
```
#### 7. PK와 FK 설명

#### 8. 인덱스 언제 쓰는지

#### 9. 제약조건 종류

#### 10.시퀀스 허허ㅓ허 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTcyMTEwNDI2XX0=
-->