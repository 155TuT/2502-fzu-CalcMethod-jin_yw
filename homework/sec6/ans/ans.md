# 数值分析第六章作业

052403137 王智壹

## 1

设线性方程组

$$
\begin{cases}
5x_1+2x_2+x_3=-12,\\
-x_1+4x_2+2x_3=20,\\
2x_1-3x_2+10x_3=3.
\end{cases}
$$

（1）考察用雅可比迭代法、高斯-塞德尔迭代法解此方程组的收敛性；

（2）用雅可比迭代法及高斯-塞德尔迭代法解此方程组，要求当

$$
\left\lVert x^{(k+1)}-x^{(k)} \right\rVert_\infty < 10^{-4}
$$

时迭代终止。

答：

将方程组改写为迭代格式。雅可比迭代为

$$
\begin{cases}
x_1^{(k+1)}=-2.4-0.4x_2^{(k)}-0.2x_3^{(k)},\\
x_2^{(k+1)}=5+0.25x_1^{(k)}-0.5x_3^{(k)},\\
x_3^{(k+1)}=0.3-0.2x_1^{(k)}+0.3x_2^{(k)}.
\end{cases}
$$

其迭代矩阵为

$$
B_J=
\begin{pmatrix}
0&-0.4&-0.2\\
0.25&0&-0.5\\
-0.2&0.3&0
\end{pmatrix}.
$$

计算得

$$
\rho(B_J)\approx 0.5061<1,
$$

故雅可比迭代法收敛。

高斯-塞德尔迭代为

$$
\begin{cases}
x_1^{(k+1)}=-2.4-0.4x_2^{(k)}-0.2x_3^{(k)},\\
x_2^{(k+1)}=5+0.25x_1^{(k+1)}-0.5x_3^{(k)},\\
x_3^{(k+1)}=0.3-0.2x_1^{(k+1)}+0.3x_2^{(k+1)}.
\end{cases}
$$

其迭代矩阵为

$$
B_{GS}=
\begin{pmatrix}
0&-0.4&-0.2\\
0&-0.1&-0.55\\
0&0.05&-0.125
\end{pmatrix}.
$$

计算得

$$
\rho(B_{GS})=0.2<1,
$$

故高斯-塞德尔迭代法也收敛。

取初值 $x^{(0)}=(0,0,0)^T$。按

$$
\left\lVert x^{(k+1)}-x^{(k)}\right\rVert_\infty<10^{-4}
$$

作为终止条件，得到：

$$
\begin{array}{c|c|c}
\text{方法} & \text{迭代次数} & x^{(k)}\\ \hline
\text{雅可比} & 18 & (-3.999996,\ 2.999974,\ 2.000000)^T\\
\text{高斯-塞德尔} & 8 & (-4.000033,\ 2.999983,\ 2.000002)^T
\end{array}
$$

精确解为

$$
x=(-4,3,2)^T.
$$

## 2

设线性方程组

（1）

$$
\begin{cases}
x_1+0.4x_2+0.4x_3=1,\\
0.4x_1+x_2+0.8x_3=2,\\
0.4x_1+0.8x_2+x_3=3;
\end{cases}
$$

（2）

$$
\begin{cases}
x_1+2x_2-2x_3=1,\\
x_1+x_2+x_3=1,\\
2x_1+2x_2+x_3=1.
\end{cases}
$$

试考察解此线性方程组的雅可比迭代法及高斯-塞德尔迭代法的收敛性。

答：

判断迭代法是否收敛，使用迭代矩阵谱半径条件：

$$
\rho(B)<1.
$$

（1）对

$$
A_1=
\begin{pmatrix}
1&0.4&0.4\\
0.4&1&0.8\\
0.4&0.8&1
\end{pmatrix},
$$

雅可比迭代矩阵为

$$
B_J=
\begin{pmatrix}
0&-\frac25&-\frac25\\
-\frac25&0&-\frac45\\
-\frac25&-\frac45&0
\end{pmatrix}.
$$

其特征多项式为

$$
\frac{(5\lambda-4)(25\lambda^2+20\lambda-8)}{125}=0,
$$

故

$$
\rho(B_J)=\frac{2+2\sqrt3}{5}\approx 1.0928>1.
$$

所以雅可比迭代法不收敛。

高斯-塞德尔迭代矩阵的特征多项式为

$$
\frac{\lambda(125\lambda^2-104\lambda+16)}{125}=0,
$$

故

$$
\rho(B_{GS})=\frac{52+8\sqrt{11}}{125}\approx 0.6283<1.
$$

所以高斯-塞德尔迭代法收敛。

（2）对

$$
A_2=
\begin{pmatrix}
1&2&-2\\
1&1&1\\
2&2&1
\end{pmatrix},
$$

雅可比迭代矩阵为

$$
B_J=
\begin{pmatrix}
0&-2&2\\
-1&0&-1\\
-2&-2&0
\end{pmatrix}.
$$

其特征多项式为

$$
\lambda^3=0,
$$

所以

$$
\rho(B_J)=0<1,
$$

雅可比迭代法收敛。

高斯-塞德尔迭代矩阵的特征多项式为

$$
\lambda(\lambda-2)^2=0,
$$

所以

$$
\rho(B_{GS})=2>1,
$$

高斯-塞德尔迭代法不收敛。

## 4

设

$$
A=
\begin{pmatrix}
10 & a & 0\\
b & 10 & b\\
0 & a & 5
\end{pmatrix},
\qquad \det A\ne 0,
$$

用 $a,b$ 表示解线性方程组 $Ax=f$ 的雅可比迭代与高斯-塞德尔迭代收敛的充分必要条件。

答：

记 $A=D+L+U$。雅可比迭代矩阵为

$$
B_J=-D^{-1}(L+U)
=
\begin{pmatrix}
0&-\frac{a}{10}&0\\
-\frac{b}{10}&0&-\frac{b}{10}\\
0&-\frac{a}{5}&0
\end{pmatrix}.
$$

其特征多项式为

$$
\det(\lambda I-B_J)
=\lambda\left(\lambda^2-\frac{3ab}{100}\right).
$$

因此雅可比迭代收敛的充分必要条件为

$$
\rho(B_J)<1
\quad\Longleftrightarrow\quad
\sqrt{\frac{3|ab|}{100}}<1
\quad\Longleftrightarrow\quad
3|ab|<100.
$$

高斯-塞德尔迭代矩阵为

$$
B_{GS}=-(D+L)^{-1}U
=
\begin{pmatrix}
0&-\frac{a}{10}&0\\
0&\frac{ab}{100}&-\frac{b}{10}\\
0&-\frac{a^2b}{500}&\frac{ab}{50}
\end{pmatrix}.
$$

其特征多项式为

$$
\det(\lambda I-B_{GS})
=\lambda^2\left(\lambda-\frac{3ab}{100}\right).
$$

因此高斯-塞德尔迭代收敛的充分必要条件为

$$
\rho(B_{GS})<1
\quad\Longleftrightarrow\quad
\left|\frac{3ab}{100}\right|<1
\quad\Longleftrightarrow\quad
3|ab|<100.
$$

又

$$
\det A=-5(3ab-100)\ne 0,
$$

题设只排除了 $3ab=100$，而两种迭代法收敛都还需满足 $3|ab|<100$。

## 6

用雅可比迭代与高斯-塞德尔迭代解线性方程组 $Ax=b$，证明若取

$$
A=
\begin{pmatrix}
3 & 0 & -2\\
0 & 2 & 1\\
-2 & 1 & 2
\end{pmatrix},
$$

则两种方法均收敛，试比较哪种方法收敛快？

答：

对

$$
A=
\begin{pmatrix}
3&0&-2\\
0&2&1\\
-2&1&2
\end{pmatrix},
$$

雅可比迭代矩阵为

$$
B_J=
\begin{pmatrix}
0&0&\frac23\\
0&0&-\frac12\\
1&-\frac12&0
\end{pmatrix}.
$$

其特征多项式为

$$
\lambda\left(\lambda^2-\frac{11}{12}\right)=0,
$$

所以

$$
\rho(B_J)=\sqrt{\frac{11}{12}}=\frac{\sqrt{33}}{6}\approx 0.9574<1.
$$

故雅可比迭代法收敛。

高斯-塞德尔迭代矩阵为

$$
B_{GS}=
\begin{pmatrix}
0&0&\frac23\\
0&0&-\frac12\\
0&0&\frac{11}{12}
\end{pmatrix}.
$$

其特征多项式为

$$
\lambda^2\left(\lambda-\frac{11}{12}\right)=0,
$$

所以

$$
\rho(B_{GS})=\frac{11}{12}\approx 0.9167<1.
$$

故高斯-塞德尔迭代法也收敛。

由于

$$
\rho(B_{GS})=\frac{11}{12}<\sqrt{\frac{11}{12}}=\rho(B_J),
$$

所以从渐近收敛速度看，高斯-塞德尔迭代法收敛更快。
