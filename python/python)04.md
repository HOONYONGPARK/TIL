# __객체 지향 프로그래밍__

## __프로그래밍을 하는 방법 중 하나__

### __장점__

- 클래스 단위로 모듈화 시켜서 개발이 가능하다! (관련 있는 코드들을 묶어 클래스로 표현 가능)
- 사용자 정의 자료구조처럼 사용한다.
- 프로그램의 유지보수가 쉬워진다!

### __단점__

- 설계시 많은 노력과 시간이 필요하다.
- 실행 속도가 상대적으로 느리다.

---

## __객체__

- 속성과 행동으로 구성된 모든 것들
    - 속성 : 객체를 표현할 수 있는 특징(변수)
    - 행동 : 객체가 동작하는 것(메서드)
- ex) 가수를 객체로 만든다면?
    - 가수를 나타내는 속성 : 가수의 이름, 대표곡 등
    - 가수가 하는 행동 : 노래, 춤, 제스쳐 등

## __클래스와 객체__

- 클래스 : 객체를 어떻게 만들어야 하는지 설명되어 있는 설계도라고 볼 수 있다. (객체가 어떻게 구성되어 있는지 설명한다.)
    - 객체의 속성이 어떤 것들이 있는지..
    - 객체가 하는 행동들이 무엇이 있는지..
    - 가수라는 클래스를 만든다면??
        - 가수의 속성 : 이름, 대표곡
        - 가수의 행동 : 노래하기
    객체 : 클래스(설계도)를 통해서 실제로 만들어낸 사례
        - 이름 : 아이유
        - 대표곡 : 내 손을 잡아
        - 행동 : 노래하기

---
- 인스턴스 : 아이유는 객체다(o) 아이유는 인스턴스다(x)
    - 아이유는 가수라는 클래스의 인스턴스다(o)
- 자동차로 예를 들면?
    - 소나타는 객체다(o) / 소나타는 인스턴스다(x)
    - 소나타는 자동차라는 클래스의 인스턴스다(o)

---

## __클래스를 정의하는 방법__

- class 클래스이름:
    - 들여쓰기를 해서 클래스 범위의 코드를 작성

```
# person 이라는 이름을 가진 클래스
class Person:
    pass

person1 = Person() # 클래스(설계도)를 통해 객체 만듦
# person1은 Person 클래스의 인스턴스다.
```
---
## __객체는? 속성과 행동!__

- 속성에 해당하는 클래스의 변수
    1. 클래스 변수(모든 객체들이 공통으로 가지고 있는 속성)
    2. 인스턴스 변수(인스턴스마다 다르게 가지고 있는 속성)

    ```
    class Car:

    소나타 : 바퀴가 4개, 이름은 소나타
    그랜저 : 바퀴가 4개, 이름은 그랜저
    아반떼 : 바퀴가 4개, 이름은 아반떼

    바퀴 : 클래스 변수
    이름 : 인스턴스 변수
    ```
```
    class Car:
        tire = 4 # 클래스 변수

        def __init__(self, name): # self --> 인스턴스 자기 자신을 뜻하는 파라미터
        # __init__: 클래스를 통해 인스턴스를 만들때 무조건 실행되는 메서드
        self.name = name # 인스턴스 변수를 생성

car1 = Car('아반떼') # 4
car2 = Car('소나타') # 4
car3 = Car('그랜저') # 4
car1.name # 아반떼
car2.name # 소나타
car3.name # 그랜저
```

```
a_car = Car("소나타")
b_car = Car("아반떼")

# 클래스 변수를 수정하고싶다.
# 클래스 변수는 반드시 클래스의 이름을 통해 접근해서 수정한다.
Car.tire = 2
print(a_car.tire) # 2
print(b_car.tire) # 2

# 만약에 클래스 이름이 아니라 인스턴스의(변수) 이름을 가지고 변경
a_car.tire = 6 # a_car 안에 tire 라는 이름을 가진 새로운 인스턴스 변수를 생성하고, 값을 할당
print(a_car.tire) # 6
print(b_car.tire) # 2

# 클래스 변수를 수정할때는 반드시 클래스 이름을 통해서 접근
Car.tire = 4
print("--------")
print(a_car.tire) # 6
print(b_car.tire) # 4

del a_car.tire # a_car 의 인스턴스 변수 tire를 삭제
print("--------")
print(a_car.tire) # 4
print(b_car.tire) # 4

a_car.speed = 100
print(a_car.speed) # 100
```
---
## __메서드(동작, 행동)__

1. 인스턴스 메서드
    1. 인스턴스 변수를 사용하거나 인스턴스 변수에 값을 설정할 수 있는 메서드
    2. 대부분의 클래스 안에 있는 메서드들이 인스턴스 메서드이다!
    3. 호출시 첫번째 인자로 반드시 self가 전달된다.
        - self : 자기 자신을 가리키는 인자
</br>

2. 클래스 메서드
    1. 인스턴스 변수를 사용할 수 없다.
    2. 호출 시 첫번째 인자로 반드시 cls가 전달된다.
        - cls : 클래스를 가리키는 인자

</br>

3. 정적메서드(스태틱메서드)

</br>

---

```
class Car:

    def __init__(self, speed):
        self.speed = speed

    def speed_up(self): # 첫번째 인자로 self 가 전달되었으니 인스턴스 메서드다!!!
        self.speed += 10 # 인스턴스 변수를 변경할 수 있다.

car1 = Car(100)
car2 = Car(80)
print(car1.speed) # 100
car1.speed_up() # car1 의 인스턴스 메서드호출
print(car1.speed) # 110

```
---

### __클래스 메서드__

- 클래스가 사용하는 메서드
- 인스턴스 변수를 수정할 수 없다!!
- 첫번재 인자로 cls(클래스) 자신을 뜻하는 인자가 전달된다.
- 클래스 메서드로 만들고 싶은 메서드의 위에 @classmethod 데코레이터를 추가

```
class Person:
    count = 0 # 클래스 변수

    def __init__(self):
        Person.count += 1 # Person 클래스를 통해서 인스턴스가 생성될 때마다
        # 클래스 변수인 count가 1씩 증가한다.

    @classmethod
    def number_of_population(cls): # cls : 클래스를 뜻하는 인자
        # 클래스 내부에있는 클래스 변수에 접근하기 위해서 cls를 전달받는다.
        print(f"인구수는 {cls.count}입니다.")

person1 = Person()
person2 = Person()
person3 = Person()

# 클래스 메소드는 기본적으로 클래스 이름을 통해 호출한다.
Person.number_of_population()
# 인구수는 3입니다.

# 물론, 인스턴스의 이름(변수 이름)을 통해서 호출이 가능하다.
person1.number_of_population()
# 인구수는 3입니다.
# 하지만 클래스 메소드는 클래스 명으로 호출하는것이 국룰이다!
```

## __클래스 메서드와 인스턴스 메서드의 차이__

- __클래스 메서드 : 클래스 변수 사용가능, 인스턴스 변수는 사용 불가능__
- __인스턴스 메서드 : 클래스 변수 사용가능, 인스턴스 변수도 사용 가능!__

### __스태틱 메서드__

- 인스턴스 변수, 클래스 변수 모두를 사용하지 않는 메서드
    - 언제 사용하는거지??
        - 클래스의 속성을 아예 사용하지 않는 메서드를 정의할 때 쓴다!
        - @staticmethod 데코레이터를 사용해서 정의

```
class Car:
    tire = 4 # 클래스 변수

    def __init__(self, name):
        self.name = name # 인스턴스 변수

    @staticmethod
    def horn(): # cls, self 를 사용할수 없다.
        print("빵빵")

car1 = Car("소나타")

# 인스턴스를 통해 호출
car1.horn() # 빵빵
# 클래스 이름을 통해 호출
Car.horn() # 빵빵
```
- 인스턴스 메서드 : self 매개변수를 통해 인스턴스 변수 수정 가능
- 클래스 메서드 : cls 매개변수를 통해 클래스 변수 수정 가능
- 스태틱 메서드 : 클래스 안에 있는 어떤 변수에도 접근 불가...
    - 객체의 상태나 클래스의 상태를 변경할수 없는 메서드이다.
    - 클래스 변수나 인스턴스 변수를 사용하지 않는 기능(메소드)를 만들때 사용
---

# __객체 지향의 핵심개념 4가지__
## __상추캐다!!__

1. 상 : 상속 = 클래스의 자원을 재사용 할 수 있도록 하는것
    - 부모가 가지고 있던 것들을 내가 다시 만들 필요 없이 처음부터 사용 가능하게 만들어주는것!
2. 추 : 추상화 = 복잡한 것은 숨기고, 필요한 것만 노출시키는 것
3. 캐 : 캡슐화 = 객체 내부의 정보(데이터)들을 보호하기 위해 사용하는 방법
4. 다 : 다형성 = 똑같은 동작을 시켜도 객체에 따라 그 동작 결과가 다르게 나오는것

```
# 상속 예시
class Person:
    def greeting(self):
        print("안녕하세요~~")

class Student(Person): # Student 클래스는 Person 클래스의 기능들을 물려받는다.
    pass

person1 = Person()
person1.greeting() # 안녕하세요~~
student1 = Student()
student1.greeting() # 안녕하세요~~
```

- 다형성은 동일한 이름을 가진 메서드가 클래스(객체)에 따라 다르게 동작하는것.
    - 메서드 오버라이딩(덮어쓰기)로 구현한다.

```
class Animal:

    def make_sound(self):
        print("동물이 소리를 냅니다.")

class Cat(Animal): # Cat 클래스는 Animal 클래스의 기능을 물려받는다.

    def make_sound(self):
        print("야옹")

class Dog(Animal):

    def make_sound(self):
        print("멍멍")

animal1 = Animal()
dog1 = Dog()
cat1 = Cat()
# 똑같은 기능을 가진 메소드를 실행했으나, 클래스에따라 그 결과가 다르게 나온다.
# 다형성
animal1.make_sound() # 동물이 소리를 냅니다.
dog1.make_sound() # 멍멍
cat1.make_sound() # 야옹
```

- 캡슐화 : 객체의 구현 내용에 대해서 외부로부터 직접적인 접근을 차단, 내부의 정보를 보호한다.
- 객체 내부에 숨기고 싶은 정보가 있을 때 캡슐화!
    - 접근제어자 : 접근할 수 있는 범위를 지정한다.
        - public :  어디서나 호출 가능한 메서드, 변수
        - protected : 부모 자식 간에만 호출이 가능한 메서드 , 변수
        - private : 자기 자신만 호출이 가능한 메서드, 변수 외부에서는 절대로 접근이 불가능하다.
        - private 변수는 캡슐화를 통해 보호한다. getter / setter 메서드로 접근 가능
            - getter : 변수에 접근 가능하도록, 변수를 읽어주는 메서드 @property 데코레이터를 통해 선언
            - setter : 변수를 수정 가능 하도록, 변수의 값을 설정하는 메서드 @변수.setter 사용

```
class Person:
    def __init__(self, name): # name 이라는 변수를 외부에서 숨기고싶다.
        self.__name = name # private

    # getter
    @property
    def my_name(self):
        return self.__name

    # setter
    @my_name.setter
    def my_name(self, new_name):
        if len(new_name) > 1:
            self.__name = new_name

person1 = Person("김싸피")
print(person1.my_name) # __name ==> my_name # 김싸피
person1.my_name = "박싸피"
print(person1.my_name) # 박싸피
person1.my_name = "홍" 
print(person1.my_name) # 박싸피
# print(person1.__name) # 외부에서 접근 불가능
```
