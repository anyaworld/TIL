# Singleton pattern

## 싱글턴을

## singleton을 구현하는 방법은 몇가지가 있다.
  *  예시1: 간단한 singleton
```bash
  public class Elvis{
      public static final Elvis INSTANCE=new Elvis();

      private Elvis(){}
  }
```
  * 예시2: public 으로 선언된 정적 팩터리 메서드를 이용한다.
  ```bash
  public class Elvis{
      private static INSTANCE instance;

      private Elvis(){}

      public static Elvis getInstance(){
        if(INSTANCE==null){
          INSTANCE=new Elvis();
        }
        return INSTANCE;
      }
  }
  ```
  * 예시 3: 멀티스레드 환경에서 메서드의 원자성이 결여단 탓에 경합 조건이 발생하면 에러가 날 소지가 있다. 두개의 쓰레드에서 인스턴스를 반환하기 전까지 동시에 접근할수 없도록 synchronized로 Lock을 건다.
  ```bash
  public class Elvis{
      private static INSTANCE instance;

      private Elvis(){}

      public static synchronized Elvis getInstance(){
        if(INSTANCE==null){
          INSTANCE=new Elvis();
        }
        return INSTANCE;
      }
  }
  ```
* 단점으로 생성자를 private으로 선언하면 상속이 불가능하게 된다.
* 게다가 이 방법들은 리플렉션기능을 통해 private 생성자를 호출할 수 있다.
  ```bash
  import java.lang.reflect.Constructor;
  public class PrivateInvoker{
    public static void main(String[] args) throws Exception{
      Constructor<?> con=Private.class.getDeclaredConstructors()[0];
      con.setAccessible(true);
      Private p=(Private)con.newInstance();
    }
  }
  class Private{
    private Private(){
      System.out.println("Hello");
    }
  }
  ```
 (출처:https://stackoverflow.com/questions/4081227/singleton-pattern)

## enum으로 생성하는것이 최선이다
* enum은 원래 singleton이라 jvm이 알아서 생성해주므로 생성 및 동기화 그리고 초기화 관련 문제를 고민하지 않아도 되게 해준다.
* 다음과 같이 생성한다.
```bash
  public enum MySingletonEnum{
    INSTANCE;
    public void doSomethingInteresting(){}
  }
```
* 싱글톤 객체 인스턴스를 이렇게 사용한다.
```bash
  MySingletonEnum mse=MySingletonEnum.INSTANCE;
  mse.doSomethingInteresting();
```


## 이 Singleton패턴은 어떻게 사용할수 있을까?
* 인스턴스가 한개만 존재하는 것을 보증하는 패턴이다.
* 많은 블로그에서 멀티쓰레드 환경에서 신중하게 사용하라는 의견이 많은 패턴이다.
* 그러므로 android의 logging, 사용자 설정, 시스템 설정이나 DB파일, 이미지, 오디오 영상같은 리소스를 관리하는 객체에 사용하면 되겠다.


* 예제 출처:<br/>
JavaEE 디자인 패턴, 4 싱글톤 패턴 길벗출판사<br/>
Effective Java 규칙 3 private 생성자나 enum 자료형은 싱글턴 패턴을 따르도록 설계하라. 조슈아 블로, 인사이트
