# Git rebaase and squash

## Git: “Cannot 'squash' without a previous commit” error while rebase

### Squash 할때 중간 commit 메시지를 pick해서 생기는 애러

### 해결방법

```bash
git log --pretty=oneline
git rebase -i HEAD~7

1 s 01cc5a08 Removes open div
2 s a2b6eecf Restores old fonts
3 s 603479ff Cleans left out div
4 pick 5afdbc33 Update: show logo on landing page
5 s 04c1cb13 change version of dev and prod from 1 to 2
6 s bbe6a8f8 Update: show logo on landing page if they have one
7 s c0d6008a Adds check for C users

git rebase --abort // 리베이스 중지
git rebase -i HEAD~7

1 r 01cc5a08 Removes open div // r means use commit, but edit the commit message
2 s a2b6eecf Restores old fonts
3 s 603479ff Cleans left out div
4 s 5afdbc33 Update: show logo on landing page
5 s 04c1cb13 change version of dev and prod from 1 to 2
6 s bbe6a8f8 Update: show logo on landing page if they have one
7 s c0d6008a Adds check for C users

After saving, the interactive shell asked me for the rewording of the chosen commit.
```

[출처](https://stackoverflow.com/questions/39595034/git-cannot-squash-without-a-previous-commit-error-while-rebase/42796983#42796983)