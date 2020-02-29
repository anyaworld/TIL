# Git Steps

## 순서
1. create project
2. git init
3. add .
4. git commit -m "commit message"
5. git remote add origin gitpath
6. git push orgin master

## 어차피 모르는 명령어는 구글신에게 물어보면 되고 아리송 했던것을 정리하자(언젠가?)
1. git 에는 나만 알고 싶은 내용은 커밋하지 않는다.  stash 라는 훌륭한 기능이 있다.
2. branch 전략은 따로 배워둘 만 한 것같다. 남들은 브랜치를 어떤 단위로 만들고 사용하는지 궁금해 하고 꼭 정리해두자.


## Create Repository

```bash
$ git init #init
```

## Create branch

```bash
$ git branch # show branch list
$ git branch [BRANCH_NAME]
```

## Checkout branch

```bash
$ git branch
$ git checkout [BRANCH_NAME]
```

## Commit

```bash
$ git status # to see file changed
$ git add [FILE_NAME]
$ git commit -m "commit message"
```

## Push

```bash
$ git push origin [BRANCH_NAME]
```

## Print Git log
```bash
$ git log
```
