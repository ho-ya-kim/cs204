# Chapter 1: 논리와 증명

## 1.1 명제 논리 (Propositional Logic)

### 명제 (Proposition)

명제는 참(True) 또는 거짓(False)으로 판별할 수 있는 선언적 문장을 말합니다. 예를 들어:

- "1 + 3 = 4"는 참인 명제입니다.
- "0 + 0 = 2"는 거짓인 명제입니다.
- "x + 1 = 2"와 같이 변수 $x$가 포함된 문장은 명제가 아닙니다. 변수가 특정 값으로 정해지지 않으면 참인지 거짓인지 판단할 수 없기 때문입니다.

### 논리 연산 (Logical Connectives)

논리 연산은 명제들 사이의 관계를 나타내기 위한 도구입니다.

1. **부정 (Negation)**  
   명제 $p$의 부정은 $\neg p$로 표현하며, 이는 "p가 참이 아님"을 의미합니다.
   $$
   \begin{array}{c|c}
   p & \neg p \\
   \hline
   T & F \\
   F & T \\
   \end{array}
   $$

2. **논리곱 (Conjunction)**  
   명제 $p$와 $q$의 논리곱은 $p \land q$로 표현하며, "p와 q가 모두 참"일 때 참이 됩니다.
   $$
   \begin{array}{c|c|c}
   p & q & p \land q \\
   \hline
   T & T & T \\
   T & F & F \\
   F & T & F \\
   F & F & F \\
   \end{array}
   $$

3. **논리합 (Disjunction)**  
   명제 $p$와 $q$의 논리합은 $p \lor q$로 표현하며, "p 또는 q가 참"일 때 참입니다.
   $$
   \begin{array}{c|c|c}
   p & q & p \lor q \\
   \hline
   T & T & T \\
   T & F & T \\
   F & T & T \\
   F & F & F \\
   \end{array}
   $$

4. **배타적 논리합 (Exclusive Or)**  
   $p$와 $q$ 중 하나만 참일 때 참이 되는 논리합으로, $p \oplus q$로 표현됩니다.
   $$
   \begin{array}{c|c|c}
   p & q & p \oplus q \\
   \hline
   T & T & F \\
   T & F & T \\
   F & T & T \\
   F & F & F \\
   \end{array}
   $$

5. **조건문 (Implication)**  
   $p$와 $q$가 명제일 때, $p \to q$는 "p이면 q이다"를 의미하는 조건문입니다. 조건문은 다음과 같은 진리표로 표현됩니다.
   $$
   \begin{array}{c|c|c}
   p & q & p \to q \\
   \hline
   T & T & T \\
   T & F & F \\
   F & T & T \\
   F & F & T \\
   \end{array}
   $$

6. **쌍조건문 (Biconditional)**  
   $p$와 $q$가 명제일 때, $p \leftrightarrow q$는 "p와 q가 동시에 참이거나 동시에 거짓일 때 참"인 논리식을 나타냅니다.
   $$
   \begin{array}{c|c|c}
   p & q & p \leftrightarrow q \\
   \hline
   T & T & T \\
   T & F & F \\
   F & T & F \\
   F & F & T \\
   \end{array}
   $$

## 1.2 논리 연산 (Logical Connectives)

### 부정 (Negation)

명제 $p$의 부정은 $\neg p$로 표현하며, 이는 "p가 참이 아님"을 의미합니다.
$$
\begin{array}{c|c}
p & \neg p \\
\hline
T & F \\
F & T \\
\end{array}
$$

### 논리곱 (Conjunction)

명제 $p$와 $q$의 논리곱은 $p \land q$로 표현하며, "p와 q가 모두 참"일 때 참이 됩니다.
$$
\begin{array}{c|c|c}
p & q & p \land q \\
\hline
T & T & T \\
T & F & F \\
F & T & F \\
F & F & F \\
\end{array}
$$

### 논리합 (Disjunction)

명제 $p$와 $q$의 논리합은 $p \lor q$로 표현하며, "p 또는 q가 참"일 때 참입니다.
$$
\begin{array}{c|c|c}
p & q & p \lor q \\
\hline
T & T & T \\
T & F & T \\
F & T & T \\
F & F & F \\
\end{array}
$$

### 배타적 논리합 (Exclusive Or)

$p$와 $q$ 중 하나만 참일 때 참이 되는 논리합으로, $p \oplus q$로 표현됩니다.
$$
\begin{array}{c|c|c}
p & q & p \oplus q \\
\hline
T & T & F \\
T & F & T \\
F & T & T \\
F & F & F \\
\end{array}
$$

### 조건문 (Implication)

$p$와 $q$가 명제일 때, $p \to q$는 "p이면 q이다"를 의미하는 조건문입니다. 조건문은 다음과 같은 진리표로 표현됩니다.
$$
\begin{array}{c|c|c}
p & q & p \to q \\
\hline
T & T & T \\
T & F & F \\
F & T & T \\
F & F & T \\
\end{array}
$$
**조건문** $p \to q$는 논리적으로 $\neg p \lor q$와 동일합니다.

### 역, 이, 대우 (Converse, Inverse, Contrapositive)

1. **역 (Converse)**: $p \to q$의 **역**은 $q \to p$로 나타냅니다.
2. **이 (Inverse)**: $p \to q$의 **이**는 $\neg p \to \neg q$로 나타냅니다.
3. **대우 (Contrapositive)**: $p \to q$의 **대우**는 $\neg q \to \neg p$로 나타냅니다.

#### 예시:
"비가 오면 나는 집에 있다"라는 조건문 $p \to q$에 대해:
- **역**: "내가 집에 있으면 비가 온다" ($q \to p$)
- **이**: "비가 오지 않으면 나는 집에 있지 않다" ($\neg p \to \neg q$)
- **대우**: "내가 집에 있지 않으면 비가 오지 않는다" ($\neg q \to \neg p$)

대우는 원래 조건문과 항상 논리적으로 동일한 진리값을 가집니다.

### 쌍조건문 (Biconditional)

$p$와 $q$가 명제일 때, $p \leftrightarrow q$는 "p와 q가 동시에 참이거나 동시에 거짓일 때 참"인 논리식을 나타냅니다.
$$
\begin{array}{c|c|c}
p & q & p \leftrightarrow q \\
\hline
T & T & T \\
T & F & F \\
F & T & F \\
F & F & T \\
\end{array}
$$

### 예시: 진리표 작성

$p \lor q \to \neg r$에 대한 진리표를 구성합니다:
$$
\begin{array}{c|c|c|c|c|c}
p & q & r & \neg r & p \lor q & (p \lor q) \to \neg r \\
\hline
T & T & T & F & T & F \\
T & T & F & T & T & T \\
T & F & T & F & T & F \\
T & F & F & T & T & T \\
F & T & T & F & T & F \\
F & T & F & T & T & T \\
F & F & T & F & F & T \\
F & F & F & T & F & T \\
\end{array}
$$

## 1.3 명제의 등가 (Propositional Equivalences)

### 항진 명제와 모순 명제 (Tautologies and Contradictions)

- **항진 명제 (Tautology)**: 항상 참인 명제입니다. 예를 들어, $p \lor \neg p$는 참입니다.
- **모순 명제 (Contradiction)**: 항상 거짓인 명제입니다. 예를 들어, $p \land \neg p$는 거짓입니다.
- **상황 명제 (Contingency)**: 참일 수도 있고 거짓일 수도 있는 명제입니다. 예를 들어, $p \lor q$는 $p$와 $q$의 진리값에 따라 달라집니다.

### 드모르간 법칙 (De Morgan's Laws)

드모르간 법칙은 다음과 같이 표현할 수 있습니다:
$$
\neg (p \land q) \equiv \neg p \lor \neg q
$$
$$
\neg (p \lor q) \equiv \neg p \land \neg q
$$

이 법칙을 통해 논리 연산을 부정 연산과 결합하여 쉽게 변환할 수 있습니다.

### 주요 논리 법칙 (Key Logical Equivalences)

- **항등 법칙 (Identity Laws)**: 
  $$
  p \land T \equiv p, \quad p \lor F \equiv p
  $$
- **우세 법칙 (Domination Laws)**: 
  $$
  p \lor T \equiv T, \quad p \land F \equiv F
  $$
- **이중 부정 법칙 (Double Negation Law)**: 
  $$
  \neg (\neg p) \equiv p
  $$
- **교환 법칙 (Commutative Laws)**: 
  $$
  p \lor q \equiv q \lor p, \quad p \land q \equiv q \land p
  $$
- **분배 법칙 (Distributive Laws)**: 
  $$
  p \land (q \lor r) \equiv (p \land q) \lor (p \land r)
  $$
  $$
  p \lor (q \land r) \equiv (p \lor q) \land (p \lor r)
  $$


## 1.4 술어와 양화사 (Predicates and Quantifiers)

### 술어 논리 (Predicate Logic)

술어 논리는 변수와 술어를 사용하여 더 복잡한 명제를 표현합니다. 예를 들어, "모든 사람은 죽는다"는 술어 논리로 표현할 수 있습니다.

### 양화사 (Quantifiers)

- **전칭 양화사 (Universal Quantifier)**: 
  $$
  \forall x \, P(x)
  $$
  이는 "모든 $x$에 대해 $P(x)$가 참이다"를 의미합니다.
  
- **존재 양화사 (Existential Quantifier)**: 
  $$
  \exists x \, P(x)
  $$
  이는 "어떤 $x$가 존재하여 $P(x)$가 참이다"를 의미합니다.

#### 예시

- $\forall x \, (x > 0)$: "모든 $x$는 양수이다."
- $\exists x \, (x < 0)$: "어떤 $x$는 음수이다."

### 양화사와 논리 연산 (Quantifiers and Logical Connectives)

양화사는 논리 연산과 결합될 수 있습니다. 예를 들어:
$$
\neg \forall x \, P(x) \equiv \exists x \, \neg P(x)
$$
$$
\neg \exists x \, P(x) \equiv \forall x \, \neg P(x)
$$


## 1.5 중첩된 양화사 (Nested Quantifiers)

중첩된 양화사는 여러 양화사가 결합된 형태입니다. 예를 들어:
$$
\forall x \, \exists y \, (x + y = 0)
$$
이 식은 "모든 $x$에 대해, 어떤 $y$가 존재하여 $x + y = 0$이 성립한다"를 의미합니다.

### 중첩된 양화사 사용법

- 양화사의 순서는 논리적 의미에 큰 영향을 미칩니다. 예를 들어:
  $$
  \forall x \, \exists y \, (P(x, y)) \neq \exists y \, \forall x \, (P(x, y))
  $$
  앞의 식은 "모든 $x$에 대해 적어도 하나의 $y$가 존재하여 $P(x, y)$가 성립한다"는 뜻이지만, 뒤의 식은 "적어도 하나의 $y$가 존재하여 모든 $x$에 대해 $P(x, y)$가 성립한다"는 뜻입니다.



## 1.6 증명 기법 (Methods of Proof)

### 진리표를 이용한 증명 (Proof by Truth Table)

모든 가능한 경우에 대해 진리값을 계산하여 명제의 참/거짓 여부를 확인하는 방법입니다.

### 직접 증명 (Direct Proof)

주어진 가정으로부터 결론을 이끌어내는 증명 방식입니다. $p \to q$를 증명하려면, $p$가 참일 때 $q$도 참임을 보여야 합니다.

### 간접 증명 (Indirect Proof)

결론의 부정을 가정하여 모순을 유도하는 방법입니다. $p \to q$를 증명하려면 $\neg q$가 참일 때 $\neg p$가 참임을 보여야 합니다.


## 1.7 정규형 (Normal Forms)

### 주된 논리합 정규형 (Principal Disjunctive Normal Form, PDNF)

모든 참인 경우를 논리곱으로 표현한 후 논리합으로 결합합니다.

### 주된 논리곱 정규형 (Principal Conjunctive Normal Form, PCNF)

모든 거짓인 경우를 논리합으로 표현한 후 논리곱으로 결합합니다.

### 정규형 변환 예시

- $p \lor (\neg p \land q)$를 PDNF로 표현하면:
  $$
  (p \land q) \lor (\neg p \land q)
  $$

- 동일한 식을 PCNF로 표현하면:
  $$
  (\neg p \lor q) \land (p \lor q)
  $$

위와 같은 방식으로 주어진 명제를 정규형으로 변환할 수 있습니다.
