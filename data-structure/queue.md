# 🖥 Queue (큐)
---
## 특징

- **선형** 자료구조 (Linear Data Structure)
- **삽입은 rear(tail)** 에서, **삭제는 front(head)** 에서 진행
- **FIFO(First In First Out)**: 먼저 들어온 데이터가 먼저 나오는 구조

---


## Queue 주요 연산

| 연산 | 설명 |
|-----|-----|
| enqueue | 큐의 rear에 원소 삽입 |
| dequeue | 큐의 front에 있는 원소 삭제 및 반환 |
| peek | front에 있는 원소 조회 |
| isEmpty | 큐가 비어있는지 확인 |

---

## Queue 구현

Python에서는 `collections.deque`를 사용하여 queue 구현

```python
from collections import deque

queue = deque()

# enqueue
queue.append(10)
queue.append(20)
queue.append(30)

print("Queue:", queue)

# peek
print("Front:", queue[0])

# dequeue
print("Dequeue:", queue.popleft())

print("Queue:", queue)

# isEmpty
print("Is Empty:", len(queue) == 0)
```
---
## Queue 시간 복잡도
| 연산 | 시간 복잡도 |
|-----|-----|
| enqueue | O(1) |
| dequeue | O(1) |
| peek | O(1) |
| 탐색 | O(n) |

---
## Queue 활용
- process ready queue
- CPU scheduling
- Cache 구현
- Event loop
- 키보드 입력 버퍼
- BFS
    1. 시작 노드 queue 삽입
    2. deque
    3. 해당 노드와 연결된 노드들 queue 삽입
    4. 과정 반복
---
## 💡 핵심 정리
- Queue는 FIFO 구조의 선형 자료구조
- 삽입은 rear, 삭제는 front에서 발생
- enqueue / dequeue 연산
- 삽입 / 삭제 O(1)

---
# 📝 면접 예상 질문
<details> <summary>Q. Queue란 무엇인가요?</summary>

Queue는 데이터의 삽입과 삭제가 서로 다른 방향에서 이루어지는 선형 자료구조이며
FIFO(First In First Out) 구조를 가지는 자료구조입니다.

</details> <details> <summary>Q. Queue의 주요 연산에는 무엇이 있나요?</summary>

Queue의 주요 연산은 다음과 같습니다.

enqueue : 데이터를 삽입
dequeue : 데이터를 제거
peek : front 데이터 확인
isEmpty : 큐가 비어있는지 확인
</details> <details> <summary>Q. Queue와 Stack의 차이는 무엇인가요?</summary>

Queue는 FIFO 구조이고
Stack은 LIFO 구조입니다.

Queue는 먼저 들어온 데이터가 먼저 나오고
Stack은 나중에 들어온 데이터가 먼저 나옵니다.

</details> <details> <summary>Q. Queue는 어디에 사용되나요?</summary>

Queue는 다음과 같은 곳에서 사용됩니다.

CPU 스케줄링
네트워크 패킷 처리
이벤트 처리 시스템
BFS 탐색
</details> <details> <summary>Q. Array 기반 Queue의 문제점은 무엇인가요?</summary>

Array 기반 Queue는 dequeue 연산 시
front가 이동하면서 공간 낭비가 발생할 수 있습니다.

이를 해결하기 위해 Circular Queue(원형 큐) 를 사용합니다.

</details> <details> <summary>Q. Python에서 Queue를 구현할 때 list 대신 deque를 사용하는 이유는 무엇인가요?</summary>

Python의 list는 앞쪽에서 요소를 삭제할 때 O(n)의 시간이 걸립니다.

하지만 deque는 양쪽에서 삽입과 삭제가 모두 O(1)이기 때문에
Queue 구현에 더 적합합니다.

</details> <details> <summary>Q. Queue보다 Deque를 사용하는 것이 더 좋은 경우는 언제인가요?</summary>

Deque는 양쪽에서 삽입과 삭제가 모두 가능하기 때문에
다음과 같은 경우에 더 효율적입니다.

슬라이딩 윈도우 문제
양방향 처리 필요
Stack + Queue 기능을 동시에 사용할 때
</details>
