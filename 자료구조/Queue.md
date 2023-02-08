#### Queue

- Collection 프레임워크의 일부이며 java.util 패키지에 소속

- 먼저 들어온 데이터가 먼저 나가는 형식 = `FIFO`

  ![img](https://blog.kakaocdn.net/dn/4xNC4/btq5pEMF0sO/Hz54KOz8oU8QwR8uCqyIMK/img.png)

- `front`

  - 큐의 앞 부분으로, **삭제 연산**만 수행

- `rear`

  - 큐의 뒷 부분으로, **삽입 연산**만 수행

<br>

1. 사용법

   - 선언

     - **Queue, LikedList**

     ````java
     Queue<Integer> queue = new LikedList<>();
     ````

   - 값 추가

     ````java
     queue.add(1);
     ````

   - 값 삭제

     ````java
     1. 맨 앞의 값 삭제
     	queue.poll(); -> 비어있다면 `null` 반환
     	queue.remove(); -> 비어있다면 `NoSuchElement` 에러 반환
     	
     2. 해당하는 값 삭제
     	queue.remove(1);
     	
     3. Index의 값 삭제
     	queue.clear(); -> Queue의 모든 값을 삭제하고 초기화
     	
     ````

   <br>

2. 관련 용어

   - `enqueue`
     - Queue에 **데이터 추가**
     - 자바에서의 메서드
       - offer, add
   - `Dequeue`
     - Queue에서 **데이터 추출**
     - 자바에서의 메서드
       - remove, poll
   - `peek`
     - Queue에서 **데이터 확인**
     - 자바에서의 메서드
       - peek, element



<br><br>

#### Priority Queue

- 데이터의 우선순위를 정해 **우선순위가 높은 순서대로** 나간다
- 데이터 삽입 시, 우선순위의 최대, 최소를 구성하여 데이터가 빠지면 중간을 계속해서 채워넣는 방식
- 데이터 추출 시, 루트 노드를 얻어 루트 노드를 삭제할 때는 빈 루트 노드 위치에 맨 마지막 노드를 삽입 후  아래 노드를 내려가면서 정렬하는 방식으로 진행
- `최대힙`
  - 최대 값이 우선순위인 큐
- `최소힙`
  - 최소 값이 우선순위인 큐

<br>

1. 특징
   - 값을 비교해야 하므로 **null 허용**:x:
   - 비교할 수 없는 객체는 큐를 만들 수 없음
   - **내부구조**는 **이진트리 힙**으로 구성
     - add() 및 poll() 메서드 => O(log(n))

<br>

2. 사용법

   - 선언

     ````java
     1. 낮은 숫자 순으로 우선순위 결정
     	PriorityQueue<Integer> priorityQueue = new PriorityQueue<>();
     
     2. 높은 순자 순으로 우선순위 결정
         PriorityQueue<Integer> priorityQueue2= new PriorityQueue<>(Collections.reverseOrder());
     ````

   - 값 추가

     ````java
     priorityQueue.add(1);
     ````

   - 값 삭제

     ````java
     1. 우선순위가 가장 높은 값 제거
     	priorityQueue.poll();
     	priorityQueue.remove();
     
     2. Index 순위에 해당하는 값 제거
         priorityQueue.remove(Index);
     
     3. 우선순위 큐의 모든 값 삭제
         priorityQueue.clear();
     ````

     

