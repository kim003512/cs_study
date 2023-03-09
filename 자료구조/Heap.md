### Heap

:heavy_check_mark: 개념

- **최소값 및 최대값을 최대한 빠르게 찾아내기 위해** 특별히 고안된 자료 구조
- **완전 이진트리**(마지막 레벨을 제외하고 모든 레벨이 완전히 채워져 있는 트리의 형태)를 기본으로 하고 있다

<br>

:heavy_check_mark: 종류

1. Max-Heap
   - root 노드의 key는 무조건 해당 노드의 자식 노드들의 key보다 크거나 같다
   - 같은 속성의 모든 sub-tree 들에게도 재귀적으로 적용됨
2. Min-Heap
   - root 노드의 key는 모든 자식들의 key보다 작거나 같다
   - 재귀적으로 자식 트리들 모두 해당 조건 만족

<br>

:heavy_check_mark: PriorityQueue

````java
public class PriorityQueue {
    public static void main(String[] args) {
        java.util.PriorityQueue<Integer> minHeap = new java.util.PriorityQueue<>();
        minHeap.add(2);
        minHeap.add(0);
        minHeap.add(4);
        
        System.out.println(minHeap.poll()); //0
        System.out.println(minHeap.poll()); //2
        System.out.println(minHeap.poll()); //4
    }
}

public class MaxHaep {
    public static void main(String[] args) {
        java.util.PriorityQueue<Integer> maxHeap = new java.util.PriorityQueue<>((o1, 02) -> Integer.compare(o1, o2));
        
        maxHeap.add(2);
        maxHeap.add(0);
        maxHeap.add(4);
        
        System.out.println(maxHeap.poll()); //4
        System.out.println(maxHeap.poll()); //2
        System.out.println(maxHeap.poll()); //0
    }
}
````

<br>

:heavy_check_mark: Heap 자료구조를 사용하는 이유

- 최소, 최대 값을 구하는데 특화되어 있는 자료구조
- 루트의 값만 바로 가져오면 되기 때문에 **O(1)**의 시간 복잡도만으로 바로 최대값이나 최소값을 찾을 수 있다

<br>

:heavy_check_mark: 시간복잡도

- 새로운 값을 추가(add)하거나 삭제(poll) 하는 경우
  - `O(log n)`
    - 힙트리의 높이가 `h = log(2, n+1)`이며 연산을 최대 `h-1`번 하게 되기 때문
