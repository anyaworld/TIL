# Token authentication requirements for Git operations

* id/password 방식의 github 로그인은 2021년 8월 13일부터 더 이상 지원하지 않는다고 한다.[Link](https://github.blog/2020-12-15-token-authentication-requirements-for-git-operations/)

* 미리미리 token으로 로그인 방식을 바꾸자

1. 키체인에 등록된 github 로그인 정보 지우기
    1. 키체인을 실행
    2. 터미널에 다음과 같이 입력(엔터 주의!) [출처](https://stackoverflow.com/questions/11067818/how-do-you-reset-the-stored-credentials-in-git-credential-osxkeychain/13421154)
    ```bash
    $ git credential-osxkeychain erase⏎
    host=github.com⏎
    protocol=https⏎
    ⏎
    ⏎
    ```
    3. 키체인에 github으로 검색해서 검색되는지 여부 확인한다.

1. Personal access token 생성하기
    1. 여기를 참고해서 토큰을 생성한다. [Link](https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token)
    1. git clone 하고 password에 토큰을 입력하면 됨



