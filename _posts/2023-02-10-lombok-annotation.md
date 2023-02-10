---
title:  "[JAVA] 실무에서 자주 사용하는 Lombok 코드 정리"
excerpt: "실제 회사 실무에서 자주 사용하는 Lombok 어노테이션을 정리해보자"

categories:
  - JAVA
tags:
  - [JAVA, LOMBOK, SPRING]

toc: true
toc_sticky: true
 
date: 2023-02-10
last_modified_at: 2023-02-10
---

# Lombok Annotations

롬복은 `getters`, `setters`, `equals`, `hashCode`, `toString` 메서드와 같은 상용 코드를 자동으로 생성하는 Java 라이브러리이다!

이러한 메서드를 직접 작성할 필요없이 깨끗하고 간결한 코드를 작성할 수 있다.

Lombok은 아래와 같이 몇 가지 어노테이션을 제공하는데, 아래는 실무에서 자주 사용하는 어노테이션의 일부를 가져왔다.

## @Getter
Getter 어노테이션은 속성에 대한 getter 메서드를 생성한다.

예제
```java
@Getter
public class User {
  private String name;
  private int age;
}
```
위 코드는 아래와 같은 코드를 생성한다.
```java
public String getName() {
  return this.name;
}

public int getAge() {
  return this.age;
}
```


## @Setter
`@Setter` 어노테이션은 속성에 대한 setter 메서드를 생성한다.

예제
```java
@Setter
public class User {
  private String name;
  private int age;
}
```
위 코드는 아래와 같은 코드를 생성한다.
```java
public void setName(String name) {
  this.name = name;
}

public void setAge(int age) {
  this.age = age;
}
```

## @ToString
`@ToString` 어노테이션은 객체의 문자열 표현을 생성합니다.

예제
```java
@ToString
public class User {
  private String name;
  private int age;
}
```
위 코드는 아래와 같은 코드를 생성한다.
```java
public String getName() {
  return this.name;
}

public int getAge() {
  return this.age;
}
```

## @Builder
`@Builder` 어노테이션은 객체의 빌더 패턴 구현을 생성합니다.

예제
```java
@Getter
public class User {
  private String name;
  private int age;
}
```
위 코드는 아래와 같은 코드를 생성한다.
```java
@Override
public String toString() {
  return "User(name=" + this.name + ", age=" + this.age + ")";
}
```

## @AllArgsConstructor
`@AllArgsConstructor` 어노테이션은 모든 속성을 파라미터로 갖는 생성자를 생성합니다.

예제
```java
@AllArgsConstructor
public class User {
    private String firstName;
    private String lastName;
    private int age;
    private boolean active;
}
```
위 코드는 아래와 같은 코드를 생성한다.
```java
public User(String firstName, String lastName, int age, boolean active) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
    this.active = active;
}
```
아래와 같이 사용 가능
```java
User user = new User("John", "Doe", 32, true);
```

## @NoArgsConstructor
`@NoArgsConstructor` 어노테이션은 매개변수 없는 기본 생성자를 생성합니다.

예제
```java
@NoArgsConstructor
public class User {
    private Long id;
    private String name;
    private int age;
}
```
위 코드는 아래와 같은 코드를 생성한다.
```java
public User() {}
```

## @JsonFormat
`@JsonFormat` 어노테이션은 JSON 형식으로 데이터를 직렬화할 때 날짜 및 시간 형식을 지정하는 데 사용됩니다.

```java
import com.fasterxml.jackson.annotation.JsonFormat;

public class Example {
  
  private String name;
  
  @JsonFormat(pattern="yyyy-MM-dd")
  private Date date;
  
}
```
`@JsonFormat` 어노테이션을 사용하여 date 필드의 날짜 형식을 "yyyy-MM-dd"로 지정했습니다. 이를 통해 JSON 출력에서이 날짜 필드가 "yyyy-MM-dd" 형식으로 표시됩니다.

## @DateTimeFormat
`@DateTimeFormat` 어노테이션은 날짜 및 시간 형식을 지정하는 데 사용됩니다. 

이 어노테이션은 Spring MVC에서 날짜 및 시간 형식을 지정하는 데 사용되며, 

`@JsonFormat`과 마찬가지로 JSON 형식으로 데이터를 직렬화할 때 날짜 및 시간 형식을 지정하는 데도 사용될 수 있습니다.

```java
@DateTimeFormat(pattern = "yyyy-MM-dd")
private Date date;
```
위와 같이 pattern 속성에 날짜 형식을 지정하면, JSON 변환시 해당 형식으로 변환됩니다.
```java
{"date":"2022-12-31"}
```