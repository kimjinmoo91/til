  # - **WIL** (Weekly I Learn) 2주차 **회고** -

## "OOP" 객체지향 프로그래밍?  
<br>
  
> 객체지향 프로그래밍(Object-Oriented Programming)=OOP
> >프로그램을 설계하는 개념이자, 방법론이며, 단어의 뜻 그대로 프로그램(실세계)를 객체(사물)라는 기본 단위로<br>
   나누고 이 객체들간의 상호작용을 기본 개념으로 한다.  
   <br>  
     
   <br>  
   
   <br>  

   ### **객체지향의 4 특징**  
   1.  **추상화(Abstraction)**   -abstract, interface-  
     - 목적과 관련이 없는 것을 제거하고 필수적인 요소만을 표현해 둔 것으로 <br>  
     용도에 맞는 필수적인 요소들을 강제적으로 포함시키기 위함이다.<br>  
     <br>  

   2. **캡슐화(Encapsulation)**  -public, private, protected-  
      - 연관있는 변수와 메소드를 묶어주는 것을 말하고, 접근제어자를 통해 외부로부터의 접근을 제한하여 객체 내에서만<br>  접근이 가능하도록 해주며, 정보은닉이라고도 한다.<br>  
      외부의 클래스 혹은 모듈에 의존적인 프로그램의 경우 변경이나 오류에 취약해 정보은닉을 통해서<br>  
      결합도를 낮추며 응집도를 높여준다.
   3. **상속(Inheritance)**  
      - 상속을 통해 부모클래스의 속성과 기능을 상속받아 사용하는 것을 말한다. <br>  
      중복되는 속성과 기능이 발생되는데 상속을 통해 중복되는 기능의 반복을 줄일 수 있다.  
      - 자식은 부모의 클래스로 상속받는다.  
      - 다형을 통해 변경이 필요한 부분을 변경하여 사용할 수 있다.
   4. **다형성(Polymorphism)**   -Overriding, Overloading-
      - 부모, 자식 상속 관계에 있는 클래스에서 상위 클래스가 동일한 메시지로 <br>  
        하위 클래스들을 서로 다르게 동작시키는 객체 지향 원리.  
        - Overriding :  
         부모클래스를 상속받은 자식 클래스에서 부모 클래스의(추상) 메소드를 같은 이름, 반환값, 인자로<br>  
          메소드 내의 로직들을 새롭게 정의함.<br>  
          즉, 부모 클래스를 상솓받는 자식클래스들이 같은 이름으로 다른 기능을 사용할 수 있는데, 입맛대로 재정의 함.  
        - Overloading :  
          하나의 클래스에서 같은 이름의 메서드들을 여러개 가질 수 있지만 메서드 인자들은 달라야 함(반환값은 제외).<br>  
          인자들의 타입이나 개수가 다르면 메서드 이름이 같더라도 어떤 메서드를 호출할지 컴파일러는 안다.<br>  
          같은 클래스 내에서 메서드명을 같게 해주는 이유는 따로 따로 만들면 효율성이 떨어지기 때문이다.  
<br>

<br>

<br>

<br>
  
<br>  

<br>  
  

  # **JVM?**
<br>  
 Java Virtual Machine 가상 머신의 약어.<br>  
 가상머신이란? 프로그램을 실행하기 위해 물리적 머신과 유사한 머신을 소프트웨어로 구현한 것.<br>  
 JVM 역할은 자바 애플리케이션을 클래스 로더를 통해 읽어 들여, 자바 API와 실행한다.<br>  
 또한 JAVA와 OS사이에서 중개자 역할로 재사용 가능하게 한다. 메모리 관리, Garbage collection을 수행한다.<br>  
 ARM 아키텍처같은 하드웨어는 레지스터 기반으로 동작하는데 비해 스택기반으로 동작하는 가상머신이다.<br>  

 <br>  
 
 <br>  

 <br>  

 ### **JVM을 왜..알야야 됨.? 필요한 것인가...입문자에겐 질문이다**  
 최고의 성능을 내되 한정된 메모리를 효율적으로 사용하기 위해서?... <br>  

 메모리 효율성을 위해 메모를 구조를 알아야 하기 때문이고,, 동일한 기능의 프로그램이어도 메모리 관리에 따라 <br>  
 성능은 달라지듯..! 메모리 관리가 되지 않은 경우 속도저하나, 튕김이 발생할 수 있다. 그래서 알아야 하는구나...!!!
 <br>  

 <br>  

 <br>  

 <br>  


### **JVM 구성**  
 <br>  

 1. Class Loader  
    - JVM내로 클래스(.class)를 로드하고, 링크를 통해 배치하는 모듈이다. Runtime시에 동적으로 클래스를 로드한다. <br>  
    jar 파일 내 저장된 클래스들을 JVM 위에 탑재하고 사용하지 않는 클래스들은 메모리에서 삭제한다. <br>  

    자바는 동적코드, 컴파일 타임이 아니라 Runtime에 참조한다. 즉, 클래스를 처음으로 참조할 때,  <br>  

    해당 클래스를 로드하고 링크하고, 그 역할을 클래스 로더가 수행한다. <br>  

     <br>  

 2. Execution Engine  
    - 클래스를 실행시키는 역할로 클래스 로더가 JVM내에 Runtime 데이터 영역에 바이트 코드를 배치시키고, <br>  

      실행엔진에 의해 실행된다. java 바이트코드는 기계가 바로 수행할 수 있는 언어보단 사람이 보기 편한 형태로 <br>  

      기술됬고, 실행엔진은 이와 같은 바이트코드를 실제 JVM내부에서 기계가 실행할 수 있는 형태로 변경한다. <br>  

      이 때 두가지 방법을 사용하게 된다. <br>  

       <br>  

 3. Interpreter  
    - 실행 엔진은 java 바이트코드를 명령어 단위로 읽어서 실행하고 이 방식은 인터프리터 언어의 단점을 그대로 갖고 있다. <br>  

    한 줄씩 수행하기 때문에 느리다. <br>  

     <br>  

 4. JIT  
    - 인터프리터의 단점을 보완하기 위해서 도임된 컴파일러 JIT. 인터프리터 방식으로 실행하닥 적절한 시점에 <br>  

      바이트코드 전체를 컴파일 해 네이티브 코드로 변경하고, 이후에 더 인터프리팅하지 않고, 직접 실행하는 방식이다. <br>  

      네이티브 코드는 캐시에 보관하기 때문에 컴파일 된 코드는 빠르게 수행한다. JIT컴파일러의 컴파일 과정은 <br>  

      바이트코드를 인터프리팅하는 것보다 오래걸리므로 한번만 실행되는 코드라면 컴파일하지 않고 인터프리팅 하는 것이 유리하다.<br>  

      JIT 컴파일러를 사용하는 JVM들은 내부적으로 해당하는 메서드의 빈도수 체크하고, 일정 정도를 넘을 때 컴파일 수행한다<br>  

<br>  

 5. Garbage collerctor  
    - GC를 수행하는 모듈(스레드)가 있다.   
  <br>  

 <br>  

 <br>  

 <br>  

 <br>  

 <br>  

  <br>  

 <br>  

 <br>  

 <br>  

 <br>  

 <br>  

  <br>  

 <br>  

 <br>  

 <br>  

 <br>  

 <br>  



- **WIL** (Weekly I Learn) 1주차 **회고** -  

# - **WIL** (Weekly I Learn) 회고 -  

 

## JWT / API 무엇일까?  
<br>

### -JWT-  
> - JWT :  
> > JWT(JSON Web Token)란 인증에 필요한 정보들을 암호화시킨 JSON 토큰을 의미한다.  
>그리고 JWT 기반 인증은 JWT 토근 (Access Token)을 HTTP 헤더에 실어 서버가 클라이언트를 식별하는 방식이다.  
>JWT는 JSON 데이터를 Base64 URL- safe Encode 를 통해 인코딩하여 직렬화한 것이며,  
토큰 내부에는 위변조 방지를 위해 개인키를 통한 전자서명도 들어있다.  
>따라서 사용자가 JWT를 서버로 전송하면 서버는 서명을 검증하는 과정을 거치게 되며 검증이 완료되면 요청한 응답을 돌려준다.

  <br> 

   1. #### 장점
   - 인증 정보에 대한 별도의 저장소가 필요하다.
   - 클라이언트 인증 정보를 저장하는 세션과 다르게, 서버는 무상태(StateLess)가 된다.
   - 확장성이 우수하다.
   - 토큰 기반으로 다른 로그인 시스템에 접근 및 권한 공유가 가능하다.
   - 모바일 어플리케이션 환경에서도 잘 동작한다, (모바일은 세션 사용 불가능)
   - OAuth의 경우 Facebook, Googe 등 소셜 계정을 이용하여 다른 웹서비스에서도 로그인을 할 수 있다.
   - JWR는 토큰에 대한 기본 정보와 전달할 정보 및 토큰이 검증 됬음을 증명하는 서명 등 필요한 모든 정보를 자체적으로 지니고 있다.
   - Header 와 Payload를 가지고 Signatur를 생성하므로 데이터 위변조를 막을 수 있다.  
<br>

<br>

<br>

<br>
  2. #### 단점
   - 토큰을 탈취당하면 대처하기 어렵다.
   - Payload 자체는 암호화되지 않기 때문에 유저의 중요한 정보는 담을 수 없다.
   - 쿠키 / 세션과 다르게 JWT는 토큰의 길이가 길어, 인증 요청이 많아질 수록 네트워크 부하가 심해진다.  
<br>

<br>

<br>

<br>
  
<br>  

### **JWT 요소**
<br>
<br>

  - **헤더(Header)**  
    

     JWT를 검증하는데 필요한 정보를 가진 JSON 객체는 Base64 URL-Safe 인코딩된 문자열이다. 헤더(Header)는 JWT를 어떻게 검증(Verify)하는가에 대한 내용을 담고 있다. 참고로 alg는 서명 시 사용하는 알고리즘이고, kid는 서명 시 사용하는 키(Public/Private Key)를 식별하는 값이다.  

     아래와 같이 JSON 객체를 문자열로 직렬화하고 UTF-8과 Base64 URL-Safe로 인코딩하면 다음과 같이 헤더를 생성할 수 있다.  
     <p align="center">
 <img src =  "https://user-images.githubusercontent.com/97110814/179412733-d01bf311-a4a4-4748-a82f-be3ee176c8bf.png">
</p>  
     <p align="center">
 <img src =  "https://user-images.githubusercontent.com/97110814/179413438-188f9fde-6958-4ab3-ab73-abef58bcc3f4.png">
</p>  
  
<br>
<br>

 - **페이로드(Paylord)**  
  
   JWT의 내용이다. 페이로드(Payload)에 있는 속성들을 클레임 셋(Claim Set)이라 부른다. 클레임 셋은 JWT에 대한 내용(토큰 생성자(클라이언트)의 정보, 생성 일시 등)이나 클라이언트와 서버 간 주고 받기로 한 값들로 구성된다.  
   <br>
   위와 같은 JSON 객체를 문자열로 직렬화하고 Base64 URL-Safe로 인코딩하면 다음과 같이 페이로드를 생성할 수 있다.
   
   <p align="center">
 <img src =  "https://user-images.githubusercontent.com/97110814/179414427-7c87ac75-c6c3-4a53-80c3-ec8cdc8fe638.png">
</p>   
    <p align="center">
 <img src =  "https://user-images.githubusercontent.com/97110814/179414458-d39f93d2-f0d4-47ed-9857-52d0cf5faae9.png">
</p>  

<br>
<br>

 - **시그니처(Signature)**  
   
   점(.)을 구분자로 해서 헤더와 페이로드를 합친 문자열을 서명한 값이다. 서명은 헤더의 alg에 정의된 알고리즘과 비밀 키를 이용해 성성하고 Base64 URL-Safe로 인코딩한다.  

   <p align="center">
 <img src =  "https://user-images.githubusercontent.com/97110814/179416077-81acd637-c424-4ae2-82bc-d4b634fa2957.png">
</p>  
  
   <p align="center">
 <img src =  "https://user-images.githubusercontent.com/97110814/179416078-0b11be1e-a703-4ec6-bc56-ddaeec68bff0.png">
</p>  
<br>

### **JWT** = Header + Paylord + Signature  
아래와 같이 표현 할 수 있다.
<p align="center">
 <img src =  "https://supertokens.com/static/b0172cabbcd583dd4ed222bdb83fc51a/9af93/jwt-structure.png">
</p>  

<br>
<br>
<br>
<br>
<br>
<br>

### -API-  
> - API :  
> >  API(Application Programming Interface)는 응용 프로그램에서 사용할 수 있도록 운영체제나 프로그래밍 언어가 제공하는 기능을 제어할 수 있게 만든 인터페이스를 뜻한다.  
<br>
> 아래와 같이 그림으로 이해하기 쉽게 표현 할 수 있다.
><p align="center">
 <img src =  "https://blog.wishket.com/wp-content/uploads/2019/10/API-%EC%89%BD%EA%B2%8C-%EC%95%8C%EC%95%84%EB%B3%B4%EA%B8%B0.png">
</p>  
<br>

<br>

<br>

<br>

<br>

#### **API 종류**  
  - private API   
    : private API는 내부 API로, 회사      개발자가 자체 제품과 서비스를 개선하기 위해 내부적으로 발행하고, 제 3자에게 노출되지 않는다.  

  - public API  
    : public API는 개방형 API로, 모두에게 공개되고, 누구나 제한 없이 API를 사용할 수 있는 게 특징.  

  - partner API  
    : partner API는 기업이 데이터 공유에 동의하는 특정인들만 사용할 수 있다. 비즈니스 관계에서 사용되는 편이며, 종종 파트너 회사 간에 소프트웨어를 통합하기 위해 사용된다.  

  - CRUD(Create Read Update Delete)에 따라 4가지로 나누는데 주소는 명사(복수형), 요청 방식(동사)를 사용해서 의도를 명확하게 드러낸다.  
         1. GET
         2. POST
         3. PUT
         4. DELETE
  
  
    <br>
      
    <br>
    
    <br>
    
    <br>

    <br>

#### **그래서 API는 무슨 일은 한다는거에요?**  
<br>

1.  서버와 데이터베이스에 대한 출입구 역할을 하고,  
2.  애플리케이션과 기기가 원활하게 통신할 수 있도록 하며,  
3.  모든 접속을 표준화한다.  
  
<br>

<br>

<br>

<br>

<br>

<br>

## **그래서 배운게 뭔데?**  
아쉽게도 저런게 있다는 것을 알고, 들어본 것을 찾아보고 읽어 봤기에 무슨 말인지는 알겠지만, 어떻게 어디서 사용하는지까지는 잘 모르겠어.  

하지만,  
 많이 읽어보게 되니 이해는 다 되지 않아도 다시 검색해보거나 사용해보기 위해 찾아볼 때 도움이 많이 될 것 같다. 개념은 알게 되었어. 네 덕이야.

배울 게 많고, 집중과 몰입하기에 너무 좋은 분야야. 하루하루 허투루 보내기엔 너무 아쉬워.  
<br>

<br>

<br>

<br>

<br>

<br>

<br>

## **-나는 누구일까-**  
<br>

도 대표 선수출신이며, 서비스계에서 약 5년간 근무했고 근무 중, 개발자를 알게 되어 준비하고 있는 운동하는 무무입니다.  
백엔드에 빠져 Java를 배우고 있는 입문자입니다~
4년제 공과계열을 나와 C언어, 매트랩을 해본 경험은 있으나 오래되어, 공대생이지만 입문자와 다를 바 없는 취준생이죠!  
항해99라는 온라인 부트캠프를 수강하고 있으며, 2주차에 막 진입했습니다. 주 100시간의 부트캠프지만,  
100시간이 결코 길지 않음에 하루가 짧게 지내고 있어요. 평균 일일 15~16시간 정도 코딩을 하고 있지만, 내내 하는 것은 아니에요!!
식사시간을 1시간씩, 구글링하는 시간, 소통하는 시간, 강의가 있는 날엔 강의 포함해서 무무가 코딩하는 순수 시간은 몇 시간이 안되거든요!
그래서 하루가 짧다하고 15시간 이상씩 잡고 있는거에요! 생각보다 몸은 피곤치 않고, 생각보다 코딩하는게 재밌어요.
알고리즘 문제가 기초단계지만, 버벅이면서 풀어 나갈 때 희열이 있답니다! 그 맛에 계속 풀어보고 있는 것 같아요.  




