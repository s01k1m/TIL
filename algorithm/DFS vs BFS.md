

#DFS #BFS

# 🍎 그래프 탐색 방법
비선형 구조인 그래프 구조는 표현된 모든 자료를 빠짐없이 탐색하는 것이 중요하다.
그래서 아래와 같은 탐색 기번이 존재한다.

|DFS|BFS|
|---|---|
|stack 활용|큐 활용|


## DFS
stack 활용
- 내가 다시 돌아올 곳을 저장하기 위해 스택을 이용한다.
- **가장 마지막에 만났던 갈림길 간선이 있는 정점으로 되돌아**와서 다른 방향의 정점으로 계속 반복 탐색하여 모든 정점을 탐색 한다.
- 스택의 후입선출 구조 또는 재귀 호출을 이용하여 구현
- 인접 행렬
- 인접 행렬은 메모리 낭비가 심하다. 대안은?


```python
# 재귀로 표현한 DFS


# arr은 인접행렬
# visited 리스트는 방문했는지 기록
def DFS(v):    # 입력 파라미터: 탐색 시작정점 v
	visited[v] = 1
	print(v, end=" ")
	# 인접한 정점 중 방문을 안한 곳 탐색
	for w in range(1, V+1):
		if arr[v][w] == 1 and visited[w] == 0:    # v에 인접해 있고 방문하지 않은 경우
			dfs(w)                                # 재귀

```

```python
# 반복문으로 dfs 구현하기

def DFS(v):    # 입력 파라미터: 탐색 시작정점 v
	stack = [v]
	while len(stack):   # 스택이 비지 않은 경우
		v = stack.pop()
		visited[v] = 1  # 방문했음을 표시
		for w in range(1, V + 1):
			if arr[v][w] == 1 and visited[w] == 0:    # v에 인접해 있고 방문하지 않은 경우
				stack.append(w)                       # 스택에 푸쉬

```



## BFS

Queue 활용
- 시작점의 인접한 정점들을 모두 차례로 방문한 후 방문했던 정점을 시작점으로 하여 다시 인접한 정점들을 차례로 방문하는 방식
- **인접한 정점들을 탐색**한 후, 차례로 너비 우선 탐색을 진행해야 하므로, **선입선출** 형태의 자료구조인 큐 활

```python

# visited 리스트는 방문했는지 기록
# queue 너비우선탐색의 진행 상황을 저장
def BFS(G, v): # 입력 파라미터: 그래프 G, 탐색 시작점 v
    visited = [0] * n # n: 정점의 개수
	queue = []        # 큐 생성
	queue.append(v)   # 시작점 v를 큐에 삽입
	while queue:      # 큐가 비어있지 않은 경우
		t = queue.pop()   # 큐의 첫번째 원소 반환
		if not visited[t] # 방문되지 않은 곳이라면
			visited[t] = Treu # 방문한 것으로 표시
			visit(t)
		for i in G[t]:    # t와 연결된 모든 선에 대해
			if not visited[i]: # 방문되지 않은 곳이라면
			queue.append(i)    # 큐에 넣기

```