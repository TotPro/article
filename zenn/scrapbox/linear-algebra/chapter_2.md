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

