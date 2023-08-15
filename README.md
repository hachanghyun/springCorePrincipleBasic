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
    Deprecated Gradle features were used in this build, making it incompatible with Gradle 9.0. You can use '--warning-mode all' to show the individual deprecation warnings and determine if they come from your own scripts or plugins.









