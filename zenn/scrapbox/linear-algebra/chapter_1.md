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

![figure1](./ch1-assets/1-2-1.drawio.svg)

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
![figure2](./ch1-assets/1-2-2.drawio.svg)

:::details 例1
平面上の点$P$から直線$(l)$へ下した垂線の足$P'$および$P$との最短距離$\overline{PP'}$を求める.

![figure3](./ch1-assets/1-2-3.drawio.svg)

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
![figure4](./ch1-assets/1-2-4.drawio.svg)

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

![figure5](./ch1-assets/1-2-5.drawio.svg)

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

![figure6](./ch1-assets/1-2-6.drawio.svg)

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

![figure7](./ch1-assets/1-2-7.drawio.svg)

:::

## 平面の回転と行列. 線形変換

### 行列
平面上の全ての点を原点$O$を中心に角$\alpha$だけ回転させた場合を考える. 点$P$が点$P'$に移ったとしてそれぞれの位置ベクトルを$\mathbf{x} = \begin{pmatrix} x \\ y \end{pmatrix}, \quad \mathbf{x'} = \begin{pmatrix} x' \\ y' \end{pmatrix}$とする.

![figure8](./ch1-assets/1-3-1.drawio.svg)

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
\begin{equation}
  \mathbf{x''} = B(A\mathbf{x})
\end{equation}
$$

を得る.

また, 角$\alpha, \beta$の回転を続けて行うということは角$\alpha + \beta$の回転であるから

$$
\begin{pmatrix}
  x'' \\ y''
\end{pmatrix} = 
\begin{pmatrix}
  \cos (\alpha + \beta) & - \sin (\alpha + \beta) \\
  \sin (\alpha + \beta) & \cos (\alpha + \beta)
\end{pmatrix}
\begin{pmatrix}
  x \\ y
\end{pmatrix}
$$

あるいは

$$
\begin{equation}
  \mathbf{x''} = C\mathbf{x}
\end{equation}
$$

ただし

$$
C = 
\begin{pmatrix}
  \cos (\alpha + \beta) & - \sin (\alpha + \beta) \\
  \sin (\alpha + \beta) & \cos (\alpha + \beta)
\end{pmatrix}.
$$

行列$C$を行列$B$と行列$A$との積と定義し, $C=BA$と表記する.

$$
B(A\mathbf{x}) = (BA)\mathbf{x}
$$

が成り立つ.

もう少し一般的な話として...

$$
A =
\begin{pmatrix}
  a & b \\
  c & d
\end{pmatrix}
$$

も行列と言うことにする.

ベクトル$\mathbf{x} = \begin{pmatrix} x \\ y \end{pmatrix}$との積も同様に

$$
\begin{equation}
  \mathbf{x'} = A\mathbf{x} =
  \begin{pmatrix}
    a & b \\
    c & d
  \end{pmatrix}
  \begin{pmatrix}
    x \\ y
  \end{pmatrix} =
  \begin{pmatrix}
    ax + by \\
    cx + dy
  \end{pmatrix}
\end{equation}
$$

と定義できる.

行列$A$による変換を行ったあと, 行列$B = \begin{pmatrix} p & q \\ r & s \end{pmatrix}$による変換を続けて行う.

定義より

$$
\begin{align*}
  \mathbf{x''} = B\mathbf{x'} =
  \begin{pmatrix}
    p & q \\
    r & s
  \end{pmatrix}
  \begin{pmatrix}
    ax + by \\
    cx + dy
  \end{pmatrix} &=
  \begin{pmatrix}
    p(ax + by) + q(cx + dy)) \\
    r(ax + by) + s(cx + dy)
  \end{pmatrix} \\
  &=
  \begin{pmatrix}
    (pa + qc)x + (pb + qd)y \\
    (ra + sc)x + (rb + sd)y
  \end{pmatrix}
\end{align*}
$$

これもまた

$$
\mathbf{x''} = B(A\mathbf{x}) = (BA)\mathbf{x}.
$$

![figure9](./ch1-assets/1-3-2.drawio.svg)

:::details 例6
式(13)において, $\mathbf{x}, \mathbf{x'}$をそれぞれ点$P, P'$の位置ベクトルとすれば平面から平面への写像（平面の変換）が引き起こされる.

例えば

$$
A =
\begin{pmatrix}
  1 & 0 \\
  0 & -1
\end{pmatrix}
$$

とすれば, $A$の引き起こす変換は平面のすべての点を$x$軸に関して対称移動させる変換である.

$$
A\mathbf{x} =
\begin{pmatrix}
  1 & 0 \\
  0 & -1
\end{pmatrix}
\begin{pmatrix}
  x \\ y
\end{pmatrix} =
\begin{pmatrix}
  x \\ -y
\end{pmatrix}
$$

これを$x$軸に関する**折返し**という.

:::

:::details 例7
変換の順序で結果に違いがあるかどうか?

- 角$\pi / 2$の回転に対応する行列$A = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}$
- $x$軸に関する折返しの行列$B = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$

とする.

したがって

$$
AB = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}, \qquad BA = \begin{pmatrix} 0 & -1 \\ -1 & 0 \end{pmatrix}
$$

となり, $AB \neq BA$である.

実際, $x$軸に関して折返してから$\pi / 2$回転させる操作($AB$)と$\pi / 2$回転させてから$x$軸に関して折返す操作$(BA)$は結果が異なる.

$$
(AB)\mathbf{x} =
\begin{pmatrix}
  0 & 1 \\
  1 & 0
\end{pmatrix}
\begin{pmatrix}
  x \\ y
\end{pmatrix} =
\begin{pmatrix}
  y \\ x
\end{pmatrix}
$$

$$
(BA)\mathbf{x} =
\begin{pmatrix}
  0 & -1 \\
  -1 & 0
\end{pmatrix}
\begin{pmatrix}
  x \\ y
\end{pmatrix} =
\begin{pmatrix}
  -y \\ -x
\end{pmatrix}
$$

:::

### 線形変換 平面ver
任意の行列$A$と, 任意のベクトル$\mathbf{x, y}$, 定数$c$に対して

$$
\begin{equation}
  \begin{rcases}
    A(\mathbf{x} + \mathbf{y}) = A\mathbf{x} + A\mathbf{y} \\
    A(c\mathbf{x}) = c(A\mathbf{x})
  \end{rcases}
\end{equation}
$$

が成り立つ.

この性質を, 行列$A$によって引き起こされる$\bold{V}^2$の変換$T_A: \mathbf{x} \to A\mathbf{x}$の**線形性**と言う.

一般に, 任意のベクトル$\mathbf{x}$に対してもう一つのベクトル$T\mathbf{x}$を対応させる規則$T$($\bold{V}^2$の変換$T$)があって, 以下の二つの性質を持つとする.

```memo:txt
↑これ, 規則$T$って言うより写像て呼んだ方がわかりよくない?
```

$$
\begin{rcases}
  T(\mathbf{x} + \mathbf{y}) = T\mathbf{x} + T\mathbf{y} \\
  T(c\mathbf{x}) = c(T\mathbf{x})
\end{rcases}
$$

このような$T$を, $\bold{V}^2$の**線形変換**と言う.

式(14)は, 任意の行列$A$によって定まる変換$T_A$が線形変換であることを示している.

線形変換は、ある行列によって定まる変換に限ることが証明される.

:::details 例8
$T$が線形変換である時, 単位ベクトル$\mathbf{e_1, e_2}$に着目して,

$$
T\mathbf{e_1} = \begin{pmatrix} a \\ c \end{pmatrix}, \quad T\mathbf{e_2} = \begin{pmatrix} b \\ d \end{pmatrix}
$$

とする. 任意のベクトル$\mathbf{x} = \begin{pmatrix} x \\ y \end{pmatrix}$は, 

$$
\mathbf{x} = x\mathbf{e_1} + y\mathbf{e_2}
$$

と表されるから, $T$の線形性より

$$
\begin{align*}
  T\mathbf{x} = T(x\mathbf{e_1} + y\mathbf{e_2}) &= T(x\mathbf{e_1}) + T(y\mathbf{e_2}) \\
  &= xT(\mathbf{e_1}) + yT(\mathbf{e_2}) \\
  &= x\begin{pmatrix} a \\ c \end{pmatrix} + y\begin{pmatrix} b \\ d \end{pmatrix} \\
  &= \begin{pmatrix} ax + by \\ cx + dy \end{pmatrix} \\
  &= \begin{pmatrix} a & b \\ c & d \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix}
\end{align*}
$$

したがって, $T$は行列$A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$によって定まる変換.

:::

:::details 例9
$\mathbf{o}$ではないベクトル$\mathbf{a}$がある. 任意のベクトル$\mathbf{x}$に対して$\mathbf{a}$に平行なベクトル$\mathbf{x'}$で$\mathbf{x}-\mathbf{x'}$が$\mathbf{a}$と直行するようなものがただ一つ存在する.

![figure10](./ch1-assets/1-3-3.drawio.svg)

$\mathbf{x}$に$\mathbf{x'}$を対応させる変換$T$を$\bold{V}^2$の$\mathbf{a}$への**射影子**と言い, $\mathbf{x'} = T\mathbf{x}$を$\mathbf{x}$の$\mathbf{a}$への**正射影**と言う.
例1より

$$
T\mathbf{x} = \frac{(\mathbf{a, x})}{(\mathbf{a, a})} \mathbf{a}
$$

射影子$T$は$\bold{V}^2$の線形変換である.

:::

## 三次行列と$\bold{V}^3$の線形変換

### 線形変換 空間ver
空間の任意のベクトル$\mathbf{x}$に対して, もう一つの空間ベクトル$T\mathbf{x}$を対応させる規則$T$が以下の二つの性質を持つとする.

$$
\begin{rcases}
  T(\mathbf{x} + \mathbf{y}) = T\mathbf{x} + T\mathbf{y} \\
  T(c\mathbf{x}) = c(T\mathbf{x})
\end{rcases}.
$$

このような$T$を$\bold{V}^3$の**線形変換**と言う.

### 三次行列
九個の数$a_{ij}(1 \le i, j \le 3)$を正方形に並べた

$$
A =
\begin{pmatrix}
  a_{11} & a_{12} & a_{13} \\
  a_{21} & a_{22} & a_{23} \\
  a_{31} & a_{32} & a_{33}
\end{pmatrix}
$$

を三次の行列と言う.

行列とベクトルの積, 行列同士の積が今までと全く同様に定義される.

$\mathbf{x} = \begin{pmatrix} x \\ y \\ z \end{pmatrix}, B = \begin{pmatrix} b_{11} & b_{12} & b_{13} \\ b_{21} & b_{22} & b_{23} \\ b_{31} & b_{32} & b_{33} \end{pmatrix}$に対して,

$$
A\mathbf{x} =
\begin{pmatrix}
  a_{11}x + a_{12}y + a_{13}z \\
  a_{21}x + a_{22}y + a_{23}z \\
  a_{31}x + a_{32}y + a_{33}z
\end{pmatrix}
\\
AB = 
\begin{pmatrix}
  a_{11}b_{11} + a_{12}b_{21} + a_{13}b_{31} & a_{11}b_{12} + a_{12}b_{22} + a_{13}b_{32} & a_{11}b_{13} + a_{12}b_{23} + a_{13}b_{33} \\
  a_{21}b_{11} + a_{22}b_{21} + a_{23}b_{31} & a_{21}b_{12} + a_{22}b_{22} + a_{23}b_{32} & a_{21}b_{13} + a_{22}b_{23} + a_{23}b_{33} \\
  a_{31}b_{11} + a_{32}b_{21} + a_{33}b_{31} & a_{31}b_{12} + a_{32}b_{22} + a_{33}b_{32} & a_{31}b_{13} + a_{32}b_{23} + a_{33}b_{33}
\end{pmatrix}
$$

によって定義する.

$AB = \begin{pmatrix} c_{11} & c_{12} & c_{13} \\ c_{21} & c_{22} & c_{23} \\ c_{31} & c_{32} & c_{33} \end{pmatrix}$として

$$
c_{ik} = \sum_{j = 1}^{3}a_{ik}b_{kj} = a_{i1}b_{1k} + a_{i2}b_{2k} + a_{i3}b_{3k} \quad (i, k = 1, 2, 3)
$$

と表記することもある(こっちの方が簡潔)

これに対しても同様に

$$
\begin{equation}
  \begin{rcases}
    (AB)\mathbf{x} = A(B\mathbf{x}) \\
    (AB)C = A(BC) 
  \end{rcases}
\end{equation} \\
\begin{equation}
  \begin{rcases}
    A(\mathbf{x} + \mathbf{y}) = A\mathbf{x} + A\mathbf{y} \\
    A(c\mathbf{x}) = c(A\mathbf{x})
  \end{rcases}
\end{equation} \\
$$

が成り立つ.

三次行列$A$に対し, $\bold{V}^3$の変換を$T_A$を

$$
T_A = A\mathbf{x}
$$

によって定義すれば(16)により$T_A$は$\bold{V}^3$の線形変換である.

:::details 例10
$T$が線形変換である時, 単位ベクトル$\mathbf{e_1, e_2, e_3}$に着目して,

$$
T\mathbf{e_1} = \begin{pmatrix} a_{11} \\ a_{21} \\ a_{31} \end{pmatrix}, \quad T\mathbf{e_2} = \begin{pmatrix} a_{12} \\ a_{22} \\ a_{32} \end{pmatrix}, \quad T\mathbf{e_3} = \begin{pmatrix} a_{13} \\ a_{23} \\ a_{33} \end{pmatrix}
$$

とする. 任意のベクトル$\mathbf{x} = \begin{pmatrix} x \\ y \\ z \end{pmatrix}$は,

$$
\mathbf{x} = x\mathbf{e_1} + y\mathbf{e_2} + z\mathbf{e_3}
$$

と表されるから, $T$の線形性より

$$
\begin{align*}
  T\mathbf{x} = T(x\mathbf{e_1} + y\mathbf{e_2}) &= T(x\mathbf{e_1}) + T(y\mathbf{e_2}) +T(z\mathbf{e_3}) \\
  &= xT(\mathbf{e_1}) + yT(\mathbf{e_2}) + zT(\mathbf{e_3}) \\
  &= x\begin{pmatrix} a_{11} \\ a_{21} \\ a_{31} \end{pmatrix} + y\begin{pmatrix} a_{12} \\ a_{22} \\ a_{32} \end{pmatrix} + z\begin{pmatrix} a_{13} \\ a_{23} \\ a_{33} \end{pmatrix} \\
  &= \begin{pmatrix} a_{11}x + a_{12}y + a_{13}z \\ a_{21}x + a_{22}y + a_{23}z \\ a_{31}x + a_{32}y + a_{33}z \end{pmatrix} \\
  &= \begin{pmatrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \\ a_{31} & a_{32} & a_{33} \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} \\
  &= A\mathbf{x} = T_A\mathbf{x}
\end{align*}
$$

したがって, $T = T_A$.

:::

:::details 例11
空間の全ての点を原点に関して対称移動させる変換に対応する行列は

$$
\begin{pmatrix}
  -1 & 0 & 0 \\
  0 & -1 & 0 \\
  0 & 0 & -1
\end{pmatrix}.
$$

実際

$$
\begin{pmatrix}
  -1 & 0 & 0 \\
  0 & -1 & 0 \\
  0 & 0 & -1
\end{pmatrix}
\begin{pmatrix}
  x \\ y \\ z
\end{pmatrix} =
\begin{pmatrix}
  -x \\ -y \\ -z
\end{pmatrix}
$$

また$z$軸まわりに角$\alpha$だけ回転させる変換に対応する行列は

$$
\begin{pmatrix}
  \cos \alpha & - \sin \alpha  & 0\\
  \sin \alpha & \cos \alpha & 0 \\
  0 & 0 & 1
\end{pmatrix}
$$

```memo:txt
$z$軸まわりなので平面の点の回転と同じなので(1, 1)(1, 2)(2, 1)(2, 2)成分は平面の時と同じ
また$z$軸に対応する座標は変わらないので1
```

:::

:::details 例12
$\mathbf{o}$でないベクトル$\mathbf{a}$に対し, $\mathbf{a}$への射影子$T$が$\bold{V}^2$の場合と全く同様に定義できて$\bold{V}^3$の線形変換となる.
このときも

$$
T\mathbf{x} = \frac{(\mathbf{a, x})}{(\mathbf{a, a})} \mathbf{a}
$$

一方

線形独立なベクトル$\mathbf{b, c}$があるとする. 任意のベクトル$\mathbf{x}$に対し, $\mathbf{b,c}$の線型結合$\mathbf{x'}$で, $\mathbf{x}-\mathbf{x'}$が$\mathbf{b}$とも$\mathbf{c}$とも直交するような唯一存在する.

```memo:txt
つまり$\mathbf{b, c}$の張る平面と直交するような$\mathbf{x}-\mathbf{x'}$が唯一存在する
```

$\mathbf{x}$に$\mathbf{x'}$を対応させるような変換$S$を$\bold{V}^3$の$\mathbf{b, c}$の張る平面への射影子と言い, $\mathbf{x'} = S\mathbf{x}$を$\mathbf{x}$の$\mathbf{b, c}$の張る正射影と言う.

![figure11](./ch1-assets/1-3-4.drawio.svg)

例4より

$$
T\mathbf{x} = \mathbf{x} - \frac{(\mathbf{a, x})}{(\mathbf{a, a})} \mathbf{a}
$$

射影子$S$は$\bold{V}^3$の線形変換である.

:::

## 行列式およびベクトル積

### 行列式$(2 \times 2)$
行列$A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$に対して, 

$$
ad - bc
$$

を$A$の行列式(determinant)と言い,

$$
\begin{vmatrix}
a & b \\
c & d
\end{vmatrix}, \quad
|A|, \quad \det A
$$

などで表す.

$\mathbf{a} = \begin{pmatrix} a \\ c \end{pmatrix}, \mathbf{b} = \begin{pmatrix} b \\ d \end{pmatrix}$とするとき, $\det (\mathbf{a, b})$と表すこともある.

次の諸性質がある.
- $\mathbf{a, b}$が線形独立 $\iff$ $\det (\mathbf{a, b}) \neq 0$
- $\det (\mathbf{a, b}) = -\det (\mathbf{b, a})$
- $\det (\mathbf{a_1}+\mathbf{a_2}, \mathbf{b}) = \det (\mathbf{a_1, b}) + \det (\mathbf{a_2, b})$
- $\det (c\mathbf{a, b}) = c \det (\mathbf{a, b})$
- $|AB| = |A||B|$

$\det (\mathbf{a, b})$は$\mathbf{a, b}$の張る平行四辺形の面積に符号をつけたものに等しい.

$$
\mathbf{x_1} = \begin{pmatrix} x_1 \\ y_1 \end{pmatrix}, \quad \mathbf{x_2} = \begin{pmatrix} x_2 \\ y_2 \end{pmatrix}, \quad X = \begin{pmatrix} x_1 & x_2 \\ y_1 & y_2 \end{pmatrix}
$$

とすれば

$$
|AX| = \det(A\mathbf{x_1}, A\mathbf{x_2}).
$$

また$|AX| = |A||X| = |A|\det(\mathbf{x_1, x_2})$であるから

$$
|A| = \frac{\det(A\mathbf{x_1}, A\mathbf{x_2})}{\det(\mathbf{x_1, x_2})}
$$

線形変換$T_A$によって任意の平行四辺形は平行四辺形に移るが, 行列式$|A|$はその面積比に等しい.

```memo:txt
$\mathbf{x_1, x_2}$が張る平行四辺形→$A\mathbf{x_1}, A\mathbf{x_2}$が張る平行四辺形
っていう変換
$|A|$はその面積比
```

したがって, 行列式$|A|$は線形変換$T_A$によって決まり, 座標系の選び方によらない.

:::details 例13
$ad - bd \neq 0$ならば, 連立方程式

$$
\begin{rcases}
  ax + by = e \\
  cx + dy = f
\end{rcases}
$$

は唯一の解を持ち

$$
x = \frac
{
  \begin{vmatrix}
    e & b \\
    f & d
  \end{vmatrix}
}
{
  \begin{vmatrix}
    a & b \\
    c & d
  \end{vmatrix}
}, \quad
y = \frac
{
  \begin{vmatrix}
    a & e \\
    c & f
  \end{vmatrix}
}
{
  \begin{vmatrix}
    a & b \\
    c & d
  \end{vmatrix}
}

$$

で与えられる. (愚直に計算すれば確かめられる)

また

$$
\mathbf{a} = \begin{pmatrix} a \\ c \end{pmatrix}, \quad \mathbf{b} = \begin{pmatrix} b \\ d \end{pmatrix}, \quad \mathbf{c} = \begin{pmatrix} e \\ f \end{pmatrix}
$$

と置けば上の連立一次方程式は

$$
x\mathbf{a} + y\mathbf{b} = \mathbf{c}
$$

とかける.

$\det (\mathbf{a, b}) \neq 0$の時, $\mathbf{a, b}$は線形独立であるから任意の$\mathbf{c}$は$\mathbf{a, b}$の線型結合で一意的に表される. つまり$x, y$が一意的に決まるので方程式は唯一の解を持つ.

:::

### 外積
$\bold{V}^3$の二つのベクトル$\mathbf{a, b}$が線型独立である時, 次の性質を満たすベクトル$\mathbf{c}$がちょうど一つ存在する.
- $\mathbf{c}$は$\mathbf{a}$とも$\mathbf{b}$とも直交する.
- $\mathbf{a, b, c}$は右手系を成す.
- $\mathbf{c}$の長さは$\mathbf{a, b}$の貼る平行四辺形の面積に等しい.

:::details 右手系
単位ベクトル$\mathbf{e}_1, \mathbf{e}_2, \mathbf{e}_3,$がそれぞれ右手の親指, 人差し指, 中指の上にあるような座標系を**右手系**と言う

:::

この$\mathbf{c}$を$\mathbf{a}$と$\mathbf{b}$の**外積**または**ベクトル積**と言う.
- $\mathbf{a} \times \mathbf{b}$で表す.
- $\mathbf{a, b}$が線型独立でない時, $\mathbf{a} \times \mathbf{b} = \mathbf{o}$.
- $\mathbf{a} \times \mathbf{b} = -\mathbf{b} \times \mathbf{a}$.
- $c(\mathbf{a} \times \mathbf{b}) = c\mathbf{a} \times \mathbf{b} = \mathbf{a} \times c\mathbf{b}$.

![figure12](./ch1-assets/1-3-5.drawio.svg)

右手系に関して$\mathbf{a} = \begin{pmatrix} a \\ b \\ c \end{pmatrix}, \quad \mathbf{b} = \begin{pmatrix} a' \\ b' \\ c' \end{pmatrix}$ならば

$$
\begin{equation}
  \mathbf{a} \times \mathbf{b} =
  \begin{pmatrix}
    \begin{vmatrix}
      b & b' \\
      c & c'
    \end{vmatrix} \\ \\
    \begin{vmatrix}
      c & c' \\
      a & a'
    \end{vmatrix} \\ \\
    \begin{vmatrix}
      a & a' \\
      b & b'
    \end{vmatrix}
  \end{pmatrix}
\end{equation}.
$$

:::details 証明
式(17)の右辺を$\mathbf{c}$として$\mathbf{c}$が三つの条件
1. $\mathbf{c}$は$\mathbf{a}$とも$\mathbf{b}$とも直交する.
2. $\mathbf{a, b, c}$は右手系を成す.
3. $\mathbf{c}$の長さは$\mathbf{a, b}$の貼る平行四辺形の面積に等しい.

を満たすことを示す.

1. 直接計算によって確かめられる.

$$
\begin{align*}
  &\| \mathbf{a} \|^2 = a^2 + b^2 + c^2 \\
  &\| \mathbf{c} \|^2 = (bc' - cb')^2 + (ca' - ac')^2 + (ab' - ba')^2 \\
  &\| \mathbf{c} - \mathbf{a} \|^2 = (bc' - cb' - a)^2 + (ca' - ac' - b)^2 + (ab' - ba' - c)^2 \\
  &\| \mathbf{a} \|^2 + \| \mathbf{c} \|^2 - \| \mathbf{c} - \mathbf{a} \| = \text{\textasciitilde} = 0
\end{align*} \\
\therefore \frac{1}{2} (\| \mathbf{a} \|^2 + \| \mathbf{c} \|^2 - \| \mathbf{c} - \mathbf{a} \|) = (\mathbf{a, c}) = 0
$$

$\mathbf{a}$と$\mathbf{c}$が直交することが確かめられた. $\mathbf{b}$と$\mathbf{c}$も同様. (のはず)

2. $\mathbf{a} = \mathbf{e}_1, \mathbf{b} = \mathbf{e}_2$に関しては, 式(17)の両辺は共に$\mathbf{e}_3$となる.  
ベクトルの組$\mathbf{e}_1, \mathbf{e}_2, \mathbf{e}_3$から連続的に$\mathbf{a, b, c}$まで$\mathbf{a, b}$の線型独立性を保ちながら移す. もし途中で左手系に変わる場合, 変わる瞬間に$\mathbf{c}$の長さは$0$になり$\mathbf{a, b}$が線型独立であることに反するため, $\mathbf{a, b, c}$は右手系である.
3. 

$$
\begin{align*}
  \| \mathbf{c} \|^2 &= (bc' - cb')^2 + (ca' - ac')^2 + (ab' - ba')^2 \\
  &= (a^2 + b^2 + c^2)(a'^2 + b'^2 + c'^2) - (aa' + bb' + cc')^2 \\
  &= \| \mathbf{a} \|^2 \| \mathbf{b} \|^2 - (\mathbf{a, b})^2
\end{align*} \\
\therefore \| c \| = \sqrt{\| \mathbf{a} \|^2 \| \mathbf{b} \|^2 - (\mathbf{a, b})^2}
$$

$\| c \|$は$\mathbf{a, b}$の張る平行四辺形の面積に等しい.

証明終.

:::

- $\mathbf{a} \times (\mathbf{b}_1 + \mathbf{b}_2) = \mathbf{a} \times \mathbf{b}_1 + \mathbf{a} \times \mathbf{b}_2$
- $(\mathbf{a}_1 + \mathbf{a}_2) \times \mathbf{b} = \mathbf{a_1} \times \mathbf{b} + \mathbf{a_2} \times \mathbf{b}$

:::details 例14
$\mathbf{x}_0$を位置ベクトルとする点$P$と$(l): \mathbf{x} = \mathbf{x}_1 + t\mathbf{a}$を持つ直線との最短距離は例3より

$$
\frac{\| \mathbf{a} \times (\mathbf{x}_0 - \mathbf{x}_1) \|}{\| \mathbf{a} \|}
$$

```memo:txt
例3の最短距離の公式と証明の3.を照らし合わせるときれいに外積で表せる
```

:::

::::details 平行六面体
ベクトル$\mathbf{a, b, c}$の張る平行六面体の体積$v$は

$$
v = |(\mathbf{a} \times \mathbf{b}, \mathbf{c})|
$$

で与えられる.

![figure13](./ch1-assets/1-5-1.drawio.svg)

:::details 証明
$\mathbf{c}$と$\mathbf{a} \times \mathbf{b}$との交角を$\theta (0 \le \theta \le \pi)$とすれば

$$
v = \| \mathbf{a} \times \mathbf{b} \| \cdot \| \mathbf{c} \| | \cos\theta | = |(\mathbf{a} \times \mathbf{b}, \mathbf{c}) |.
$$

:::

::::

### 行列式$(3 \times 3)$
三次行列$A = \begin{pmatrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \\ a_{31} & a_{32} & a_{33} \end{pmatrix}$に対して, 

$$
\mathbf{a}_1 = \begin{pmatrix} a_{11} \\ a_{21} \\ a_{31} \end{pmatrix}, \quad
\mathbf{a}_2 = \begin{pmatrix} a_{12} \\ a_{22} \\ a_{32} \end{pmatrix}, \quad
\mathbf{a}_3 = \begin{pmatrix} a_{13} \\ a_{23} \\ a_{33} \end{pmatrix}
$$

と置く.

$\mathbf{a}_1 \times \mathbf{a}_2$と$\mathbf{a}_3$との内積$(\mathbf{a}_1 \times \mathbf{a}_2, \mathbf{a}_3)$を行列$A$の行列式と言い,

$$
\begin{vmatrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \\ a_{31} & a_{32} & a_{33} \end{vmatrix}, \quad
|A|, \quad
\det A, \quad
\det(\mathbf{a}_1, \mathbf{a}_2, \mathbf{a}_3)
$$

などで表す.

$\det (\mathbf{a}_1, \mathbf{a}_2, \mathbf{a}_3)$はベクトル$\mathbf{a}_1, \mathbf{a}_2, \mathbf{a}_3$の張る平行六面体の体積に符号をつけたものに等しい.

- $\mathbf{a}_1, \mathbf{a}_2, \mathbf{a}_3$が線形独立 $\iff$ $\det (\mathbf{a}_1, \mathbf{a}_2, \mathbf{a}_3) \neq 0$.
- $(\mathbf{a}_1, \mathbf{a}_2, \mathbf{a}_3)$のうち, 二つのベクトルの順序を交換すれば, $\det (\mathbf{a}_1, \mathbf{a}_2, \mathbf{a}_3)$は符号が変わり, 絶対値は等しい.
- $\det (\mathbf{a}_1 + \mathbf{a'}_1, \mathbf{a}_2, \mathbf{a}_3) = \det (\mathbf{a}_1, \mathbf{a}_2, \mathbf{a}_3) + \det (\mathbf{a'}_1, \mathbf{a}_2, \mathbf{a}_3)$. $\mathbf{a}_2, \mathbf{a}_3$も同様.
- $\det (c\mathbf{a}_1, \mathbf{a}_2, \mathbf{a}_3) = c \cdot \det (\mathbf{a}_1, \mathbf{a}_2, \mathbf{a}_3)$. $\mathbf{a}_2, \mathbf{a}_3$も同様.

実際に計算してみると

$$
\begin{align*}
  \det A &= (\mathbf{a}_1 \times \mathbf{a}_2, \mathbf{a}_3) \\
  &= \begin{vmatrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \\ a_{31} & a_{32} & a_{33} \end{vmatrix} \\
  &= a_{13} \begin{vmatrix} a_{21} & a_{22} \\ a_{31} & a_{32} \end{vmatrix} +
      a_{23} \begin{vmatrix} a_{31} & a_{32} \\ a_{11} & a_{12} \end{vmatrix} +
      a_{33} \begin{vmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{vmatrix} \\
  &= a_{13}a_{21}a_{32} + a_{23}a_{31}a_{12} + a_{33}a_{11}a_{22} - a_{13}a_{22}a_{31} - a_{23}a_{32}a_{11} - a_{33}a_{12}a_{21}
\end{align*}
$$

$|AB| = |A||B|$も確かめられる. (計算が面倒くさいので割愛)

$$
\mathbf{x}_1 = \begin{pmatrix} x_1 \\ y_1 \\ z_1 \end{pmatrix}, \quad
\mathbf{x}_2 = \begin{pmatrix} x_2 \\ y_2 \\ z_2 \end{pmatrix}, \quad
\mathbf{x}_3 = \begin{pmatrix} x_3 \\ y_3 \\ z_3 \end{pmatrix}, \quad
X = \begin{pmatrix} x_1 & x_2 & x_3 \\ y_1 & y_2 & y_3 \\ z_1 & z_2 & z_3 \end{pmatrix} 
$$

とすれば

$$
|AX| = \det (A\mathbf{x}_1, A\mathbf{x}_2, A\mathbf{x}_3)
$$

また$|AX| = |A||X| = |A| \cdot \det (\mathbf{x}_1, \mathbf{x}_2, \mathbf{x}_3)$であるから

$$
|A| = \frac{\det (A\mathbf{x}_1, A\mathbf{x}_2, A\mathbf{x}_3)}{\det (\mathbf{x}_1, \mathbf{x}_2, \mathbf{x}_3)}
$$

以下, $(2 \times 2)$と同様.

:::details 例15
二直線が同一平面上にないとき, それらは**捩れの位置**にあると言う. つまり二直線が交わらず平行でないことである.

二直線

$$
(l_1): \mathbf{x} = \mathbf{x}_1 + t\mathbf{a} \\
(l_2): \mathbf{x} = \mathbf{x}_2 + t\mathbf{a}
$$

が捩れの位置にあるとき, この両方と直行するよう直線がちょうど一本存在することを示し, $(l_1)$と$(l_2)$の最短距離を求める.

![figure14](./ch1-assets/1-5-2.drawio.svg)

点$P, Q$のそれぞれの位置ベクトルを

$$
\mathbf{p} = \mathbf{x}_1 + t\mathbf{a} \\
\mathbf{q} = \mathbf{x}_2 + s\mathbf{b}
$$

とする.

点$P, Q$を結ぶ直線が$(l_1), (l_2)$と直交する条件は

$$
(\mathbf{q} - \mathbf{p}, \mathbf{a}) = (\mathbf{q} - \mathbf{p}, \mathbf{b}) = 0
$$

つまり

$$
\begin{align*}
  & (\mathbf{q} - \mathbf{p}, \mathbf{a}) = 0 \\
  & (\mathbf{x}_2 + s\mathbf{b} - \mathbf{x}_1 - t\mathbf{a}, \mathbf{a}) = 0 \\
  & (\mathbf{x}_2 - \mathbf{x}_1 + s\mathbf{b} - t\mathbf{a}, \mathbf{a}) = 0 \\
  & (\mathbf{x}_2 - \mathbf{x}_1, \mathbf{a}) + (s\mathbf{b}, \mathbf{a}) - (t\mathbf{a}, \mathbf{a}) = 0 \\
  & t(\mathbf{a, a}) - s(\mathbf{b, a}) = (\mathbf{x}_2 - \mathbf{x}_1, \mathbf{a}) \\
  & t(\mathbf{a, a}) - s(\mathbf{a, b}) = (\mathbf{a}, \mathbf{x}_2 - \mathbf{x}_1), \\
  \\
  & (\mathbf{q} - \mathbf{p}, \mathbf{b}) = 0 \\
  & \qquad \wr \\
  & t(\mathbf{b, a}) - s(\mathbf{b, b}) = (\mathbf{b}, \mathbf{x}_2 - \mathbf{x}_1)
\end{align*} \\
\begin{rcases}
  t(\mathbf{a, a}) - s(\mathbf{a, b}) = (\mathbf{a}, \mathbf{x}_2 - \mathbf{x}_1) \\
  t(\mathbf{b, a}) - s(\mathbf{b, b}) = (\mathbf{b}, \mathbf{x}_2 - \mathbf{x}_1)
\end{rcases}
$$

これを$t, s$に関する連立一次方程式と考える.

$$
\begin{align*}
  \begin{vmatrix}
    (\mathbf{a, a}) & -(\mathbf{a, b}) \\
    (\mathbf{b, a}) & -(\mathbf{b, b})
  \end{vmatrix} &=
  -(\mathbf{a, a})(\mathbf{b, b}) + (\mathbf{b, a})^2 \\
  &= - \| \mathbf{a} \|^2 \| \mathbf{b} \|^2 + (\mathbf{b, a})^2 \\
  &= - \{ \| \mathbf{a} \|^2 \| \mathbf{b} \|^2 - (\mathbf{b, a})^2 \} \\
  &\ne 0
\end{align*}
$$

より連立一次方程式は唯一の解$s_0, t_0$を持つ.

$\mathbf{x}_1 + t_0\mathbf{a}, \quad \mathbf{x}_2 + s_0\mathbf{b}$を位置ベクトルとする点$P_0, Q_0$を結ぶ直線は, $(l_1)$とも$(l_2)$とも直交する唯一の解である.

$\overline{P_0Q_0}$は$(l_1)$と$(l_2)$との最短距離を与える. 

![figure15](./ch1-assets/1-5-3.drawio.svg)

$\mathbf{c} = \overrightarrow{P_0Q_0}$とする. $\mathbf{x}_1, \mathbf{x}_2$を位置ベクトルとする点を$P_1, Q_1$とすれば

$$
\begin{align*}
  \mathbf{x}_2 - \mathbf{x}_1 = \overrightarrow{P_1Q_1} &= \overrightarrow{P_1P_0} + \overrightarrow{P_0Q_0} + \overrightarrow{Q_0Q_1} \\
  &= t_0\mathbf{a} + \mathbf{c} - s_0\mathbf{b}
\end{align*}
$$

$\mathbf{c}$は$\mathbf{a}$とも$\mathbf{b}$とも直交するから

$$
(\mathbf{c}, \mathbf{x}_2 - \mathbf{x}_1) = (\mathbf{c, c}) + t_0(\mathbf{c, a}) - s_0(\mathbf{c, b}) = (\mathbf{c, c}), \\
\mathbf{c} = k(\mathbf{a} \times \mathbf{b}) \quad k \ne 0
$$

ゆえに

$$
\| \mathbf{c} \| =
\frac{| (\mathbf{c, c}) |}{\| \mathbf{c} \|} =
\frac{| (\mathbf{c}, \mathbf{x}_2 - \mathbf{x}_1) |}{| k | \| \mathbf{a} \times \mathbf{b} \|} =
\frac{| (k(\mathbf{a} \times \mathbf{b}), \mathbf{x}_2 - \mathbf{x}_1) |}{| k | \| \mathbf{a} \times \mathbf{b} \|} =
\frac{| k | | (\mathbf{a} \times \mathbf{b}, \mathbf{x}_2 - \mathbf{x}_1) |}{| k | \| \mathbf{a} \times \mathbf{b} \|} =
\frac{| (\mathbf{a} \times \mathbf{b}, \mathbf{x}_2 - \mathbf{x}_1) |}{\| \mathbf{a} \times \mathbf{b} \|} \\
= \frac{| \det(\mathbf{a}, \mathbf{b}, \mathbf{x}_2 - \mathbf{x}_1) |}{\| \mathbf{a} \times \mathbf{b} \|}
$$

これが$(l_1)$と$(l_2)$との最短距離となる.

また, $(l_1)$と$(l_2)$が捩れの位置にあるための条件は

$$
\det(\mathbf{a}, \mathbf{b}, \mathbf{x}_2 - \mathbf{x}_1) \ne 0
$$

となる.

```memo:txt
\det(\mathbf{a}, \mathbf{b}, \mathbf{x}_2 - \mathbf{x}_1) = 0の場合, 距離$\| \mathbf{c} \|$が0になるので交わるし, 線型独立ではなくなるので平行にもなる
```

:::
