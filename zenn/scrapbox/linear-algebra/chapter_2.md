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
つまり, 行列の積を型が小さい行列の積に帰着させる.

#### 区分け

$$
A =
\begin{pmatrix}
  1 & 2 & -1 & 0 \\
  2 & 1 & 3 & 2 \\
  1 & 2 & 3 & 4
\end{pmatrix}
$$

を例にとる.

行列$A$を横線と縦線とで四つの区画に分ける.

$$
A =
\left(
\begin{array}{ccc:c}
  1 & 2 & -1 & 0 \\
  2 & 1 & 3 & 2 \\
  \hdashline
  1 & 2 & 3 & 4
\end{array}
\right)
$$

分けたそれぞれの区画は一つの行列とみなすことができる.

$$
A_{11} =
\begin{pmatrix}
  1 & 2 & -1 \\
  2 & 1 & 3
\end{pmatrix}, \quad
A_{12} =
\begin{pmatrix}
  0 \\ 2
\end{pmatrix}, \quad
A_{21} =
\begin{pmatrix}
  1 & 2 & 3
\end{pmatrix}, \quad
A_{22} =
\begin{pmatrix}
  4
\end{pmatrix}
$$

と置いて

$$
A =
\begin{pmatrix}
  A_{11} & A_{12} \\
  A_{21} & A_{22}
\end{pmatrix}
$$

一般に$(l, m)$型行列$A = (a_{ij})$を$p-1$個の横線と$q-1$個の縦線とによって$pq$個の区画に分ける. 上から$s$番目, 左から$l$番目の区画の行列を$A_{st}$とする時,

$$
\begin{equation}
  A =
  \begin{pmatrix}
    A_{11} & A_{12} & \cdots & A_{1t} & \cdots & A_{1q} \\
    A_{21} & A_{22} & \cdots & A_{2t} & \cdots & A_{2q} \\
    \vdots & \vdots & \ddots & \vdots & \ddots & \vdots \\
    A_{s1} & A_{s2} & \cdots & A_{st} & \cdots & A_{sq} \\
    \vdots & \vdots & \ddots & \vdots & \ddots & \vdots \\
    A_{p1} & A_{p2} & \cdots & A_{pt} & \cdots & A_{pq} \\
  \end{pmatrix}
\end{equation}
$$

と書く.

これを行列の**区分け**という.

この区分けが行列の積にどう活きてくるのか.  
&darr;  
区分けされた行列同士の積が通常の行列の積と同じように実行できる.  
&darr;  
区分け(1)において, $A_{st}$が$(l_s, m_t)$型行列であるとする.

$$
l = l_1 + l_2 + \cdots + l_p, \\
m = m_1 + m_2 + \cdots + m_q
$$

である.

ここで$(m, n)$型行列$B = (b_{ij})$を

$$
B = 
\begin{pmatrix}
  B_{11} & B_{12} & \cdots & B_{1r} \\
  B_{21} & B_{22} & \cdots & B_{2r} \\
  \vdots & \vdots & \ddots & \vdots \\
  B_{q1} & B_{q2} & \cdots & B_{qr}
\end{pmatrix}
$$

のように$qr$個の区画にわけ, $B_{tu}(t=1, 2, \cdots, q, \quad u=1, 2, \cdots, r)$は$(m_t, n_u)$型行列とする.

$$
m = m_1 + m_2 + \cdots + m_q ,\\
n = n_1 + n_2 + \cdots + n_r
$$

ここで$A$と$B$での$m$の分割が同じである必要がある.

積$C = AB$を$pr$個の区画に分ける.

$$
C =
\begin{pmatrix}
  C_{11} & C_{12} & \cdots & C_{1r} \\
  C_{21} & C_{22} & \cdots & C_{2r} \\
  \vdots & \vdots & \ddots & \vdots \\
  C_{p1} & C_{p2} & \cdots & C_{pr} \\
\end{pmatrix}
$$

ここで, $C_{su}$は$(l_s, n_u)$型行列であるとする.

この時

$$
\begin{equation}
  C_{su} = A_{s1}B_{1u} + A_{s2}B_{2u} + \cdots + A_{sq}B_{qu} \qquad (s = 1, 2, \cdots, p \quad t = 1, 2, \cdots, r)
\end{equation}
$$

が成り立つという話.

:::details 証明っぽいもの
最初に, (2)の右辺が意味を持つことを確認する. 実際, $A_{st}$は$(l_s, m_t)$型行列で$B_{tu}$は$(m_t, n_u)$型行列である. よって$A_{st}B_{tu}$は定義できて, $t$の如何に拘らず$(l_s, n_u)$型行列となる. したがって, それらの和は（つまり(2)の右辺）は意味を持ち, 左辺$C_{su}$と同じく$(l_s, t_u)$型行列となる.

次に, (2)の両辺に対応する成分が等しいことを確認する. その成分を$(v, w)$成分とする.

$$
i = l_1 + l_2 + \cdots + l_{s-1} + v, \\
k = n_1 + n_2 + \cdots + n_{u-1} + w
$$

と置く.

$C_{su}$の$(v, w)$成分 = $C$の$(i, k)$成分 = $\sum_{j=1}^{m} a_{ij}b_{jk}$

一方

$A_{st}B_{tu}$の$(v, w)$成分 $= \sum_{j = m_1 + m_2 + \cdots + m_{t-1} + 1}^{m_1 + m_2 + \cdots + m_t} a_{ij}b_{jk}$

であるから

$\sum_{t=1}^{q}A_{st}B_{tu}$の$(v, w)$成分 $= \sum_{t=1}^{q}\sum_{j = m_1 + m_2 + \cdots + m_{t-1} + 1}^{m_1 + m_2 + \cdots + m_t} a_{ij}b_{jk} = \sum_{j=1}^{m}a_{ij}b_{jk}$

証明終

:::

:::details 例1
$p = q = r = 2$の時

$$
\begin{pmatrix} A_{11} & A_{12} \\ A_{21} & A_{22} \end{pmatrix}
\begin{pmatrix} B_{11} & B_{12} \\ B_{21} & B_{22} \end{pmatrix}
= \begin{pmatrix} A_{11}B_{11} + A_{12}B_{21} & A_{11}B_{12} + A_{12}B_{22} \\ A_{21}B_{11} + A_{22}B_{21} & A_{21}B_{12} + A_{22}B_{22} \end{pmatrix}.
$$

$A_{21}, B_{21}$が零行列ならば


$$
\begin{pmatrix} A_{11} & A_{12} \\ \mathcal{O} & A_{22} \end{pmatrix}
\begin{pmatrix} B_{11} & B_{12} \\ \mathcal{O} & B_{22} \end{pmatrix}
= \begin{pmatrix} A_{11}B_{11} & A_{11}B_{12} + A_{12}B_{22} \\ \mathcal{O} & A_{22}B_{22} \end{pmatrix}.
$$

さらに$A_{12}, B_{12}$も零行列ならば

$$
\begin{pmatrix} A_{11} & \mathcal{O} \\ \mathcal{O} & A_{22} \end{pmatrix}
\begin{pmatrix} B_{11} & \mathcal{O} \\ \mathcal{O} & B_{22} \end{pmatrix}
= \begin{pmatrix} A_{11}B_{11} & \mathcal{O} \\ \mathcal{O} & A_{22}B_{22} \end{pmatrix}.
$$

:::
