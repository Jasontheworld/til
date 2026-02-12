#2026-01-22

## 파이썬 for, if 문에서 dict, list 등 다양한 자료구조를 다루는 방법을 배웠다

---

### 실습 문제 중 어려웠던 것

```python

def rental_book(info):
    for name, age in info.items():
        rental_num = age // 10
        decrease_book(rental_num)
        print(f"{name}님이 {rental_num}권의 책을 대여하였습니다.")

```  

- info 변수로 딕셔너리를 입력 받을 때, 딕셔너리의 key와 value 값을 모두 다른 변수로 할당하는 방법으로 items() 라는 함수를 사용했음
- 근데 items() 라는 함수를 안 뜯어봐서 조만간에 어떤 방식으로 움직이는지 확인 해봐야 할 듯.


### 람다, 맵

```python

def create_user(name, age, address):
    user_info = {}
    increase_user()
    user_info["name"] = name
    user_info["age"] = age
    user_info["address"] = address
    print(f"{name}님 환영합니다!")
    return user_info

    

name = ['김시습', '허균', '남영로', '임제', '박지원']
age = [20, 16, 52, 36, 60]
address = ['서울', '강릉', '조선', '나주', '한성부']

user_list = list(map(lambda x, y, z: create_user(x, y, z), name, age, address ))
print(user_list)
```

- 위에서 **name, age, address** 리스트를 list, map에 넣어서 create_user 함수를 돌려서 user_info에 딕셔너리로 만들어서 리스트에 저장을 했는데 솔직히 아직 직관적으로 이해가 안된다.

#### 제미나이가 설명해준 map, lambda, list comprehension

>  💡 1. 람다(lambda) : "이름 없는 일용직 알바"
>  
>  원래 함수(def)는 정규직 직원이야. 이름도 있고(create_user), 명함도 있지. 근데 lambda는 이름도 없는 **'일용직 알바'**야.
>  
>   - 왜 써? 딱 한 번만 쓰고 버릴 기능을 굳이 정규직으로 채용(정의)하기 귀찮을 때 써.
>   - 구조: lambda x, y, z : 일해라(x, y, z)너의 코드에선: "야, 알바생! 너 x, y, z 3개 받아서 create_user 함수에 던져주고 와!"라는 뜻이야.
>   - 
> 💡 2. 맵(map) : "반복 작업 전문 컨베이어 벨트"
> map은 공장의 컨베이어 벨트야. 리스트에 있는 애들을 하나씩 꺼내서 알바생(lambda)한테 전달해주고, 결과물을 다시 담아주는 역할이지.
> 
> 🔥 너의 코드를 직관적으로 해석하면?Pythonuser_list = list(map(lambda x, y, z: create_user(x, y, z), name, age, address ))
> 이 한 줄은 사실 내부적으로 이렇게 움직여:
> 
> 1. 준비: name, age, address 세 개의 리스트(재료 상자)를 컨베이어 벨트에 올려.
> 2. 가동: 벨트가 돌아가면서 첫 번째 재료인 **'김시습', 20, '서울'**을 쏙 뽑아.
> 3. 알바생 투입: lambda 알바생이 이걸 받아서 create_user('김시습', 20, '서울')를 실행해.
> 4. 결과 보관: 실행 결과(딕셔너리)가 나오면 그걸 바구니에 담아.
> 5. 반복: 다음 재료인 **'허균', 16, '강릉'**으로 똑같이 해. 다 끝날 때까지!
> 6. 마무리: list()가 그 바구니를 예쁜 파이썬 리스트로 포장해줘.
> 
> 👑 Best Practice: 리스트 컴프리헨션사실 파이썬 전문가들은 map + lambda 보다는 아래 방식을 훨씬 좋아해. 이게 훨씬 직관적이거든.Python# zip은 세 리스트를 하나로 묶어주는 역할이야
> 
> ```python
> user_list = [create_user(n, a, d) for n, a, d in zip(name, age, address)]
> ```
> 
> 동료의 한마디: "야 재현아, map은 다른 언어에서도 많이 쓰지만, 파이썬에서는 zip이랑 저 for 문 한 줄짜리가 진짜배기다. 나중에 저걸로 갈아타봐."
