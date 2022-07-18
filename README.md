- **WIL** (Weekly I Learn)1주차 **회고** -  

# - **WIL** (Weekly I Learn) 회고 -  
<br>  

<br>

<br>

<br>


 

## JWT / API 무엇일까?  
<br>
### -JWT-  
> - JWT :  
> > JWT(JSON Web Token)란 인증에 필요한 정보들을 암호화시킨 JSON 토큰을 의미한다.  
>그리고 JWT 기반 인증은 JWT 토근 (Access Token)을 HTTP 헤더에 실어 서버가 클라이언트를 식별하는 방식이다.  
>JWT는 JSON 데이터를 Base64 URL- safe Encode 를 통해 인코딩하여 직렬화한 것이며,  
토큰 내부에는 위변조 방지를 위해 개인키를 통한 전자서명도 들어있다.  
>따라서 사용자가 JWT를 서버로 전송하면 서버는 서명을 검증하는 과정을 거치게 되며 검증이 완료되면 요청한 응답을 돌려준다.


<>  

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




