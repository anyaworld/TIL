# Git clean

git clean 명령은 추적 중이지 않은 파일만 지우는 게 기본 동작이다. 즉, .gitignore 에 명시하여 무시되는 파일은 지우지 않는다. [출처](https://gmlwjd9405.github.io/2018/05/25/git-add-cancle.html)

```bash
# 만약 지워질 파일을 미리 알고 싶다면  --dry-run 옵션을 붙여줌
git clean -fd --dry-run

# 디렉터리를 제외한 파일들만 삭제
git clean -f

# 디렉터리까지 삭제
git clean -f -d

# 무시된 파일까지 삭제
git clean -f -d -x
```
