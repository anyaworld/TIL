# Git Steps

## 내가 사용하는 순서

```bash
git add add .
git status
git diff  // git status, git diff 꼭 확인하고 커밋하자. 특히 여러개의 파일을 수정했을경우는 특히.
git commit -m "commit message"
git remote add origin https://<username>:<password>@github.com/<username>/<git_repository_name>.git
git push orgin master
```

## 기억할 것

1. git 에는 나만 알고 싶은 내용은 커밋하지 않는다.  stash 라는 훌륭한 기능이 있다.
1. 새 기능을 넣을때는 꼭 branch를 생성하고 추가한다. master에 직접 새 기능을 구현하지 않는다.
    * 긴급 패치를 할 경우에도 master 에서 hotfix로 브랜치를 생성해서 고칠 것

1. 빌드가 깨진 상태에서는 commit하지 않는다.

    * 빌드가 깨진 상태에서 꼭 저장을 해야 한다면 stash를 이용한다.

1. 기능단위로 commit할것

    * 예를들어 안드로이드에서 실행가능한 메모장을 만든다고 하면, 단순하게 일단 하나의 메모를 Create, Read, Update, Delete 하는 기능을 생각할 수 잇다.
    * 그러면 일단 임시 메모클래스를 추가하고 메모 내용을 넣은 메모인스턴스를 한개 생성해서 Acvitiy에 출력하고 결과가 제대로 나오면 커밋을 한다.
    * 메모를 추가할수 있는 기능을 가진 Activity를 추가하고 구현하고 commit한다.
    * 이렇게 기능단위로 커밋을 하면 나중에 어느 시점으로 가더라도 프로그램을 실행할수 있다.

1. 커밋은 일단 습관을 들여놓는것이 매우 중요하다.

1. 어떤 하나의 기능을 구현한다 목표로 하고 그것에 관련된 것만 구현하는것도 습관이더라..ㅜㅜ

    * 나에게 정말 중요한 것이지만 작은것부터 구현해서 크게 만들 생각을 할것
    * 처음부터 잘 만들려는 욕심을 내려놓자.

## Create branch

```bash
git branch # show branch list
git branch [BRANCH_NAME]
```

## Checkout branch

```bash
git branch
git checkout [BRANCH_NAME]
```

## Commit

```bash
git status # to see file changed
git add [FILE_NAME]
git commit -m "commit message"
```

## Commit 메시지 수정

```bash
git commit --amend
```

## Print Git log

```bash
git log
```

## git 이력확인

```bash
git reflog
```

## 모든 파일을 작업 이전의 상태로 되돌리기

```bash
git reset --hard
```

## 특정 파일만 되돌리기

```bash
git checkout -- <파일명>
```
