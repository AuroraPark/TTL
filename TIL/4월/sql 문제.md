#### Q5. 각 부서별(dept_id)로 평균 급여(avg(salary))를 구하되 평균 급여가 2000 이상(avg(salary)>=2000)인 부서만 나타내시오
```
select dept_id,avg(salary) from s_emp

group by dept_id

having avg(salary) >= 2000 
-- 그룹함수 조건은 where 절이 아닌 having에 넣는다
;


#### Q3. 각 부서내에서(dept_id) 각 직책별(title)로 몇명의 인원(count(*))이 있는지 나타내시오
```
select title, count(*) from s_emp--1. 몇명있는지 출력

group by title--3. 직책별로 그룹화

order by title
;
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTY5NDQ2MTc0XX0=
-->