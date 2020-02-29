# 두개의 SSH Key 만들어 등록해보자

1. SSH key를 생성하자
* SSH key 파일 생성
```bash
$ ssh-keygen -t rsa -b 4096 -C "id_rsa_github_user01" -f ~/.ssh/id_rsa_github_user01
$ ssh-keygen -t rsa -b 4096 -C "id_rsa_github_user02" -f ~/.ssh/id_rsa_github_user02
```
* 다음과 같은 파일이 생성됨
```bash
~/.ssh/id_rsa_github_user01
~/.ssh/id_rsa_github_user01.pub
~/.ssh/id_rsa_github_user02
~/.ssh/id_rsa_github_user02.pub
```

* 다음 config파일에
```bash
~/.ssh/config
```

 * 코드를 넣는다.
```bash
# global
Host *
UseKeychain yes
AddKeysToAgent yes
```

* SSH Agent에 key 등록
```bash
$ ssh-add -K ~/.ssh/id_rsa_github_user01
$ ssh-add -K ~/.ssh/id_rsa_github_user02
```

```bash
$ ssh-add -l
4096 SHA256:O2MoTWlJD8yE+VxrxR5bOu0 ~/.ssh/id_rsa_github_user01 (RSA)
4096 SHA256:W2cnWtNK9tU9/dkWvOjLxNQ ~/.ssh/id_rsa_github_user02 (RSA)
```
* SSH Key 생성 - https://elmland.blog/2018/08/13/multiple-git-accounts/
* SSH 키 분리 - https://blog.outsider.ne.kr/1448
