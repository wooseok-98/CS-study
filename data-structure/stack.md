# 🖥 Stack (스택)
---
## 특징
- **선형** 자료구조 (Linear Data Structure)
- 데이터의 삽입과 삭제가 **한 방향(top)** 에서만 진행
- **LIFO(Last In Fisrt Out)**: 최근에 삽입된 데이터가 먼저 나오는 구조

---
## 주요 연산
| 연산 | 설명 |
|-----|-----|
| push | 스택의 top에 원소를 삽입 |
| pop | 스택의 top에 있는 원소를 삭제하고 반환 |
| peek | 스택의 top에 있는 원소를 반환 |
| isEmpty | 스택이 비어있는지 확인 |

---
## Stack 구현
Python에서는 **list 사용**하여 stack 구현
```python
stack = []

# push
stack.append(10)
stack.append(20)
stack.append(30)

print("Stack:", stack)

# peek
print("Top:", stack[-1])

# pop
print("Pop:", stack.pop())

print("Stack:", stack)

# isEmpty
print("Is Empty:", len(stack) == 0)
```
---
## Stack 시간 복잡도
| 연산 | 시간 복잡도 |
|-----|-----|
| push | O(1) |
| pop | O(1) |
| peek | O(1) |
| 탐색 | O(n) |

--- 
## Stack 활용
- 인터럽트 루트 처리
- 웹 브라우저 뒤로가기 기능
- 실행 취소 (undo) 기능
- 수식 괄호식 검사
- **DFS** (Depth-First Search)
- **함수 호출 관리** (Call Stack)
    - 프로그램에서 함수 호출은 **Call Stack**을 이용하여 관리
    1. 함수 호출 시 **Stack Frame 생성**
    2. Stack Frame에 정보 **(지역 변수, 매개 변수, 복귀 주소)** 저장
    3. 함수 실행 종료 시 Stack Frame **pop**
    4. 저장된 **복귀 주소**로 복귀
    5. 프로그램 계속 진행
---
## 💡 핵심 정리
- Stack은 LIFO 구조의 선형 자료구조
- 삽입/삭제는 top에서만 발생
- push / pop / peek 연산
- 삽입 / 삭제 O(1)

---

# 📝 면접 예상 질문

<details> <summary>Q. Stack이란 무엇인가요?</summary>

Stack은 데이터의 삽입과 삭제가 한 방향에서만 이루어지는 선형 자료구조이며
LIFO(Last In First Out) 구조를 가진 자료구조입니다.

</details> <details> <summary>Q. Stack의 주요 연산에는 무엇이 있나요?</summary>
Stack의 주요 연산은 다음과 같습니다.
push : 데이터를 스택에 삽입
pop : 데이터를 스택에서 제거
peek : top 데이터를 확인
isEmpty : 스택이 비어있는지 확인

</details> <details> <summary>Q. Stack이 사용되는 대표적인 예시는 무엇인가요?</summary>

대표적인 사용 예는 다음과 같습니다.
함수 호출 관리 (Call Stack)
DFS 탐색
괄호 검사
웹 브라우저 뒤로가기
실행 취소(Undo)

</details> <details> <summary>Q. Stack을 Array로 구현할 수 있나요?</summary>

가능합니다. 배열을 사용하면 push와 pop 연산을 배열의 끝에서 수행할 수 있습니다.
Python에서는 list를 사용하여 Stack을 구현할 수 있으며
append() 와 pop() 연산을 이용하면 됩니다.

</details> <details> <summary>Q. Stack과 Queue의 차이는 무엇인가요?</summary>

Stack은 LIFO(Last In First Out) 구조이고
Queue는 FIFO(First In First Out) 구조입니다.

Stack은 나중에 들어온 데이터가 먼저 나오고
Queue는 먼저 들어온 데이터가 먼저 나옵니다.

</details>
