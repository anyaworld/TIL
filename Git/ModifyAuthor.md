## modify Author

* 깃계정을 두개 쓰다보니 작성자를 잘못 쓴 적이 많아 정리한다.
* rebase 명령어를 사용했는데 작성자를 수정했다는 커밋이 남아 별로 좋은 것 같지 않아 더 찾아봤다.
* git filter-branch라는 기능이 유용했다.

```bash
git filter-branch --env-filter '
WRONG_EMAIL="잘못된 이메일 주소"
NEW_NAME="바꿀 이름"
NEW_EMAIL="바꿀 이메일 주소"

if [ "$GIT_COMMITTER_EMAIL" = "$WRONG_EMAIL" ]
then
    export GIT_COMMITTER_NAME="$NEW_NAME"
    export GIT_COMMITTER_EMAIL="$NEW_EMAIL"
fi
if [ "$GIT_AUTHOR_EMAIL" = "$WRONG_EMAIL" ]
then
    export GIT_AUTHOR_NAME="$NEW_NAME"
    export GIT_AUTHOR_EMAIL="$NEW_EMAIL"
fi
' --tag-name-filter cat -- --branches --tags
```

* 위 명령어를 실행하고 push할때는 push가 되지 않는다.

```bash
To https://github.com/nyagum/architectureexample.git
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to '깃계정'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```
* 기존에 push된 커밋과 일치 되지 않아서 발생한 에러인데 간단하게 force옵션을 사용하면 해결된다.

```bash
git push --force origin master
```


filter-branch 출처:https://madplay.github.io/post/change-git-author-name
