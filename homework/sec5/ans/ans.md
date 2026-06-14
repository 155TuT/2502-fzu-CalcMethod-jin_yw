# 数值分析第五章作业

052403137 王智壹

## 7

用列主元消去法解线性方程组

$$
\begin{cases}
12x_1-3x_2+3x_3=15,\\
-18x_1+3x_2-x_3=-15,\\
x_1+x_2+x_3=6,
\end{cases}
$$

并求出 $\det A$ 的值。

答：

系数矩阵和右端项为

$$
A=
\begin{pmatrix}
12&-3&3\\
-18&3&-1\\
1&1&1
\end{pmatrix},
\qquad
b=
\begin{pmatrix}
15\\-15\\6
\end{pmatrix}.
$$

第 1 列选主元，因 $|-18|$ 最大，交换第 1、2 行：

$$
\left[
\begin{array}{ccc|c}
-18&3&-1&-15\\
12&-3&3&15\\
1&1&1&6
\end{array}
\right].
$$

消去第 1 列后得

$$
\left[
\begin{array}{ccc|c}
-18&3&-1&-15\\
0&-1&\frac73&5\\
0&\frac76&\frac{17}{18}&\frac{31}{6}
\end{array}
\right].
$$

第 2 列选主元，交换第 2、3 行，再消去，得

$$
\left[
\begin{array}{ccc|c}
-18&3&-1&-15\\
0&\frac76&\frac{17}{18}&\frac{31}{6}\\
0&0&\frac{22}{7}&\frac{66}{7}
\end{array}
\right].
$$

回代得

$$
x_3=3,\qquad x_2=2,\qquad x_1=1.
$$

所以

$$
x=(1,2,3)^T.
$$

两次换行，行列式符号不变，因此

$$
\det A=(-18)\cdot\frac76\cdot\frac{22}{7}=-66.
$$

## 8

用直接三角分解（杜利特尔（Doolittle）分解）求线性方程组

$$
\begin{cases}
\dfrac{1}{4}x_1+\dfrac{1}{5}x_2+\dfrac{1}{6}x_3=9,\\
\dfrac{1}{3}x_1+\dfrac{1}{4}x_2+\dfrac{1}{5}x_3=8,\\
\dfrac{1}{2}x_1+x_2+2x_3=8
\end{cases}
$$

的解。

答：

记

$$
A=
\begin{pmatrix}
\frac14&\frac15&\frac16\\
\frac13&\frac14&\frac15\\
\frac12&1&2
\end{pmatrix},
\qquad
b=
\begin{pmatrix}
9\\8\\8
\end{pmatrix}.
$$

作杜利特尔分解 $A=LU$，其中

$$
L=
\begin{pmatrix}
1&0&0\\
\frac43&1&0\\
2&-36&1
\end{pmatrix},
\qquad
U=
\begin{pmatrix}
\frac14&\frac15&\frac16\\
0&-\frac1{60}&-\frac1{45}\\
0&0&\frac{13}{15}
\end{pmatrix}.
$$

先解 $Ly=b$：

$$
\begin{cases}
y_1=9,\\
\frac43y_1+y_2=8,\\
2y_1-36y_2+y_3=8,
\end{cases}
$$

得

$$
y_1=9,\qquad y_2=-4,\qquad y_3=-154.
$$

再解 $Ux=y$：

$$
\begin{cases}
\frac14x_1+\frac15x_2+\frac16x_3=9,\\
-\frac1{60}x_2-\frac1{45}x_3=-4,\\
\frac{13}{15}x_3=-154.
\end{cases}
$$

回代得

$$
x_3=-\frac{2310}{13},\qquad
x_2=\frac{6200}{13},\qquad
x_1=-\frac{2952}{13}.
$$

因此线性方程组的解为

$$
x=\left(-\frac{2952}{13},\frac{6200}{13},-\frac{2310}{13}\right)^T.
$$
