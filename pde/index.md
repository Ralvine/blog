# 偏微分方程


<!--more-->

{{< admonition quote "课程信息" true >}}
🎓 数学科学学院<br>
🕙 2021-2022 春夏，2022-2023 春夏<br>
🧑‍🏫 鲁汪涛，孔德兴<br>
📝 作业，（小测，）期末考试
{{< /admonition >}}

{{< admonition note "课程大纲" true >}}

- 绪论
- 一阶方程
  - 线性方程
  - 拟线性方程
  - 偏微分方程组
- 双元二阶方程
- 波动方程
  - 一维
      - 导出、定解条件
      - 柯西问题
      - 初边值问题
          - 分离变量法
  - 高维
      - 球平均法
  - 传播
  - 能量不等式
- 热传导方程
  - 导出、定解条件
  - 柯西问题
      - 傅立叶变换法
  - 初边值问题
  - 极值原理
- Laplace方程
  - 导出、定解条件
  - 变分法
  - 调和函数
      - 格林公式
      - 极值原理
  - 格林函数
      -镜像法
  - 强极值原理

{{< /admonition >}}

## 引言

### 发展史

> 17 - 微积分 Newton & Lebnitz<br>
> 18 - Euler & Bernoulli & Lagrange & Laplace & Poisson<br>
> 19 - pde应用 Fourier & Green & Cauchy & Hadamard<br>
> 20 - 复杂理论<br>
> 21 - 计算机数值分析 & 微分方程数值解

### 基本定义

#### 概念

- **向量：** 开区域 $$x=(x_1,x_2,\cdots,x_n)\in \mathbb{R}^n,x\in \Omega$$
- **函数：**
$$u:\Omega\rightarrow\mathbb{R}$$
$$偏导\ \displaystyle\frac{\partial u}{\partial x_1}=\partial_{x_{1}}u=\partial_{1}u$$
- **梯度：**$$grad/\nabla/Du=(\partial_{1}u,\partial_{2}u,\cdots,\partial_{n}u)$$
- **散度：**$$\vec{F}=(F_1,F_2,\cdots,F_n),\Omega\rightarrow \mathbb{R}^n\Rightarrow div\vec{F}=\displaystyle\sum\limits_{i=1}^n\frac{\partial F_i}{\partial x_i}$$
- **Hessian矩阵：** {{< math >}}$$D^2u=\begin{pmatrix}\displaystyle\frac{\partial^2u}{\partial x_1^2}&\displaystyle\frac{\partial^2 u}{\partial x_1x_2}&\cdots&\displaystyle\frac{\partial^2u}{\partial x_1x_n}\\\vdots&\vdots&\ddots&\vdots\\\displaystyle\frac{\partial^2u}{\partial x_nx_1}&\displaystyle\frac{\partial^2u}{\partial x_nx_2}&\cdots&\displaystyle\frac{\partial^2u}{\partial x_n^2}\end{pmatrix}$${{< /math >}}
- **Laplace算子：** $$\Delta u=tr(D^2u)=\displaystyle\sum\limits_{i=1}^n\frac{\partial ^2u}{\partial x_i^2}=\text{div}(Du)\ 散度的梯度$$  
- **所有k阶偏导：**
$$D^ku=\displaystyle\frac{\partial^ku}{\partial x_{i1}\partial x_{i2}\cdots\partial x_{ik}}\in\mathbb{R}^{n^k},\ n^k个$$
$$|D^ku|=(\sum\limits_{i1=1}^n\sum\limits_{i2=1}^n\cdots\sum\limits_{ik=1}^n|\partial_{x1}\partial_{x2}\cdots\partial_{xk}u|)^{1/2}$$

- **多重指标：**
$$\alpha=(\alpha_1,\alpha_2,\cdots,\alpha_n),$$
$$阶\ |\alpha|=\alpha_1+\alpha_2+\cdots+\alpha_n$$
$$去重\ D^\alpha u=\partial_{x1}^{\alpha1}\partial_{x1}^{\alpha2}\cdots\partial_{x1}^{\alpha n}\Rightarrow|D^ku|=(\sum\limits_{|\alpha|=k}|D^\alpha u|^2)^{1/2}$$

- **偏微分方程：**
{{< math >}} 
$$F(D^ku(x),D^{k-1}u(x),\cdots,Du(x),u(x),x)=0, x\in\Omega.\ k阶$$

$$\left\{\begin{array}{l}
F:\mathbb{R}^{n^k}\times\mathbb{R}^{n^{k-1}}\times\cdots\times\mathbb{R}^{n}\times\mathbb{R}\times\Omega\rightarrow\mathbb{R}.（已知）\\
u:\Omega\rightarrow\mathbb{R}.（未知）\\
\end{array}\right.$$
{{< /math >}}

#### 线性空间

- **函数：**
{{< math >}} 
$$u\rightarrow C(\Omega), ||u||_{C(\Omega)}=\sup\limits_{x\in\Omega} |u(x)|.$$
{{< /math >}} 

- **k次连续可微函数：**
{{< math >}} 
$$ ||u||_{C^k(\Omega)}=\sup\limits_{x\in\Omega}|u(x)| + \displaystyle\sum\limits_{|\alpha|=1}^2 \sup\limits_{x\in\Omega}|D^\alpha u(x)| $$
{{< /math >}}

- **支集：**
{{< math >}}
$$spt\space u=\overline{\{ x\in\Omega|u(x)\neq0\}}.$$
{{< /math >}}
所有满足$u(x)\neq0$点集在$\Omega$上的闭包
- $C_0^k$ 具有紧支集的函数
- $C^\infty(\Omega)=\bigcap\limits_{k=1}^\infty C^k(\Omega)$任意阶偏导存在且连续的函数类

#### 解的光滑性

<center>解析 $\rightarrow$ 无穷光滑 $\rightarrow$ k次连续可微(古典解) $\rightarrow$ 弱解(广义解)</center>

#### 分类

- **线性：**$\displaystyle\sum\limits_{|\alpha|\leq k}a_{\alpha}(x)D^{\alpha}u=f(x)$
- **半线性：**$\displaystyle\sum\limits_{|\alpha|=k}a_{\alpha}(x)D^{\alpha}u=f[D^{k-1}u(x),\cdots,Du(x),u(x),x]$
- **拟线性：**$\displaystyle\sum\limits_{|\alpha|=k}a_{\alpha}[D^{k-1}u(x),\cdots,Du(x),u(x),x]D^{\alpha}u=f[D^{k-1}u(x),\cdots,Du(x),u(x),x]$

- 完全非线性：非线性依赖 $D^ku$

### 实例

1. **Laplace方程：**$\Delta u=0$
2. **特征值方程：**$\Delta u+\lambda u=0$
3. **热方程：**$u_t-a^2\Delta u=0(a>0)$
4. ...

### 椭圆型&

### 适定性

#### 定义

- 定解问题：PDE+条件

- 适定：解存在、唯一、连续依赖已知函数

- 形式解：对实际问题假设解的光滑性以求出表达式（先验估计）

- $\Omega$ - 开域、$\overline\Omega$ - 闭包、$\partial\Omega$ - 边界

  {{< math >}} $\mathbb{R}_+^n=\{x=(x_1,\cdots,x_n)\in\mathbb{R}^n|x_n>0\}$ 上半空间 {{< /math >}}<br>
  
  {{< math >}} $\mathbb{R}_+^1=\mathbb{R}_+,\space\mathbb{R}_+^{n+1}=\mathbb{R}_+^n\times\mathbb{R}_+$ {{< /math >}}

- **闭球：**$B(x,r),$ 体积 $\alpha(n)r^n$


#### 定理

- **Green 公式**

## 位势方程

### Possion方程

$$-\Delta u=f(x)$$

### 调和函数

$$\displaystyle\int_a^b\hspace{-1.5em}-\ f(x)\, \mathrm{d}x$$

## 热方程

### 基本定义

#### 热方程

- **基本形式：**$u_t-a^2\Delta u=f,\space u(x,t),\space f(x,t),\space x\in\Omega\subset\mathbb{R^n},t>0$
- **推导**
- 反应扩散方程：反应项、扩散项

#### 概念

- **定解问题：**

  - **定解条件**

    - **初始条件：**$u(x,0)=\varphi (x)$

    - **边值条件：** 边界分布或外围介质影响（$x\in\partial\Omega,t\ge0$）

      $u(x,t)=g(x,t)$. $g=\text{const}$ 恒温
      
      $k\frac{\partial}{\partial\displaystyle\vec{n}}u(x,t)=g(x,t)$. $g\ge0$ 热量流入；$g\equiv0$ 绝热

  - **偏微分方程**

- **函数集：** 所有$Q$内关于$x$二阶偏导连续，关于$t$一阶偏导连续函数
  
  {{< math >}} $C^{2,1}(Q)=\{u\in C(Q)|u_t, u_{xi},u_{xixj}\in C(Q);i,j=1,\cdots,n\}$ {{< /math >}}

- **古典解：** 热方程在上述集中的解

- $C^{1,0}(Q)$

### 初值问题

#### Fourier

- **Fourier 级数展开**

  $f(x)\in C^1(\mathbb{R}),\space\forall l>0,\space x\in(-l,l)$

  $f(x)=\displaystyle\frac{a_0}{2}+\displaystyle\sum\limits_{k=1}^\infty \big (a_k\cos \displaystyle\frac{k\pi}{l}x+b_k\sin\displaystyle\frac{k\pi}{l}x\big )$

- **Fourier 积分：** 级数极限

#### 一维热方程初值问题

{{< math >}}
$$
\displaystyle\left\{\begin{array}{l}
 \displaystyle\frac{\partial{u}}{\partial t}-a^2\displaystyle\frac{\partial^2u}{\partial x^2}=f(x,t), & (x,t)\in\mathbb{R}\times\mathbb{R}_+\\
u(x,0)=\varphi(x), & x\in\mathbb
{R}\\
  \end{array}\right.
$$
{{< /math >}}

