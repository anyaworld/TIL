# Upgrage에 따라서 바뀌는 것 정리

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
