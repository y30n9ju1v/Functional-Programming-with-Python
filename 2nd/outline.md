### **파이썬으로 쉽게 풀어쓴 함수형 프로그래밍**

#### **목차**

**1장: 함수형 프로그래밍 개요**

- **1.1 함수형 프로그래밍이란 무엇인가?**
    - 문제 분해와 함수의 역할
    - 명령형(Imperative) vs. 선언형(Declarative) 프로그래밍
    - 객체 지향(Object-Oriented) 프로그래밍과의 관계 및 패러다임 혼합
- **1.2 함수형 프로그래밍의 핵심 원칙**
    - **순수 함수(Pure Functions)와 부수 효과(Side Effects) 제거**
        - 예측 가능성 및 테스트 용이성
        - I/O와 같은 '더러운' 부수 효과 관리 전략
    - **데이터 불변성(Immutability)**
        - 변수 업데이트 대신 새로운 복사본 생성
    - **일급 함수(First-Class Functions)와 고차 함수(Higher-Order Functions)**
        - 함수를 값처럼 다루는 능력
    - 지연 평가(Lazy Evaluation)
- **1.3 함수형 프로그래밍의 장점과 단점**
    - **이점: 모듈성, 디버깅 및 테스트 용이성, 조합성, 명확성, 동시성, 버그 감소**
    - 단점: 순수성 유지의 어려움, 학습 곡선, 잠재적 비효율성

**2장: 파이썬에서 함수형 프로그래밍의 기본 구성 요소**

- **2.1 함수를 값으로 다루기**
    - 파이썬의 함수 객체
    - 람다(Lambda) 표현식: 익명 함수 생성
    - `operator` 모듈: 간단한 연산자 함수 사용
- **2.2 불변 데이터와 효율적인 처리**
    - 파이썬의 불변 타입: 튜플, 문자열, Frozen Set
    - 가변 데이터(리스트, 딕셔너리, 셋)를 불변적으로 다루는 방법
    - 구조적 공유(Structural Sharing) 개념 소개 (외부 정보)
- **2.3 이터레이터와 제너레이터: 데이터 스트림 처리**
    - 이터레이터 개념과 프로토콜 (`__next__`, `StopIteration`)
    - 제너레이터 함수와 `yield` 키워드
    - 제너레이터 표현식(Generator Expressions)과 리스트/딕셔너리/셋 컴프리헨션(List/Dict/Set Comprehensions)
- **2.4 재귀(Recursion): 반복적인 문제 해결**
    - 재귀의 기본 개념: 함수가 자신을 호출하는 방식
    - 기본 사례(Base Case)와 재귀 사례(Recursive Case)
    - 꼬리 호출 최적화(Tail Call Optimization) 부재와 파이썬의 성능 고려사항
    - 메모이제이션(Memoization)을 통한 성능 개선: `functools.lru_cache`

**3장: 파이썬의 고차 함수와 함수형 패턴**

- **3.1 내장 고차 함수 활용**
    - `map()`: 각 요소에 함수 적용
    - `filter()`: 조건에 맞는 요소 선택
    - `functools.reduce()`: 요소를 단일 값으로 집계
    - `sorted()`, `min()`, `max()`, `sum()`, `any()`, `all()`
    - `enumerate()`, `zip()`: 여러 시퀀스 동시 처리
    - **`filter()`, `map()`, `reduce()` 패턴 적용**
- **3.2 `itertools` 모듈: 강력한 이터레이터 도구**
    - 무한/유한 시퀀스 생성 (`count`, `cycle`, `repeat`)
    - 이터레이터 결합 및 복제 (`chain`, `zip_longest`, `tee`)
    - 요소 선택 및 변환 (`islice`, `starmap`, `filterfalse`, `takewhile`, `dropwhile`, `compress`)
- **3.3 `functools` 모듈: 함수 도구 상자**
    - **부분 함수 적용(Partial Function Application): `functools.partial`**
    - **함수 합성(Function Composition)**
        - 파이프라인 처리 (Pipelines)

**4장: 고급 함수형 프로그래밍 개념 및 패턴**

- **4.1 클로저(Closures)**
    - 함수가 외부 환경의 변수를 참조하는 방식
    - 클로저를 이용한 상태 유지 및 불순 함수 생성
    - 클래스(Classes)와 클로저의 비교
- **4.2 커링(Currying)**
    - 여러 인자를 받는 함수를 단일 인자 함수들의 연속으로 변환
    - 파이썬에서의 커링 구현 및 실용적 활용
- **4.3 데코레이터(Decorators)**
    - 고차 함수의 문법적 설탕(Syntactic Sugar)
    - `*args`와 `**kwargs`를 사용한 유연한 함수 장식
- **4.4 Functor, Applicative, Monad 소개**
    - **데이터를 감싸고 함수 적용을 제어하는 Functor**
    - **함수를 감싸고 적용하는 Applicative**
    - **Monad: 복잡한 연산 및 부수 효과 처리 추상화**
        - Haskell과 파이썬에서의 역할 차이
    - **값으로서의 오류 처리(Error Handling as Values)와 Combinator 패턴**
        - 유효성 검사 등 실제 시나리오 적용

**5장: 실용적인 함수형 파이썬 프로그래밍과 애플리케이션**

- **5.1 함수형 프로그래밍 스타일로 애플리케이션 구축**
    - 다양한 프로그래밍 패러다임의 혼합 전략
    - 입출력(I/O) 및 부수 효과를 격리하고 관리하는 방법
    - 함수형 애플리케이션의 모듈성 및 유지보수성
- **5.2 함수형 스타일 디버깅 및 테스트**
    - 순수 함수의 테스트 용이성
    - 문제 격리 및 중간 결과 확인
- **5.3 파이썬 생태계의 함수형 지원 도구**
    - 표준 라이브러리(Standard Library)의 역할
    - `PyMonad`, `OSlash`와 같은 서드파티 라이브러리
    - (선택 사항) 함수형 프로그래밍에 유용한 다른 파이썬 유틸리티 및 패턴
