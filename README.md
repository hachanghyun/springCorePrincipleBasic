# springCorePrincipleBasic 

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
    cmd + option + M
    
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

#### 내가 정리하기
	Bean으로 스프링컨테이너에서 관리되고 return 된 객체로 관리함

#### 스프링 컨테이너
	요즘은 XML 방식보다 애노테이션 기반의 자바설정클래스로 만들어서 사용하는게 추세
	jUnit5 부터는 테스트코드메소드에 public 안붙여줘도됨

#### 리스트있을시 단축키
	iter쳐주면 for문이 자동완성됨

#### 기타 명령어
	soutv 변수명 찍어주는 print문
 	cmd + E => enter 예전에 작업했던 파일 불러오기
  	option + enter => static import 하기

#### ApplicationContext 정리
	ApplicationContext는 BeanFactory의 기능을 상속받는다.
	ApplicationContext는 빈 관리기능 + 편리한 부가 기능을 제공한다.
	BeanFactory를 직접 사용할 일은 거의 없다. 부가기능이 포함된 ApplicationContext를 사용한다. BeanFactory나 ApplicationContext를 스프링 컨테이너라 한다.

#### 싱글톤 정리
	memberService = hello.core.member.MemberServiceImpl@65e98b1c
	memberService2 = hello.core.member.MemberServiceImpl@61322f9d
 	@뒤의 값은 객체주소값?

#### 생성자에 붙여주기
	@Autowired
	@Autowired //ac.gettBean(MemberRepository.class);

#### 컴포넌트 스캔 기본 대상
	컴포넌트 스캔은 `@Component` 뿐만 아니라 다음과 내용도 추가로 대상에 포함한다. `@Component` : 컴포넌트 스캔에서 사용
	`@Controller` : 스프링 MVC 컨트롤러에서 사용
	`@Service` : 스프링 비즈니스 로직에서 사용
	`@Repository` : 스프링 데이터 접근 계층에서 사용 `@Configuration` : 스프링 설정 정보에서 사용

#### 다양한 의존관계 주입 방법
	생성자 주입
 	수정자 주입(setter 주입)
  	필드 주입
   	일반 메서드 주입
