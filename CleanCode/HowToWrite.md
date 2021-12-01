# 코드 작성법
## Naming
기준 없이 작성된 이름은 수 개월 뒤의 나에게 고통을 선사한다.<br>
개발자들 사이에서 이름을 작성할 때의 일반적인 관습을 파악하고 그에 맞게 작성하도록 노력한다.<br>
Java를 기준으로 Naming Rule을 기억하자.

- 기본적으로 lowerCamelCase를 사용한다.
  - 클래스, 인터페이스는 UpperCamelCase를 사용한다. 
```java
  String userName = "sanghyun";

  public Class User {
    ......
  }
```
- 상수는 SCREAMING_SNAKE_CASE를 사용한다.
```java
  public static final String  IP_ADDRESS  = "127.0.0.1";
  public static final int     LISTEN_PORT = 80;
```
- 특수기호, 숫자를 사용하는 것은 되도록 피한다.
```java
  Member member1 = new Member("developer");
  Member member2 = new Member("admin");

  // Much better
  Member developer = new Member("developer");
  Member admin = new Member("admin");
```
- 명시적으로 의미있는 단어를 사용한다.
  - 누구나 알수 있는 것이 아니라면 축약어 사용도 최대한 피한다.
```java
  // Bad practice
  public boolean between(int a1, int a2, int a3) {
    return a2 <= a1 && a1 <= a3;
  }
  User u = new User();

  // Much better
  public boolean hasBetweenNumber(int value, int minimun, int maximum) {
    return minimum <= value && value <= maximun;
  }
  User user = new User();
```
- 동일한 어휘를 사용한다.
```java
  // Bad practice
  public User getUserInfo();
  public User getUserDetail();
  public User getUserData();

  // Much better
  public User getUser();
```
- 검색 가능한 이름의 변수로 사용한다.
```java
  // Bad practice
  session.setMaxInactiveInterval(8640000);

  // Much better
  const MILLISECONDS_IN_A_DAY = 8640000;
  session.setMaxInactiveInterval(MILLISECONDS_IN_A_DAY);
```
- 이름으로 너무 장황하게 설명하지 않는다.
```java
  // Bad practice
  public void saveUserIntoMySQLDatabase(user);

  // Much better
  public void saveuser(user);
```
- Function은 간략한 문장으로 클래스, 속성은 명사로 작성한다.
- 메소드의 이름에 And, Or 등의 연결된 문장을 사용하지 않는다.
  - 하나의 메소드에서는 하나의 기능만을 수행한다.
```java
  // Bad practice
  public void saveUserAndChargeCard(User user, Card card) {
    ......
  }

  // Much better
  public void saveUser(User user) {
    ......
  }
  public void chargeCard(Card card) {

  }
```
- 문맥상 중복되거나 필요없는 단어는 생략한다.
```java
  // Bad practice
  public Class Car {
    String carMake;
    String carModel;
    String carColor;
  }

  // Much better
  public Class Car {
    String make;
    String model;
    String color;
  }
```

## Declared
- 변수의 위치는 항상 사용하는 클래스 혹은 메소드의 상단에 위치한다.
  - 하나의 메소드에서만 사용되다면 로컬 변수로 선언한다.
- 변수, 메소드는 일반적으로 사용되는 순서대로 선언한다.
  - 중요도가 높은 변수, 메소드를 상단에 작성한다.

## Method
- 다시 한번 강조하지만 하나의 메소드에서는 하나의 기능만을 수행한다.
- 메소드는 최대한 간략하게 작성한다.
```java
  // Bad practice
  public boolean hasBetweenNumber(int value, int minimun, int maximum) {
    if(minimum <= value && value <= maximun) {
      return true;
    } else {
      return false;
    }
  }

  // Much better
  public boolean hasBetweenNumber(int value, int minimun, int maximum) {
    return minimum <= value && value <= maximun;
  }
```

## Code
- 중복된 내용을 반복적으로 작성하지 않는다.
  - 중복된 내용을 제거하면 재사용성은 자동적으로 올라간다.
- 코드는 최대한 단순화 하여 작성한다.

## Comments
- 복잡한 로직이거나 특이점이 발생한 것이 아니라면 코멘트는 생략한다.
  - 코드 수정에 대한 이력은 형상관리가 더 잘 알고 있다.

## 의미가 전달될 수 있는 한도 내에서 최대한 간략하게

