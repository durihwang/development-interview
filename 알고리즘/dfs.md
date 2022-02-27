## 정의
깊이 우선 탐색

인접한 노드가 있으면 방문하고 해당 노드에 인접한 노드를 게속 방문한다.

## 코드
```java
// 이진트리에서 사용하는 노드 클래스
public class Node {
    int value;
    Node left;
    Node right;

    public Node(int value) {
        this.value = value;
        left = null;
        right = null;
    }
}
```
```java
public int bfs(int v) {

    // 큐를 선언해준다.
    Queue<Integer> q = new LinkedList<>();
    // 처음 시작되는 v값을 넣어준다.
    q.offer(v);

    // 큐가 비어있을 떄까지 while문을 돌린다.
    while (!q.isEmpty()) {
        // 제일 위에 큐를 꺼낸다.
        Integer p = q.poll();
        // 큐를 출력한다.
        System.out.print(p + " ");

        // 입력된 간선의 최대수만큼 for문을 돌려준다.
        for (int i = 1; i <= n; i++) {
            // 입력된 값이 존재하고, 방문하지 않았는지 체크해준다.
            if ((graph[p][i] == 1 || graph[i][p] == 1) && ch2[i] == 0) {
                // 제일 처음 방문 표시를 한다.
                ch2[i] = 1;
                // 꺼낸 큐에서 이동된 값이 i 이므로 i를 큐에 넣어준다.
                q.offer(i);
            }
        }
    }

    return 0;
}
```
```java
// 이차원 배열 정렬하는 소스
Arrays.sort(tickets_compare,(o1,o2)->{
    if(o1[0].contentEquals(o2[0]))
        return o1[1].compareTo(o2[1]);
    else
        return o1[0].compareTo(o2[0]);
});
```

## 백트래킹
답을 찾는 도중에 막히면, 되돌아가서 다시 답을 찾아가는 기법

백트래킹에서 제일 중요한 것은 현재 지점에서 여러 갈래로 갈 수 있기 때문에

재귀를 하고 난 뒤에 꼭 해당 지점에 대한 방문을 해제해 주어야 한다.

## 스택프레임
함수의 호출과 관계되는 지역 변수와 매개변수가 저장되는 영역

함수가 어느 라인까지 호출되었는지를 저장한다.

## 재귀함수
자신을 재참조 하는 함수

dfs처럼 깊이우선 탐색을 할 때 사용한다.

재귀함수에서는 ++을 사용하게 되면 호출 이후에 ++이 되는 것이기 때문에 무한으로 재귀함수가 호출되게 되므로 +1로 연산을해주어야 한다.

재귀에서 종료조건이 없어도 체크배열같은 걸로 아예 재귀함수를 실행 안시킬 수도 있다.

## 메모이제이션
재귀함수를 실행할 때 이전에 계산한 값을 배열로 저장해놓고 사용하는 방식