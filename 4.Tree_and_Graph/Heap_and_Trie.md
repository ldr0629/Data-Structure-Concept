# Binary heap
최소 힙은 각 노드의 원소가 자식들의 원소보다 작다는 특징이 있고, 루트는 트리 전체에서 가장 작은 원소가 된다. 
최대힙은 원소가 내림차순으로 정렬되어 있다는 점만 다를 뿐, 최소 힙과 비슷하다.

## 삽입
최소 힙에 원소를 삽입할 때는 언제나 트리의 밑바닥에서부터 삽입을 시작한다.
완전 이진 트리의 속성에 위배되지 않게 새로운 원소는 밑바닥 가장 오른쪽 위치로 삽입된다.
이후, 새로 삽입된 원소가 제대로 된 자리를 찾을 때까지 부모 노드와 교환해 나간다. 이와 같은 방식으로
최소 원소를 위쪽으로 올린다. 시간 복잡도는 힙에 있는 노드의 개수를 n이라 할 때 O(log n) 시간이 걸린다.

## 최소 원소 뽑아내기

최소 원소는 최소 힙에서 언제나 가장 위에 놓인다.

    1. 최소 원소를 제거한 후에 힙에 있는 가장 마지막 원소(밑바닥 가장 왼쪽에 위치한 원소)와
    교환한다.

    2.그 다음 최소 힙의 특성을 만족하도록 해당 노드를 자식 노드와 교환해 나감으로써 밑으로
    내보낸다. 왼쪽, 오른쪽 자식 중 최소 힙의 특성을 유지하기 위해선 더 작은 원소와 교환해 나가야 한다.

이도 마찬가지로 시간복잡도는 O(log n) 시간이 걸린다.

# Trie(prefix tree)
트라이는 n-차 트리의 변종으로 각 노드에 문자를 저장하는 자료구조이다. 널 노드(null node)라고도
불리우는 '* 노드'는 종종 단어의 끝을 나타낸다.  '* 노드'의 구현은 특별한 종류의 자식 노드로 표현되며,
예컨대, TrieNode를 상속한 TerminatingTrieNode로 표현되거나 '* 노드'의 부모 노드 안에 불린
boolean flag를 새로 정의함으로써 단어의 끝을 표현할 수도 있다.

트라이에서 각 노드는 1개에서 ALPHABET_SIZE + 1개까지 자식을 갖고 있을 수 있다 ('* 노드' 대신
플래그로 표현했다면 0개에서 ALPHABET_SIZE까지). 접두사를 빠르게 찾아보기 위한 흔한 방식으로 
모든 단어를 트라이에 저장해놓는 방식이 있다.

트라이는 길이가 K인 문자열이 주어졌을 때 O(K) 시간에 해당 문자열이 유효한 접두사인지 확인할
수 있다.
