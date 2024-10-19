# cs204

2024 가을학기 이산구조 정라하려고 만든거  
영어를 못해서 한국어로 보고 싶어서 만들어봄  
빠트린 내용, 추가할 설명 등은 풀 리퀘로  
마크다운, latex 많이 안 써봐서 좀 이상한 부분이 있을 수도 있음  

## Chepter 1, 2  
ch1은 그냥 기초  
논리 연산 관련 내용인데  
드모르간 증명같은 것도 나올 수 있을지도  
<img src=images/dmorgan_prove.png width=600>  
그리고 ⊕ 이 기호 xor로 나와있던데 많이 안 쓰는 거라 알아두면 좋을듯 

---
Quantifiers에 대해 배우는데 당연히 교환법칙 성립 안함  
여러 개 있을 경우 어떻게 된다 설명이 있긴 한데 이건 그냥 생각 좀 하면 된다.  
슬라이드에 나온 내용은 딱히 없는데 숙제에 나왔던 내용 정도만 알면 될 것 같다.  
<img src=images/quantifiers.jpg width=400>  
대부분은 논리적으로 생각해서 해결되긴 할텐데 어려운 문제, 원리 있으면 풀 리퀘 보내주세요  

---
Normal Forms에 대해 배우는데  
PDNF, PCNF에 대해서만 알아두면 된다  

Minterm -> TF 논리 테이블에서 1개만 True로 만드는 and로 연결된 조건  
Maxterm -> TF 논리 테이블에서 1개만 False로 만드는 or로 연결된 조건  
Minterm에 or연산 한 것으로 모든 연산을 나타내는 것이 가능하고  
Maxterm에 and연산 한 것으로 모든 연산을 나타내는 것이 가능하다.  
Minterm을 Disjunctive 해서 만든게 PDNF  
Maxterm을 Conjunctive 해서 만든게 PCNF  

---
기수는 일대일대응이 존재함을 보이거나  
한쪽으로 포함되는 것도 있고 다른쪽으로 포함되는 것도 있다.  
이걸 증명하면 된다.  
연속체 가설로 2^2^2...^N (N은 자연수 집합 크기) 이중에 무조건 같은 집합이 존재하게 될거임  
실수 uncountable, countable union is countable 등은 쉬워서 건너뜀  
풀 리퀘를 주시면 넣도록 할게요  

---
$|P(A)| > |A|$에 대한 증명  

어떤 $f : A → P(A)$ injective 함수가 존재한다고 가정하자  
그러면 어떤 집합 $X$를  
$X=\{ a|a \notin f(a) \}$이렇게 잡으면  
$f(x)=X$인 $x$가 존재하지 않음을 보이면 된다.  
만약 $x \in X \Rightarrow X \notin x$ since def of x  
만약 $x \notin X \Rightarrow X \in x$ since def of x  
contradiction 따라서 $f$는 존재하지 않음  

---
String is countable  
So Program is countable  
But function is uncountable  
$\Rightarrow$ There are not computable functions

---
행렬 내용은 별거 없고  
bool 행렬곱은 ⨀ 이 기호를 사용한다.  


## Chepter 3
정렬, 검색은 너무 쉽다.

---
정지 문제에 대해 간단히 생각해보면  
어떤 프로그램 P(p, i)가 존재하여 어떤 프로그램이 정지하면 True, 아니면 false를 반환한다고 하자  
그러면 어떤 프로그램 D를 정의하여  
D(p)=if P(p, p) then loop, else stop(halt)  
이 상태에서 D(D)를 넣어주면  
D가 멈출 경우 P는 True로 무한루프가 돌아서 모순
D가 무한루프일 경우 P는 False로 정지하여 모순
따라서 P같은건 존재하지 않는다.  

---
Big-O, Big-$ \Omega $, Big-$ \Theta $가 나온다.  
Big-O는 미적1에서도 나왔지만 충분히 큰 n에 대해 상수를 곱한 것보다 작으면 된다.  
Big-$ \Omega $의 경우 최적의 경우 어떻게 증가하는지 나타낸다.  
충분히 큰 n에 대해 상수를 곱한 것보다 크면 된다. 
insertion sort의 경우 Big-$ \Omega $로는 $ \Omega(n) $이고  
보고정렬의 경우 $ \Omega(1) $이 된다.  
Big-$ \Theta $는 2개가 같을 경우 사용한다. 

---
간단하게 행렬곱에서 곱셈 순서도 언급되는데  
결합법칙은 성립하지만 여기에서 곱셈 계산 횟수는 달라진다.  

P, NP 문제에 대해서도 다루는데  
P는 다항 시간 안에 해결 가능한 문제이고 NP는 아닌 문제이다.  
NP-완전 문제 중 하나라도 P문제이면 P=NP가 되지만 아닐 것 같다. 

## Chapter 4
여기부터 시작이다.  

---
나머지 연산에 대해 다룬다.  
잘 정의되는 것을 보이는 것은 쉽다.  

---
진법에 대해 배우고 비트 연산에서 덧셈, 곱셈, 나머지 연산을 어떻게 실행하는지 배운다.  
덧셈은 O(n) 시간복잡도, 곱셈은 O($n^2$) 시간복잡도, a//d, a%d 연산은 ppt 코드를 보면 O(a)로 보인다.  
하지만 O($\log a \log d$)의 시간복잡도를 가지는 나누기 연산이 가능하다.  

이진법을 이용해서 지수 연산을 빠르게 할 수 있다.  
분할정복이랑 딱히 다르지 않긴 한데 손으로 나머지 계산 등을 할때는 이게 더 편할 수도 있다.  
지수를 이진법으로 나타내서 곱셈으로 바꾼다. 

예시 : $7^{101101_2} \mod 13$을 구해라  
$7^1=7, 7^2=10, 7^4=10^2=9, 7^8=3$  
페르마 소정리 $7^{12} \mod 13=1$  
$1100_2$로 나누면 $10101_2, 1001_2=9$ 가 되어  
3*7=21=8

---
소수 관련 내용 나온다.  
소수정리 1~N까지 소수의 개수는 $\frac{N}{\ln N}$로 근사 가능하다.  
따라서 N까지 소수 중 하나 확인하면 대충 $\frac{1}{\ln N}$ 확률로 소수다.  

RSA 암호에서는 주로 512, 1024bit 소수를 주로 사용하는데  
1024bit 안에서 랜덤으로 수 얼마나 골라야 하나쯤 소수가 나올지 계산하면  
$\ln 2^{1024}=1024\ln 2 = 720$  
720개 정도 검사하면 대충 소수 하나쯤은 나온다.  
사실 이렇게만 계산해도 되는지는 몰?루겠음  
저렇게 720번 검사해도 하나도 못 찾을 수도 있는거고 여러개 찾을 수도 있어서  
대충 50% 넘기는거만 계산해보면 $(1-\frac{1}{\ln 2^{1024}})^{x}=0.5 \Rightarrow x=492$ 정도 나온다.  
이렇게 뽑은 수가 소수인지 판별하는건 $O(n^{\frac{1}{2}})$ 안에 가능  

p is prime and $2^p$ is prime일 경우 $2^p$는 메르센 소수 ㄴ 
효율적인 판정법이 존재한다고 한다.  

---
gcd 관련 내용이 있다.  
소인수분해로 구하는건 쉽고  
여기서 나오는 소인수분해 유일성도 뒤에 귀납적으로 증명하는거 나온다.  

2는 당연히 2 자신으로 유일하게 소인수분해된다.  
2 to n에서 유일하게 소인수분해된다고 가정  
n+1이 2 to n중에 나누어떨어지는 k가 존재한다면  
k, (n+1)/k는 당연히 유일하게 소인수분해되고  
이 소인수분해 곱도 당연히 유일하다.  
k가 없으면 그냥 소수라서 자신으로 유일하게 소인수분해된다.  

유클리드 알고리즘 자체는 매우 쉽다.  
$\gcd(a, b)=n$이라고 하면  
$\gcd(b, a \mod b)=n$이다.  

증명   
$n|a$ and $n|b \Rightarrow n|a \mod b$는 식 조금만 만들어봐도 된다.  
if &nbsp;&nbsp;&nbsp;$ \exist m>n$&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;s.t&nbsp;&nbsp;&nbsp;&nbsp;$m|b$&nbsp;&nbsp;&nbsp; and &nbsp;&nbsp;&nbsp;$m|a \mod b$  
$\Rightarrow m|b$&nbsp;&nbsp;&nbsp;and&nbsp;&nbsp;&nbsp;$m|(a \mod b)+qb=a$&nbsp;&nbsp;&nbsp;so $n=\gcd(a, b)>m$ contradiction

그리고 이것을 확장하면 $gcd(a, b)=sa+tb$ 형식 표현이 가능해지는데 이것이 베조의 등식  
<img src=images/gcd_linear.jpg width=500>  
뒤에 나올 내용에서도 좀 쓰인다.  

---
$a|bc, \gcd(a, b)=1 \Rightarrow a|c$  
a, b로 베조의 등식 사용하면  
$sac+tbc=c\Rightarrow a(sc+an)=c$  
$(∵ a|bc\Rightarrow bc=an)$  
따라서 $a|c$가 된다.  

---
모듈러 역원(inverse) : 모듈러 곱셈에서 1이 나오도록 하는 수  
$a$의$\mod m$에 대한 역원은 $\gcd(a, m)=1$일 때 베조의 등식으로 항상 존재한다.  
유클리디안 알고리즘 반대로 쭉 가면 나온다.  
<img src=images/inverse.jpg width=500>  

---
중국인 나머지 정리  
서로소 n개 $m_1, m_2, ..., m_n$있을 경우  
어떤 자연수 N을 $m_i$로 나눈 나머지가 각각 정해졌을 때  
N을 모든 $m_i$ 곱으로 나눈 나머지가 유일하게 결정된다.  
아래 증명처럼 계산하면 이론상 존재함은 보일 수 있다. 손계산은 저걸로 하긴 너무 힘들다.  
<img src=images/cmt.jpg width=500>  

손으로 할 경우 하나씩 모듈러 적용하면서 찾으면 된다.  

예시  
$x=2 (\mod 3), x=3 (\mod 5), x=5 (\mod 7)$  
$x=3a+2$  
$3a+2=3 (\mod 5)$  
$a=5b+2 \Rightarrow 15b+8=3 (\mod 5)$  
$15b+8=5 (\mod 7)$  
$b=7c+4 \Rightarrow 105c+68=5 (\mod 7)$  
$\Rightarrow x=105c+68=68 (\mod 105)$  

---
페르마 소정리  
$\gcd(a,p)=1 \Rightarrow a^{p-1}=1 (\mod p)$  
Euler's Theorem만 알아도 증명 가능하기는 함  

Euler's Theorem  
$\gcd(a, n)=1 \Rightarrow a^{\phi(n)}=1 (\mod n)$  
n이 소수일 경우 페르마 소정리와 동일하다.  

증명  
$S=\{x|\gcd(x, n)=1, x<n\} \subset \mathbb{Z_n}$인 S의 원소를 작은 수부터 나열하여 $\{a_i\}$라고 하면  
$\forall x \in S \Rightarrow ax \mod n \in S (∵gcd(x, n)=1, gcd(a, n)=1)$  
if $\exist x_1,x_2$ s.t $ax_1=ax_2 (\mod n) \Rightarrow a(x_1-x_2)|n$  
but $\gcd(a, n)=1$ and $|x_1-x_2|<n$ so $x_1-x_2=0$  
따라서 a를 각 원소에 곱해도 전체 집합은 동일하다. (f(x)=ax는 S->S로 가는 일대일대응 함수)

$∴\prod_{x \in S}^{} x=\prod_{x \in S}^{} ax=a^{\phi(n)}\prod_{x \in S}^{} x (\mod n)$  
$\Rightarrow n|(a^{\phi(n)}-1)\prod_{x \in S}^{} x$  
but $\forall x \in S \gcd(x, n)=1$  
$∴n|(a^{\phi(n)}-1) \Rightarrow a^{phi(n)}=1 (\mod n)$

---
페르마 소수 증명  
$1<\forall a<n-1$  
$a^{n-1}=1 (\mod n)$일 경우 n은 높은 확률로 소수  
하지만 561이 반례로 존재  

---
Primitive Root  
어떤 n에 대해 k를 0~n-1번 모듈러 제곱을 했을 때 나오는 수가 모두 다를 경우  
k를 Primitive Root라고 한다.  
$\phi(n)$의 약수에서 1이 나오는지만 확인하면 된다.  

Primitive Root에서 모든 a에 대한 이산 로그($k^x=a (\mod n)$인 x가 이산 로그다)를 정의 가능하다.  
영어로는 Discrete Logarithm이라고 한다.  

---
RSA 암호  
<img src=images/RSA.jpg width=600>  
이거 다 쓰기는 너무 귀찮다... 기여 좀 부탁

---
디피-헬만 키 교환  
소수 p와 p의 Primitive Root g를 정해서 공개  
p이하 자연수 하나씩 적당히 정해서 각각 a, b라고 하면 g^a, g^b mod p 연산을 해서 를 교환한다.  
교환한 것에 자기가 정한 수를 한번씩 더 제곱해서 p로 나눈 나머지를 구하면 그것을 키로 사용한다.  
외부에서 알아내려면 이산 로그 문제를 풀어서 a, b중 하나를 알아내야 하는데 그냥 찍어서 검사해야 한다.  


## Chapter 5

Mathematical Induction(수학적 귀납법)  
개념은 쉽다.  

---
Well-Ordering Property  
어떤 집합 S가 있을 때 어떻게 S의 부분집합을 잡아도 그 안에서 최소 원소를 가진다면 Well-Ordered라고 한다. 
Well-Ordered인 집합에서 귀납법이 유효하다.  
이거는 왜 있는건지 모르겠다.  

---
Lame's Theorem  
유클리디안 알고리즘에서 몫이 항상 1이상이라는 사실을 이용하여 최소 계산 횟수를 찾는다. 
<img src=images/lame.jpg width=600>  
따라서 $b \rightarrow r_n$ 결과를 얻을 때까지 걸리는 시간을 계산할 수 있다.  
b 이하의 최대 피보나치 수가 n+1번째라고 할 때 n번 이하의 나머지 연산으로 $r_n$이 나온다.  
귀납적으로 $b≥f_{n+1}>(\frac{1+\sqrt{5}}{2})^{n-1}$  
$\log_{10}{\frac{1+\sqrt{5}}{2}}=0.208>1/5$  
$\log_{10}b>(n-1)log_{10}\frac{1+\sqrt{5}}{2}>\frac{n-1}{5}$  
$∴n-1<5log_{10}b$

---
집합같은 것도 재귀적으로 정의 가능하다.  
모든 영어 스트링 집합같은 걸 만들어도  
$S_0=\{a, b, c, ..., z\}, S_{i+1}=S_i+S_0$  
$S=\bigcup_{i=0}^∞S_i$ 이렇게 정의 가능하다.  
그리고 이렇게 정의해도 각 원소가 모두 유한한 스트링이기 때문에 countable이다. 

논리 연산 결과 역시 연산을 재귀적으로 정의 가능하다.  
트리도 재귀적으로 트리를 이어붙이는 것으로 정의 가능하다.  
Full Binary Tree도 마찬가지  
실수 집합이 $R\rightarrow R$ 초등함수 집합보다 크다는 것도 보일 수 있다.  

---
이후에는 재귀함수 관련 내용 나오는데 딱히 어렵지 않다.  



