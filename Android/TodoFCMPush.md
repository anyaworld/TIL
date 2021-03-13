# Todo FCMPush

## 진행 중

### 정책

1. FCM토큰, SSAID는 개인정보이므로 관련된 개인정보 약관을 업데이트해야 함. SSAID는 약관이 업데이트 되어 전달 예정. (업데이트 된 약관 전달 받으면 완료 됨)

### 순서도

1. 앱 설치하고 처음 실행할 때 푸시 수신 동의를 받아야 함.(flow는 추후 정리 예정)

### 개발 이슈

1. FCM토큰 언제 보낼지 잘 생각해보자
    1. onNewToken으로 보내긴 한데, jwt토큰을 서버로부터 어떻게 받을지 여부 문제가 있음.

1. FCM토큰 길이는 backend와 논의 필요
    1. 최근 조사된 것 중에 제일 긴 길이는 317 [출처](https://stackoverflow.com/questions/39959417/what-is-the-maximum-length-of-an-fcm-registration-id-token)

1. network disconnected 처리
    1. 모든 네트워크 요청시 에러가 나는데 이것을 어떻게 처리할지 일단 - _-보류

1. jwt토큰이 일정 주기마다 바뀌는데, 이것을 어떻게 처리할까? -_-

## 완료

1. FCM토큰 일단 서버로 보냄(검증 수준)

1. AdvancedWebView 를 적용하면 DeadObject Exception 을 내면서 죽는다.(에러 찾는중)
    1. [해결]Webview생성자 3개 재정의해줌 Context가 없어서 inflate를 못하는 것이 문제였음.

1. SSAID 길이는 16 character long(전달완료)

1. 푸시 메시지를 background, foreground 일때 모두 똑같이 띄우기 완료.  
    1. 과정
        * 안드로이드 푸시 메시지 수신할때 기기마다 다르게 뜰 때도 있고 안 뜰때도 있다.

        * 알림 필드가 notification 과 data 두개로 나뉘어져 있음.

        * 포그라운드, 백그라운드에서 메시지를 다르게 띄움 [출처](https://dongsik93.github.io/til/2021/01/28/til-fcm-push/)
    1. 해결
        * notificationBuilder 에 .setStyle(NotificationCompat.BigTextStyle().bigTex(message)) 을 추가 한다.
        * 푸시 메시지를 보낼때 notification 이 아니라 data에 보내면 해결된다.(if you need them while in background you can use a FCM data message.For data messages the onMessageReceived(message) method is always called, so you can use the message.getData() method and create your custom notification) [출처](https://stackoverflow.com/questions/38504078/firebase-expandable-notification-show-image-when-app-is-in-background)
    1. 알림 기본 템플릿이 달라서 생긴 문제가 아님 [출처](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#notification)

    ```bash
    {
    "title": string,
    "body": string,
    "image": string
    }
   ```

1. A라는 사용자가 2개 이상의 안드로이드 기기에 접속했을때는 두개의 안드로이드에 푸시 메시지를 보내야 한다. 그래서 기기를 식별할수 있는 정보 필요.(SSAID)
    1. 개인정보이므로 약관에 수집가능한지 문의해야 함.-> 답변 왔음. 써도 됨.

### 요청한 디자인

1. 로그인 했을 때 뜨는 이벤트/프로모션 푸시 수신동의 팝업(3/10 전달받음)

1. 사용자가 언제, 이벤트/프로모션 푸시 수신동의를 했음을 알려주는 팝업(3/10 전달받음)

### 정책(완료)

1. 이벤트/프로모션 동의 를 받아야 이벤트/프로모션 푸시 메시지 를 보낼수 있다.
