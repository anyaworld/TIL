# 두개의 Github 계정 로컬에서 분리해서 사용하기

* MAC에서는 원격 저장소에 접근할때마다 osxkeychain에 저장된 인증 정보를 이용하여 접근한다.
* 회사,집에서 사용할 두개의 계정을 이용하여 서로 다른 원격 저장소에 접근해야 한다.
* 하나의 계정을 쓰면 osxkeychain에 저장된 정보를 쓰면 되는데
* 나는 상위 폴더 두개에서 각각 git init 하면 각 폴더 설정에 따라 서로 다른 원격 저장소에 접근할수 있게 하고 싶다.

## 문제

1. 기존 계정(A) 대신 github계정(B)을 하나 더 만들게 됨
2. remote 설정을 다르게 하여 다른 계정B를 remote에 추가했더니 403 에러 발생

## 원인
 * git Credential이 원인 - 권한문제
 * 하나의 인증 인증 정보를 초기화 하고 다시 설정하자
 * 그러면 다른 하나 계정을 사용할때 어떻게 되는거지?

## 시도

1. 우선 global .gitconfig 에 default로 설정할 github 계정 정보를 입력한다.
  ```bash
  [user]
          email = <gighub-email>
          name = <github-name>
  ```

   * 특정 디렉토리에서는 user설정을 덮어 써서 적용하도록
  ```bash
  [includeIf "gitdir:~/<another_user_local_repository_path>"]
    path=~/.<other_user_config_file_path>
  ```

   *other_user_config_file_path 에는 다음과 같이 덮어쓸 새 user정보를 넣는다.
   그러면 another_user_local_repository_path에서는 새 user정보로 접근이 가능해진다.

  ```bash
  [user]
          email = <gighub-email>
          name = <github-name>
  ```

2. osxkeychain unset
```bash
$ git config --list
```
 * 위의 명령어를 실행했을 때 다음 권한을 없애기 위해

```bash
credential.helper=osxkeychain
```

 * 다음 명령어를 실행하여 unset 시도하였으나 실패

```bash
$ git config --local --unset credential.helper
$ git config --global --unset credential.helper
$ git config --system --unset credential.helper
```
 * 그래서 ```bash ~/.gitconfig ``` 로 직접 접근하여 마지막에 다음과 같이 빈값을 넣어줌
 (왜 osxkeychain값을 쓸수 없게 못하는지는 아직 알수 없음.)
```bash
[credential]
  helper =
```

* 위의 helper 를 빈값으로 넣어주었더니 push할때마다 계정 이름과 패스워드를 입력해야 하는 문제가 발생함
 그래서 로컬 config파일의 remote에 다음과 같이 넣어줌
```bash
 [remote "origin"]
  url=https://username:password@github.com/username/repo.git
```

* osxkeychain에 git 계정 두개가 추가 되어있는 것을 발견함.음?

3. 생각의 변화
* 403에러가 났을때 osxkeychain에는 하나만 저장되는 줄 알았다.
* osxkeychain을 수동으로 지우고, 안쓰고(helper= 빈값)넣고 .git/config 파일에 계정정보를 등록했더니 이것도 귀찮다

4.결론-keychain을 쓰자
* helper=빈값을 지우면 자동으로 osxkeychain으로 지정됨(default인지는 모름)
* .git/config 파일에 계정정보를 등록 하면 osxkeychain에도 저장이 된다.
* 패스워드에 < * . 같은 특수문자가 있으면 에러가 났었다. 좀더 쉬운 패스워드를 사용해야 했음. 그렇다고 짧은패스워드는 금물

-------

### 도움 받은 사이트:
* includeIf를 이용한 설정 - https://www.codexpedia.com/devops/includeif-for-creating-different-git-identities/
* osxkeychain값 설정- https://stackoverflow.com/questions/13198143/how-do-i-disable-gits-credential-helper-for-a-single-repository/36435803#36435803
