# Social Login

## Wechat

### Wechat 참고 문서

* [Lnik](https://programmer.group/android-wechat-login-sharing-payment.html)
* [공식 홈페이지 가이드](https://developers.weixin.qq.com/doc/oplatform/en/Mobile_App/Access_Guide/Android.html)
* [Examples of flow](https://mts.jk51.com/tushuo/1876558.html)
* [Link](https://www.codetd.com/ko/article/11797285#WXEntryActivity_84)

### 안되는면 붙잡지 말고 내가 놓친것부터 하나씩 보자

* activity에  android:launchMode="singleTask" 추가 안해서 token을 못 가지고 왔었다.(하루반이면 그래도 빨리 끝낸거다! :tada:)
* 스파게티 코드의 입장에서 실행되게 하자! ->리펙토링은 나중에
