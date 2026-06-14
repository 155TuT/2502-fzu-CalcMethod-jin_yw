# 数值分析第七章作业

052403137 王智壹

## 6

设 $\varphi(x)=x-p(x)f(x)-q(x)f^2(x)$，试确定函数 $p(x)$ 和 $q(x)$，使求解 $f(x)=0$ 且以 $\varphi(x)$ 为迭代函数的迭代法至少三阶收敛。

答：

设 $\alpha$ 是 $f(x)=0$ 的单根，即

$$
f(\alpha)=0,\qquad f'(\alpha)\ne 0.
$$

迭代函数为

$$
\varphi(x)=x-p(x)f(x)-q(x)f^2(x).
$$

至少三阶收敛要求

$$
\varphi(\alpha)=\alpha,\qquad
\varphi'(\alpha)=0,\qquad
\varphi''(\alpha)=0.
$$

其中 $\varphi(\alpha)=\alpha$ 自动成立。求导得

$$
\varphi'(\alpha)=1-p(\alpha)f'(\alpha),
$$

故需

$$
p(\alpha)=\frac{1}{f'(\alpha)}.
$$

再求二阶导数并代入 $f(\alpha)=0$：

$$
\varphi''(\alpha)
=-2p'(\alpha)f'(\alpha)-p(\alpha)f''(\alpha)
-2q(\alpha)[f'(\alpha)]^2.
$$

取

$$
p(x)=\frac{1}{f'(x)}
$$

时，

$$
p'(\alpha)=-\frac{f''(\alpha)}{[f'(\alpha)]^2}.
$$

代入 $\varphi''(\alpha)=0$，得

$$
q(\alpha)=\frac{f''(\alpha)}{2[f'(\alpha)]^3}.
$$

因此可取

$$
p(x)=\frac{1}{f'(x)},\qquad
q(x)=\frac{f''(x)}{2[f'(x)]^3}.
$$

对应迭代公式为

$$
x_{k+1}
=x_k-\frac{f(x_k)}{f'(x_k)}
-\frac{f''(x_k)}{2[f'(x_k)]^3}f^2(x_k),
$$

这是至少三阶收敛的切比雪夫型迭代法。

## 8

分别用二分法和牛顿法求 $x-\tan x=0$ 的最小正根。

答：

$x=0$ 是平凡根；除零根外的最小正根位于区间

$$
(\pi,\frac{3\pi}{2})
$$

内。令

$$
F(x)=x-\tan x.
$$

取二分初始区间 $[4,4.5]$，有

$$
F(4)>0,\qquad F(4.5)<0.
$$

不断二分可得

$$
x\approx 4.493409458.
$$

牛顿法公式为

$$
x_{k+1}
=x_k-\frac{x_k-\tan x_k}{1-\sec^2x_k}
=x_k+\frac{x_k-\tan x_k}{\tan^2x_k}.
$$

取 $x_0=4.5$，迭代结果为

$$
\begin{array}{c|c}
k & x_k\\ \hline
0 & 4.500000000\\
1 & 4.493613903\\
2 & 4.493409655\\
3 & 4.493409458
\end{array}
$$

故二分法和牛顿法都得到最小正根

$$
x\approx 4.493409458.
$$

## 9

研究求 $\sqrt{a}$ 的牛顿公式

$$
x_{k+1}=\frac{1}{2}\left(x_k+\frac{a}{x_k}\right),
\qquad x_0>0,
$$

证明对一切 $k=1,2,\cdots$，有 $x_k\ge \sqrt{a}$ 且序列 $x_1,x_2,\cdots$ 是递减的。

答：

设 $\alpha=\sqrt a$，其中 $a>0$。由迭代公式

$$
x_{k+1}=\frac12\left(x_k+\frac{a}{x_k}\right)
$$

得

$$
x_{k+1}-\alpha
=\frac12\left(x_k+\frac{\alpha^2}{x_k}\right)-\alpha
=\frac{(x_k-\alpha)^2}{2x_k}\ge 0.
$$

由于 $x_0>0$，所以所有 $x_k>0$，从而对 $k=1,2,\cdots$，

$$
x_k\ge \alpha=\sqrt a.
$$

又当 $k\ge 1$ 时，$x_k\ge \sqrt a$，所以

$$
x_{k+1}-x_k
=\frac12\left(x_k+\frac{a}{x_k}\right)-x_k
=\frac{a-x_k^2}{2x_k}\le 0.
$$

因此序列 $x_1,x_2,\cdots$ 单调递减，且下界为 $\sqrt a$。

## 12

应用牛顿法于方程 $x^3-a=0$ 导出求立方根 $\sqrt[3]{a}$ 的迭代公式，并讨论其收敛性。

答：

设

$$
F(x)=x^3-a.
$$

牛顿法为

$$
x_{k+1}=x_k-\frac{F(x_k)}{F'(x_k)}.
$$

因为

$$
F'(x)=3x^2,
$$

所以

$$
x_{k+1}
=x_k-\frac{x_k^3-a}{3x_k^2}
=\frac{2}{3}x_k+\frac{a}{3x_k^2},
\qquad x_k\ne 0.
$$

这就是计算 $\sqrt[3]{a}$ 的牛顿迭代公式。

设 $\alpha=\sqrt[3]{a}$，且 $\alpha\ne 0$。迭代函数为

$$
\varphi(x)=\frac{2}{3}x+\frac{a}{3x^2}.
$$

有

$$
\varphi'(\alpha)=\frac23-\frac{2a}{3\alpha^3}=0,
$$

且

$$
\varphi''(\alpha)=\frac{2a}{\alpha^4}=\frac{2}{\alpha}.
$$

因此当初值充分接近 $\alpha$ 时，牛顿法局部二阶收敛，并且误差满足

$$
e_{k+1}
=\frac{1}{\alpha}e_k^2+O(e_k^3),
\qquad e_k=x_k-\alpha.
$$

若 $a>0$ 且 $x_0>0$，则从

$$
\frac{x_{k+1}}{\alpha}
=\frac{1}{3}\left(2\frac{x_k}{\alpha}
+\frac{1}{(x_k/\alpha)^2}\right)
$$

可知 $x_1\ge \alpha$；之后序列单调递减且有下界 $\alpha$，故收敛到 $\sqrt[3]{a}$。

## 15

证明迭代公式

$$
x_{k+1}=
\frac{x_k(x_k^2+3a)}{3x_k^2+a}
$$

是计算 $\sqrt{a}$ 的三阶方法。假定初值 $x_0$ 充分靠近根 $x^*$，求

$$
\lim_{k\to\infty}
\frac{\sqrt{a}-x_{k+1}}{(\sqrt{a}-x_k)^3}.
$$

答：

设

$$
\alpha=\sqrt a,\qquad e_k=\alpha-x_k.
$$

由迭代公式

$$
x_{k+1}=\frac{x_k(x_k^2+3\alpha^2)}{3x_k^2+\alpha^2}
$$

得

$$
\alpha-x_{k+1}
=\alpha-\frac{x_k(x_k^2+3\alpha^2)}{3x_k^2+\alpha^2}.
$$

通分化简：

$$
\alpha-x_{k+1}
=\frac{\alpha(3x_k^2+\alpha^2)-x_k(x_k^2+3\alpha^2)}
{3x_k^2+\alpha^2}
=\frac{(\alpha-x_k)^3}{3x_k^2+\alpha^2}.
$$

因此

$$
e_{k+1}=\frac{e_k^3}{3x_k^2+a}.
$$

当 $x_k$ 充分靠近 $\alpha$ 时，

$$
3x_k^2+a\to 3\alpha^2+\alpha^2=4a,
$$

所以该迭代法为三阶方法，并且

$$
\lim_{k\to\infty}
\frac{\sqrt a-x_{k+1}}{(\sqrt a-x_k)^3}
=\frac{1}{4a}.
$$
