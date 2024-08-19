# 투 포인터 (Two Pointer)

참고 : [이것이 코딩 테스트다 with Python - 39강 투 포인터](https://www.youtube.com/watch?v=ttLRltNDiCo&t=6s)

### 적용 조건

- 리스트에 순차적으로 접근해야 하는 경우
- 크기가 엄청 큰 1차원 배열 (1만개 이상)
- 완전탐색으로 해결하면 시간초과가 나는 경우 => 투 포인터를 사용하면 O(N) 의 시간복잡도를 갖는다
- 연속된 수들의 합
- ex) 특정한 합을 가지는 부분 연속 수열 찾기
    1. 시작점, 끝점 모두 idx=0 을 가리키도록 한다.
    2. 현재의 부분합이 m과 같다면 `cnt += 1`
    3. 현재의 부분합이 m보다 **작다면 `end +=1`**
    4. 현재의 부분합이 m보다 **크거나 작으면 `start +=1`**
    5. 2~4번 반복
       => 이중 반복문이 아니라 하나의 반복문에서 start, end 두 변수를 같이 변경

### 원리

- 리스트에 순차적으로 접근해야 할 때, 2개의 점의 위치를 기록하면서 처리하는 알고리즘
- 시작점과 끝점으로 접근할 데이터의 범위를 표현한다.



## 문제 풀이

| 번호 |    날짜    | 문제 번호                                            | 풀이법                                                     | 주의사항                                                                               | 새롭게 배운 내용                                                                                               | 다시 풀어보기 |
|:--:|:--------:|:-------------------------------------------------|:--------------------------------------------------------|:-----------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------|:-------:|
| 1  | 24.08.17 | [BOJ 2003](https://www.acmicpc.net/problem/2003) | 딱 위에 적어 놓은 부분 연속 수열 찾기 예제처럼 풀었음!                        |                                                                                    |                                                                                                         |         |
| 2  | 24.08.17 | [BOJ 1806](https://www.acmicpc.net/problem/1806) | 브루트 포스(이중 반복문) 으로 풀다가 계속 시간 초과가 나서 투 포인터(반복문 1번)로 풀었당~! | **🚨 누적합, 투 포인터 기법을 사용할 때에는 첫번째 요소가 포함되도록 하기 위해서 0번째 인덱스에 0을 추가해야 한다!! 🚨**        |                                                                                                         |         |
| 3  | 24.08.18 | [BOJ 1644](https://www.acmicpc.net/problem/1644) | 소수의 배열에서 투 포인터를 사용해서 연속된 수들의 합이 m이 되는 경우의 수 세기          | 오른쪽 포인터(end)는 증가 후 덧셈을 하기 때문에 while 조건문에 걸리기 전에 index error가 발생할 수 있다. 범위 조건문 추가하기 | 1~n까지의 소수를 구하는 방법 = 에라토스테네스의 체 = 1~n으로 초기화된 배열에서 특정수의 배수에 해당하는 모든 수를 지운다. (2중 for문, O(N<sup>1/2</sup>)) |         |