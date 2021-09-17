# Boolean Object

Boolean 타입은 null, true, false 값을 가질수 있다.
근데 Boolean 타입은 내가 젤 극혐하는 타입이다.
 
1.나타내는 상태가 제한적이다.
나타낼수 있는게 null, true, false 3가지 상태라 뭔가 제한적이라고 해야 하나?
성별도 예전에는 남,여 가 당연했지만
지금 시대 나보다 어린 사람들일수록
남,여, 트렌스젠더, 알리고싶지 않음, 남여로구분하기 싫음. 뭐 기타 등등으로 나뉘는 당연하게 여기더라
아무튼 성별을 담기엔 이젠 Boolean은 그닥 좋은 타입이 아닌것 같다.
페북에서도 예전에 가입할때 성별은 남/여로만 표기하지 않았다.. 지금은 페북 논란으로 가입을 막고 있다만.. 이건 딴소리
세상에는 빛과 어둠도 있지만 그 경계도 있지 않나?
아무튼 내 생각으로는 세상에 어떤 정보를 Boolean으로 나타내기에는 세상은 너무 다양하고 다체롭다.
컴퓨터는 101010011111 같은 이진으로 나타낸다지만
엄밀히 말하자면 어디서부터 1이고 어디서부터 0일지 정하는건 결국 인간 아닌가?
 
2.타입 자체가 확장이 잘 안된다.
옆자리 두분이 Boolean으로 화면의 night 모드, day 모드를 전환 하는거 구현하는데 어려움을 겪었는데…
그때 그 두분이 day mode, night mode 를 Boolean 으로 나타내는거 보면서 나는 헉했다..
나중에 확장하면 어쩌려고..그러시지?ㅜㅜ
엄밀히 내 일은 아니니까.. 난 리액트 모르니까 그냥 가만히 있었는뎅
아니.. 안드로이드 스튜디오만 하더라도
IntelliJ Light, Dracula, Hight contrast 세가지 모드를 지원하는데,
애플에서 day, night mode만 지원하다가
cloudy 를 하나 더 지원한다고 하면 어쩔려고 그러지 싶던데
확장성 있는 답변을 준비해보자면
Enum이 좀더 나은 답변이 될것 같다.

```bash
public enum Theme {
  DAY, NIGHT, CLOUDY;
  public static Theme from(String text) {
    if (null == text) {
      return DAY; // 널일때는 무조건 DAY 로 출력
    } else {
      return valueOf(text.toUpperCase());
    }
  }
}
```
이러면 어떤 타입이 추가되어도 테마에 Theme Enum에 추가 되면 깔끔하겠다.
근데 그러고 보니까
자바스크립트는 널이 없는데…
걔넨 undefined잖아.. - _-

java null, swift nil, javascript undefined 는 서로 다른것일텐뎅.. 뭔 차이점이 있지?