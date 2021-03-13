# Todo FCMPush

## 진행 중

1. 이벤트/프로모션 동의 를 받아야 함(이벤트 동의 문구는 월요일에 받기로 함)

1. FCM토큰 같이 개인정보에 관한 약관 파일 전달(완료) 인줄 알았으나
    1. SSAID도 확인 받아야 함.

1. FCM토큰 언제 보낼지 잘 생각해보자
    1. onNewToken으로 보내긴 한데, jwt토큰을 서버로부터 어떻게 받을지 여부 문제가 있음.

1. A라는 사용자가 2개 이상의 안드로이드 기기에 접속했을때는 두개의 안드로이드에 푸시 메시지를 보내야 한다. 그래서 기기를 식별할수 있는 정보 필요.
    1. 개인정보이므로 약관에 수집가능한지 문의해야 함.->문의함

1. FCM토큰 길이는 backend와 논의 필요
    1. 최근 조사된 것 중에 제일 긴 길이는 317 [출처](https://stackoverflow.com/questions/39959417/what-is-the-maximum-length-of-an-fcm-registration-id-token)

1. jwt토큰이 일정 주기마다 바뀌는데, 이것을 어떻게 처리할까? -_-

## 완료

1. FCM토큰 일단 서버로 보냄(검증 수준)

1. AdvancedWebView 를 적용하면 DeadObject Exception 을 내면서 죽는다.(에러 찾는중)
    1. [해결]Webview생성자 3개 재정의해줌 Context가 없어서 inflate를 못하는 것이 문젱였음.

1. SSAID 길이는 16 character long(전달완료)
