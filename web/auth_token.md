### Token 방식의 인증

이전 회사에서는 업무상 인증을 굳이 신경쓰지 않아도 되었는데, 새 회사에서 처음 알게된 토큰 인증 방식<br>
내가 경력직이라 당연히 알 것이라고 생각한 팀분이 말하기 조심스러워 하셔서 괜스래 창피했다. 그동안 공부를 게을리 한것이 티가 났다.. <br>

인증방식에는 크게 서버기반의 인증방식과 토큰기반 인증방식으로 나눠지는데, 기존에 주로 봐왔던건 서버기반의 인증방식인가보다. (세션 등...)<br>

토큰 기반 인증방식은 인증받은 사용자들에게 토큰 발급, 서버에 요청할때 헤더에 토큰을 같이 보내도록 하여 서버가 상태를 저장할 필요 없이 사용자 인증을 거칠 수 있다. <br>
주로 사용하는 토큰은 [JWT(Json Web Tokens)](https://jwt.io/), json 문자열들을 base64로 인코딩하여 헤더에 담아서 전송한다.
일반적으로 토큰은 요청 헤더의 Authorization 필드에 담아서 보낸다.<br>
예시 > 
``` 
Authorization: <type> <credentials> 
```
<br>
type 에는 bearer 가 들어가는데, 다른 타입의 종류는 [이곳](https://velog.io/@cada/%ED%86%A0%EA%B7%BC-%EA%B8%B0%EB%B0%98-%EC%9D%B8%EC%A6%9D%EC%97%90%EC%84%9C-bearer%EB%8A%94-%EB%AC%B4%EC%97%87%EC%9D%BC%EA%B9%8C) 에서 참고했다.

이 토큰 인증 방식은 헤더만 확인해보면 누구나 디코딩 할 수 있어서, 알고나니 이곳저곳 사이트에서 진짜로 사용하는지 확인도 할 수 있었다.

참고 https://mangkyu.tistory.com/55
