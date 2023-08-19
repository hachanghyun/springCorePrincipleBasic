# springCorePrincipleBasic


#### 나중에 java17로 변경할날이 오면 이것 사용
https://stackoverflow.com/questions/71059252/mac-the-operation-couldn-t-be-completed-unable-to-locate-a-java-runtime-that-su
 

#### 실습 환경 start.spring.io
    Project : Gradle 
    Language : Java
    springBoot ver : 2.7.14
    Group : hello
    Artifact : core
    Name : core
    Packaging : jar
    Java -version : openjdk version "11.0.20" 2023-07-18
    Dependencies : x

#### intellij java 버전 변경
    File => Project Structure

#### preference 들어가서 gradle 입력
    Build Tool : gradle => Intellij 
    
#### Gradle 오류 
    Deprecated Gradle features were used in this build, making it incompatible with Gradle 9.0. 
    You can use '--warning-mode all' to show the individual deprecation warnings and determine 
    if they come from your own scripts or plugins.

    File > Invalidate Caches 에 들어가서 
    'Invalidate and Restart' 로 해결

#### intellij 단축키
    한줄복사 cmd + D
    한줄이동 shift + option + 상하방향키
    패키지 및 파일 추가 cmd + N
    생성자 추가 cmd + N
    cmd + o 전체찾기
    
#### intellij 단축키 찾는법
    preference => keymap 들어가서 검색해서 단축키 찾으면 됨

#### package Tree 구조 변경
    project 상단 톱니바퀴모양 => Tree appearance

#### intellij 세미콜론 자동완성 단축키
    cmd + shift + enter

#### 프로젝트 tab 이동
    cmd + 상 방향키

#### 코드 tab 이동 
    cmd + 하 뱡향키

#### 빨간줄 뜨면 option + enter

#### 파일 처음, 끝 (windows home, end 버튼)
    fn + 위아래 방향키

#### 전체파일 검색 
    cmd + shift + F

#### 이전 탭으로 이동 
    ⌘ + ⇧ + [	
	
#### 다음 탭으로 이동
    ⌘ + ⇧ + ]

#### service 와 serviceimpl 패턴 설계 이유
    이론상으로 위와 같은 Service, ServiceImpl 패턴으로 설계를 해야하는 이유는 인터페이스와 구현체를 분리함으로써 구현체를 
    독립적으로 확장할 수 있으며, 구현체 클래스를 변경하거나 확장해도 이를 사용하는 클라이언트의 코드에 영향을 주지 않도록 하기 위함입니다.
    이 같은 추상화를 통한 구현 방식은 객체지향의 특징 중 하나인 다형성과 객체지향의 다섯 가지 원칙 중 하나인 OCP 원칙을 가장 
    잘 실현해주는 설계 방식이라고 할 수 있습니다.
    결론적으로 Implements 클래스를 유연하게 변경하기 위해서라고 볼수 있다.
    
<img width="966" alt="스크린샷 2023-08-15 오후 9 11 04" src="https://github.com/hachanghyun/springCorePrincipleBasic/assets/33058284/9701aa22-e107-4fa9-954b-5c08d6342f45">

#### system.out.println 
	soutv

#### 프로젝트 재시작 단축키
	control + shift + R


<img width="937" alt="스크린샷 2023-08-16 오후 4 46 28" src="https://github.com/hachanghyun/springCorePrincipleBasic/assets/33058284/162c9d06-9c34-47d8-b8aa-008115e2ddb3">

#### 앞에 return 값 담아주는 변수, 객체 자동생성해주는 단축키 (문장끝에서 쓰면 자동생성)
	option + cmd + v


#### 메소드 testcase 생성 단축키
	cmd + shift + T

 #### assertions 비교
 	option + enter 치면 간결해짐

  #### 과거 작업 이력 파일 조회 단축키
  	cmd + E

   #### 중요 DIP 완성
	AppConfig는 애플리케이션의 실제 동작에 필요한 **구현 객체를 생성**한다. 
	`MemberServiceImpl`
	`MemoryMemberRepository` 
	`OrderServiceImpl` 
	`FixDiscountPolicy`
	AppConfig는 생성한 객체 인스턴스의 참조(레퍼런스)를 **생성자를 통해서 주입(연결)**해준다. `MemberServiceImpl` `MemoryMemberRepository`
	`OrderServiceImpl` `MemoryMemberRepository` , `FixDiscountPolicy`

#### 의존관계 주입 의존성 주입(DI)
	OrderServiceImpl은 기능을 실행하는 역할만 가지여함!!!!
 
#### cmd + option + M
 
#### 책임의 분리 Appconfig

#### 좋은 객체 지향 설계의 5가지 원칙 

##### 1. SRP 단일 책임 원칙 
	한 클래스는 하나의 책임만 가져야한다. 
 
 ###### 2. DIP 의존관계 역전 원칙 
 	추상화에 의존, 구체화에 의존(x)
  
##### 3. OCP 소프트웨어 요소는 확장에는 열려있으니 변경에는 닫혀있어야 한다
	애플리케이션을 사용영역과 구성영역으로 나눔 
 	소프트웨어 요소를 새롭게 확장해도 사용 영역의 변경은 닫혀있다. -> 클라이언트 소스를 변경할 필요가 없음
  	외부에서 의존관계만 주입하면 끝남. 사용영역은 변경할 필요가없음.

#### 스프링관련 용어 설명 
	Inversion of Control (제어의 역전) IOC
   
  프레임워크(junit) vs 라이브러리 

#### 의존관계주입 (DI)
정적인 클래스 의존관계 , 실행 시점에 결정되는 동적인 객체 (인스턴스) 의존관계 둘을 분리해서 생각해야한다.

IOC컨테이너, DI컨테이너로 변경


#### 스프링으로 전환해보자!!!

ApplicationContext 얘가 스프링컨테이너인데 @Bean 같이 모든객체들을 다관리해줌 

MemberService memberService = applicationContext.getBean("memberService" 이객체를 찾을거야 , MemberService.class : 반환타입);

22:30:06.735 [main] DEBUG org.springframework.beans.factory.support.DefaultListableBeanFactory - Creating shared instance of singleton bean 'appConfig'
22:30:06.738 [main] DEBUG org.springframework.beans.factory.support.DefaultListableBeanFactory - Creating shared instance of singleton bean 'memberService'
22:30:06.744 [main] DEBUG org.springframework.beans.factory.support.DefaultListableBeanFactory - Creating shared instance of singleton bean 'memberRepository'
22:30:06.745 [main] DEBUG org.springframework.beans.factory.support.DefaultListableBeanFactory - Creating shared instance of singleton bean 'orderService'
22:30:06.745 [main] DEBUG org.springframework.beans.factory.support.DefaultListableBeanFactory - Creating shared instance of singleton bean 'discountPolicy'

스프링컨테이너가 객체를 생성해줬음 . 저이름으로 빼서 사용해주면됨!!!!

`ApplicationContext` 를 스프링 컨테이너라 한다.
기존에는 개발자가 `AppConfig` 를 사용해서 직접 객체를 생성하고 DI를 했지만, 이제부터는 스프링 컨테이너를 통해서 사용한다.
스프링 컨테이너는 `@Configuration` 이 붙은 `AppConfig` 를 설정(구성) 정보로 사용한다. 여기서 `@Bean` 이 라 적힌 메서드를 모두 호출해서 반환된 객체를 스프링 컨테이너에 등록한다. 이렇게 스프링 컨테이너에 등록된 객체를 스프링 빈이라 한다.

#### 내가 정리하기
Bean으로 스프링컨테이너에서 관리되고 return 된 객체로 관리함


스프링 빈은 `@Bean` 이 붙은 메서드의 명을 스프링 빈의 이름으로 사용한다. ( `memberService` ,
       
 `orderService` )
이전에는 개발자가 필요한 객체를 `AppConfig` 를 사용해서 직접 조회했지만, 이제부터는 스프링 컨테이너를 통 해서 필요한 스프링 빈(객체)를 찾아야 한다. 스프링 빈은 `applicationContext.getBean()` 메서드를 사용 해서 찾을 수 있다.
기존에는 개발자가 직접 자바코드로 모든 것을 했다면 이제부터는 스프링 컨테이너에 객체를 스프링 빈으로 등록 하고, 스프링 컨테이너에서 스프링 빈을 찾아서 사용하도록 변경되었다.


스프링컨테이너를 사용했을때 이점이 뭘까?????? 
왜 여기에서 bean으로 관리할까????

스프링컨테이너가 주는 이점은 다음시간에 계쏙...

#### 스프링 컨테이너

요즘은 XML 방식보다 애노테이션 기반의 자바설정클래스로 만들어서 사용하는게 추세

ApplicationContext` 를 스프링 컨테이너라 한다.
`ApplicationContext` 는 인터페이스이다.
스프링 컨테이너는 XML을 기반으로 만들 수 있고, 애노테이션 기반의 자바 설정 클래스로 만들 수 있다. 직전에 `AppConfig` 를 사용했던 방식이 애노테이션 기반의 자바 설정 클래스로 스프링 컨테이너를 만든 것이 다.
자바 설정 클래스를 기반으로 스프링 컨테이너( `ApplicationContext` )를 만들어보자.
`new AnnotationConfigApplicationContext(AppConfig.class);` 이 클래스는 `ApplicationContext` 인터페이스의 구현체이다.
참고: 더 정확히는 스프링 컨테이너를 부를 때 `BeanFactory` , `ApplicationContext` 로 구분해서 이야기 한다. 이 부분은 뒤에서 설명하겠다. `BeanFactory` 를 직접 사용하는 경우는 거의 없으므로 일반적으로
`ApplicationContext` 를 스프링 컨테이너라 한다.

jUnit5 부터는 테스트코드메소드에 public 안붙여줘도됨

#### 리스트있을시 단축키
	iter쳐주면 for문이 자동완성됨

 #### soutv 변수명 찍어주는 print문
 
#### cmd + E => enter 예전에 작업했던 파일 불러오기
#### option + enter => static import 하기

 **정리**
ApplicationContext는 BeanFactory의 기능을 상속받는다.
ApplicationContext는 빈 관리기능 + 편리한 부가 기능을 제공한다.
BeanFactory를 직접 사용할 일은 거의 없다. 부가기능이 포함된 ApplicationContext를 사용한다. BeanFactory나 ApplicationContext를 스프링 컨테이너라 한다.

