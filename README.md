# springCorePrincipleBasic

#### MAC JAVA 11 version 설치 (처음에 java17 버젼설치되있어서 버전변경하다 생쇼하다가 이거 하나로 해결!!!)
    brew install openjdk@11
    sudo ln-sfn $(brew --prefix)/opt/openjdk@11/libexec/openjdk.jdk

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




