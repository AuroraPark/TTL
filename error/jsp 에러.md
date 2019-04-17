```java.lang.ClassNotFoundException```



[1. The server time zone value ‘KST’ is unrecognized or represents more than one time zone : mysql-connector-java 버전 5.1.X 이후 버전부터 KST 타임존을 인식하지 못하는 이슈](https://yenaworldblog.wordpress.com/2018/01/24/java-mysql-%EC%97%B0%EB%8F%99%EC%8B%9C-%EB%B0%9C%EC%83%9D%ED%95%98%EB%8A%94-%EC%97%90%EB%9F%AC-%EB%AA%A8%EC%9D%8C/)


```
Loading class `com.mysql.jdbc.Driver'. This is deprecated. The new driver class is `com.mysql.cj.jdbc.Driver'. The driver is automatically registered via the SPI and manual loading of the driver class is generally unnecessary.
```


[[오류] import javax.servlet.http.* The import javax.servlet.http cannot be resolved](https://nyhooni.tistory.com/70)

[Editor Tools/Eclipse](https://nyhooni.tistory.com/category/Editor%20Tools/Eclipse) 

이클립스에서 새로운 프로젝트를 만들고 첫 로그인 서블릿을 야심차게 만들었으나,,,, 오류!!  

아래 소스는 "뇌를 자극하는 JSP & Servlet"에서 나온 소스다.  

그런데 import javax.servlet.http.* 오류.. 이건 뭘까???  

검색해서 보니 이클립스내에서 path를 다시 잡아 줘야 한다고 하는데.. 암튼 오류는 해결!!

하지만 전 프로젝트 생성후에는 없었던 에러라.. 난감했다!!

  
  [해결]  

이클립스 -> 왼쪽 프로젝트 명 마우스 오른쪽 클릭 -> Build Path -> Configure Build Path..

-> 새창에서 왼쪽 Java Build Path 선택 확인 -> 중앙 Libraries 탭 -> ADD External JARs.. 에서

톰캣(tocat) - lib 폴더에 jsp-api.jar / servlet-api.jar를 선택하면 끝!!!!  


출처: [https://nyhooni.tistory.com/70](https://nyhooni.tistory.com/70) [NewYorker IT Report]  

```
INFO : org.springframework.context.annotation.ClassPathBeanDefinitionScanner - JSR-330 'javax.inject.Named' annotation found and supported for component scanning
```
이게멀까

web.xml 오류라고하는디 
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzc4OTI1NjIzLC0xNDU4NTYyNzkxLDI5MD
IzODU4NywtMTIyODM5NzEyNyw4MDgxMzQzODEsLTEwNzQ3Nzc0
MjRdfQ==
-->