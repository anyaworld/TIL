# token 정보 서버에 보내기

## Apache HTTP Client가 api23이후부터는 기본지원을 하지 않습니다.[출처](https://developer.android.com/about/versions/marshmallow/android-6.0-changes?hl=ko#behavior-apache-http-client)

## 대안 : OKHttpClient 선정

* OkHttp works on Android 5.0+ (API level 21+) and Java 8+.[출처](https://square.github.io/okhttp/#requirements)
