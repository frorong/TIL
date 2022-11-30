# 2-3Tree

-   차수가 2개 또는 3개가 될 수 있다
    -   ```
                      [Root]
                         |
                 [node1] + [node2]
                              |
                   [node3]+[node4]+[node5]
        ```

*   모든 Leaf Node가 같은 레벨에 있어야한다
    -   ```
                      [Root]
                         |
                 [node1] + [node2]
                    |         |
                 [node3]   [node4] + [node5]
        ```

-   2-3 Tree는 Internal Node와 External Node가 존재한다
    -   Internal Node는 Key가 들어있는 Node이다
    -   External Node는 데이터가 없는 가상의 Node이다

*   각 Internal Node는 2-node거나 3-node 이다
    -   2-Node는 1개의 key값과 2개의 자식을 가지고 3-Node는 2개의 key값과 3개의 자식을 가진다

## 규칙

-   2-Node의 두 자식을 1번자식 2번자식이라 하고 해당 Node의 key를 1번key 라고 하겠다
    -   root가 1번자식인 모든 서브트리의 key값은 1번key보다 작아야한다
    -   root가 2번자식인 모든 서브트리의 key값은 1번key보다 커어야한다
-   3-Node의 세 자식을 1번자식 2번자식 3번자식이라 하고 해당 Node의 key를 1번key와 2번key 라고 하겠다
    -   root가 1번자식인 모든 서브트리의 key값은 1번key보다 작아야한다
    -   root가 2번자식인 모든 서브트리의 key값은 1번key보다 크고 2번key보다 작아야한다
    -   root가 3번자식인 모든 서버트리의 key값은 2번key보다 커어야한다

*   ### 모든 External Node는 같은 레벨에 있어야한다

-   leaf Node인 External Node에는 데이터가 들어있지 않다

## 검색

-   찾으려는 값을 root Node의 1번key, 2번key와 비교한다
-   1번key보다 작은 경우 leftSubtree를 탐색한다
-   1번key보다 크고, 2번key보다 작은 경우 middleSubtree를 탐색한다
-   2번key보다 큰 경우 rightSubtree를 탐색한다

## 추가

-   반드시 leaf Node에 데이터를 삽입한다
    -   1.  값이 추가될 위치를 찾는다
    -   2.  추가될 leaf Node가 용량을 초과하지 않았다면 오름차순으로 데이터를 삽입한다
        -   만약 용량을 초과했다면 분할을 한다

## 분할

-   추가될 데이터를 포함하여 중앙값을 설정한다

    -   중앙값을 부모 Node에 추가시키고 중앙값보다 작은 값은 왼쪽에 큰 값은 오른쪽에 저장된다
    -   부모 Node가 없다면 새롭게 생성된다
    -   부모 Node에도 용량이 가득찼다면 또 분할을 진행한다

-   삽입할 때 Node가 가득 차 삽입할 수 없는 상황이라면?
    -   해당 Node의 중간값을 찾아서 그 중간값을 부모 Node로 하는 서브트리를 만든다
-   항상 높이를 맞춰주어야 하기 때문에 새롭게 만들어준 서브트리의 root를 부모 Node와 합친다
    -   이 때 부모 Node가 2-Node라면 바로 삽입이 가능하나 3-Node라면 어쩔 수 없이 앞의 내용을 반복한다

## 삭제

### 회전

-   원소가 삭제되는 Node를 기준으로
    -   삭제되는 Node의 형제Node의 원소 하나를 부모 Node로
        -   부모 Node의 원소 하나를 자신의 Node로 가져와 회전을 시킨다
-   삭제되는 Node의 형제 노드중 3-Node가 있다면 회전이 가능하다

### 병합

-   원소가 삭제되는 Node를 기준으로
    -   삭제되는 Node의 직후 형제Node와 자신 사이에 포함되는 부모 원소를 합친다
    -   merge 이후 Node의 용량이 초과되었다면 분할을 진행한다
-   삭제되는 Node의 형제 노드중 3-Node가 없다면 병합이 필요하다

#### Leaf Node가 아닌 Node삭제시 삭제되는 Key의 왼쪽 서브트리의 최대값으로 비어있는 부분을 채워준다

#### 회전은 가장 왼쪽 서브트리를 제외하고는 반드시 왼쪽 형제Node를 확인하여 가능할 때만 발생한다

-   왼쪽을 우선적으로 확인한다

## 삭제 상황

-   ### 1. 3-Node인 Leaf Node삭제
    -   삭제 후 남아있는 key가 2번key라면 위치를 옮겨준다
-   ### 2. 2-Node인 Leaf Node삭제
    -   형제 Node중 3-Node가 있는 경우
        -   가장 왼쪽 Node라면
            -   회전을한다
        -   아니라면
            -   병합을한다
    -   형제 Node중 3-Node가 없는 경우
        -   병합을 한다
-   ### 3. 3-Node인 안 Leaf Node삭제
    -   Leaf Node의 삭제 형태로 바꾼다
-   ### 4. 2-Node인 안 Leaf Node삭제
    -   Leaf Node의 삭제 형태로 바꾼다

### 삭제, 삽입은 여려 형태로 나타날 수 있다
