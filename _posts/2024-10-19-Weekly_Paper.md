---
layout: single
title:  "파이썬 클래스(Class)와 인스턴스(Instance)는 무엇인가?"
permalink: /about/
toc: true
toc_sticky: true
toc_label: "MYSELF"
---

# Weekly-Paper with Codeit! Data Analyst_4

### Class란 무엇인가?

**Class** 는 객체를 표현하기 위한 문법으로 볼 수 있습니다.
게임을 예시로 들어 스타크래프트 게임에는 3가지 종족인 테란, 저그, 프로토스가 존재하는데
테란의 기본 유닛인 마린의 특징(속성)과 행동(메서드)을 정의하는 것이 바로 클래스입니다.

마린 클래스는 속성으로 체력, 공격력, 이동속도 등을 정의 할 수 있습니다.
마린은 공격유닛으로 상대방의 유닛을 공격할 수 있으며, 움직이는 이동도 가능합니다.

```python
class Marine: # 마린 클래스 정의
    def __init__(self, health, attack_power, speed):
        self.health = health           # 체력
        self.attack_power = attack_power  # 공격력
        self.speed = speed             # 이동 속도
    
    def attack(self):
        print(f"마린이 {self.attack_power}의 공격력으로 공격합니다!")
    
    def stimpack(self):
        self.health -= 10  # 스팀팩 사용 시 체력 감소
        print("마린이 스팀팩을 사용했습니다! 체력이 10 감소합니다.")
    
    def move(self):
        print(f"마린이 {self.speed}의 속도로 이동하고 있습니다.")
```

위 코드처럼 마린의 클래스를 정의해주면 매번 마린 유닛을 생성할 때 체력, 공격력, 이동속도를 정의해주지 않아도 된다.
또한 공격, 스팀팩(이동속도 및 공격속도 증가), 유닛이동 행동을 함수로 정의하여 함수를 호출하여 쉽게 마린에게 명령을 내릴 수 있다.

### Instance란 무엇인가?

**Instance**는 클래스 안에 존재하는 객체라고 볼 수 있다. 정의된 클래스를 통해 인스턴스 객체를 만들 수 있다.

```python
# 마린의 인스턴스인 마린1, 마린2를 생성
# 각 마린의 기본 스텟(체력:40, 공격력:6, 이동속도:63)
marine1 = Marine(40, 6, 63)  # 첫 번째 마린
marine2 = Marine(40, 6, 63)  # 두 번째 마린

# 마린 클래스에서 정의한 공격 함수를 실행
marine1.attack()  # print: 마린이 6의 공격력으로 공격합니다!
marine2.attack()  # print: 마린이 6의 공격력으로 공격합니다!

# 마린 클래스에서 정의한 스팀팩 함수를 실행
marine1.stimpack()  # print: 마린이 스팀팩을 사용했습니다! 체력이 10 감소합니다.
```
위 코드처럼 한번 선언한 클래스를 통해 클래스에서 선언한 인스턴스를 쉽게 불러올 수 있다.

### 정적 메소드와 호출하는 방법

**Class**에는 크게 3가지의 메소드가 있다.
1. 인스턴스 메소드(Instance Method) : 가장 일반적인 클래스에서 인스턴스를 생성할 때 자기 자신(인스턴스)를
   메소드로 전달하기 때문에 인스턴스 내부의 속성과 메소드에 접근할 수 있다.
   
2. 정적 메소드(Static Method)
   자기 자신을 전달하지 않고, 전달받은 인자로만 행동하는 함수이다. 클래스와 관련된 함수를 만들고 싶지만
   클래스나 인스턴스에 영향이나 의존받고 싶지 않을 때 사용한다.
   
3. 클래스 메소드(Class Method)
   클래스 메소드는 자기 자신을 인자로 전달한다. 클래스 내부의 속성과 인스턴스에 접근할 수 있으며
   인스턴스를 호출하지 않고 호출할 수 있다.

정적 메소드는 클래스의 영향을 받지 않기 때문에 클래스나 인스턴스에 정의된 인자를 입력할 필요가 없다.

```python
@staticmethod
    def minerals_needed():
        return "마린 생성 미네랄 : 50 미네랄"
```

```python
# 정적 메소드를 통해 클래스 이름으로 호출가능
print(Marine.minerals_needed()) # print: 마린 생성 미네랄 : 50 미네랄
```

정적 메소드를 실행하기 위해서는 정의하고 싶은 함수 위에 @staticmethod 를 입력하여 반드시 정적 메소드임을
알려줘야 한다.

위 코드를 통해 마린 1유닛을 생성하기 위해서는 50 미네랄 소요됨을 정적 메소드를 통해 선언할 수 있다.

