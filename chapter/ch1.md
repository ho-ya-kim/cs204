# Chapter 1
## Propositional Logic
### proposition : 명제

|기호|의미|영어|
|:---:|:---:|:---:|
|$\neg$|**not**|Negation|
|$\wedge$|**and**|Conjunction|
|$\vee$|**or**|Disjunction|
|$\to$|**implies**| Implication|
|$\leftrightarrow$| **iff** (if and only if)| Biconditional|
|$\otimes$| **XOR** | Exclusive or


### 역, 대우, 이
$p \to q$ 명제에 대해

* Converse : 역
$$q \to p$$

* Contrapsoitive : 대우 (대우는 항상 참이다.)
$$\neg q \to \neg p$$

*  Inverse : 이
$$\neg p \to \neg q$$

### Truth Table
각 조건?에 대해 명제가 참인지를 확인할 수 있는 표

> *How many rows are needed for a truth table with 𝑛 propositional
variables?*
> 
> 만약 $n$개의 변수?에 연관되어 있다면, 각 변수가 True, False인 경우에 대해 모두 살펴봐야 하므로 $2^n$개의 열이 필요하다.

### 동치 (Equivalent)
두 명제가 같은 Truth Table을 가진다면, *logically equivalent*라 한다.
$$\tilde p \equiv \tilde q$$
$$\tilde p \iff \tilde q$$


## Propositional Equivalences

### 참, 거짓, 우발성(?)
* Tautology : 참 (True)
* Contradiction : 거짓 (False)
* Contingency : 우발성 (따져봐야 앎)

### De Mordan's Laws
고딩 집합에서 나오는 그거임
$$ \neg (p \wedge q) \equiv \neg q \vee \neg p $$
$$ \neg (p \vee q) \equiv \neg q \wedge \neg p $$

### Key Logical Equivalences