
1.

오류 :

> org.springframework.test.context.TestContextManager - Caught exception while allowing TestExecutionListener

  

해결법 (참고블로그주소) :

  
  

2.

오류 :

> org.springframework.web.servlet.PageNotFound - No mapping found for HTTP request with URI

  
  

해결법 :

> [참고 블로그]([https://stufeel.tistory.com/8](https://stufeel.tistory.com/8))

  
  

3.

  

오류 :

> WARN : org.springframework.web.servlet.PageNotFound - No mapping found for HTTP request with URI [/board/list] in DispatcherServlet with name ''

  

해결법 (참고블로그주소) :

> selvlet-context.xml 경로 확인

> <context:component-scan base-package="org.zerock.controller" />

>  주소 두번확인!!!!!!!!!

  
  

4.

오류 :

> text area 공백 에러 !!

  

해결법 :

> [참고블로그]([https://okky.kr/article/292680](https://okky.kr/article/292680))

  
  
  
  

5.

오류 :

> javax.el.PropertyNotFoundException: Property [type] not found on type [org.zerock.domain.Criteria]]

  

해결법 :

> [참고블로그]([https://teqoo.tistory.com/](https://teqoo.tistory.com/))

  

6.

오류 :

> [Failed to load resource: net::ERR_INCOMPLETE_CHUNKED_ENCODING]

  

해결법 :

> 태그 안이 비었는지 확인

  

7.

오류 :

> Error configuring application listener of class [org.springframework.web.context.ContextLoaderListener]

  

해결법 :

> [참고 블로그]([http://myblog.opendocs.co.kr/archives/1657](http://myblog.opendocs.co.kr/archives/1657))

  

8.

오류 :

> cookie config 오류

  

해결법 :

> web.xml의 servlet-api 버전을 3.1.0 이상으로 고쳐줘야함

  

9.

오류 :

> org.springframework.web.util.NestedServletException: Request processing failed; nested exception is java.lang.NullPointerException

  

해결법 :





  

10.

오류 :

> net.sf.log4jdbc.sql.jdbcapi.ConnectionSpy.getNetworkTimeout()I)

  

해결법 :

> 9/10 둘이 같은문제인듯 pom.xml 수정해야함(새로 복붙ㅎ)

  

11.

오류 :

> Cannot change version of project facet Dynamic Web Module to 2.5.

  

해결법 :

> [참고 블로그](https://lng1982.tistory.com/199)

  
  
  

12.

오류 :

> 에러는 아니고 log4j 노란줄 뜨는거

Q:\Document.Project\workspace\document-project\src\main\java\log4j.dtd (지정된 파일을 찾을 수 없습니다)" that is specified as

  

해결법 :

> [(https://hermeslog.tistory.com/261)](https://hermeslog.tistory.com/261))

  
  

13.

오류 :

> Classpath entry 어쩌구 하는 워닝

  

해결법 :

> ([https://pcandme.tistory.com/50](https://pcandme.tistory.com/50))

  

14.

오류 :

> nested PropertyAccessExceptions (1) are:

  

해결법(참고 주소) :

> 폼이 잘못됨 다시 잘봐보기

  

x

  
  

15.

오류 :

415 Unsupported Media Type (Restlet Client 테스트 결과) (코드로 배우는 스프링 p.395)

해결법 :

데이터를 json 형식으로 바꾸는 라이브러리가 설정파일(pom.xml)에서 빠져서 생긴 문제.

<jackson> library 를 추가하자(코드로 배우는 스프링 p.357 참고)
<!--stackedit_data:
eyJoaXN0b3J5IjpbNDg3MjE2NjEyLC0xMzEzNzQ3NjY4LC0zNj
M4NTU0MTcsLTgwODkwODEyNSw5NDY4NjA1MjIsLTE1MTIyMjUx
MzUsLTE3NDk2NDQ1MywtMzg2NTQ1MzYzLC02ODU4ODA3MTUsMT
M1ODg1MTMzMCwtMTgzOTM4MjI1MSwtNDU3Mzk3MTQ0LDg1ODkz
ODgwMywtMTgwNzM2NzAzMCwtMjAyNDEyNDc3MywtMTA5MDI4Nj
A3NiwxMDkwNDg0NTM3LC0xNjQwNTUwODIxLC0yNzg0ODUxNjhd
fQ==
-->