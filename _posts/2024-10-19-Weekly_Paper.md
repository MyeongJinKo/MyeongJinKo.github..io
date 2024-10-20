---
layout: single
title:  "파이썬 클래스(Class)와 인스턴스(Instance)는 무엇인가?"
---

# What is "Class" in Python

**Class** 는 객체를 표현하기 위한 문법으로 볼 수 있습니다.
게임을 예시로 들어 스타크래프트 게임에는 3가지 종족인 테란, 저그, 프로토스가 존재하는데
테란의 기본 유닛인 마린의 특징(속성)과 행동(메서드)을 정의하는 것이 바로 클래스입니다.

마린 클래스는 속성으로 체력, 공격력, 이동속도 등을 정의 할 수 있습니다.
마린은 공격유닛으로 상대방의 유닛을 공격할 수 있으며, 움직이는 이동도 가능합니다.

'''python
<pre>
<code>
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
</code>
</pre>
'''

위 코드처럼 마린의 클래스를 정의해주면 매번 마린 유닛을 생성할 때 체력, 공격력, 이동속도를 정의해주지 않아도 된다.
또한 공격, 스팀팩(이동속도 및 공격속도 증가), 유닛이동 행동을 함수로 정의하여 함수를 호출하여 쉽게 마린에게 명령을 내릴 수 있다.

# What is "Instance" in Python

**Instance**는 클래스 안에 존재하는 객체라고 볼 수 있다. 정의된 클래스를 통해 인스턴스 객체를 만들 수 있다.

'''python
<pre>
<code>
# 마린의 인스턴스인 마린1, 마린2를 생성
# 각 마린의 기본 스텟(체력:40, 공격력:6, 이동속도:63)
marine1 = Marine(40, 6, 63)  # 첫 번째 마린
marine2 = Marine(40, 6, 63)  # 두 번째 마린

# 마린 클래스에서 정의한 공격 함수를 실행
marine1.attack()  # print: 마린이 6의 공격력으로 공격합니다!
marine2.attack()  # print: 마린이 6의 공격력으로 공격합니다!

# 마린 클래스에서 정의한 스팀팩 함수를 실행
marine1.stimpack()  # print: 마린이 스팀팩을 사용했습니다! 체력이 10 감소합니다.
</code>
</pre>
'''
위 코드처럼 한번 선언한 클래스를 통해 클래스에서 선언한 인스턴스를 쉽게 불러올 수 있다.

