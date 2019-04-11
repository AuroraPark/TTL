1. org.springframework.test.context.TestContextManager - Caught exception while allowing TestExecutionListener 

 2. org.springframework.web.servlet.PageNotFound - No mapping found for HTTP request with URI
 [참고 블로그](https://stufeel.tistory.com/8)


3. WARN : org.springframework.web.servlet.PageNotFound - No mapping found for HTTP request with URI [/board/list] in DispatcherServlet with name ''

> 해결책 : selvlet-context.xml 경로 확인
-> 	
	<context:component-scan base-package="org.zerock.controller" />
	
>	주소 두번확인!!!!!!!!!


4. text area 공백 에러 !!
[참고블로그](https://okky.kr/article/292680)




javax.el.PropertyNotFoundException: Property [type] not found on type [org.zerock.domain.Criteria]] 



### [  
테쿠의 개발 일기장](https://teqoo.tistory.com/)

## [Failed to load resource: net::ERR_INCOMPLETE_CHUNKED_ENCODING]

태그 안이 비었는지 확인




Error configuring application listener of class [org.springframework.web.context.ContextLoaderListener]

>[http://myblog.opendocs.co.kr/archives/1657](http://myblog.opendocs.co.kr/archives/1657)




cookie config 오류
> servlet 버전이 다름

org.springframework.web.util.NestedServletException: Request processing failed; nested exception is java.lang.NullPointerException
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzI5NDE4MjI5LC00NTczOTcxNDQsODU4OT
M4ODAzLC0xODA3MzY3MDMwLC0yMDI0MTI0NzczLC0xMDkwMjg2
MDc2LDEwOTA0ODQ1MzcsLTE2NDA1NTA4MjEsLTI3ODQ4NTE2OF
19
-->