## 정의
넓이 우선 탐색

최단거리를 탐색할 떄 사용된다.

queue를 이용해서 탐색한다.

노드의 레벨을 전부다 탐색해야 한다.

queue가 비어있을 떄까지 실행하고 해당 노드를 모두 탐색해야 하기 떄문에 노드 개수만큼 for문을 실행해준다.

## 기본 코드
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