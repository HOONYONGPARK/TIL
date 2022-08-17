# __그리드 시스템/ 반응형 웹__

## __CSS Layout__

### css 원칙
- 모든것이 네모이고 위에서부터 아래로, 왼쪽부터 오른쪽으로 쌓인다.
---

- float
    - 박스를 왼쪽 혹은 오른쪽으로 이동시켜서 텍스트를 포함 주변 요소들이 주변을 감싸도록 한다.
    - 요소가 normal flow를 벗어나도록 함
    - float의 속성
        - None : 기본값
        - left : 요소를 왼쪽으로 띄움
        - right : 요소를 오른쪽으로 띄움


- flexbox
    - 행과 열 형태로 아이템들을 배치하는 1차원 모델
    - 축
        - main axis (메인축)
        - cross axis (교차축)
    - 구성요소
        - flex container
        - flex item

    - flex 속성 : flex-direction
        - main axis 기준 방향설정
        - 역방향은 HTML 태그 선언 순서와 시각적으로 다르니 유의

    - flex 속성 : flex-wrap
        - 아이템이 컨테이너를 벗어나는 경우 해당 영역 내에 배치되도록 설정
        - 기본적으로 컨테이너를 벗어나지 않도록 함
    - flex 속성 : justify-content & align-content
        - start
        - end
        - cnter
        - space-between
        - space-around
        - space-evenly


# __Bootstrap__

## __bootstrap 기본원리__

- sapcing
    - {property}{sides}-{size}
        - ex)mt-3
    - .mx0 ? : 가로 마진이 0!
    - .mx-auto : 수평 중앙 정렬, 가로 가운데 정렬
    - .py-0 ? : 위아래 padding이 0

- color
- position
- components
- form
- Navbar


## __Grid system__

- 기본적으로 그리드시스템은 12칸임
- 부트스트랩의 그리드 시스템
- 요소(태그)들의 디자인과 배치에 도움을 주는 시스템
- style 태그 또는 css파일을 통해서 클래스 이름을 정하고, 어떤 속성을 지정할지
- 간단하게 정의된 클래스 이름만 가지고 css를 적용시킬 수 있다.
- 그리드 시스템을 구성하는 요소
    - column : 실제로 내용물을 포함하는 부분(아이템)
    - Gutter : 컬럼과 컬럼사이의 공간 (빈 간격)
    - container : 컬럼들을 담고있는 공간
        - 범위를 넓게해서 div 태그를 통해 사용

- 부트스트랩의 그리드 시스템을 이용하는 방법
    - container, row, col ==> 이 세가지 클래스를 이용해 배치하고 정렬할 수 있다.
    - 12개의 column을 한줄로 표현한다. ==> 한줄을 12칸으로 나누어 표현한다.
    - 6개의 breakpoint ==> 사용자가 보는 브라우저의 화면 크기에 따라서 다르게 표현가능

```
row 클래스를 가진 div안에서 사용
{property}-{breakpoint}-{size}
col-md-4 col : item 역할 (컬럼)
md : 중간사이즈이상의 브라우저
4 : 12칸중에 4칸을 차지하도록

부트스트랩의 그리드시스템도 flex 기반으로 되어있기때문에, 정렬 기능 사용가능

가로 가운데 정렬 : justify-content-center (정렬대상 아이템이 아닌 row div에다가 클래스를 설정)
세로 가운데 정렬 : align-items-center (정렬대상 아이템이 아닌 row div에다가 클래스를 설정)
아이템 자체 정렬 : align-self-center , align-self-start, align-self-end (정렬 대상 col div에다가 설정)
```
    ---

    ## align-items, align-content의 차이


