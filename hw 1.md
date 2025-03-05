### 113258015 林旻駿 計量第一次作業

### 1.
#### (a)
$$
\mathbb{E}[Y|X]=\mathbb{E}[X+X^2+e|X]=X+X^2+\mathbb{E}[e|X]=X+X^2
$$
#### (b)
$$
\begin{pmatrix}
    \beta_{0} \\
    \beta_{1}
\end{pmatrix}=\begin{pmatrix}
    \mathbb{E}[Y]-\beta_{1}\mathbb{E}[X] \\
    \frac{Cov[Y,X]}{Var[X]}
\end{pmatrix}=
\begin{pmatrix}
    1-0 \\
    \frac{1}{1}
\end{pmatrix}=\begin{pmatrix}
    1 \\
    1
\end{pmatrix}
$$
其中
$$
Cov[Y,X]=\mathbb{E}[XY]-\mathbb{E}[X]\mathbb{E}[Y]=1-0=1 \\
Var[X]=\mathbb{E}[X^2]-\mathbb{E}[X]^2=1 \\
\mathbb{E}[X]=0\Rightarrow \mathbb{E}[X^2]=1 \Rightarrow \mathbb{E}[X^3]=0 \hspace{1em}(\because X\sim \mathbb{N}(0,1))\\
\mathbb{E}[Y]=\mathbb{E}[X^2]+\mathbb{E}[X]=1+0=1\\
\mathbb{E}[XY]=\mathbb{E}[X^2]+\mathbb{E}[X^3]=1+0=1
$$
所以
$$
\mathbb{P}(Y|X)=1+X
$$

##### (c)
$$
\begin{pmatrix}
    \beta_{0} \\
    \beta_{1}
\end{pmatrix}=\begin{pmatrix}
    \mathbb{E}[Y]-\beta_{1}\mathbb{E}[X] \\
    \frac{Cov[Y,X]}{Var[X]}
\end{pmatrix}=
\begin{pmatrix}
    \frac{1}{3} \\
    \frac{\frac{1}{3}}{c}
\end{pmatrix}=\begin{pmatrix}
    \frac{1}{3} \\
    1
\end{pmatrix}
$$
其中
$$
\because X \sim \mathbb{U}(-1,1) \\
\therefore \mathbb{E}(X)=0,\mathbb{E}(X^2)=\frac{1}{3},\mathbb{E}(X^3)=0 \\
\Rightarrow Var(X)=\frac{1}{3},\\ 
\mathbb{E}[Y]=\mathbb{E}(X^2)+\mathbb{E}(X)=\frac{1}{3},\mathbb{E}[XY]=\mathbb{E}(X^3)+\mathbb{E}(X^2)=\frac{1}{3} \\ \Rightarrow Cov(X,Y)=\frac{1}{3} \\
$$
所以
$$
\mathbb{P}(Y|X)=\frac{1}{3}+X
$$

#### (d)
- 垂直投影無法擷取 $X^2$ 這個非線性的部分
- 截距項的部分不同

### 2.
$$
\mathbb{E}(s^2|X)=\sigma^2 ,s^2=\frac{\hat{e}'\hat{e}}{n-k}
$$
已知
$$
\hat{e}=(I-P)(Y-X\beta)
$$

$$
\hat{e}'\hat{e}=(Y-X\beta)'(I-P)(Y-X\beta)
$$

$$
\begin{align*}
  \mathbb{E}[\hat{e}'\hat{e}]&=\mathbb{E}[(Y-X\beta)'(I-P)(Y-X\beta)]\\&=
\text{tr}\{\mathbb{E}[(Y-X\beta)'(I-P)(Y-X\beta)] \}\\
&=\text{tr}\{(I-P)\mathbb{E}[(Y-X\beta)(Y-X\beta)'] \}\\
&=\sigma^2\text{tr}[(I-P)]\\
&=\sigma^2(n-k)
\end{align*}
$$
所以
$$
\mathbb{E}[\hat{\sigma^2}]=\mathbb{E}[\frac{\hat{e}'\hat{e}}{n-k}]=\frac{\sigma^2(n-k)}{n-k}=\sigma^2
$$
$\hat{\sigma^2}$是 $\sigma^2$ 的不偏估計。

### 3.
因為$Q$ 是symmetric 和 idempotent，所以其可以特徵分解成
$$
Q=C\Lambda C'
$$
其中$C$是orthogonal matrix，所以可以寫成以下
$$
z'Qz=z'C\Lambda C'z=(C'z)'\Lambda (C'z)
$$
其中
$$
w \equiv (C'z) \sim \mathbb{N}(0,\mathbb{I_n}) \\
w_{i}^2\sim \chi_{1}^2
$$
所以
$$
w'\Lambda w = \sum_{i=1}^{k}w_{i}^2 \sim\chi_{k}^2
$$

### 4.
#### (a)
$$
M_1-M=(I-P_1)-(I-P)=P-P_1
$$
$$
(M_1-M)(M_1-M)=(P-P_1)(P-P_1)=PP-P_1P-P_1P+P_1P_1\\
=P-P_1-P_1+P_1=P-P_1
$$
所以$M_1-M$idempotent。
$$
rank(M_1-M)=rank(P-P_1)=\text{tr}(P-P_1) \\ =\text{tr}(P)-\text{tr}(P_1)=K-K_1=K_2
$$

#### (b)
$$
(M_1-M)M=(P-P_1)(I-P)=P-P-P_1+P_1=0
$$

#### (c)
$$
\sigma^{-1}e|X \sim N(0,\mathbb{I_{n}})
$$

$$
(\sigma^{-1}e)'(M_1-M)(\sigma^{-1}e)=\frac{1}{\sigma^2}[e'(M_1-M)e]=\sum_{i-1}^{k}w_{i^2} \sim \chi_{k}^2
$$

$$
\therefore e'(M_1-M)e \sim \sigma^2\chi_{k_2}^2
$$
$$
rank(M_1-M)=k_2\\
rank(M)=rank(I-P)=\text{tr}(I-P)=n-k\\
\therefore e'(M_1-M)e \sim\chi_{k_2}^2,e'Me \sim\chi_{n-k}^2
$$

$$
n-k+k_2=n-k_1\\
\therefore e'(M_1-M)e+e'Me \sim \chi_{n-k_1}^2
$$

$$
e'(M_1-M)e+e'Me=e'M_1e
$$

$$
rank(M_1)=rank(I_n-P_1)=\text{tr}(I_n-P_1)=n-k_1
$$
$$
\because df(e'M_1e)=df(e'(M_1-M)e)+df(e'Me)\\
\therefore e'(M_1-M)e \perp e'Me
$$


### 5.
$$
e'(M_1-M)e=e'(P-P_1)e=e'(P_{X_1|X_2})e=e'(w(w'w)^{-1}w')e\\
=e'[M_1X_2(X_2'M_1X_2)^{-1}X_2'M_1]e 
$$
其中
$$
w \equiv M_1X_2
$$









