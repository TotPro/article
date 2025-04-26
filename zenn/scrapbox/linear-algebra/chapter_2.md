# 第2章

## 行列の演算と定義

### 行列(Matrix)
- **$(m, n)$型行列**...自然数$m, n$に対して, $m \times n$個の複素数を縦$m$個, 横$n$個に並べたもの.  
$a_{ij} \in \mathbb{C} \quad (1 \le i \le m, 1 \le j \le n)$とした時に, 以下で表す.

$$
A =
\begin{pmatrix}
  a_{11} & a_{12} & \cdots & a_{1n} \\
  a_{21} & a_{22} & \cdots & a_{2n} \\
  \vdots & \vdots & \ddots & \vdots \\
  a_{m1} & a_{m2} & \cdots & a_{mn}
\end{pmatrix}
$$

![figure1](./ch2-assets/2-1-1.drawio.svg)

- **実行列**...成分がすべて実数であるような行列.

行列$A$を$(a_{ij})$と略記することがある（が,　混同の元なのでなるべく避けたほうがよい）

- **$m$項列ベクトル**...$(m, 1)$型行列  
![figure2](./ch2-assets/2-1-2.drawio.svg)

- **$n$項行ベクトル**...$(1, n)$型行列]  
![figure3](./ch2-assets/2-1-3.drawio.svg)

### 行列演算の一般化
#### 和
二つの$(m,n)$型行列$A, B$に対し, 以下を$A$と$B$の和とする.

$$
A =
\begin{pmatrix}
  a_{11} & a_{12} & \cdots & a_{1n} \\
  a_{21} & a_{22} & \cdots & a_{2n} \\
  \vdots & \vdots & \ddots & \vdots \\
  a_{m1} & a_{m2} & \cdots & a_{mn} \\
\end{pmatrix},
\quad
B =
\begin{pmatrix}
  b_{11} & b_{12} & \cdots & b_{1n} \\
  b_{21} & b_{22} & \cdots & b_{2n} \\
  \vdots & \vdots & \ddots & \vdots \\
  b_{m1} & b_{m2} & \cdots & b_{mn} \\
\end{pmatrix}
$$

ならば

$$
A + B =
\begin{pmatrix}
  a_{11} + b_{11} & a_{12} + b_{12} & \cdots & a_{1n} + b_{1n} \\
  a_{21} + b_{21} & a_{22} + b_{22} & \cdots & a_{2n} + b_{2n} \\
  \vdots & \vdots & \ddots & \vdots \\
  a_{m1} + b_{m1} & a_{m2} + b_{m2} & \cdots & a_{mn} + b_{mn} \\
\end{pmatrix}.
$$

#### 定数倍
$c \in \mathbb{C}$に対して, 行列の各成分を$c$倍して得られる行列を$A$の$c$倍と言い, $cA$で表す.

$$
cA =
\begin{pmatrix}
  ca_{11} & ca_{12} & \cdots & ca_{1n} \\
  ca_{21} & ca_{22} & \cdots & ca_{2n} \\
  \vdots & \vdots & \ddots & \vdots \\
  ca_{m1} & ca_{m2} & \cdots & ca_{mn} \\
\end{pmatrix}
$$

---
- $-1A$を$-A$で表す.
- $A+(-B)$を$A-B$で表す.
- 成分が全て$0$であるような行列を**零行列**という.
  - $\mathcal{O}$で表す.
  - $A + \mathcal{O} = A$
  - $A - A = \mathcal{O}$
---

次の演算法則が成り立つ.
- $(A + B) + C = A + (B + C)$
- $A + B = B + A$
- $c(A + B) = cA + cB$
- $(c + d)A = cA + dA$
- $(cd)A = c(dA)$
- $1A = A$
- $0A = \mathcal{O}$

#### 積
$(l, m)$型行列$A$, $(m, n)$型行列$B$の積を$(l, n)$型行列となるように定義する.

$$
A =
\begin{pmatrix}
  a_{11} & a_{12} & \cdots & a_{1m} \\
  a_{21} & a_{22} & \cdots & a_{2m} \\
  \vdots & \vdots & \ddots & \vdots \\
  a_{l1} & a_{l2} & \cdots & a_{lm}
\end{pmatrix},
\quad
B =
\begin{pmatrix}
  b_{11} & b_{12} & \cdots & b_{1n} \\
  b_{21} & b_{22} & \cdots & b_{2n} \\
  \vdots & \vdots & \ddots & \vdots \\
  b_{m1} & b_{m2} & \cdots & b_{mn}
\end{pmatrix}
$$

$$
AB =
\begin{pmatrix}
  c_{11} & c_{12} & \cdots & c_{1n} \\
  c_{21} & c_{22} & \cdots & c_{2n} \\
  \vdots & \vdots & \ddots & \vdots \\
  c_{l1} & c_{l2} & \cdots & c_{ln}
\end{pmatrix}
$$

としたときに

$$
c_{ik} = \sum_{j = 1}^{m} a_{ij}b_{jk} \qquad (1 \le i \le l, 1 \le k \le n)
$$

となる.

積$AB$が定義されるからといって$BA$が必ず定義できるわけではないし, 定義できたとしても$AB == BA$であるとは限らない.

次の諸性質を持つ.
- $A$が$(k, l)$型, $B$が$(l, m)$型, $C$が$(m, n)$型の行列ならば

$$
(AB)C = A(BC)
$$

:::details 証明
式の両辺が定義され共に$(k, n)$型行列になることは明らかである.

$$
A = (a_{pq}), \quad B = (b_{qr}), \quad C = (c_{rs}) \\
(1 \le p \le k, \quad 1 \le q \le l, \quad 1 \le r \le m, \quad 1 \le s \le n)
$$

とする. $AB$の$(p, r)$成分は$\sum_{q = 1}^{l} a_{pq}b_{qr}$であるから, $(AB)C$の$(p, s)$成分は

$$
\sum_{r = 1}^{m} \{ \sum_{q = 1}^{l} a_{pq}b_{qr} \} c_{rs} = \sum_{r = 1}^{m} \sum_{q = 1}^{l} a_{pq}b_{qr} c_{rs}.
$$

一方, $BC$の$(q, s)$成分は$\sum_{r = 1}^{m} b_{qr}c_{rs}$であるから, $A(BC)$の$(p, s)$成分は

$$
\sum_{q = 1}^{l} \{ a_{pq} \sum_{r = 1}^{m} b_{qr}c_{rs} \} = \sum_{q = 1}^{l} \sum_{r = 1}^{m} a_{pq}b_{qr}c_{rs}.
$$

したがって, $(AB)C = A(BC)$である.

証明終

:::

- $A(B + C) = AB + AC$
- $(A + B)C = AC + AC$
- $A\mathcal{O} = \mathcal{O}A$

### 単位行列
**$n$次単位行列**...$(n, n)$型行列で$(i, i)$成分$1 \le i \le n$のみが$1$, その他の成分が全て$0$である行列

$$
E =
\begin{pmatrix}
  1 & 0 & \cdots & 0 \\
  0 & 1 & \cdots & 0 \\
  \vdots & \vdots & \ddots & \vdots \\
  0 & 0 & \cdots & 1
\end{pmatrix}.
$$

$E_n$と表すこともある.

単位行列の$(i. j)$成分を$E = (\delta_{ij})$と略記できる. $\delta_{ij}$をクロネッカーの記号と言う.

- 任意の$(m, n)$型行列$A$に対して$AE = A, EA = A$.

### 線型結合
$(m, n)$型行列$A = (a_{ij})$の第$j$列だけを取り出せばそれは$m$項列ベクトルである. これを行列$A$の第$j$列ベクトルと言う.

$$
\mathbf{a}_{1} = \begin{pmatrix} a_{11} \\ a_{21} \\ \vdots \\ a_{m1} \end{pmatrix}, \quad
\mathbf{a}_{2} = \begin{pmatrix} a_{12} \\ a_{22} \\ \vdots \\ a_{m2} \end{pmatrix}, \quad
\cdots , \quad
\mathbf{a}_{n} = \begin{pmatrix} a_{1n} \\ a_{2n} \\ \vdots \\ a_{mn} \end{pmatrix}
$$

とするとき

$$
A = (\mathbf{a}_1, \mathbf{a}_2, \cdots,  \mathbf{a}_n)
$$

と書くことがある. 行ベクトルでも同様.

単位行列$E_n$の$n$個の列ベクトル

$$
\mathbf{e}_1 = \begin{pmatrix} 1 \\ 0 \\ \vdots \\ 0 \end{pmatrix}, \quad
\mathbf{e}_1 = \begin{pmatrix} 0 \\ 1 \\ \vdots \\ 0 \end{pmatrix}, \quad
\cdots, \quad
\mathbf{e}_1 = \begin{pmatrix} 0 \\ 0 \\ \vdots \\ 1 \end{pmatrix}
$$

を$n$項単位ベクトルと言う.

$A$が$(l, m)$型行列, $B$が$(m, n$型行列である時, $B$の列ベクトルを$\mathbf{b}_1, \mathbf{b}_2, \cdots, \mathbf{b}_n$とすれば$(l, n)$型行列$AB$の列ベクトルは$A\mathbf{b}_1, A\mathbf{b}_2, \cdots , A\mathbf{b}_n$である.

$$
AB = (A\mathbf{b}_1, A\mathbf{b}_2, \cdots , A\mathbf{b}_n).
$$

特に$B = E$の時

$$
AE = (A\mathbf{e}_1, A\mathbf{e}_2, \cdots , A\mathbf{e}_n).
$$

任意の$n$項列ベクトル$\mathbf{x} = (x_i)$は単位ベクトルにより,

$$
\mathbf{x} = x_1\mathbf{e}_1 + x_2\mathbf{e}_2 + \cdots + x_n\mathbf{e}_n
$$

と表される.

一般に, $n$項列ベクトル$\mathbf{a}_1, \mathbf{a}_2, \cdots , \mathbf{a}_n$に対し

$$
x_1\mathbf{a}_1 + x_2\mathbf{a}_2 + \cdots + x_n\mathbf{a}_n
$$

の形のベクトルを$\mathbf{a}_1, \mathbf{a}_2, \cdots , \mathbf{a}_n$の線型結合と言う.

### 複素共役行列, 転置行列
#### 複素共役行列
行列$A=(a_{ij})$の各成分を共役複素数で置き換えた行列$(\tilde{a}_{ij})$を複素共役行列と言い$\bar{A}$で表す.

次の諸関係が成り立つ.
- $\overline{\overline{A}} = A$.
- $\overline{A + B} = \bar{A} + \bar{B}$.
- $\overline{cA} = \bar{c}\bar{A}$.
- $\overline{AB} = \bar{A}\bar{B}$.

#### 転置行列
$(m, n)$型行列$A$の縦横を逆にした$(n, m)$型行列を$A$の転置行列と言い, $^{t}A$で表す.

$$
A =
\begin{pmatrix}
  a_{11} & a_{12} & \cdots & a_{1n} \\
  a_{21} & a_{22} & \cdots & a_{2n} \\
  \vdots & \vdots & \ddots & \vdots \\
  a_{m1} & a_{m2} & \cdots & a_{mn}
\end{pmatrix}
$$

ならば$A$の転置行列は

$$
^{t}A =
\begin{pmatrix}
  a_{11} & a_{21} & \cdots & a_{m1} \\
  a_{12} & a_{22} & \cdots & a_{m2} \\
  \vdots & \vdots & \ddots & \vdots \\
  a_{1n} & a_{2n} & \cdots & a_{mn}
\end{pmatrix}.
$$

次の諸関係が成り立つ.
- $^{t}(^{t}A) = A$.
- $^{t}(\bar{A}) = \overline{^{t}A}$.
- $^{t}(A + B) = ^{t}A + ^{t}B$.
- $^{t}(cA) = c^{t}A$.
- $^{t}(AB) = ^{t}B ^{t}A$.

### 行列の積 $\to$ 小さい行列の積
