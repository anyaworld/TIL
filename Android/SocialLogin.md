# Social Login

## Wechat

### Wechat 참고 문서

* [공식 홈페이지 가이드](https://developers.weixin.qq.com/doc/oplatform/en/Mobile_App/Access_Guide/Android.html)
* [Lnik](https://programmer.group/android-wechat-login-sharing-payment.html)
* [Link](https://www.codetd.com/ko/article/11797285#WXEntryActivity_84)

### App ID 발급 받기 위해 내가 한거

1. https://open.weixin.qq.com/ 에서 개발자로 로그인
1. android app 정보 입력
1. 앱 흐름도 작성하여 입력 : 기획자분께 참고할 자료 조사해서 전달함.
    * App ID를 발급 받기 위한 절차중 앱 흐름도를 입력해야 함.(귀찮다)
    * [참고자료(중국어)](https://mts.jk51.com/tushuo/1876558.html)
1. 고객사에 AppSecret 인증 요청
    * 고객사 아이디에 Bind시켜야 해서 고객사에 요청해서 고객사에서 인증 후 key정보를 받아야 함.

### 배울점 : 안되는면 붙잡지 말고 내가 놓친것부터 하나씩 보자

* activity에  android:launchMode="singleTask" 추가 안해서 token을 못 가지고 왔었다.(하루반이면 그래도 빨리 끝낸거다! :tada:)
* 스파게티 코드의 입장에서 실행되게 하자! -> 리펙토링은 나중에
