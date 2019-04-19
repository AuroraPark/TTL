
#### Q1. 각 부서별(dept_id)로 평균 급여(avg(salary))를 구하되 평균 급여가 2000 이상(avg(salary)>=2000)인 부서만 나타내시오
```
select dept_id 부서이름, avg(salary) 평균급여

from s_emp

group by dept_id

having avg(salary) >= 2000 
-- 그룹함수 조건은 where 절이 아닌 having에 넣는다
;
```

#### Q2. 각 직책별(title)로 급여의 총합(sum(salary))을 구하되 직책이 사원인 사람은 제외하시오, 단, 급여 총합이 3000만원 이상인 직책만 나타내며, 급여 총합에 대한 내림차순으로 정렬하시오
```
select title, sum(salary) from s_emp--1. 급여의 총합 - (sum(salary))

where title <> '사원' -- 부장인 사람은 제외

group by title--2. 직책별로 - (title)

having sum(salary) >= 3000--3. 급여 총합이 3000만원 이상

order by 2 desc;--4. 오름차순

```



#### Q3. 직책(s_emp.title)이 '부장(영업부장, 지부장 포함)'인 사람이 2명 이하인 부서(s_emp.dept_id)가 몇개인지 나타내시오.
```
select dept_id 부서, count(*) 인원 from s_emp--1. 몇명있는지 출력

where title like '%부장'

group by dept_id--3. 부서별로 그룹화
;
```



#### Q4.  담당 직원이 배정되지 않은 고객을 찾는 경우
```
SELECT e.name 사원명, e.id, c.name 고객명 

FROM s_emp e, s_customer c

--WHERE e.id (+) = c.sales_rep_id  -- LEFT OUTER JOIN
WHERE e.id = c.sales_rep_id (+) -- RIGHT OUTER JOIN

ORDER BY 2;
```


#### Q5. PK와 FK 설명

> PK 

- 인덱스 자동생성
- 트리구조
- 중복 x, 색인 빠름 
- NULL x
- 테이블, 컬럼 단계에서 가능

> FK

- 부모 테이블 값과 일치하거나 NULL이어야함
- 부모 테이블 먼저 생성
- ON DELETE CASCADE 덧글도 삭제

#### Q6. 제약조건 종류

> NN, UNIQUE, PK, FK, CHECK

#### Q7.자동으로 고유한 숫자값을 생성해 주며 주로 기본키 값을 생성하기 위해 사용하는 object는 ?

> 시퀀스

#### Q8. 직원(S_EMP) 테이블에서 연봉순으로 정렬하여 3개의 데이터만 나타내시오.

```
select name 연봉킹이름, salary 연봉

from (
	select name, salary from s_emp 
	order by 2 desc	) -- 정렬먼저

where rownum < 4;
```

#### Q9. 인덱스 언제 쓰는지


#### Q10.아래의 sql문은 비효율적이다. (title에 인덱스가 작성되어 있다고 가정)
이 문장을 not exists를 사용해서 효율적으로 작성하시오.

```
select * from s_emp where title <> '사원';
```

```
select * from s_emp where not exists (select * from s_emp where title='사원');
```

#### Q1. 각 부서별(dept_id)로 평균 급여(avg(salary))를 구하되 평균 급여가 2000 이상(avg(salary)>=2000)인 부서만 나타내시오
```
select dept_id 부서이름, avg(salary) 평균급여

from s_emp

group by dept_id

having avg(salary) >= 2000 
-- 그룹함수 조건은 where 절이 아닌 having에 넣는다
;
```

#### Q2. 각 직책별(title)로 급여의 총합(sum(salary))을 구하되 직책이 사원인 사람은 제외하시오, 단, 급여 총합이 3000만원 이상인 직책만 나타내며, 급여 총합에 대한 내림차순으로 정렬하시오
```
select title, sum(salary) from s_emp--1. 급여의 총합 - (sum(salary))

where title <> '사원' -- 부장인 사람은 제외

group by title--2. 직책별로 - (title)

having sum(salary) >= 3000--3. 급여 총합이 3000만원 이상

order by 2 desc;--4. 오름차순

```



#### Q3. 직책(s_emp.title)이 '부장(영업부장, 지부장 포함)'인 사람이 2명 이하인 부서(s_emp.dept_id)가 몇개인지 나타내시오.
```
select dept_id 부서, count(*) 인원 from s_emp--1. 몇명있는지 출력

where title like '%부장'

group by dept_id--3. 부서별로 그룹화
;
```



#### Q4.  담당 직원이 배정되지 않은 고객을 찾는 경우
```
SELECT e.name 사원명, e.id, c.name 고객명 

FROM s_emp e, s_customer c

--WHERE e.id (+) = c.sales_rep_id  -- LEFT OUTER JOIN
WHERE e.id = c.sales_rep_id (+) -- RIGHT OUTER JOIN

ORDER BY 2;
```


#### Q5. PK와 FK 설명

> PK 

- 인덱스 자동생성
- 트리구조
- 중복 x, 색인 빠름 
- NULL x
- 테이블, 컬럼 단계에서 가능

> FK

- 부모 테이블 값과 일치하거나 NULL이어야함
- 부모 테이블 먼저 생성
- ON DELETE CASCADE 덧글도 삭제

#### Q6. 제약조건 종류

> NN, UNIQUE, PK, FK, CHECK

#### Q7.자동으로 고유한 숫자값을 생성해 주며 주로 기본키 값을 생성하기 위해 사용하는 object는 ?

> 시퀀스

#### Q8. 직원(S_EMP) 테이블에서 연봉순으로 정렬하여 3개의 데이터만 나타내시오.

```
select name 연봉킹이름, salary 연봉

from (
	select name, salary from s_emp 
	order by 2 desc	) -- 정렬먼저

where rownum < 4;
```

#### Q9. 인덱스 언제 쓰는지


#### Q10.아래의 sql문은 비효율적이다. (title에 인덱스가 작성되어 있다고 가정)
이 문장을 not exists를 사용해서 효율적으로 작성하시오.

```
select * from s_emp where title <> '사원';
```

```
select * from s_emp where not exists (select * from s_emp where title='사원');
```

#### Q1. 각 부서별(dept_id)로 평균 급여(avg(salary))를 구하되 평균 급여가 2000 이상(avg(salary)>=2000)인 부서만 나타내시오
```
select dept_id 부서이름, avg(salary) 평균급여

from s_emp

group by dept_id

having avg(salary) >= 2000 
-- 그룹함수 조건은 where 절이 아닌 having에 넣는다
;
```

#### Q2. 각 직책별(title)로 급여의 총합(sum(salary))을 구하되 직책이 사원인 사람은 제외하시오, 단, 급여 총합이 3000만원 이상인 직책만 나타내며, 급여 총합에 대한 내림차순으로 정렬하시오
```
select title, sum(salary) from s_emp--1. 급여의 총합 - (sum(salary))

where title <> '사원' -- 부장인 사람은 제외

group by title--2. 직책별로 - (title)

having sum(salary) >= 3000--3. 급여 총합이 3000만원 이상

order by 2 desc;--4. 오름차순

```



#### Q3. 직책(s_emp.title)이 '부장(영업부장, 지부장 포함)'인 사람이 2명 이하인 부서(s_emp.dept_id)가 몇개인지 나타내시오.
```
select dept_id 부서, count(*) 인원 from s_emp--1. 몇명있는지 출력

where title like '%부장'

group by dept_id--3. 부서별로 그룹화
;
```



#### Q4.  담당 직원이 배정되지 않은 고객을 찾는 경우
```
SELECT e.name 사원명, e.id, c.name 고객명 

FROM s_emp e, s_customer c

--WHERE e.id (+) = c.sales_rep_id  -- LEFT OUTER JOIN
WHERE e.id = c.sales_rep_id (+) -- RIGHT OUTER JOIN

ORDER BY 2;
```


#### Q5. PK와 FK 설명

> PK 

- 인덱스 자동생성
- 트리구조
- 중복 x, 색인 빠름 
- NULL x
- 테이블, 컬럼 단계에서 가능

> FK

- 부모 테이블 값과 일치하거나 NULL이어야함
- 부모 테이블 먼저 생성
- ON DELETE CASCADE 덧글도 삭제

#### Q6. 제약조건 종류

> NN, UNIQUE, PK, FK, CHECK

#### Q7.자동으로 고유한 숫자값을 생성해 주며 주로 기본키 값을 생성하기 위해 사용하는 object는 ?

> 시퀀스

#### Q8. 직원(S_EMP) 테이블에서 연봉순으로 정렬하여 3개의 데이터만 나타내시오.

```
select name 연봉킹이름, salary 연봉

from (
	select name, salary from s_emp 
	order by 2 desc	) -- 정렬먼저

where rownum < 4;
```

#### Q9. 인덱스 언제 쓰는지


#### Q10.아래의 sql문은 비효율적이다. (title에 인덱스가 작성되어 있다고 가정)
이 문장을 not exists를 사용해서 효율적으로 작성하시오.

```
select * from s_emp where title <> '사원';
```

```
select * from s_emp where not exists (select * from s_emp where title='사원');
```

#### Q1. 각 부서별(dept_id)로 평균 급여(avg(salary))를 구하되 평균 급여가 2000 이상(avg(salary)>=2000)인 부서만 나타내시오
```
select dept_id 부서이름, avg(salary) 평균급여

from s_emp

group by dept_id

having avg(salary) >= 2000 
-- 그룹함수 조건은 where 절이 아닌 having에 넣는다
;
```

#### Q2. 각 직책별(title)로 급여의 총합(sum(salary))을 구하되 직책이 사원인 사람은 제외하시오, 단, 급여 총합이 3000만원 이상인 직책만 나타내며, 급여 총합에 대한 내림차순으로 정렬하시오
```
select title, sum(salary) from s_emp--1. 급여의 총합 - (sum(salary))

where title <> '사원' -- 부장인 사람은 제외

group by title--2. 직책별로 - (title)

having sum(salary) >= 3000--3. 급여 총합이 3000만원 이상

order by 2 desc;--4. 오름차순

```



#### Q3. 직책(s_emp.title)이 '부장(영업부장, 지부장 포함)'인 사람이 2명 이하인 부서(s_emp.dept_id)가 몇개인지 나타내시오.
```
select dept_id 부서, count(*) 인원 from s_emp--1. 몇명있는지 출력

where title like '%부장'

group by dept_id--3. 부서별로 그룹화
;
```



#### Q4.  담당 직원이 배정되지 않은 고객을 찾는 경우
```
SELECT e.name 사원명, e.id, c.name 고객명 

FROM s_emp e, s_customer c

--WHERE e.id (+) = c.sales_rep_id  -- LEFT OUTER JOIN
WHERE e.id = c.sales_rep_id (+) -- RIGHT OUTER JOIN

ORDER BY 2;
```


#### Q5. PK와 FK 설명

> PK 

- 인덱스 자동생성
- 트리구조
- 중복 x, 색인 빠름 
- NULL x
- 테이블, 컬럼 단계에서 가능

> FK

- 부모 테이블 값과 일치하거나 NULL이어야함
- 부모 테이블 먼저 생성
- ON DELETE CASCADE 덧글도 삭제

#### Q6. 제약조건 종류

> NN, UNIQUE, PK, FK, CHECK

#### Q7.자동으로 고유한 숫자값을 생성해 주며 주로 기본키 값을 생성하기 위해 사용하는 object는 ?

> 시퀀스

#### Q8. 직원(S_EMP) 테이블에서 연봉순으로 정렬하여 3개의 데이터만 나타내시오.

```
select name 연봉킹이름, salary 연봉

from (
	select name, salary from s_emp 
	order by 2 desc	) -- 정렬먼저

where rownum < 4;
```

#### Q9. 인덱스 언제 쓰는지


#### Q10.아래의 sql문은 비효율적이다. (title에 인덱스가 작성되어 있다고 가정)
이 문장을 not exists를 사용해서 효율적으로 작성하시오.

```
select * from s_emp where title <> '사원';
```

```
select * from s_emp where not exists (select * from s_emp where title='사원');
```

#### Q1. 각 부서별(dept_id)로 평균 급여(avg(salary))를 구하되 평균 급여가 2000 이상(avg(salary)>=2000)인 부서만 나타내시오
```
select dept_id 부서이름, avg(salary) 평균급여

from s_emp

group by dept_id

having avg(salary) >= 2000 
-- 그룹함수 조건은 where 절이 아닌 having에 넣는다
;
```

#### Q2. 각 직책별(title)로 급여의 총합(sum(salary))을 구하되 직책이 사원인 사람은 제외하시오, 단, 급여 총합이 3000만원 이상인 직책만 나타내며, 급여 총합에 대한 내림차순으로 정렬하시오
```
select title, sum(salary) from s_emp--1. 급여의 총합 - (sum(salary))

where title <> '사원' -- 부장인 사람은 제외

group by title--2. 직책별로 - (title)

having sum(salary) >= 3000--3. 급여 총합이 3000만원 이상

order by 2 desc;--4. 오름차순

```



#### Q3. 직책(s_emp.title)이 '부장(영업부장, 지부장 포함)'인 사람이 2명 이하인 부서(s_emp.dept_id)가 몇개인지 나타내시오.
```
select dept_id 부서, count(*) 인원 from s_emp--1. 몇명있는지 출력

where title like '%부장'

group by dept_id--3. 부서별로 그룹화
;
```



#### Q4.  담당 직원이 배정되지 않은 고객을 찾는 경우
```
SELECT e.name 사원명, e.id, c.name 고객명 

FROM s_emp e, s_customer c

--WHERE e.id (+) = c.sales_rep_id  -- LEFT OUTER JOIN
WHERE e.id = c.sales_rep_id (+) -- RIGHT OUTER JOIN

ORDER BY 2;
```


#### Q5. PK와 FK 설명

> PK 

- 인덱스 자동생성
- 트리구조
- 중복 x, 색인 빠름 
- NULL x
- 테이블, 컬럼 단계에서 가능

> FK

- 부모 테이블 값과 일치하거나 NULL이어야함
- 부모 테이블 먼저 생성
- ON DELETE CASCADE 덧글도 삭제

#### Q6. 제약조건 종류

> NN, UNIQUE, PK, FK, CHECK

#### Q7.자동으로 고유한 숫자값을 생성해 주며 주로 기본키 값을 생성하기 위해 사용하는 object는 ?

> 시퀀스

#### Q8. 직원(S_EMP) 테이블에서 연봉순으로 정렬하여 3개의 데이터만 나타내시오.

```
select name 연봉킹이름, salary 연봉

from (
	select name, salary from s_emp 
	order by 2 desc	) -- 정렬먼저

where rownum < 4;
```

#### Q9. 인덱스 언제 쓰는지


#### Q10.아래의 sql문은 비효율적이다. (title에 인덱스가 작성되어 있다고 가정)
이 문장을 not exists를 사용해서 효율적으로 작성하시오.

```
select * from s_emp where title <> '사원';
```

```
select * from s_emp where not exists (select * from s_emp where title='사원');
```

#### Q1. 각 부서별(dept_id)로 평균 급여(avg(salary))를 구하되 평균 급여가 2000 이상(avg(salary)>=2000)인 부서만 나타내시오
```
select dept_id 부서이름, avg(salary) 평균급여

from s_emp

group by dept_id

having avg(salary) >= 2000 
-- 그룹함수 조건은 where 절이 아닌 having에 넣는다
;
```

#### Q2. 각 직책별(title)로 급여의 총합(sum(salary))을 구하되 직책이 사원인 사람은 제외하시오, 단, 급여 총합이 3000만원 이상인 직책만 나타내며, 급여 총합에 대한 내림차순으로 정렬하시오
```
select title, sum(salary) from s_emp--1. 급여의 총합 - (sum(salary))

where title <> '사원' -- 부장인 사람은 제외

group by title--2. 직책별로 - (title)

having sum(salary) >= 3000--3. 급여 총합이 3000만원 이상

order by 2 desc;--4. 오름차순

```



#### Q3. 직책(s_emp.title)이 '부장(영업부장, 지부장 포함)'인 사람이 2명 이하인 부서(s_emp.dept_id)가 몇개인지 나타내시오.
```
select dept_id 부서, count(*) 인원 from s_emp--1. 몇명있는지 출력

where title like '%부장'

group by dept_id--3. 부서별로 그룹화
;
```



#### Q4.  담당 직원이 배정되지 않은 고객을 찾는 경우
```
SELECT e.name 사원명, e.id, c.name 고객명 

FROM s_emp e, s_customer c

--WHERE e.id (+) = c.sales_rep_id  -- LEFT OUTER JOIN
WHERE e.id = c.sales_rep_id (+) -- RIGHT OUTER JOIN

ORDER BY 2;
```


#### Q5. PK와 FK 설명

> PK 

- 인덱스 자동생성
- 트리구조
- 중복 x, 색인 빠름 
- NULL x
- 테이블, 컬럼 단계에서 가능

> FK

- 부모 테이블 값과 일치하거나 NULL이어야함
- 부모 테이블 먼저 생성
- ON DELETE CASCADE 덧글도 삭제

#### Q6. 제약조건 종류

> NN, UNIQUE, PK, FK, CHECK

#### Q7.자동으로 고유한 숫자값을 생성해 주며 주로 기본키 값을 생성하기 위해 사용하는 object는 ?

> 시퀀스

#### Q8. 직원(S_EMP) 테이블에서 연봉순으로 정렬하여 3개의 데이터만 나타내시오.

```
select name 연봉킹이름, salary 연봉

from (
	select name, salary from s_emp 
	order by 2 desc	) -- 정렬먼저

where rownum < 4;
```

#### Q9. 인덱스 언제 쓰는지


#### Q10.아래의 sql문은 비효율적이다. (title에 인덱스가 작성되어 있다고 가정)
이 문장을 not exists를 사용해서 효율적으로 작성하시오.

```
select * from s_emp where title <> '사원';
```

```
select * from s_emp where not exists (select * from s_emp where title='사원');
```


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAwNjk5MzUzMCwxNjg3NjQxNjcxLC0yMD
g4NzQ2NjEyLC03MjExMDQyNl19
-->