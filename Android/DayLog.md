# Day Log

## 2021년 2월 15일

* Is a Issue or Is Not a Issue

* 상황 : Debug 일때만 나타나는 버튼이 있음. BuildConfig.Debug로 생성됨

* 문제점 : 이 버튼이 Manafest.xml 에 Application 태그에 .name 속성에 application 을 상속받은 SubApp 클래스이름을 입력하면 BuildConfig가 자동 생성이 안됨.

* 원인 : BuildConfig 가 자동 생성되지 않음. 왜냐,[Link](https://developer.android.com/studio/releases/gradle-plugin#version_properties_removed_from_buildconfig_class_in_library_projects)

* 대안1. Debug일때만 생성되는 코드를 지운다.
* 대안2. [Link](https://ichi.pro/ko/android-modyul-eseo-buildconfig-saengseong-jungji-138001015316721)

* 결론 : 대안 1선택, 문제가 되는 코드는 디버깅 편의를 위한 코드로 릴리즈에는 안들어감 굳이 시간을 들여 수정할 필요 없음. 이슈가 아님.

## 2021년 4월 26일

1. 정규식 공부하기 -> target='_blank' 로 띄우는 부분 url하드코딩 -> 정규식으로 바꿈
1. 버전 1.4 플레이스토어 베타로 심사 중
1. 버전 1.0 기능 테스트 중

## 2021년 4월 27일

1. 버전 1.0 기능 테스트
1. 플레이어 전체화면 안되는 문제 있음(웹,모바일웹 작동, 앱에서 동작안함) -> 담당자에게 전달
1. 고객사 인스타그램 계정이 연결이 안되는 문제 문의

## 2021년 4월 28일

1. 지라에 작업 내용 정리 및 작업상태 입력 완료
1. 앱 버전 1.5의 내부테스트로 심사 시작
1. 인스타그램 계정 연결 답변 도착 -> dev에 반영됨
1. 고객사에 유심 요청 -> 답변 받기로 함

## 2021년 4월 29일

1. 파일 업로드 제한 테스트 완료 및 JIRA에 등록완료
1. Navivation Example-Step10 까지 완료 [Link](https://developer.android.com/codelabs/kotlin-android-training-add-navigation/index.html#9)

## 2021년 4월 30일

1. 심카드 요청 -> 다음주 월요일 퀵으로 도착 예정
1. Full Screen Error Debugging 중

## 2021년 5월 3일

1. 심사 결과 거절됨 -> 설정 지우고, 심사 다시 시작
1. FileUpLoad 보는 중

## 2021년 5월 4일

1. 심사 통과됨
1. 테스트 결과 정리 > JIRA에 등록
    1. 찾아낸 버그는 버그로 등록
1. WebView에 전달 할수 있을까..-_-
1. 어린이날 이것 볼 것[Link](https://github.com/rohitpsoman/Android-Kotlin-MVVM-Navigation-Room-Coroutines-Databinding.git)

## 2021년 5월 6일

1. 5월 4일 5.4 [link](https://github.com/rohitpsoman/Android-Kotlin-MVVM-Navigation-Room-Coroutines-Databinding.git) 안봤다 ㅋㅋㅋ
1. WeChat 쓰는 앱 decompile해서 보는건 시간 낭비였다.
1. 다시 Wechat봐야지 모-_-

## 2021년 5월 7일

1. 고객사 문의 사항 : 테스트용 위챗 아이디를 심카드 번호로 가입해도 되는지 문의 >> 굳이 거기까지 안해도 됨
1. 고객사에서 개발자 계정 접근하려다가 로그인된 안드로이드에서 인증 못받아서 연락왔었음.
1. 위챗 로그인은 로그인 시도 너무 많이 해서 block됨. 내일 다시 시도해봐야지 실마리는 찾은것 같음.

## 2021년 5월 10일

1. Native >> JS 호출이 가능함. webview.evaluateJavascript[Link](https://g-y-e-o-m.tistory.com/28)

## 2021년 5월 13일

1. MainActivity의 onResume 이 두번 호출되는 문제 해결
    1. onPause 가 호출되었기 때문에 onResume이 두번 호출됨.
    1. onPause는 MainActivity에서 권한이 있는지 확인했기 때문에 onPause가 호출됨. (이미 권한을 가지고 있어도 권한이 가지고 있는지 체크하면 onPause 호출됨)
    1. 앱의 권한을 체크하는 프로세스는 SplashActivity에서 처리하도록 해결함.
    1. 전체적으로 앱을 실행하는 순서는 SplashActivity -> MainActivity 순으로 실행됨

1. TODO

    기존의 activity순서는 MainActivity -> WXEntryActivity(위챗 로그인) -> WebviewActivity 순으로 이루어졌습니다.
    우선, 물리 backbutton을 여러 activity사이에서 제어하기 힘들다고 판단하여

    1. WXEntryActivity 에서 다시 MainActivity의 webview에서 결과를 받을 수 있도록 하였습니다.

        WXEntryActivity에서 MainActivity를 startActiviy를 시킬때, onResume이 두번 호출 되는 문제가 있었는데
        이것은 MainActivity에서 권한 체크를 하는 과정에서 이미 권한을 획득하였다 하더라도 권한이 있는지 체크하면 onPause가 호출되어 onResume이 두번 호출되는 문제였습니다.
        권한을 체크하는 프로세스를 SplashActivity를 생성하여 여기서 체크하도록 하여 해결 하였습니다.
    2. WebView.loadData로 임시의 html에서 로그인 정보를 백엔드로 보내는데, 이것도 backbutton 문제가 있었습니다.

    이 백버튼 문제는 webview.post(runnable { }) 로 새로운 쓰레드를 만들어 return받은 url을 webviw.loadURL로 처리 완료하였습니다.
    결과적으로 백 버튼 문제를 이 문제를 해결 하기 위하여 권한을 체크하는 Splash Activity가 생성되었습니다.

## 2021년 5월 14일

1. 결과 받아오는 동안 화면 하얀것 원인 알아보고 대응방안 찾을것(네트워크가 느려도 로딩 중이라고 사용자가 알아야 함)
    1. [Link](https://thdev.tech/androiddev/2020/07/13/Android-Fragment-ViewModel-Example/)
    1. [Link](https://medium.com/@joongwon/android-aac%EB%A5%BC-%ED%99%9C%EC%9A%A9%ED%95%9C-mvvm-%ED%8C%A8%ED%84%B4-e24a685fc25d)
    1. [Link](https://github.com/AgustaRC/MVVMArchitecture)
    1. [Link](https://stackoverflow.com/questions/29666844/onshowfilechooser-from-android-webview-works-only-once)

## 2021년 5월 17일

1. 5월 14일 1번 문항 대안 찾음. 기본 프로그래스 바에 progressBarStyleLarge 를 주어서 해결함.
    1. 이 동글뱅이 돌아가는것을 늘 제어할수 있어야 함. 아직은 계속 테스트 중
1. wechat login 기능을 넣은 앱이 플레이스토어로 배포 되었는데 위챗 api 키가 디버그로 릴리즈로 된 서명값이 등록되어 있어서 안됨.
    1. 잘못된 서명 오픈플랫폼에 있는 이름과 동일한지 ~ 확인하라는 메시지 뜸
    1. 해결 방안 위챗 오픈api 개발자 사이트에 로그인해서 릴리즈로 서명된 키로 등록해야 함.[Link](https://m.blog.naver.com/lys1900/221081398964)

## 2021년 5월 18일

1. 위챗 오픈api 개발자 사이트에 로그인해서 릴리즈로 서명된 키로 등록함.
1. 바로 적용 안되고 1시간 반정도 기다렷는데도 안되서 위챗 로그아웃하고 시도하니까 됨!
1. 고객사에 위챗 로그인 테스트 요청 메일 보냄.
1. 고객사에서 앱이 정상동작한 것을 동영상으로 캡처하여 메일로 보내서 확인 완료.
1. 동시에 고객사에서 로그인을 할 때 약관 동의를 하라는 페이지가 나와서 정상 동작인지 문의가 왔었슴
1. 오늘 테스트 서버 디비의 데이터가 삭제되었다가 운영데이터 베이스의 값이 업데이트 되면서 동작한 결과라고 답변함.

## 2021년 5월 20일

1. 불필요한 코드 정리
1. 돌아가는 동글뱅이가 connectionError일때 에도 계속 돌아감 - onPageFinished 일 때도 동글뱅이를 없애야 함.
1. setBackground를 0으로 주었더니, error페이지에서도 0으로 뜸. > error처리할때 background 를 하얗게 처리해야 한다.
1. Progressbar랑 webview를 fragment로 이동해야 하나?
1. 다운로드관련된 디비 정보가 리셋되면서 안드로이드에서도 테스트 다시 해야함!

## 2021년 5월 24일

1. about Content-Desposion 의 값이 ''filename="filename.jpg" >> 이렇게 와서 프론트에 정상 동작 확인 요청 함
    1. 참고 [Link](https://developer.mozilla.org/ko/docs/Web/HTTP/Headers/Content-Disposition)

1. 어쩐지 webview의 downloadListener에 contentDisposition, mimeType 애 반 문자열 오더라ㅜㅜ

## 2021년 5월 25일

1. sample files, (pdf, doc, docx, etc...) [From](https://filesamples.com/categories/image)
1. Webview에서 주는 권한 확인 -> 권한 다시 작업 필요

## TODO

1. 도서구매 취소시 window.close처리 [Link](<https://holika.tistory.com/m/entry/내-맘대로-정리한-안드로이드-WebView에서-windowclose-이벤트-받아서-창-닫기>)

1. Android 플레이스토어에서 내 앱으로 이동.

    ```java
    String uri = "market://details?id=" +getPackageName();
    Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse(uri));
    startActivity(intent);
    ```

1. 푸시 메시지 수신받을 때 필요한 것들
    * 아이콘 디자인 필요 (현재는 쓰레기통아이콘 이미지)
    * 푸시 할때 넣은 이미지 크기 Spec 필요( 이미지파일 확장자(png, jpg), 이미지 url(축약해서), 안드로이드에서 기기마다 깨지지 않을 이미지 크기(px))
    * 푸시 알림 채널 설정,(api > 27?이상에서 채널 설정 필수)
    * 방해 금지 모드일때 알림 중요도 순위 설정
