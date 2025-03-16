表記まとめ
- $A \xrightarrow{T} B$
  - $T$ : $A$から$B$への写像
  - $x$の$T$による像 : $A$の元に対して$T$によって決まる$B$の元
    - $T(x), Tx$で表す
- $A \xrightarrow{T} B \xrightarrow{S} C$
  - 合成写像 : $A$の元$x$に対して$S(Tx)$を対応させる写像
    - $S \circ T, ST$で表す
- $A \xrightarrow{T} A$
  - $A$の変換 : 写像$T$


# 第1章
## 平面および空間のベクトル
### 線形独立
- 2つのベクトル$\mathbf{a, b}$が平行でないとき, それらは**線形独立**である.
- 3つのベクトル$\mathbf{a,b,c}$が同一平面上の矢印で表せないとき, それらは**線形独立**である.
  - $\mathbf{a}=\overrightarrow{(OP)}, \mathbf{b}=\overrightarrow{(OQ)}, \mathbf{c}=\overrightarrow{(OR)}$と表示したときに4点$O, P, Q, R$が同一平面上にないこと.
- $\mathbf{a, b, c}$が線形独立$\iff x\mathbf{a}+y\mathbf{b}+z\mathbf{c}$ for $\{x,y,z\} \in \mathbb{Z}$と一意的に表せる.
  - $\mathbf{a,b,c}$の**線型結合**という.
### 内積
2つのベクトルの交わる角を$\theta(0\le\theta\le\pi)$とする.

$$
\lVert\mathbf{a}\rVert \cdot \lVert\mathbf{b}\rVert cos\theta = \frac{1}{2} (\lVert\mathbf{a}\rVert^2+\lVert\mathbf{b}\rVert^2 - \lVert\mathbf{b}-\mathbf{a}\rVert^2)
$$

この両辺を$\mathbf{a, b}$の**内積**と呼ぶ.
- $(\mathbf{a, b})$で表す.
- $(\mathbf{a, a}) = \lVert\mathbf{a}\rVert^2$.
- $(\mathbf{a, b}) = 0$が$\mathbf{a}$と$\mathbf{b}$が直交する条件.

諸々の関係
- $|(\mathbf{a,b})| \le \lVert\mathbf{a}\rVert \cdot \lVert\mathbf{b}\rVert$
  シュヴァルツの不等式
- $\rVert\mathbf{a}+\mathbf{b}\lVert \le \lVert\mathbf{a}\rVert+\lVert\mathbf{b}\rVert$
  三角不等式
- $c(\mathbf{a, b}) = (c\mathbf{a,b}) = (\mathbf{a}, c\mathbf{b})$
- $(\mathbf{a}, \mathbf{b}_{1} + \mathbf{b}_{2}) = (\mathbf{a},\mathbf{b}_{1}) + (\mathbf{a}, \mathbf{b}_{2})$
- $(\mathbf{a}_{1} + \mathbf{a}_{2}, \mathbf{b}) = (\mathbf{a}_1, \mathbf{b}) + (\mathbf{a}_{2}, \mathbf{b})$
- $(\mathbf{a, b}) = (\mathbf{b, a})$

## 直線と平面
![figure1](./assets/1-2-1.drawio.svg)
上の図があるとき, 任意の実数$t$に対して$\mathbf{x_1}+t\mathbf{a}$を位置ベクトルとする点は直線$(l)$上にある.
つまり, 直線$(l)$上の任意の点$P$に対し、適当な実数$t$を取れば$\overrightarrow{(OP)}=\mathbf{x_1}+t\mathbf{a}$とかける.
### ベクトル表示（助変数表示）
$P$の位置ベクトルを$\mathbf{x}$とする.

$$
(l): \mathbf{x}=\mathbf{x_1}+t\mathbf{a}\qquad(-\infty < t < \infty).
$$

- 変数$t$: 助変数
- $\mathbf{a}$: 直線$(l)$の方向ベクトル

$P_2$の座標ベクトルを$\mathbf{x_2}$とし, 

$$
\mathbf{x} = \begin{pmatrix}x \\ y \end{pmatrix} \qquad \mathbf{x_1} = \begin{pmatrix}x_1 \\ y_1 \end{pmatrix} \qquad \mathbf{x_2} = \begin{pmatrix}x_2 \\ y_2 \end{pmatrix} = \mathbf{x_1} + \mathbf{a}
$$

とする.

$$
\begin{rcases}
x - x_1 = t(x_2 - x_1) \\
y - y_1 = t(y_2 - y_1)
\end{rcases},
$$

```txt:memo
$x_2 - x_1$も$y_2 - y_1$もそれぞれ$\mathbf{a}$の成分だから という理解で良い？
```

$$
\begin{equation}
  \frac{x - x_1}{x_2 - x_1} = \frac{y - y_1}{y_1 - y_2}
\end{equation}
$$

(1)が直線の方程式になる.

一般形になおすと

$$
\begin{align*}
  (x - x_1)(y_2 - y_1) &= (y - y_1)(x_2 - x_1) \\
  x(y_2 - y_1) - x_1y_2 + x_1y_1 &= y(x_2 - x_1) - y_1x_2 + y_1x_1
\end{align*}
\\
  (y_2 - y_1)x - (x_2 - x_1)y - x_1y_2 + x_1y_1 + y_1x_2 - y_1x_1 = 0
$$

### 法線ベクトル
平面上の直線の方程式

$$
\begin{equation}
  (l): ax + by = c
\end{equation}
$$

を考える.
$l$に平行で原点を通る直線$l_0$は

$$
\begin{equation}
  (l_0): ax + by = 0
\end{equation}
$$

$\mathbf{a} = \begin{pmatrix} a \\ b \end{pmatrix}, \mathbf{x} = \begin{pmatrix} x \\ y \end{pmatrix}$とすると, (2)(3)は内積より以下のように表される.

$$
\begin{align*}
  (l): (\mathbf{a, x}) = c \\
  (l_0): (\mathbf{a, x}) = 0
\end{align*}
$$

$\mathbf{a}$が直線$l_0$と直交していることを表している→直線$l$とも直交する. 
$\mathbf{a}$を$l$の**法線ベクトル**と呼ぶ.
```txt:memo
別に$l$は$mathbf{a}$と角を成しているわけでないので内積自体はnot zero という理解で良い？
```
![figure2](./assets/1-2-2.drawio.svg)
