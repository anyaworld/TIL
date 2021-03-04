# About CustomWebView

1. CustomWebview로 만들면 input 창 누르면 keyboard가 안나오는 문제

   * android:focusable="true" 과  android:focusableInTouchMode="true"를 추가 한다. [출처](https://stackoverflow.com/questions/34623043/android-keyboard-not-showing-when-clicking-on-input-in-webview)

   ```bash
    <io.anyaworld.webkit.CustomWebView
        android:id="@+id/webview"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:focusable="true"
        android:focusableInTouchMode="true"/>
   ```

2. input 창 나오면 View가 자동 정렬이 안되는 현상

   * 아래처럼 android:windowSoftInputMode="adjustNothing" 추가 [출처](https://scshim.tistory.com/124)

   ```bash
        <activity android:name=".MainActivity"
            android:windowSoftInputMode="adjustNothing">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
   ```
