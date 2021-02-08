# Review

## 2021-02-08

1. gitflow 꼬여서 오전 날림.(그렇지만 해결했음!)

1. 오늘의 할일은 localhost 애 token을 json으로 구성해서 post로 보내면 서버에서는 token 정보를 출력하고, 201 Created 를 보내는 것.

1. 오늘은 RequestBody 가 null 로 들어가는 것이 문제였다

1. Postman에 json으로 정보를 넣는 부분 확인함.

1. 여전히 @RequestBody는 null

1. 그럴 리는 없겠지만 openjdk version 8 로 잡여 있헜던 jdk를 11로 바꿔줌(처음 프로젝트는 11로 설정됨)

1. 여전히 안됨

1. log.warn("body: {}", body) 부분이 import 가 안됨 일단 이것 먼저 해결

1. 헐랭 실행 됨-_- 이런
