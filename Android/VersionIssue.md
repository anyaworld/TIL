# Version issue

## Runtime permissions

1. 구글에서는 마시멜로우(api>=23이상) 부터는 manifest에 선언된 권한을 앱에 설치할때가 아니라 그 권한을 사용하는 기능을 실행할때 요청하도록 권고.
1. 앱을 사용하는 중간에 사용자가 앱 설정으로 이동하여 허용한 권한을 다시 허용하지 않을때의 예외처리를 필수로 구현해야 한다.
1. 왜그런지는 모르겠지만 사용자는 앱을 이리저리 시험에 들게 하여 죽여보고 싶어하는 듯하다.
    1.내가 발견하면 다행인데 이게 고갱님 손에서 이리저리 눌러보다 권한 획득 중간에 runtime-error로 앱이 죽어버리면...

## DSL element 'android.dataBinding.enabled' is obsolete and has been replaced with 'android.buildFeatures.dataBinding'

* anroid studio 4.0미만

    ```code
    viewBinding {
            enabled = true
        }
    ```

* android studio 4.0 이상

    ```code
    buildFeatures {
        viewBinding = true
    }
    ```
