# FINAL EXAM

## Chapter 6 : COUNTING, 경우의 수

### 6.1 The Basics of Counting : 곱의 법칙, 합의 법칙
다들 알겠지 뭐...

### 6.2 The Pigeonhole Principle : 비둘기집의 원리(PHP)
$k$개 방에 $k+1$마리 비둘기가 들어가면 최소 한 방에는 두마리 이상이 같이 있다.

### 6.3 Permutations and Combinations : 순열과 조합
$n$개의 원소 중 $k$개의 원소를 중복하지 않게 순서를 가지고 뽑는 경우의 수

$$ {_nP_k}=P(n, k)=\frac{n!}{k!} $$

$n$개의 원소 중 $k$개의 원소를 중복하지 않게 **순서없이** 뽑는 경우의 수

$$ {_nC_k} = \binom{n}{k} = \frac{n!}{k!(n-k)!} $$

### 6.4 Binomial Coeffcients and Identities : 이항전개
#### 이항전개

$$ (x+y)^n = \sum_{i=0}^n\binom{n}{i}x^iy^{n-i} $$

파스칼 삼각형 (하키채 공식)

$$ \binom{n+1}{k} = \binom{n}{k-1} + \binom{n}{k} $$

$$ \binom{n+1}{r+1} = \sum_{i=r}^n\binom{i}{r} $$

### 6.5 Generalized Permutations and Conbinations : 중복순열, 중복조합
$n$개의 원소 중 $k$개의 원소를 **중복을 허용하여** 순서를 가지고 뽑는 경우의 수

$$ {_n\Pi_k} = n^k $$

$n$개의 원소 중 $k$개의 원소를 **중복을 허용하여** **순서없이** 뽑는 경우의 수

$$ {_nH_k} = \binom{n+k-1}{k}=\binom{n+k-1}{n-1}=\frac{(n+k-1)!}{k!(n-1)!} $$

### 6.6 Generating Permutations and Combinations: 사전순서
대충 사전순 정렬 이런거같은데 뭔지 잘 모르겠음... 근데 뭐가 많지도 않음

---

## Chapter 7 : Discrete Probability, 이산확률

### 7.1 An Introduction to Discrete Probability : 이산확률 기초
여러가지 확률의 성질들

$$ p(E) = \frac{|E|}{|S|} \in [0, 1] $$

$$ \overline{E} \equiv S-E \implies p\left(\overline{E}\right) = 1 - p(E)$$

그 외 몬티홀문제 등등

### 7.2 Probability Theory : 확률 정리
표본 공간 $S$에서 나올 수 있는 결과를 $s$라 하면,

$$ 0 \leq p(s\in S) \leq 1$$

$$ \sum_{s\in S}p(s) = 1 \qquad \sum_{s \in E}p(s) = p(E)$$

#### 이벤트 $E$가 발생할 확률

$$ \textrm{Pr}(E) \equiv \sum_{s \in E}p(s)$$

#### 조건부 확률 : $F$가 발생할 때 $E$가 발생할 확률

$$ p(E|F) = \frac{p(E\cap F)}{p(F)} $$

#### 두 사건 $E$, $F$가 다음을 만족하면 Independence (독립)

$$p(E\cap F) = p(E)p(F)$$

#### Random variable (무작위 변수) : 한 결과를 실수로 대응시킴

$$ X(s) = r $$

#### Distribution (분포) : random variable $X$와 실수 $r$에 대해 $X=r$일 확률을 $p(X=r)$이라 하면,

$$ (r, p(X=r)) $$

Monte Carlo (몬테 카를로) 알고리즘 : 다 검사 안하고 대충 때려맞추기

### 7.3 Bayes’ Theorem : 베이즈 정리

잘 생각해보면 생각보다 당연한 정리임 $\implies$ 2개를 여러개로 확장도 당연히 가능

$$ p(F|E) = \frac{p(E|F)p(F)}{p(E|F)p(F) + p\left(E|\bar{F}\right)p\left(\bar F\right)} = \frac{p(E|F)p(F)}{p(E)} = \frac{p(E\cap F)}{p(E)}$$

Example : 스팸 메시지 필터 <br/>
통계적?으로 메시지가 스팸일 확률 $p(S)$가 $1/2$라 하면, 어떤 단어 $w$를 포함하는 메시지가 스팸일 확률은

$$ p(S|E) = \frac{p(E|S)p(S)}{p(E|S)p(S) + p\left(E|\bar{S}\right)p\left(\bar S\right)} = \frac{p(E|S)}{p(E|S) + p\left(E|\bar{S}\right)} $$

#### Miller-Rabin Primality Test (밀러-라빈 소수 테스트)
> 자연수 $n$에 대해, $k$번 검사한다고 가정하자.
>
> $n-1$을 $2^s \cdot d$ 형태 ($d$는 홀수)로 바꾸고, 아래를 $k$번 반복한다.
>
> 임의의 $a \in \{2, 3, \ldots, n-1\}$, 모든 $r \in \{0, 1, \ldots, s-1\}$에 대해 다음을 검사한다.
>
> $$
> a^d \bmod n \neq 1 \quad \text{and} \quad a^{2^rd} \bmod n \neq n-1
> $$
>
> * 위를 만족하면 합성수
> * 만족하지 못했다면 unknown (합성수, 자연수 둘 다 가능)

이때 unknown으로 판별될 수 있도록 $a$를 고르는 최대 확률은 $1/4$이며, 따라서 $k$번의 테스트를 모두 통과할 최대 확률은 $4^{-k}$이다.

### 7.4 Expected Value and Variance : 기댓값과 분산

#### Expected Value: 기댓값 $\implies$ 확률을 고려한 평균

$$ E(X) = \sum_{s\in S}p(s)X(s) = \sum_{r\in X(S)}p(X=r)r $$

기댓값은 선형성을 가짐

$$ E(aX+b) = aE(X)+b $$

#### Variance, Standard Deviation: 분산, 표준편차

$$ V(X) = \sum_{s\in S}p(s)(X(s) - E(X))^2 \qquad \sigma(X) = \sqrt{V(X)}$$

확통에선 꽤많이 중요한 성질인데 여기서도 많이 쓰이려나

$$ V(X) = E(X^2) - E(X)^2 $$

무작위변수가 독립이라면?

$$ p(X=r_1 \wedge Y=r_2) = p(X=r_1)p(Y=r_2) \quad \implies \quad E(XY)=E(X)E(Y)$$

$$ V(X+Y) = V(X) + V(Y) $$

#### Chebyshev’s Inequality: 체비셰프 부등식  

평균에서 $n\sigma$만큼 떨어질 확률이 $\frac{1}{n^2}$이하다. ($r=n\sigma$, $\sigma^2=V$)

$$ \textrm{Pr}(|X(s)-E(X)| \geq r) \leq \frac{V(X)}{r^2} \quad \iff \quad \textrm{Pr}(|X(s)-E(X)| \geq n\sigma) \leq \frac{1}{n^2}$$

증명은 $n\sigma$만큼 떨어진 집합을 잡고 그것에 속하는 원소들은 편차가 $V(X)n^2$이상이 된다  
그런데 이것만 계산하면 충분히 보일 수 있다  
> Let $A = \{s \in S : |X(s)-E(X)| \geq r\}$. Then,
>
> $$
> V(X) = \sum_{s\in S}p(s)(X(s) - E(X))^2
> $$
> $$
> = \sum_{s\in A}p(s)(X(s) - E(X))^2 + \sum_{s\notin A}p(s)(X(s) - E(X))^2
> $$
> $$
> \geq r^2\sum_{s\in A}p(s) = r^2p(A) = r^2\textrm{Pr}(|X(s)-E(X)| \geq r)
> $$

#### Markov's Inequality: 마르코프 부등식

0보다 큰 확률변수에서 값이 커질 확률을 계산한다  

$$ \textrm{Pr}(X\geq r) \leq \frac{E(X)}{r}$$

증명은 체비셰프랑 비슷하다.

> Let $A = \{s \in S : X(s) \geq r\}$. Then,
>
> $$ 
> E(X) = \sum_{s\in S}p(s)X(s) 
> $$
> $$ 
> = \sum_{s\in A}p(s)X(s) + \sum_{s\notin A}p(s)X(s) 
> $$
> $$ 
> \geq r\sum_{s\in A}p(s) = rp(A) = r\textrm{Pr}(X \geq r)
> $$

## Chapter 8

점화식 나옴  
특성방정식 나옴  
나머지는 식을 적당히 잘 변형시키면 된다  
이건 고등학교에서 배운거  

분할정복  

### Master Theorem: 마스터 정리

점화식이 다음과 같은 형태일 때:
$$ T(n) = aT(\frac{n}{b}) + f(n) $$
여기서 $a \geq 1$, $b > 1$이고 $f(n)$은 양의 함수일 때,

다음 세 가지 경우로 나뉜다:

1. $f(n) = O(n^{\log_b a - \epsilon})$, $\epsilon > 0$인 경우:  

$$ T(n) = \Theta(n^{\log_b a}) $$

2. $f(n) = \Theta(n^{\log_b a})$인 경우:  

$$ T(n) = \Theta(n^{\log_b a}\log n) $$

3. $f(n) = \Omega(n^{\log_b a + \epsilon})$, $\epsilon > 0$이고 $af(\frac{n}{b}) \leq cf(n)$, $c < 1$인 경우:  

$$ T(n) = \Theta(f(n)) $$

이는 분할 정복 알고리즘의 시간 복잡도를 쉽게 계산할 수 있게 해준다.  
증명은 너무 끼워 맞춘 느낌이라 안나올듯  



포함배제  

---
생성함수  
<img src=genfunc.png width=600>  
대충 이 형태가 되는 다항식을 생성하는 방법에 대해 좀 고민하면 된다  
이렇게 하면 적당한 x 범위에서 무한급수 꼴이 나오게 할 수도 있어서 유용한 경우가 있다  
지수 생성함수는 저걸 k!로 나눠서 더한거  
곱하거나 더할때 유용하다  

0, 1, 2로만 이루어져 있고 0의 개수가 짝수인 길이 n의 수열 구하는 문제  
0의 개수가 짝수라는 말은 $1+x^2+x^4+...=\frac{1}{1-x^2}$  
나머지는 상관없으니까 $1+x+x^2+x^3+...\frac{1}{1-x}$

이걸 다 곱하면 뭔가 나오긴 하겠지만 모양이 아주 빡세 보인다.  
이럴 경우 지수 생성 함수를 사용하면 뭔가 편한 모양이 나온다.  
여러 개의 곱으로 나타낼 때 그냥 생성함수 써버리면 이렇게 힘든 모양이 나와서 지수를 사용한다.  

$\frac {1}{2} (e^{-x}+e^x)e^xe^x=\sum^{∞}_{n=0}\frac {3^n+1}{2}\frac{x^n}{n!}$  

그냥 생성 함수보다 더 쉽게 결과를 얻을 수 있다. $\frac {3^n+1}{2}$  
근데 솔직히 의미가 있나 싶은게 그냥 점화식 만들고 풀면 된다.  

이게 아니다. 일반 생성함수는 순서를 고려하지 않을 때 사용하고 지수 생성함수는 순서를 고려할 때 사용한다.  
위 문제의 경우 수열을 물어본 것이기 때문에 지수 생성함수를 사용하는 것이 정답이다.  

아래의 공식 정도는 외우는게 좋을듯  
$$
G(x)=\sum_{i=0}^{∞} \binom{n+i-1}{i}x^i=\frac{1}{(1-x)^n}
$$  
이것 말고도 유용한 생성함수들이 더 있다.  
<img src=genfun.png width=500>  

## Chapter 10

gpt의 용어 정리
1. **Graph**: 그래프  
   - 점(노드, vertex)과 선(엣지, edge)으로 이루어진 구조.

2. **Vertex (Vertices)**: 정점 (복수형: Vertices)  
   - 그래프에서 연결된 점, 노드라고도 부름.

3. **Edge**: 간선 (엣지)  
   - 두 정점을 연결하는 선.

4. **Loop**: 루프  
   - 하나의 정점에서 시작해 다시 그 정점으로 돌아오는 간선.

5. **Degree**: 차수  
   - 한 정점에 연결된 간선의 개수.

6. **Path**: 경로  
   - 시작 정점에서 끝 정점까지의 연결된 간선들의 연속.

7. **Circuit**: 회로  
   - 경로 중에서 시작과 끝이 같은 경우.

8. **Simple Graph**: 단순 그래프  
   - 루프와 중복된 간선이 없는 그래프.

9. **Multigraph**: 멀티그래프  
   - 동일한 두 정점 간에 여러 간선이 있을 수 있는 그래프.

10. **Directed Graph**: 방향 그래프  
    - 간선에 방향성이 있는 그래프.

11. **Adjacency Matrix**: 인접 행렬  
    - 정점 간의 연결 관계를 0과 1로 표시한 행렬.

12. **Incidence Matrix**: 발생 행렬  
    - 정점과 간선 간의 관계를 나타내는 행렬.

13. **Connected Graph**: 연결 그래프  
    - 그래프의 모든 정점들이 서로 경로로 연결된 상태.

14. **Euler Path/Circuit**: 오일러 경로/회로  
    - 모든 간선을 한 번씩만 지나가는 경로(경우에 따라 시작과 끝이 같으면 회로).

15. **Hamiltonian Path/Circuit**: 해밀턴 경로/회로  
    - 모든 정점을 한 번씩만 방문하는 경로(회로는 시작과 끝이 같음).

16. **Isomorphic Graphs**: 동형 그래프
    - 두 그래프 G1, G2에 대해 G1의 정점들과 G2의 정점들 사이에 전단사 함수 f가 존재하여, G1의 임의의 두 정점 u,v가 연결되어 있다면 f(u),f(v)도 연결되어 있고 그 역도 성립하는 경우를 말함.

이정도만 알면 딱히 어려운 내용은 없다

## Chapter 11
트리 : 회로가 없는 연결 그래프

Forest : simple circuit이 없는 그래프  
연결되어 있을 필요는 없다  

트리에서 임의의 두 정점을 잡았을 때 그 두 정점을 잇는 경로는 유일하다.  
증명 : 두 정점 u,v를 잇는 경로가 두 개 있다고 가정하자.  
u에서 v로 가는 경로를 P1, 반대 방향으로 v에서 u로 가는 경로를 P2라고 하자.  
P1과 P2는 서로 교차하지 않는 두 경로라면 두 경로를 이어붙이면 회로가 되어 트리 조건에 모순이다.  
교차하는 점이 존재한다면 그 점을 기준으로 두 경로를 이어붙이면 회로가 된다.  

rooted tree : 트리에서 하나의 정점을 선택하여 그 정점을 루트로 하는 트리

---

### Rooted Tree Terminology

1. **Parent(부모)**: 직접 연결된 자식 노드를 하나 이상 가진 노드
2. **Child(자식)**: 부모 노드와 직접 연결되어 있고 한 단계 아래에 있는 노드
3. **Siblings(형제)**: 같은 부모를 가진 노드들
4. **Ancestor(조상)**: 루트에서 특정 노드까지의 경로상에 있는 모든 노드, 자기 자신도 포함
5. **Descendant(자손)**: 특정 노드에서 리프까지의 경로상에 있는 모든 노드, 자기 자신도 포함
6. **Leaf(리프)**: 자식이 없는 노드
7. **Internal Node(내부 노드)**: 최소 하나의 자식을 가진 노드
8. **Subtree(서브트리)**: 한 노드와 그 노드의 모든 자손으로 구성된 트리

m-ary tree : 각 노드가 최대 m개의 자식을 가지는 트리  
ordered rooted tree : 자식 노드들이 순서가 있는 트리(동형 판정에서 차이가 존재하고 트리 순회에서 중요함)  

### 트리의 주요 속성과 증명

1. **모든 트리는 최소 하나의 리프 노드를 가진다**

    귀류법으로 증명:
    - 리프 노드가 없다고 가정 (모든 노드가 최소 하나의 이웃을 가짐)
    - 임의의 노드에서 시작하여 계속 이웃으로 이동
    - 유한한 노드(n개)를 가진 트리에서 n+1번째 방문은 반드시 이전 노드를 재방문
    - 이는 회로가 존재한다는 의미이므로 트리의 정의에 모순
    - 따라서 리프 노드는 반드시 존재

2. **n개의 정점을 가진 트리는 n-1개의 간선을 가진다**

    수학적 귀납법으로 증명:
    - n=1일 때 간선은 0개로 성립
    - k개 정점을 가진 트리가 k-1개의 간선을 가진다고 가정
    - 모든 k+1개의 정점을 가진 트리는 리프 노드를 가지기 때문에 그것을 제거할 수 있다
    - 그러면 그 리프 노드와 그에 연결된 간선을 제거하면 k개 정점을 가진 트리가 되고 이것은 k-1개의 간선을 가진다
    - 따라서 모든 자연수 n에 대해 성립


level : 각 노드에서 루트까지의 거리
height : 루트에서 가장 멀리 떨어진 노드까지의 거리

balanced tree : 모든 리프 노드의 레벨이 h 또는 h-1인 트리


### 트리 순회 (Tree Traversal)

트리 순회는 트리의 모든 노드를 체계적으로 방문하는 과정입니다.
주요 순회 방식에는 다음과 같은 것들이 있습니다:

1. **전위 순회 (Preorder Traversal)**
   - 순서: 노드 방문 → 왼쪽 서브트리 순회 → 오른쪽 서브트리 순회
   - 특징: 루트를 먼저 방문하고 서브트리를 순회
   - 활용: 디렉토리 구조 출력, 수식 트리의 전위 표기법 생성
   
   예시:
   ```
        A
       / \
      B   C
     / \   \
    D   E   F
   ```
   전위 순회 결과: A → B → D → E → C → F

2. **중위 순회 (Inorder Traversal)**
   - 순서: 왼쪽 서브트리 순회 → 노드 방문 → 오른쪽 서브트리 순회
   - 특징: 이진 검색 트리에서 정렬된 순서로 노드 방문
   - 활용: 수식 트리의 중위 표기법 생성

   같은 트리의 중위 순회 결과: D → B → E → A → C → F

3. **후위 순회 (Postorder Traversal)**
   - 순서: 왼쪽 서브트리 순회 → 오른쪽 서브트리 순회 → 노드 방문
   - 특징: 자식 노드를 모두 방문한 후 루트를 방문
   - 활용: 디렉토리 용량 계산, 수식 트리의 후위 표기법 생성

   같은 트리의 후위 순회 결과: D → E → B → F → C → A

4. **레벨 순서 순회 (Level-order Traversal)**
   - 순서: 레벨별로 왼쪽에서 오른쪽으로 순회
   - 특징: 너비 우선 탐색(BFS) 방식으로 구현
   - 활용: 트리의 레벨별 처리가 필요한 경우

   같은 트리의 레벨 순서 순회 결과: A → B → C → D → E → F

### 수식 트리 (Expression Tree)와 표기법

수식 트리는 수학적 표현식을 트리 구조로 나타낸 것입니다. 연산자는 내부 노드에, 피연산자는 리프 노드에 위치합니다.

예시 수식: (a + b) * (c - d)
```
     *
    / \
   +   -
  / \ / \
 a  b c  d
```

#### 세 가지 표기법

1. **중위 표기법 (Infix Notation)**
   - 일반적으로 사용하는 표기법: `(a + b) * (c - d)`
   - 연산자가 피연산자 사이에 위치
   - 괄호가 필요할 수 있음
   - 중위 순회로 생성

2. **전위 표기법 (Prefix Notation)**
   - Polish notation이라고도 함
   - 연산자가 피연산자 앞에 위치: `* + a b - c d`
   - 괄호가 필요 없음
   - 전위 순회로 생성

3. **후위 표기법 (Postfix Notation)**
   - Reverse Polish notation이라고도 함
   - 연산자가 피연산자 뒤에 위치: `a b + c d - *`
   - 괄호가 필요 없음
   - 후위 순회로 생성
   - 스택을 이용한 계산에 효율적

각 표기법의 장단점:
- 중위: 사람이 읽기 쉽지만 컴퓨터가 처리하기 어려움
- 전위/후위: 컴퓨터가 처리하기 쉽고 괄호가 불필요하지만 사람이 읽기 어려움

### 스패닝 트리 (Spanning Tree)
그래프 G의 스패닝 트리는 다음 조건을 만족하는 부분 그래프
- G의 모든 정점을 포함
- 트리를 형성 (회로가 없는 연결 그래프)

#### 스패닝 트리의 존재성
- 무향 그래프에서 스패닝 트리가 존재할 필요충분조건은 그래프가 연결되어 있는 것
- 방향 그래프에서는 모든 정점이 루트로부터 도달 가능해야 함

#### 스패닝 트리 찾기
1. **DFS (Depth-First Search)**
   - DFS 탐색 과정에서 사용된 간선들이 스패닝 트리를 형성
   - 재귀나 스택을 이용하여 구현

2. **BFS (Breadth-First Search)**
   - BFS 탐색 과정에서 사용된 간선들이 스패닝 트리를 형성
   - 큐를 이용하여 구현


