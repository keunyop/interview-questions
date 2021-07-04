# Interview Questions
인터뷰 문제 


# 공통 
- 본인의 직무를 정의한다면?
- 본인의 직무는 누구에게 어떠한 가치를 제공하는가?
- 자신의 강점은 무엇이고, 단점을 보완하기 위해 어떠한 노력을 하고 있나?
- 함께 일했던 동료들에게 당신이 어떠한 사람인지 묻는다면 어떻게 답할 것 같나?
- OO 부서의 이직률이 매우 높은 편인데, 조직장으로서 이직률을 낮출 방법을 찾아야 한다면 어떤 것부터 시작하겠나?
- 동료와 관계에서 가장 큰 실패는 무엇이었나? 당신의 책임이 있었나?


# 백엔드
 - process와 thread의 차이점?
> **process**
> - 리눅스 등의 멀티 프로세싱 OS에서 동시에 실행 중인 프로그램에 대한 인스턴스
> - 같은 프로그램을 여러 개 띄웠다고 해서 하나의 프로세스를 공유하는 것은 아님
> - 프로세스는 각각의 주소 공간, 파일, 메모리 등을 할당받음

> **thread**
> - 한 프로세스 내에서 동작하는 여러 실행의 흐름
> - 프로세스 내의 주소 공간이나 자원들을 공유
> - 하나의 프로세스는 여러개의 스레드를 가질 수 있다(멀티 스레드)
> - 멀티 스레드로 구현할 경우 메모리 등 시스템 자원 소모를 현격히 줄일 수 있다.
> - 스레드 간의 통신은 전역 변수를 이용하여 데이터를 주고 받을 수 있다.
> - 멀티 스레드 구현시 동기화 문제를 해결해야 함

> **멀티 스레드 장점**
>  - 시스템의 throughput 향상
>  - 시스템의 자원 소모 줄어듬
>  - 프로그램의 응담 시간 단축
>  - 스레드 간의 통신 방법이 훨씬 간단

> **멀티 스레드 단점**
>  - 주의 깊은 설계 필요
>  - 시간 차나 잘못된 변수 공유로 오류 발생 가능
>  - 디버깅이 어려움


- gradle과 maven의 차이점은 무엇인가?
> **Maven**
>  - 2004년 출시
>  - Ant를 사용하던 개발자들의 불편함을 해소 + 부가기능 추가
>  - 빌드를 쉽게 해줌
>  - pom.xml을 사용

> **Gradle**
>  - 2012년 출시
>  - Ant와 Maven의 장점을 모음
>  - Ant처럼 유연한 범용 빌드 도구
>  - 멀티 프로젝트에 사용하기 좋음
>  - Apache Ivy에 기반한 강력한 의존성 관리
>  - 그루비 문법 사용

> **Maven VS Gradle**
> - Maven은 build를 xml로 정의하기때문에 설정 내용이 길어지고 가독성이 떨어짐. 의존관계가 복잡한 프로젝트에선 설정하기 부적절.
> - Gradle은 Groovy를 사용하기 때문에, 동적인 빌드는 Groovy 스크립트로 플러그인을 호출하거나 직접 코드를 작성
> - Gradle이 Maven 보다 최대 100배 빠르다.


- **Elasticsearch 와 GraphQL에 대해 설명해보라.**
> **Elasticsearch**
> - Elasticsearch is a search server based on Lucene that provides a distributed, multitenant-capable full-text search engine.
> - Hosted Search

> **GraphQL**
> - GraphQL is a data query language and runtime to request and deliver data to mobile and web apps.
> - Database Tool


- **절차지향과 객체지향 개발의 차이점을 설명해보라.**
> **절차지향 프로그래밍**
> - 물이 위에서 아래로 흐르는 것처럼 순차적인 처리가 중요시 되며 프로그램 전체가 유기적으로 연결되도록 만드는 프로그래밍 기법
> - 컴퓨터의 작업 처리 방식과 유사하기 때문에 객체지향 언어를 사용하는 것에 비해 더 빨리 처리되어 시간적으로 유리

> **객체지향 프로그래밍**
> - 개발하려는 것을 기능별로 묶어 모듈화를 함으로써 하드웨어가 같은 기능을 중복으로 연산하지 않도록 하고,
> - 모듈을 재활용하기 때문에 하드웨어의 처리량을 획기적으로 줄여줌
> - 실제 세계를 모델링하여 소프트웨어를 개발하는 방법
> - 데이터와 절차를 하나의 덩어리로 묶어서 생각함
> - 3대 특성: 캡슐화, 상속, 다형성
> - 장점
>> - 신뢰성 있는 소프트웨어를 쉽게 작성할 수 있다.
>> - 코드를 재상용하기 쉽다.
>> - 업그레이드가 쉽다.
>> - 디버깅이 쉽다.

- **Spring inercepter와 filter의 순서와 차이점은?**
> **Intercepter vs. Filter**
> - 실행되는 시점이 다르다.
> - Filter는 Web Application에 등록하고, intercepter는 Spring context에 등록한다.
> - 둘다 요청에 대한 전후 처리 역할을 수행한다.
> - 가장 큰 차이점은 예외 처리.

> **Intercepter**
> - Handler를 실행하기전(preHandle), Handler를 실행한 후(postHandle), view를 렌더링한 후(afterCompletion) 등, Servlet내에서도 메서드에 따라 실행 시점을 다르게 가져간다.
```
public interface HandlerInterceptor {
  boolean preHandle(HttpServletRequest request, HttpServletResponse response, Object handler);
  void postHandle(HttpServletRequest request, HttpServletResponse response, Object handler, ModelAndView mav);
  void afterCompletion(HttpServletRequest request, HttpServeletResponse response, Object handler, Exception ex);
}
```

> **Filter**
> - Tomcat에선 deployment descriptor(web.xml)에 filter 
> - Servlet에서 처리하기 전후를 다룰 수 있다.
```
public interface Filter {
  void doFilter(ServletRequest request, ServletResponse response, FilterChain chain);
}
```

- **String Literal**
```java
String a = new String("abc");
```
> Heap 내의 일반 객체를 생성하고, 그 객체의 Reference 를 가지게 된다.
```java
String b = "abc";
```
> - Heap 내의 **String constant pool** 에 저장
> - 이미 존재하는 문자열이라면 해당 인스턴스를 여러 Reference 가 참조
> - 특별한 이유가 없다면 String 문자열을 사용하는 것이 읽기 쉽고 컴파일러가 코드를 최적화할 수 있는 기회를 제공


- **Java Annotation 생성 방법**
> 어노테이션은 소스 코드에 메타데이터를 표현
> 단순 부가정보 뿐만 아니라, 리플렉션을 사용하여 원하는 클래스 주입이 가능

> interface 아페 @를 붙이면 간간한 annotation을 만들 수 있다.
```java
public @interface TestAnno {
    String value();
}
```


- ArrayList VS LinkedList
- Quick Sort
- Iterator 를 쓰지 않고 직접 참조 시의 문제점
- 동적 스키마 설계시 고민할 점은 무엇일까?
- transaction isolation level의 종류 및 특징은 무엇인가?
- JTA란 무엇인가?
- CDN과 AWS cloudfront의 차이점과 사용 이유를 설명해보라.
- Static function의 특징은?
- MD5, AES256, SHA256의 차이점과 각 암호화 방식에 대해 설명해보라.
- Fault-tolerant(무정지) 시스템으로 가기 위해 필요한 개발 방법에 대한 생각을 말해보라.

# 프론트엔드
- api broken pipe 발생 원인과 해결 방법은 무엇인가?
