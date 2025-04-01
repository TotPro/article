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
- $\mathbf{a, b, c}$が線形独立$\iff x\mathbf{a}+y\mathbf{b}+z\mathbf{c}$ for $\{x,y,z\} \in \Z$と一意的に表せる.
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

### 平面上の直線とベクトル表示（助変数表示）

![figure1](./assets/1-2-1.drawio.svg)

上の図があるとき, 任意の実数$t$に対して$\mathbf{x_1}+t\mathbf{a}$を位置ベクトルとする点は直線$(l)$上にある.
つまり, 直線$(l)$上の任意の点$P$に対し、適当な実数$t$を取れば$\overrightarrow{(OP)}=\mathbf{x_1}+t\mathbf{a}$とかける.

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

### 法線ベクトル 平面ver
平面上の直線の方程式

$$
\begin{equation}
  (l): ax + by = c
\end{equation}
$$

を考える.
$(l)$に平行で原点を通る直線$l_0$は

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

$\mathbf{a}$が直線$l_0$と直交していることを表している→直線$(l)$とも直交する. 
$\mathbf{a}$を直線$(l)$の**法線ベクトル**と呼ぶ.
```txt:memo
別に$l$は$mathbf{a}$と角を成しているわけでないので内積自体はnot zero という理解で良い？
```
![figure2](./assets/1-2-2.drawio.svg)

:::details 例1
平面上の点$P$から直線$(l)$へ下した垂線の足$P'$および$P$との最短距離$\overline{PP'}$を求める.

![figure3](./assets/1-2-3.drawio.svg)

$P, P'$それぞれの位置ベクトルを$\mathbf{x_0, x'_0}$とする. 

直線$(l)$がベクトル表示

$$
(l): \mathbf{x} = \mathbf{x_1} + t\mathbf{a} \qquad (-\infty < t < \infty)
$$

で与えられている時, 

$$
\mathbf{x'_0} = \mathbf{x_1} + t\mathbf{a}, \quad (\mathbf{a, x_0 - x'_0}) = 0
$$

$t$を消去する.

$$
\begin{align*}
    (\mathbf{a, x_0 - x'_0}) &= 0 \\
    (\mathbf{a, x_0 - x_1 -}t\mathbf{a}) &= 0 \\
    (\mathbf{a, x_0}) - (\mathbf{a, x_1}) - (\mathbf{a, }t\mathbf{a}) &= 0 \\
    (\mathbf{a, x_0}) - (\mathbf{a, x_1}) - t(\mathbf{a, a}) &= 0 \\
    t(\mathbf{a, a}) &= (\mathbf{a, x_0}) - (\mathbf{a, x_1}) \\
    t(\mathbf{a, a}) &= (\mathbf{a, x_0 - x_1}) \\
    t &= \frac{(\mathbf{a, x_0 - x_1})}{(\mathbf{a, a})}
\end{align*}
$$

より

$$
\mathbf{x'_0} = \mathbf{x_1} + \frac{(\mathbf{a, x_0 - x_1})}{(\mathbf{a, a})}\mathbf{a}
$$

したがって, 最短距離$\| \mathbf{x_0 - x'_0} \|$は

$$
\begin{align*}
  \| \mathbf{x_0 - x'_0} \| &= \| \mathbf{x_0} - \mathbf{x_1} - \frac{(\mathbf{a, x_0 - x_1})}{(\mathbf{a, a})}\mathbf{a} \| \\
  \| \mathbf{x_0 - x'_0} \|^2 &= \| \mathbf{x_0} - \mathbf{x_1} - \frac{(\mathbf{a, x_0 - x_1})}{(\mathbf{a, a})}\mathbf{a} \|^2 \\
\end{align*}
$$

ここで$\mathbf{X} = \mathbf{x_0} - \mathbf{x_1}$をとして

$$
\begin{align*}
  \| \mathbf{x_0 - x'_0} \|^2 &= \| \mathbf{X} - \frac{(\mathbf{a, X})}{(\mathbf{a, a})}\mathbf{a} \|^2 \\
  \| \mathbf{x_0 - x'_0} \|^2 &= \| \mathbf{X} \|^2 + \frac{(\mathbf{a, X})^2}{(\mathbf{a, a})^2}(\mathbf{a, a}) - 2 \frac{(\mathbf{a, X})}{(\mathbf{a, a})}(\mathbf{X, a}) \\
  \| \mathbf{x_0 - x'_0} \|^2 &= \| \mathbf{X} \|^2 + \frac{(\mathbf{a, X})^2}{(\mathbf{a, a})} - 2 \frac{(\mathbf{a, X})^2}{(\mathbf{a, a})} \\
  \| \mathbf{x_0 - x'_0} \|^2 &= \| \mathbf{x_0} - \mathbf{x_1} \|^2 - \frac{(\mathbf{a, x_0 - x_1})^2}{(\mathbf{a, a})} \\
  \| \mathbf{x_0 - x'_0} \|^2 &= \frac{ \| \mathbf{a} \|^2 \| \mathbf{x_0} - \mathbf{x_1} \|^2 - (\mathbf{a, x_0 - x_1})^2}{ \| \mathbf{a} \|^2} \\
  \| \mathbf{x_0 - x'_0} \| &= \frac{ \sqrt{\| \mathbf{a} \|^2 \| \mathbf{x_0} - \mathbf{x_1} \|^2 - (\mathbf{a, x_0 - x_1})^2}}{ \| \mathbf{a} \|} \\
\end{align*}
$$

で与えられる.

直線$(l)$が方程式

$$
(l): (\mathbf{b, x}) = c
$$

で与えられている時,

$$
\mathbf{x_0 - x'_0} = s\mathbf{b}, \quad (\mathbf{b, x'_0}) = c
$$

$s$を消去する.

$$
\begin{align*}
  \mathbf{x'_0} = \mathbf{x_0} - s\mathbf{b}, \\
\\
  (\mathbf{b, x'_0}) &= c \\
  (\mathbf{b}, \mathbf{x_0} - s\mathbf{b}) &= c \\
  (\mathbf{b, x_0}) - s(\mathbf{b, b}) &= c \\
  s &= \frac{(\mathbf{b, x_0}) - c}{(\mathbf{b, b})}
\end{align*}
$$

より

$$
\mathbf{x'_0} = \mathbf{x_0} - \frac{(\mathbf{b, x_0}) - c}{(\mathbf{b, b})}\mathbf{b}
$$

したがって最短距離$\| \mathbf{x_0 - x'_0} \|$は

$$
\begin{align*}
  \| \mathbf{x_0 - x'_0} \| &= \| \frac{(\mathbf{b, x_0}) - c}{(\mathbf{b, b})}\mathbf{b} \| \\
  &= \frac{|( \mathbf{b, x_0}) - c |}{\| \mathbf{b} \|^2} \| \mathbf{b} \| \\
  &= \frac{|( \mathbf{b, x_0}) - c |}{\| \mathbf{b} \|}
\end{align*}
$$

で与えられる.

:::

空間内での直線も平面と同様にしてベクトル表示が行える.

:::details 例2
平面または空間内の二直線

$$
\begin{align*}
  (l_1): \mathbf{x} = \mathbf{x_1} + t\mathbf{a} \\
  (l_2): \mathbf{x} = \mathbf{x_2} + t\mathbf{b}
\end{align*}
$$

の交角を$\theta(0 \le \theta \le \pi / 2)$とすれば

$$
\cos(\theta) = \frac{|(\mathbf{a, b})|}{\|\mathbf{a}\| \|\mathbf{b}\|}
$$

```memo
直線の交角であってベクトルの交角ではないので絶対値がついていても良いのか. あと$\theta(0 \le \theta \le \pi / 2)$
```
:::

:::details 例3
位置ベクトル$\mathbf{x_0}$を持つ点$P$から$(l)$へ下した垂線の足$P'$の位置ベクトルが$\mathbf{x'_0}$で

直線$(l)$がベクトル表示

$$
(l): \mathbf{x} = \mathbf{x_1} + t\mathbf{a}
$$

で与えられている時, 平面と全く同様に点$P$と直線$(l)$の最短距離は

$$
\| \mathbf{x_0 - x'_0} \| = \frac{ \sqrt{\| \mathbf{a} \|^2 \| \mathbf{x_0} - \mathbf{x_1} \|^2 - (\mathbf{a, x_0 - x_1})^2}}{ \| \mathbf{a} \|}
$$

で与えられる.
:::

### 空間内の平面のベクトル表示
![figure4](./assets/1-2-4.drawio.svg)

空間内の平面も一つの一次方程式で表されるが, ベクトル表示でも表すことができる.

平面$(S)$上に一点$P_1$を取り, その位置ベクトルを$\mathbf{x_1}$とする. さらに平面$(S)$上に二つの線型独立なベクトル$\mathbf{a} = (\overrightarrow{P_1P_2})$と$\mathbf{b} = (\overrightarrow{P_1P_3})$を取る.

任意の実数$t, s$に対して, ベクトル$t\mathbf{a}+s\mathbf{b}$は平面$(S)$上にあり, $\mathbf{x_1} + t\mathbf{a} + s\mathbf{b}$を位置ベクトルとする点$P$は平面$(S)$上にある. つまり, 平面$(S)$上の任意の点$P$に対し, 適当な実数$t, s$を取れば, 
$(\overrightarrow{OP}) = \mathbf{x_1} + t\mathbf{a} + s\mathbf{b}$とかける.

平面のベクトル表示は点$P$の位置ベクトルを$\mathbf{x}$とした時,

$$
(S): \mathbf{x} = \mathbf{x_1} + t\mathbf{a} + s\mathbf{b} \qquad (-\infty < t,s < \infty)
$$

### 法線ベクトル 空間ver
空間上の平面の方程式

$$
\begin{equation}
  (S): ax + by + cz = d
\end{equation}
$$

があって, この平面$(S)$に平行で原点を通る平面$(S_0)$の方程式は

$$
\begin{equation}
  (S_0): ax + by + cz = 0
\end{equation}
$$

$\mathbf{a} = \begin{pmatrix} a \\ b \\ c \end{pmatrix}, \mathbf{x} = \begin{pmatrix} x \\ y \\ z \end{pmatrix}$とすると, (4)(5)は内積より以下のように表される.

$$
\begin{align*}
  (S): (\mathbf{a, x}) = d \\
  (S_0): (\mathbf{a, x}) = 0
\end{align*}
$$

$\mathbf{a}$が平面$(S_0)$と垂直であることを意味している→平面$(S)$とも垂直である.
$\mathbf{a}$を平面$(S)$の**法線ベクトル**と呼ぶ.

- 二つの平面$(S), (S')$の法線ベクトル$\mathbf{a, a'}$が直行する時, その二つの平面$(S), (S')$は直行するという.
- $\mathbf{a}$と$\mathbf{a'}$との交角を, $(S)$と$(S_0)$との交角という.

:::details 例4
点$P$から平面$(S)$へと下した垂線の足$P'$および$P$と平面$(S')$との最短距離$\overline{PP'}$を求める.

![figure5](./assets/1-2-5.drawio.svg)

$P, P'$のそれぞれの位置ベクトルを$\mathbf{x_0}, \mathbf{x'_0}$とする.

平面$(S)$が方程式

$$
(S): (\mathbf{a, x}) = d
$$

で与えられているとき, 

$$
\mathbf{x_0} - \mathbf{x'_0} = t\mathbf{a}, \quad (\mathbf{a, x'_0}) = d
$$

$t$を消去する.

$$
\begin{align*}
  \mathbf{x'_0} = \mathbf{x_0} - t\mathbf{a}, \\
  \\
  (\mathbf{a, x'_0}) &= d \\
  (\mathbf{a}, \mathbf{x_0} - t\mathbf{a}) &= d \\
  (\mathbf{a, x_0}) - t(\mathbf{a, a}) &= d \\
  t &= \frac{(\mathbf{a, x_0}) - d}{(\mathbf{a, a})}
\end{align*}
$$

より

$$
\mathbf{x'_0} = \mathbf{x_0} - \frac{(\mathbf{a, x_0}) - d}{(\mathbf{a, a})}\mathbf{a}
$$

したがって最短距離$\| \mathbf{x_0 - x'_0} \|$は

$$
\begin{align*}
  \| \mathbf{x_0 - x'_0} \| &= \| \frac{(\mathbf{a, x_0}) - d}{(\mathbf{a, a})}\mathbf{a} \| \\
  &= \frac{| (\mathbf{a, x_0}) - d|}{\| \mathbf{a} \|^2} \| \mathbf{a} \| \\
  &= \frac{| (\mathbf{a, x_0}) - d|}{\| \mathbf{a} \|}
\end{align*}
$$

で与えられる.

:::

:::details 例5
直線$(l)$が平面$(S)$に垂直でなければ, 直線$(l)$を含んだ平面$(S)$と直行する平面がちょうど一つ存在する.

![figure6](./assets/1-2-6.drawio.svg)

- $(S)$と$(S')$との交線$(l')$が直線$(l)$と成す角を, 直線$(l)$と平面$(S)$との交角という.

交角を$\theta(0 \le \theta \le \pi / 2)$とすれば

$$
\sin \theta = \frac{|(\mathbf{a,b})|}{\| \mathbf{a} \| \cdot \| \mathbf{b} \|}.
$$

```txt:memo
$\sin (\pi / 2 - \theta) = \cos (\theta)$
$\mathbf{a}$と$\mathbf{b}$の成す角を$\theta'$とすると$\sin \theta = \cos \theta'$
```

もし, 直線$(l)$が平面$(S)$に垂直であれば以下の図のように無数に直行する平面が存在する.

![figure7](./assets/1-2-7.drawio.svg)

:::

## 平面の回転と行列. 線形変換

### 行列
平面上の全ての点を原点$O$を中心に角$\alpha$だけ回転させた場合を考える. 点$P$が点$P'$に移ったとしてそれぞれの位置ベクトルを$\mathbf{x} = \begin{pmatrix} x \\ y \end{pmatrix}, \quad \mathbf{x'} = \begin{pmatrix} x' \\ y' \end{pmatrix}$とする.

![figure8](./assets/1-2-8.drawio.svg)

この時$x', y'$は三角関数の加法定理より以下のように表される.

$$
\begin{equation}
  \begin{rcases}
    x' = \cos \alpha \cdot x - \sin \alpha \cdot y \\
    y' = \sin \alpha \cdot x + \cos \alpha \cdot y
  \end{rcases}.
\end{equation}
$$

式(6)をまとめて書くと以下のようになる.

$$
\begin{equation}
  \begin{pmatrix}
    x' \\ y'
  \end{pmatrix} = 
  \begin{pmatrix}
    \cos \alpha & - \sin \alpha \\
    \sin \alpha & \cos \alpha
  \end{pmatrix}
  \begin{pmatrix}
    x \\ y
  \end{pmatrix}
\end{equation}
$$

簡単のために

$$
A = 
\begin{pmatrix}
  \cos \alpha & - \sin \alpha \\
  \sin \alpha & \cos \alpha
\end{pmatrix}
$$

とすると, 式(7)は以下のように簡潔にかける.

$$
\begin{equation}
  \mathbf{x'} = A \mathbf{x}.
\end{equation}
$$

この時, $A$を角$\alpha$に対する**行列**という.

ベクトルあるいは行列を構成する数を, そのベクトルあるいは行列の**成分**という.

式(7)(8)の右辺を, 行列とベクトルの積とみなす.

行列とベクトルの積に関して、次の諸性質がある.

$$
\begin{rcases}
  A(\mathbf{x}+\mathbf{y}) = A\mathbf{x} + A\mathbf{y} \\
  A(c\mathbf{x}) = c(A\mathbf{x})
\end{rcases}.
$$

次に角$\alpha$だけ回転したものをさらに角$\beta$だけ回転させた場合を考える. これによって点$P'$が点$P''$に移ったとする. 点$P''$の位置ベクトルを$\mathbf{x''}=\begin{pmatrix} x'' \\ y'' \end{pmatrix}$で表すと

$$
\begin{equation}
  \begin{pmatrix}
    x'' \\ y''
  \end{pmatrix} =
  \begin{pmatrix}
    \cos \beta & - \sin \beta \\
    \sin \beta & \cos \beta
  \end{pmatrix}
  \begin{pmatrix}
    x' \\ y'
  \end{pmatrix}
\end{equation}
$$

あるいは

$$
\begin{equation}
  \mathbf{x''} = B\mathbf{x'}
\end{equation}
$$

ただし

$$
B =
\begin{pmatrix}
  \cos \beta & - \sin \beta \\
  \sin \beta & \cos \beta
\end{pmatrix}.
$$

式(9)(10)に, 式(7)(8)をそれぞれ代入すれば

$$
\begin{equation*}
  \begin{pmatrix}
    x'' \\ y''
  \end{pmatrix} =
  \begin{pmatrix}
    \cos \beta & - \sin \beta \\
    \sin \beta & \cos \beta
  \end{pmatrix}
  \{
  \begin{pmatrix}
    \cos \alpha & - \sin \alpha \\
    \sin \alpha & \cos \alpha
  \end{pmatrix}
  \begin{pmatrix}
    x \\ y
  \end{pmatrix}
  \}
\end{equation*}
$$

あるいは

$$
\mathbf{x''} = B(A\mathbf{x})
$$

を得る.

また, 角$\alpha, \beta$の回転を続けて行うということは角$\alpha + \beta$の回転であるから

$$
\begin{pmatrix}
\end{pmatrix}
$$
