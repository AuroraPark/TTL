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




5. javax.el.PropertyNotFoundException: Property [type] not found on type [org.zerock.domain.Criteria]] 
[참고블로그](https://teqoo.tistory.com/)

6.  [Failed to load resource: net::ERR_INCOMPLETE_CHUNKED_ENCODING]

> 태그 안이 비었는지 확인

7. Error configuring application listener of class [org.springframework.web.context.ContextLoaderListener]
[참고 블로그](http://myblog.opendocs.co.kr/archives/1657)

8. cookie config 오류
> web.xml의 servlet-api 버전을 3.1.0 이상으로 고쳐줘야함

org.springframework.web.util.NestedServletException: Request processing failed; nested exception is java.lang.NullPointerException
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyOTk1NDU0MzAsLTQ1NzM5NzE0NCw4NT
g5Mzg4MDMsLTE4MDczNjcwMzAsLTIwMjQxMjQ3NzMsLTEwOTAy
ODYwNzYsMTA5MDQ4NDUzNywtMTY0MDU1MDgyMSwtMjc4NDg1MT
Y4XX0=
-->