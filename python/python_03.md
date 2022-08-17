# __함수 메서드 정리__

## __데이터 구조 활용__

- 데이터 구조를 활용하기 위해서는 메서드(method)를 활용
    - 메서드는 클래스 내부에 정의한 함수, 사실상 함수 동일
    - 쉽게 설명하자면 객체의 기능
    - 데이터구조.메서드() 형태로 활용!!
    - 어렵게 느껴진다면 주어.동사() 느낌

## __순서가 있는 데이터 구조__


### __문자열 메서드__

- s.find(x) : x의 첫번째 위치를 반환, 없으면 -1을 반환
- s.index(x) : x의 첫번째 위치를 반환, 업으면 오류 발생!
- s.isalpha() : 알파벳 문자 여부 (단순 알파벳이 아닌 유니코드 상 leeter )
- s.isupper() : 대문자 여부
- s.islower() : 소문자 여부
- s.istitle() : 타이틀 형식 여부

- 문자열 관련 검증 메서드
    - isdecimal() <= isdigit() <= isnumeric()

- ### __문자열 변경 메서드__

    - s.replace(old, new [,count]) : 바꿀 대상 글자를 새로운 글자로 바꿔서 반환
    - s.strip([chars]) : 공백이나 특정 문자를 제거
    - s.split(sep = None, maxsplit = -1) : 공백이나 특정 문자를 기준으로 분리
    - 'seperator'.join([iterable]) : 구분자로 iterable을 합침
    - s.capitalize() : 가장 첫번째 글자를 대문자로 변경
    - s.title() : 문자열 내 띄어쓰기 기준으로 각 단어의 첫글자는 대문자로, 나머지는 소문자로 변환
    - s.upper() : 모두 대문자로 변경
    - s.lower() : 모두 소문자로 변경
    - s.swapcase() : 대, 소문자 서로 변경
    
- 문자열은 immutable인데, 문자열 변경이 되는 이유?
    - 기존의 문자열을 변경하는게 아니라, 변경된 문자열을 새롭게 만들어서 반환
        - ex) replace, strip, title 등

    
## __리스트 메서드__

- L.append(x) : 리스트 마지막에 항목 x 추가
- L.insert(i, x) : 리스트 인덱스 i에 x 삽입
- L.remove(x) : 리스트 가장 왼족에 있는 항목(첫 번째) x를 제거 항목이 존재하지 않을 경우, ValueError
- L.pop() : 리스트 가장 오른쪽에 있는 항목(마지막)을 반환 후 제거
- L.pop(i) : 리스트의 인덱스 i에 있는 항목을 반환 후 제거
- L.extend(m) : 순회형 m의 모든 항목들의 리스트 끝에 추가 (+= 과 같은 기증)
- L.index(x, start, end) : 리스트에 있는 항목 중 가장 왼쪽에 있는 항목 x의 인덱스를 반환
- L.reverse() : 리스트를 거꾸로 정렬
- L.sort() : 리스트를 정렬(매개변수 이용가능)
- L.count(x) : 리스트에서 항목 x가 몇개 존재하는지 갯수를 반환

## __튜플 메서드__

- 튜플은 변경할 수 없기 때문에 영향을 미치지 않는 메서드만을 지원한다.
- 리스트 메서드 중 항목을 변경하는 메서드 빼고 대부분 동일

## __연산자__

- 멤버십 연산자
    - in, not in : 포함 여부 확인
- 시퀀스형 현산자 
    - 산술연산자(+) : 시퀀스 간의 concentration(연결/ 연쇄)
    - 반복연산자(*) : 시퀀스 반복


## __셋 메서드__

- s.copy() : 셋의 얕은 복사본을 반환
- s.add(x) : 항목 x가 셋에 없다면 추가
- s.pop() : 셋 s에서 랜덤하게 항목을 반환하고, 해당 항목을 제거 / set이 비어있을 경우 KeyError
- s.remove(x) : 항목 x를 셋 s에서 삭제 항목이 존재하지 않을 경우 KeyError
- s.discard(x) : 항목 x가 셋s에 있는 경우, 항목 x를 셋 s에서 제거
- s.update(t) : 셋 t에 있는 모든 항목 중에서 셋 s에 없는 항목을 추가
- s.clear() : 모든 항목을 제거
- s.isdisjoint(t) : 셋 s가 셋 t의 서로 같은 항목을 하나라도 갖고 있지 않은 경우, True 반환(서로소)
- s.issubset(t) : 셋 s가 셋 t의 하위셋인 경우, True 반환
- s.issuperset(t) : 셋 s가 셋 t의 상위셋인 경우, True 반환


## __딕셔너리 메서드__

- d.clear() : 모든 항목을 제거
- d.copy() : 딕셔너리 d의 얕은 복사본을 반환
- d.keys() : 딕셔너리 d의 모든 키를 담은 뷰를 반환
- d.values() : 딕셔너리 d의 모든 값을 담은 뷰를 반환
- d.items() : 딕셔너리 d의 모든 키-값의 쌍을 담은 뷰를 반환
- d.get(k) : 키 k의 값을 반환하는데, 키 k가 딕셔너리 d에 없을경우 None 반환
- d.get(k, v) : 키 k의 값을 반환하는데, 키 k가 딕셔너리 d에 없을 경우 v 반환
- d.pop(k) : 키 k값을 반환하고 키 k인 항목을 딕셔너리 d에서 삭제하는데, 키 k가 딕셔너리 d에 없을 경우 KeyError 발생
- d.pop(k, v) :  키 k값을 반환하고 키 k인 항목을 딕셔너리 d에서 삭제하는데, 키 k가 딕셔너리 d에 없을 경우 v 반환
- d.update([other]) : 딕셔너리 d의 값을 매핑하여 업데이트



## __얕은 복사와 깊은 복사__

### 깊은 복사가 일어나는 파이썬의 자료형들

1. int
2. float
3. string
4. blooean

### 얕은 복사가 일어나는 파이썬의 자료형들

1. list
2. dictionary
3. set

### 수정 불가능 !

1. tuple




```
# int
a = 1
b = a
b = 2
print(a, b)
```
1 2

```
# float
a = 1.0
b = a
b = 2.0
print(a, b)
```
1.0 2.0

```
# string
a = 'a'
b = a
b = 'b'
print(a, b)
```
a b

```
# boolean
a = True
b = a
b = False
print(a, b)
```
True False

```
# list
a = [1]
b = a
b[0] = 2
print(a, b)
```
[2] [2]

```
# dictionary
a = {'key': 'value'}
b = a
b['key'] = 'b'
print(a, b)
```
{'key': 'b'} {'key': 'b'}

```
# set
a = {1}
b = a
b.add(2)
print(a, b)
```
{1, 2} {1, 2}

```
# tuple
a = (1)
b = a
b[0] = 2
print(a, b)
```
- TypeError 


```
def func(arr):
    arr[0] = 'd'
    
    
def func2(arr):
    print(arr[0])
    
    
tmp = ['a', 'b', 'c']

print(tmp)
func(tmp)
print(tmp)
```
- ['a', 'b', 'c']
- ['d', 'b', 'c']


```
def change_variable(n):
    n = 'c'
    return n


def change_list(arr):
    arr[0] = 'c'
    
    
a = 'a'
a = change_variable(a)
print(a)


a_list = ['a']
change_list(a_list)
print(a_list)
```
- c
- ['c']