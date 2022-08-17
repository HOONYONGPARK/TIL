# 조건문, 반복문, 함수, 모듈

## __조건문__

- 조건문은 참/거짓을 판단할 수 있는 조건식과 함께 사용
- 기본형식
    ```
    num = int(input('숫자 입력: '))
    if num % 2: # if num % 2 == 1:
        print('홀수입니다')
    else:
        print('짝수입니다')
    ```
- 복수 조건문
    - 복수 조건문을 활용할 경우 elif 활용

- 중첩 조건문
    - 조건문은 다른 조건문에 중첩되어 사용 가능
        - 들여쓰기에 유의해야함.

- 조건 표현식
    - 조건 표현식을 일반적으로 조건에 따라 값을 정할 때 사용
    - 삼항 연산자로 부르기도함
        ```
        true인 경우 값 if 조건 else false인 경우 값

        value = num if num >= 0 else -num
        # 절대값을 저장하기 위한 코드

        num = 2
        result = '홀수입니다.' if num % 2 else '짝수입니다.'
        ```

## __반복문__

- ### __반복문의 종류__

    - while문
        - 종료 조건에 해당하는 코드를 통해 반복문을 종료시켜야함
    - for문
        - 반복 가능한 객체를 모두 순회하면 종료 (별도의 종료 조건이 필요없음)
    - 반복 제어
        - break, continue, for-else

- while문
    - 조건식이 참인 경우 반복적으로 코드를 실행
    - 코드 블록이 모두 실행되고 다시 조건식을 검사하며 반복적으로 실행됨
    - while문은 무한 루프를 하지 않도록 종료 조건이 반드시 필요

- for문
    - for문은 시퀀스(str, tuple, list, range)를 포함한 순회 가능한 객체의 요소를 모두 순회
        - 처음부터 끝까지 모두 순회하므로 별도의 종료 조건이 필요하지 않음

    - iterable
        - 순회할 수 있는 자료형(str, list, dict, tuple, range, set 등)
        - 순회형 함수 (range, enumerate)

    - enumerate 순회
        - 인덱스와 객체를 쌍으로 담은 열거형(enumerate)객체 반환
            - (index, value)형태의 tuple로 구성된 열거 객체를 반환
            ```
            members = ['도현', '훈용', '현영']
            print(list(enumerate(members)))
            # [(0, '도현'), (1, '훈용'), (2, '현영')]
            print(list(enumerate(members, start =)))
            # [(1, '도현'), (2, '훈용'), (3, '현영')]
            ```

    - List comprehension
        - 표현식과 제어문을 통해 특정한 값을 가진 리스트를 간결하게 생성하는 방법
        - [code for 변수 in iterable]
        - [code for 변수 in iterable if 조건식]
        ```
        # 1~3의 세제곱 리스트 만들기
        cubic_list = []
        for num in range(1, 4):
            cubic_list.append(num ** 3)
        print(cubic_list)
        # [1, 8, 27]

        cubic_list = [num ** 3 for num in range(1, 4)]
        print(cubic_list)
        # [1, 8, 27]
        ```

    - Dictionary comprehension
        - {key : value for 변수 in iterable}
        - {key : value for 변수 in iterable if 조건식}
        ```
        # 1 ~ 3의 세제곱 딕셔너리 만들기
        cubic_dict = {}
        for number in range(1, 4):
            cubic_dict[number] = number ** 3
        print(cubic_dict)
        # {1 : 1, 2 : 8, 3 : 27}

        cubic_dict = {number: number ** 3 for number in range(1,4)}
        print(cubic_dict)
        # {1 : 1, 2 : 8, 3 : 27}
        ```

- 반복문 제어
    - break
        - 반복문 종료
    - continue
        - continue 이후의 코드 블록은 수행하지 않고, 다음 반복을 수행
    - for-else
        - 끝까지 반복문을 실행한 이후에 else문 실행
            - break를 통해 중간에 종료되는 경우 else문은 실행되지 않음
    - pass
        - 아무것도 하지 않음(문법적으로 필요하지만, 할일이 없을때 사용)

## __함수__

- 입력으로 (재료) 데이터, 값을 주고 값을 처리(몸체, 기능) 한 다음에 결과를 반환하는 코드 조각,모음

- 특정한 기능들을 수행하는 코드들을 모아서 함수로 정의한 다음에 다음에 똑같은 기능을 수행하는 코드들이 필요할때 함수를 사용해서 코드를 다시 쓰는(중복 xx)일을 줄일수 있다 ===> 코드의 재사용을 위해서 함수를 사용한다.

- 추상화 ===> 자세한 구현은 몰라도 특징적인 키워드 ,기능, 이름을 통해서 함수가 하는 일을 알수 있게 한다.

- 다른사람이 내가 작성한 함수를 사용할때 기능이 자세하게 어떻게 동작하는지 몰라도 함수의 이름을 통해서 함수가 어떤 기능을 하는지 알 수 있다.

- print() ==> 파이썬 내부에서 어떻게 동작을 하는지는 모른다. ==> 콘솔에 우리가 원하는 데이터를 출력해주는 함수이다.

- 함수를 정의한다.(생성한다.) : 함수를 생성할떄는 def 라는 키워드를 사용한다.
    - def 함수이름(매개변수):
    

## __인수를 받는 함수를 생성__

### __인수 매개변수__

- 매개변수(파라미터 Parameter): 함수 정의시 사용하는 이름, 함수 내부에서 사용
- 인수(알규먼트 Argument): 함수 호출시(사용시) 사용하는 이름, 함수 외부에서 사용
    ```
    def echo(string): # string == 파라미터
        return string # 함수 내부에서 파라미터를 사용한다.

    str1 = "이것은 문자열"

    echo(str1) # str1 == 인수 , argument 아규먼트
    ```

- 위치 인수
    - 기본적으로 함수 호출시 인수는 위치에 따라 함수 내부에 전달된다.
    
    - 인수를 함수 호출할때 사용하려면 인수의 위치에 따른 함수 내부에서의 의미를 꼭 알고 있어야 한다. (각 위치의 의미를 알아야 한다.)
    ```
    def menu(drink, entree, dessert):
        return { "음료":drink , "메인음식" : entree, "디저트" : dessert } # 딕셔너리를 반환

    today_menu = menu("콜라" , "치킨" , "도넛") # menu 라는 함수의 결과를 today_menu라는 변수에 저장
    print(today_menu)
    # {'음료': '콜라', '메인음식': '치킨', '디저트': '도넛'}
    print(type(today_menu))
    # <class 'dict'>

    yesterday_menu = menu("스테이크" , "와인" , "푸딩") # 위치 인수는 인수의 순서가 바뀌게 되면 의도하지 않은 결과가 발생하게 된다.
    # 해당 함수의 인수의 위치에 대해서 잘 알고 있어야 함수를 제대로 동작시킬수 있다.
    print(yesterday_menu)
    # {'음료': '스테이크', '메인음식': '와인', '디저트': '푸딩'}
    ```

    ### __애스터리스크(Asterisk), 언패킹연산자__
    

    - 애스터리스크 혹은 언패킹연산자라고 불리는 *
    - 가변인자(*args): 크기가 변하는 인자
        - 여러개의 위치인수를 하나의 파라미터로 받아서 사용
        - 함수를 호출할 때 인수를 몇개로 받는지를 모르는 함수를 정의할 때 유용하다.

    - 패킹? 언패킹?

        - 패킹: 여러개의 데이터를 묶어서 하나의 변수에 (컨테이너: 리스트, 튜플, 딕셔너리, ...)할당한다.
        - 언패킹: 컨테이너 속의 요소들을 여러개의 변수에 나누어서 할당
        - __패킹/언패킹 할시에 변수의 개수와 할당(분해)하고자 하는 컨테이너의 요소의 개수가 동일해야한다.__
        ```
        numbers = (1,2,3,4,5)
        print(numbers)
        #(1,2,3,4,5)

        # 언패킹, 컨테이너에 들어가 있는 값을 분해해서 여러개의 변수에 할당
        a,b,c,d,e = numbers
        print(a,b,c,d,e)
        # 1 2 3 4 5
        ```

        - 함수에서 패킹/언패킹 연산자 * 사용하기
        ```
        def function(*args):
            # args는 파라미터의 이름 * 이 붙어서 여러개로 들어온 파라미터들을 하나로 묶어서 args라는 이름으로 사용하겠다는 의미

            function(1,2,3,4,5,'6')
            print(args)
            print(type(args))

            # (1, 2, 3, 4, 5, '6')
            # <class 'tuple'>
            ```


    - 총합을 구하고 싶은데 합을 구하려고 하는 수의 갯수를 모를때
        ```
        def sum_all(*numbers) : # numbers 에는 몇개가 인수로 전달될지 모르는 상황
        # 총합을 구한다.
            result = 0
            for num in numbers: # numbers 에는 몇개가 있는지는 모르겠으나 값이 들어 있을것이다.
                result += num
            return result

        print(sum_all(1,2,3)) # 값이 3개 6
        print(sum_all(1,2,3,4,5,6)) # 값이 6개 21
        print(sum_all(1,2,3,4,5,6,7,8,9)) # 값이 9개 45
        ```

    - 가변인자는 혼용 가능하다.
    ```
    # 가변인자는 혼용가능하다. 보통인자와 같이 사용할수 있다.
    def family(father, mother, *others):
        print("아버지 : " + father)
        print("어머니 : " + mother)
        print("다른 사람들 : ")
        for name in others: # 다른사람들이 몇명이 오든지간에 처리할수 있도록 반복문을 사용
            print(name)

    family("파더" , "마더" , "남동생" , "누나")
    family("파더")
    # 아버지 : 파더
    # 어머니 : 마더
    # 다른 사람들 : 
    # 남동생
    # 누나
    ```

    - 가변 키워드 인자(**kwargs)
        
        - 키워드 인자를 몇개 입력받을지 모르는 상태에서 함수를 정의할때 사용한다.
        - 키워드 인자 kwargs 딕셔너리처럼 묶어서 처리된다.
        - 파라미터에 사용한다.

        ```
        def family(**kwargs): # 가변 키워드 인자는 딕셔너리처럼 사용이 가능하다.
        result = {}
        for key, value in kwargs.items(): # 딕셔너리의 (키,값) 쌍을 사용가능하다.
            # return {key : value} # return 문장을 함수 내부에서 만나게 되면 바로 함수를 종료시킨다.
            result.update({key : value}) # update 함수를 통해 딕셔너리를 계속 병합시킨다.
         return result

        # family(father="아부지" , mother="아무니" , son="아들")
        print(family(father="아부지" , mother="어무니" , son="아들" , son2="둘째아들"))
        {'father': '아부지', 'mother': '어무니', 'son': '아들', 'son2': '둘째아들'}
        ```


# __파이썬의 범위 (Scope 스코프)__

### __LEGB rule__

- L: Local scope: 지역범위
- E: Enclosed scope: 지역범위 한단계 위의 범위
- G: Global scope : 최상단에 위치한범위(파이썬 파일 전체.py)
- B:  Built-in scope : 모든것을 담고있는 범위(정의하지 않아도 사용할수 있는 것들)
    - print()
        - def print(): 를 하지 않았지만 사용 가능한 것들

```
a = 0 # global scope
b = 1 # global scope 
# global scope 는 함수 내부에서 선언하지 않은 변수들이다.

def enclosed():
    a = 10
    c = 3
    def local(c):
        print(a,b,c) # 10 1 300
    local(300)
    print(a,b,c) # 10 1 3

enclosed()
print(a,b) # 0 1
```

- global x : 함수 안에서 함수 밖의 변수를 수정할때 사용

- global : 해당 식별자 이름이 global범위에 존재한다.

- global 문을 사용해서 global 변수를 사용하겠다고 선언하기 전에 같은 이름을 이용해서 변수를 정의했다면 사용이 불가능, 파라미터로 사용된 이름을 global로 선언하는것도 불가능하다.

```
nonlocal

global을 제외하고 가장 가까운(둘러싸고 있는, 들여쓰기로 구분된 scope의 변수를 연결하도록 한다.)

global과 마찬가지로 nonlocal 로 선언할 변수는 그 전에 (그위에서) 값을 할당하면 사용할수 없다.

nonlocal은 이름공간에 존재하는 변수만 사용가능하다.
global은 해당 이름을 가진 변수를 생성한적이 없다면 새로 만든다.
nonlocal 은 새로 생성하지 않는다.

def func1():
    global out
    out = 3

# out 이라는 변수는 global scope에서 생성한적이 없다.
func1()
print(out) # 3


# y = 10

def func1():
    def func2():
        nonlocal y # y라는 변수를 우리가 생성한적이 없다. ==> 에러 발생
        y = 2
    func2()

func1() # SyntaxError: no binding for nonlocal 'y' found
```

- 함수에서 선언된 변수는 기본적으로 local scope이다.
- 함수가 종료되면 사라지는 순간적인(휘발성)데이터 값
- 함수가 끝나면(호출이 끝나면) 다시 사용할 수 없다.

    - 해당 scope에 변수가 존재하지 않을 경우, L-E-G-B 순으로 이름을 검색한다. 대신 수정은 불가능한데 , global , nonlocal 키워드를 통해 할 수는 있다.

        - 코드가 복잡해지고, 변수 이름 추적이 어려워지기 때문에 사용을 지양해야한다.
        - argument, return 값을 이용해서 그 역할을 대신 코드로 구현해서 사용


