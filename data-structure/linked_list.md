# 🖥 Linked List (연결 리스트)
각 노드가 **데이터**와 **포인터**를 가지고 **일렬로 연결**되어 있는 방식
---

## 특징
- **선형** 자료구조 (Linear Data Structure)
- 각 노드는 **데이터와 포인터**로 구성
- 데이터는 메모리에 **연속적으로 저장되지 않음**
- 특정 데이터 접근을 위해 **처음부터 순차적**으로 탐색
- 데이터의 **삽입/삭제 연산이 효율적**
- **포인터**를 위한 **추가 공간** 필요
---
## 종류
### Singly Linked List
각 노드가 **다음 노드**만 가리키는 구조
- 한 반향으로만 탐색 가능
- 구조 단순
- 메모리 사용 비교적 적음

### Doubly Linke List
각 노드가 **이전 노드와 다음 노드 모두** 가리키는 구조
- 양방향 탐색 가능
- 삽입/삭제 효율적 (가까운 쪽으로 탐색 가능)
- 포인터 2개 필요 → 메모리 사용 증가
---
## Linked List 구현
```python
class Node:
    def __init__(self, data):
        self.data = data        # 노드의 데이터 구현
        self.next = None        # 노드의 포인터 구현

class LinkedList:
    def __init__(self):
        self.head = None

    # 노드 삽입 (맨 앞)
    def insert_front(self, data):
        new_node = Node(data)
        new_node.next = self.head
        self.head = new_node

    # 노드 삽입 (맨 뒤)
    def insert_end(self, data):
        new_node = Node(data)

        if self.head is None:
            self.head = new_node
            return

        current = self.head
        while current.next:
            current = current.next

        current.next = new_node

    # 노드 삭제
    def delete(self, key):
        current = self.head

        if current and current.data == key:
            self.head = current.next
            return

        prev = None
        while current and current.data != key:
            prev = current
            current = current.next

        if current is None:
            return

        prev.next = current.next
```
---
## Linked List 시간 복잡도 
연산 | 시간 복잡도
--- |  ---
데이터 조회  |	O(n)
데이터 탐색  |	O(n)
맨 앞 삽입   |	 O(1)
맨 뒤 삽입   |	 O(n)
삭제         |   O(n)

---
## Array와 Linked list의 차이
- 데이터 접근 속도
    - Array는 **index를 통한 random access**를 지원하므로 O(a)
    - Linked List는 **순차 접근 방식**을 사용하므로 O(n)
- 데이터 삽입/ 삭제 속도
    - Array는 중간 삽입/삭제 시 **shift**가 필요하므로 O(1)
    - Linked List도 **중간 탐색** O(n) 후 삽입/삭제 O(1)로 최종적으로 O(n) (맨 앞, 뒤 삽입 시 O(1))
    - 다만 Linked List는 삽입/삭제마다 **메모리 할당/해제** 발생 → **system Call적**으로 시간 더 걸림
- 메모리 할당
    - Array는 정적 메모리 할당 (Complie time)
    - Linked List는 동적 메모리 할당 (Runtime)
    - Array는 메모리 공간이 가득 차면 **새로운 공간 필요**, Linke List는 **필요할 때마다 노드 생성**
---
## 💡 핵심 정리
- Linked List는 노드와 포인터로 구성된 자료구조
- 메모리 공간이 연속적이지 않아도 된다
- 조회 O(n)
---
# 📝 면접 예상 질문
<details> <summary>Q. Linked List란 무엇인가요?</summary>

Linked List는 각 노드가 데이터와 포인터를 가지고 서로 연결된 형태의 자료구조입니다.
각 노드는 다음 노드를 가리키는 참조를 가지고 있으며, 메모리에 연속적으로 저장되지 않습니다.

</details> <details> <summary>Q. Linked List의 장점과 단점은 무엇인가요?</summary>
장점:

데이터 삽입과 삭제가 효율적
동적 메모리 할당 가능

단점:
특정 데이터 접근 시 순차 탐색 필요 (O(n))
포인터 저장을 위한 추가 메모리 필요
캐시 효율이 떨어질 수 있음

</details> <details> <summary>Q. Array와 Linked List의 차이는 무엇인가요?</summary>

Array는 연속된 메모리 공간을 사용하며 Random Access가 가능해 조회가 O(1) 입니다.

Linked List는 노드들이 포인터로 연결된 구조이며 순차 접근 방식으로 O(n) 의 시간이 필요합니다.

하지만 Linked List는 삽입과 삭제가 포인터 변경만으로 가능하기 때문에 효율적입니다.

</details> <details> <summary>Q. Singly Linked List와 Doubly Linked List의 차이는 무엇인가요?</summary>

Singly Linked List는 각 노드가 다음 노드만 가리키는 구조입니다.
Doubly Linked List는 이전 노드와 다음 노드를 모두 가리키는 구조입니다.
Doubly Linked List는 양방향 탐색이 가능하지만
포인터를 두 개 사용하기 때문에 메모리 사용량이 증가합니다.

</details> <details> <summary>Q. Linked List에서 특정 노드를 삭제하는 과정은 어떻게 되나요?</summary>

삭제하려는 노드의 이전 노드(prev) 를 찾은 뒤
prev.next = current.next
처럼 포인터를 변경하여 노드를 제거합니다.
즉, 노드를 직접 삭제하는 것이 아니라
이전 노드의 연결을 변경하여 리스트에서 제외시키는 방식입니다.

</details>
