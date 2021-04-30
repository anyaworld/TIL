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

## 2022년 4월 30일

1. 심카드 요청 -> 다음주 월요일 퀵으로 도착 예정
1. Full Screen Error Debugging 중

## TODO

1. 도서구매 취소시 window.close처리 [Link]](<https://holika.tistory.com/m/entry/내-맘대로-정리한-안드로이드-WebView에서-windowclose-이벤트-받아서-창-닫기>)
