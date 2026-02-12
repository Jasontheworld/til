# Basic Syntax

- '표현식'을 계산해서 '값'을 얻는다
- 변수: 값을 나중에 다시 사용하기 위해, 그 값에 붙여주는 이름
- 할당문 Variable = expression 오른쪽을 먼저 읽는다
- 재할당: 이미 값이 할당된 변수에 새로운 값을 다시 할당

> - 객체: 데이터(값, 타입, 행동)의 실체
> - 메모리 주소: 객체가 저장된 고유한 위치
> - 변수: 객체를 가리키는 이름표

-데이터 타입: 값의 종류와 그 값으로 할 수 있는 동작(연산)을 결정하는 속성
  - Numeric Types: int float complex
  - Text Sequence Type: str
  - Sequence Types: list, tuple, range
  - Non-sequence Types: set, dict
  - 기타: Boolean, None, Functions

- 시퀀스 타입 특징
  - 인덱싱: my_data[1]
  - 슬라이싱: my_data[1:4]
  - 길이: len(my_data)
  - 반복: for char in my_data
 
-  문장: 특정 동작(action)을 지시하는 실행 가능한 코드의 최소 단위
  - 할당문(x = 100), 정의문(def my_function()), 제어문(pass, break,...)등
 
- 표현식은 값이 남는다. 문장은 값 안남음. 지시임
- 대부분 문장은 표현식을 포함 total_price =(문장) 500+150(표현식)

---

## basic syntax 2

- 리스트

- 인덱싱 슬라이싱 [a, b]

- 튜플: (a, b)
  - 내용 수정, 추가, 삭제 불가능
- range: 연속된 정수 시퀀스를 생성하는 변경 불가능한 자료형
  - range(start, stop, step)

- 딕셔너리: 키, 밸류 쌍 {a : b, c : d}  
  - key는 고유해야 함. 변경 불가능한 자료형(str, int, float, tuple)만 가
 
- 세트: {a, b}
  - 수학의 집합과 동일
