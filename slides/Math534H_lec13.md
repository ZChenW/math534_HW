# Lecture 13

## Review (14:36 ~ 14:45)

## Continue from (++) page 8 of lecture 12

继续前言

$$
0 = \int_{-\infty}^{\infty} (u_{tt}u_t - c^2 u_{xx}u_t + ku\,u_t)\,dx
$$

$$
\int_{-\infty}^{\infty} u_{xx}u_t\,dx
= \left[ u_x u_t \right]_{-\infty}^{\infty}- \int_{-\infty}^{\infty} u_{xt}u_x\,dx
= 0 - \frac12 \frac{d}{dt}\int_{-\infty}^{\infty} u_x^2\,dx
$$

$$
0 = \frac{1}{2}\frac{d}{dt}\int_{-\infty}^{\infty}
\left( u_t^2 + c^2 u_x^2 + k u^2 \right)\,dx
$$

Constant in time:

$$\overline{E}[u](t) = \overline{E}[u](0)$$

$$\frac{d}{dt} \overline{E}[u][t] == 0$$

The energy is conserved in time.

## Heat Equation (15:07 ~ 15:50)

为什么u(x, -t) is also a solution of wave equation, but heat equation not?

Diffusion on Heating equation in 1D x \in R

Heat equation is not time-reversible

$$u_t - R u_{xx}, k > 0$$

- Properities of solution:
  - Remark: IVP
    - $u_t - k u_{xx} = 0$
    - $u(x, 0) = \phi$ 告诉你“最开始温度长什么样”
  - Maximum Principle 热方程的解在内部不会自己产生新的最大值。最大值只能出现在初始时刻或者空间边界上。
    - $x \in [0, L]$
    - $t \in [0, T]$
    - $R = [0, L] * [0, T]$ Former a Close Rectangle

|
|
x---------------------k
| | | | | | | | | | | |
| | | | | | | | | | | |
| | | | | | | | | | | |
| | | | | | | | | | | |
| | | | | | | | | | | |
| | | | | | | | | | | |
| | | | | | | | | | | |
0---------------------t-------

Remark: Uniqueness and stablility of solution to IVP for H, could be approached
in two ways:

- Using "Eneray method"
- Maximum Principle
  There is not max prin for the wave equation
  - ## Theorem (weak Maximum Principle):

### Weak Maximum Principle 的标准形式

设 \(u(x,t)\) 在矩形区域

\[
R=[0,L]\times[0,T]
\]

上满足热方程

\[
u*t-k u*{xx}=0,\qquad k>0
\]

并且 \(u\) 足够光滑、在闭区域上连续。

那么：

\[
\max\_{\overline R} u
\]

一定出现在这个区域的 **抛物边界** 上，而不是内部。

这里的抛物边界通常是

\[
([0,L]\times\{0\})\cup (\{0\}\times[0,T])\cup(\{L\}\times[0,T])
\]

也就是：

- 底边 \(t=0\)：初始时刻
- 左边 \(x=0\)
- 右边 \(x=L\)

### Weak Min Principle 的标准形式

设 \(u(x,t)\) 在矩形区域

\[
R=[0,L]\times[0,T]
\]

上满足热方程

\[
u*t-k u*{xx}=0,\qquad k>0
\]

并且 \(u\) 足够光滑、在闭区域上连续。

那么：

\[
\min\_{\overline R} u
\]

一定出现在这个区域的抛物边界上。

也就是说，若记抛物边界为

\[
\Gamma=\big([0,L]\times\{0\}\big)\cup\big(\{0\}\times[0,T]\big)\cup\big(\{L\}\times[0,T]\big),
\]

则

\[
\min*{(x,t)\in R} u(x,t)=\min*{(x,t)\in \Gamma} u(x,t).
\]

这是因为如果 \(u\) 是热方程的解，那么 \(-u\) 也是热方程的解，所以对 \(-u\) 使用最大值原理即可得到最小值原理。

### Proof Maximum Principle

记

\[
\Gamma=\big([0,L]\times\{0\}\big)\cup\big(\{0\}\times[0,T]\big)\cup\big(\{L\}\times[0,T]\big)
\]

为抛物边界。

我们想证明：

\[
\max*{(x,t)\in R}u(x,t)=\max*{(x,t)\in \Gamma}u(x,t).
\]

#### Step 1: 最大值一定能取到

因为 \(u\) 在闭矩形 \(R=[0,L]\times[0,T]\) 上连续，而 \(R\) 是紧集，所以 \(u\) 一定在 \(R\) 上取到最大值。

也就是说，存在某一点 \((x_0,t_0)\in R\)，使得

\[
u(x*0,t_0)=\max*{(x,t)\in R}u(x,t).
\]

#### Step 2: 先尝试一个最自然的想法

假设这个最大值点 \((x_0,t_0)\) 位于区域内部。

如果 \((x_0,t_0)\) 是内部极大值点，那么按照多元微积分中的极值条件，有

\[
u_x(x_0,t_0)=0,\qquad u_t(x_0,t_0)=0.
\]

并且二阶导数检验至少告诉我们

\[
u\_{xx}(x_0,t_0)\le 0.
\]

如果我们“更强地”有

\[
u\_{xx}(x_0,t_0)<0,
\]

那么代入热方程

\[
u*t-k u*{xx}=0
\]

会得到

\[
u*t(x_0,t_0)-k u*{xx}(x_0,t_0)>0,
\]

因为这时

- \(u_t(x_0,t_0)=0\),
- \(u\_{xx}(x_0,t_0)<0\),
- 所以 \(-k u\_{xx}(x_0,t_0)>0\).

于是左边大于 0，就和热方程要求它等于 0 矛盾。

所以如果内部最大值点真的满足 \(u\_{xx}(x_0,t_0)<0\)，那它不可能是解。

#### Step 3: 为什么这个证明还不够

问题在于：二阶导数检验一般只能推出

\[
u\_{xx}(x_0,t_0)\le 0,
\]

而不一定能推出严格不等式

\[
u\_{xx}(x_0,t_0)<0.
\]

例如函数在某个内部点取得平顶最大值时，可能有

\[
u\_{xx}(x_0,t_0)=0.
\]

这时代入热方程只能得到

\[
u*t(x_0,t_0)-k u*{xx}(x_0,t_0)=0- k\cdot 0=0,
\]

并不会产生矛盾。

所以，“直接在内部最大值点代入 PDE”这个最自然的方法，**还不足以完成证明**。

#### Step 4: 这说明了什么

这说明：

- 我们已经看出“内部最大值”会带来很强的限制；
- 但仅靠普通的二阶导数检验，还不能严格排除内部最大值；
- 因此真正的最大值原理证明，需要引入一个稍微更精细的论证方法。

结论仍然是：热方程的解不可能在内部凭空产生新的最大值，最大值只能出现在抛物边界 \(\Gamma\) 上。

### Remark

一旦 Weak Maximum Principle 成立，那么 Weak Minimum Principle 也立即成立，因为：

若 \(u\) 解热方程，则 \(-u\) 也解热方程。

于是对 \(-u\) 应用最大值原理：

\[
\max*{(x,t)\in R}(-u)=\max*{(x,t)\in \Gamma}(-u).
\]

两边同时乘以 \(-1\)，得到

\[
\min*{(x,t)\in R}u=\min*{(x,t)\in \Gamma}u.
\]

### Correction

这里应注意：

- wave equation 在时间上是可逆的；
- heat equation **不是** time-reversible。

所以前面笔记里那句

`Heat equation is time-reversible`

应改成

`Heat equation is NOT time-reversible`.
