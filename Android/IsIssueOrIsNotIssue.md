# Is Issue or Is Not Issue

## 2월 15일에 내내 고민했던것

* 상황 : Debug 일때만 나타나는 버튼이 있음. BuildConfig.Debug로 생성됨

* 문제점 : 이 버튼이 Manafest.xml 에 Application 태그에 .name 속성에 application 을 상속받은 SubApp 클래스이름을 입력하면 BuildConfig가 자동 생성이 안됨.

* 원인 : BuildConfig 가 자동 생성되지 않음. 왜냐,[Link](https://developer.android.com/studio/releases/gradle-plugin#version_properties_removed_from_buildconfig_class_in_library_projects)

* 대안1. Debug일때만 생성되는 코드를 지운다.
* 대안2. [Link](https://ichi.pro/ko/android-modyul-eseo-buildconfig-saengseong-jungji-138001015316721)

* 결론 : 대안 1선택, 문제가 되는 코드는 디버깅 편의를 위한 코드로 릴리즈에는 안들어감 굳이 시간을 들여 수정할 필요 없음. 이슈가 아님.
