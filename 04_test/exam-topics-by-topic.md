# 偏微分方程期中复习：知识点、考点、例题与举一反三

> 依据现有 `期中复习包`、模拟卷与答案整理。复习优先级：先掌握证明题模板，再补填空和计算。

## 0. 命题重点速览

| 模块 | 高频考点 | 常见题型 | 拿分关键 |
|---|---|---|---|
| 基本概念 | PDE 阶数、模型方程分类 | 填空/简答 | 看最高阶导数；名称写准确 |
| 向量分析 | grad、div、curl、Laplace；两个恒等式 | 填空/计算 | 混合偏导可交换 |
| Green 公式 | Green 第一、第二公式；散度定理 | 简答/证明 | 符号和边界项别写反 |
| Laplace/Poisson | 调和函数、Dirichlet/Neumann 问题 | 简答/证明 | 方程、边界条件、正则性写清 |
| 最大值原理 | 弱/强最大值原理、比较原理 | 证明 | 对差函数或障碍函数用原理 |
| Green 函数 | 定义、表示公式、Poisson 核 | 简答/综合证明 | 固定一个变量，使用 Green 第二公式 |
| 相容条件 | Neumann 必要条件 | 证明 | 对方程积分，用散度定理 |
| 能量估计 | 测试函数、积分分部、Poincare/Friedrichs | 证明 | 选对测试函数，用 Cauchy/Young |

---

## 1. PDE 基本概念与模型方程识别

### 知识点

1. PDE 阶数：方程中出现的最高阶偏导数阶数。
2. 常见算子：
   - 梯度：\(\nabla u\)
   - 散度：\(\operatorname{div}F=\sum_i \partial_i F_i\)
   - 拉普拉斯：\(\Delta u=\operatorname{div}(\nabla u)=\sum_i u_{ii}\)
   - 旋度：\(\operatorname{curl}F=\nabla\times F\)
3. 模型方程：
   - 多孔介质方程：\(u_t-\Delta(u^\gamma)=0,\ \gamma>1\)，二阶，退化抛物型。
   - KdV 方程：\(u_t+uu_x+u_{xxx}=0\)，三阶，非线性色散方程。

### 考点

- 判断方程阶数。
- 写出方程名称与类型。
- 区分“抛物/椭圆/双曲”与“色散型演化方程”。

### 例题 1

判断 \(u_t-\Delta(u^\gamma)=0\) 的阶数与类型，其中 \(\gamma>1\)。

**答案：**
\(\Delta(u^\gamma)\) 含空间二阶导数，所以最高阶为 2 阶。该方程称为多孔介质方程，是退化抛物型方程。

### 举一反三

1. \(u_t+uu_x+u_{xxx}=0\) 的最高阶是 3 阶，称为 KdV 方程，属于非线性色散方程。
2. \(-\Delta u=f\) 是 2 阶椭圆型方程，称为 Poisson 方程。
3. \(\Delta u=0\) 是 2 阶椭圆型方程，解称为调和函数。

---

## 2. 向量分析恒等式与球面计算

### 知识点

若函数足够光滑，例如 \(\varphi\in C^2\)，\(F\in C^2\)，则

\[
\nabla\times(\nabla\varphi)=0,\qquad \nabla\cdot(\nabla\times F)=0.
\]

原因：二阶混合偏导可以交换。

球面 \(\partial B(0,R)\) 的单位外法向：

\[
n(x)=\frac{x}{|x|}=\frac{x}{R}.
\]

若 \(u(x)=\psi(|x|)\) 是径向函数，则

\[
\nabla u(x)=\psi'(|x|)\frac{x}{|x|},\qquad
\partial_n u\big|_{|x|=R}=\psi'(R).
\]

### 考点

- 填空：\(\nabla\times\nabla\varphi=0\)，\(\nabla\cdot(\nabla\times F)=0\)。
- 计算球面法向导数。
- 用散度定理计算边界积分。

### 例题 2

设 \(u(x)=e^{-3|x|}\)。求在 \(\partial B(0,R)\) 上的外法向导数。

**答案：**
令 \(r=|x|\)，则 \(u=\psi(r)=e^{-3r}\)，\(\psi'(r)=-3e^{-3r}\)。因此

\[
\partial_n u=\psi'(R)=-3e^{-3R}.
\]

### 举一反三

1. 若 \(u(x)=|x|^2\)，则 \(\partial_n u|_{|x|=R}=2R\)。
2. 若 \(u(x)=\ln |x|\)，则 \(\partial_n u|_{|x|=R}=1/R\)。
3. 若 \(F(x)=x\)，则
   \[
   \int_{\partial B(0,R)}F\cdot n\,dS
   =\int_{B(0,R)}\operatorname{div}x\,dx
   =n|B(0,R)|.
   \]

---

## 3. 散度定理与 Green 公式

### 知识点

设 \(\Omega\subset\mathbb R^n\) 光滑有界，\(n\) 为单位外法向。

散度定理：

\[
\int_\Omega \operatorname{div}F\,dx=\int_{\partial\Omega}F\cdot n\,dS.
\]

Green 第一公式：

\[
\int_\Omega \nabla u\cdot\nabla v\,dx
=-\int_\Omega v\Delta u\,dx+\int_{\partial\Omega}v\partial_nu\,dS.
\]

Green 第二公式：

\[
\int_\Omega (u\Delta v-v\Delta u)\,dx
=\int_{\partial\Omega}(u\partial_nv-v\partial_nu)\,dS.
\]

### 考点

- 默写 Green 第二公式。
- 利用 Green 第一公式推相容条件。
- 利用 Green 第二公式推 Green 函数表示公式。

### 例题 3

写出 Green 第二公式，并说明两个用途。

**答案：**

\[
\int_\Omega (u\Delta v-v\Delta u)\,dx
=\int_{\partial\Omega}(u\partial_nv-v\partial_nu)\,dS.
\]

用途：推导 Green 函数表示公式；推导边值问题的必要条件、唯一性或 Poisson 核表示。

### 举一反三

1. 令 \(v=1\)，Green 第一公式可化出 \(\int_\Omega \Delta u=\int_{\partial\Omega}\partial_nu\)。
2. 若边界上 \(v=0\)，则 Green 第一公式的边界项消失。
3. 推表示公式时常取 \(v(y)=G(x,y)\)，固定 \(x\)，把 \(y\) 当变量。

---

## 4. Neumann 问题相容条件

### 知识点

Neumann 问题

\[
\begin{cases}
-\Delta u=f, & x\in\Omega,\\
\partial_nu=g, & x\in\partial\Omega
\end{cases}
\]

若存在光滑解，则必须满足

\[
\int_\Omega f\,dx+\int_{\partial\Omega}g\,dS=0.
\]

### 考点

- 这是证明题高频点。
- 关键是符号：\(-\int_\Omega\Delta u=-\int_{\partial\Omega}\partial_nu\)。

### 例题 4

证明 Neumann 问题的相容条件。

**答案：**
对方程 \(-\Delta u=f\) 在 \(\Omega\) 上积分：

\[
\int_\Omega(-\Delta u)\,dx=\int_\Omega f\,dx.
\]

由散度定理，

\[
\int_\Omega(-\Delta u)\,dx=-\int_{\partial\Omega}\partial_nu\,dS.
\]

代入边界条件 \(\partial_nu=g\)，得

\[
-\int_{\partial\Omega}g\,dS=\int_\Omega f\,dx,
\]

即

\[
\int_\Omega f\,dx+\int_{\partial\Omega}g\,dS=0.
\]

### 举一反三

1. 若 \(\partial_nu=0\)，则必须有 \(\int_\Omega f\,dx=0\)。
2. 若 \(-\Delta u=1\)，\(\partial_nu=0\)，在有界区域上通常无解，因为 \(\int_\Omega1\,dx\ne0\)。
3. 若方程写成 \(\Delta u=f\)，则相容条件变为 \(\int_\Omega f\,dx=\int_{\partial\Omega}g\,dS\)，注意符号变化。

---

## 5. 最大值原理、比较原理与唯一性

### 知识点

典型算子：

\[
Lu=-\Delta u+c(x)u,\qquad c(x)\ge0.
\]

弱最大值原理常用形式：若 \(Lu\le0\)，则最大值由边界控制。

比较原理：若 \(Lu\le Lv\) in \(\Omega\)，且 \(u\le v\) on \(\partial\Omega\)，则 \(u\le v\) in \(\Omega\)。

唯一性套路：两个解相减，令 \(w=u-v\)，则 \(Lw=0\)，边界 \(w=0\)。对 \(w\) 和 \(-w\) 用最大值原理，得 \(w\equiv0\)。

### 考点

- 叙述强/弱最大值原理。
- 用最大值原理证明 Dirichlet 问题唯一性。
- 用障碍函数证明最大模估计。

### 例题 5

证明 Dirichlet 问题

\[
\begin{cases}
Lu=f, & x\in\Omega,\\
u=g, & x\in\partial\Omega
\end{cases}
\]

至多有一个解。

**答案：**
设 \(u,v\) 都是解，令 \(w=u-v\)。则

\[
Lw=0\quad\text{in }\Omega,\qquad w=0\quad\text{on }\partial\Omega.
\]

由最大值原理，\(\max_{\bar\Omega}w\le0\)。对 \(-w\) 再用一次最大值原理，得 \(\max_{\bar\Omega}(-w)\le0\)，即 \(w\ge0\)。所以 \(w\equiv0\)，即 \(u\equiv v\)。

### 举一反三

1. 若 \(Lu\le0\)，\(u\le0\) on \(\partial\Omega\)，则 \(u\le0\) in \(\Omega\)。
2. 若 \(Lu\ge0\)，\(u\ge0\) on \(\partial\Omega\)，则 \(u\ge0\) in \(\Omega\)。
3. 若两个解边界值不同，比较原理可推出解的大小关系。

---

## 6. 最大模估计与障碍函数

### 知识点

对 Dirichlet 问题

\[
\begin{cases}
-\Delta u=f, & x\in\Omega,\\
u=g, & x\in\partial\Omega,
\end{cases}
\]

常考结论：

\[
\|u\|_{L^\infty(\Omega)}
\le C(n,\operatorname{diam}\Omega)
\left(\|g\|_{L^\infty(\partial\Omega)}+\|f\|_{L^\infty(\Omega)}\right).
\]

核心方法：构造二次障碍函数

\[
\phi(x)=A(d^2-|x-x_0|^2),\qquad d=\operatorname{diam}\Omega.
\]

因为

\[
\Delta |x-x_0|^2=2n.
\]

### 考点

- 会选 \(\phi\)。
- 会算 \(-\Delta\phi\)。
- 会对 \(u-\phi\) 和 \(-u-\phi\) 分别用最大值原理。

### 例题 6

证明存在 \(C=C(n,d)\)，使

\[
\max_{\bar\Omega}|u|\le C(\max_{\partial\Omega}|g|+\sup_\Omega |f|).
\]

**答案：**
令 \(M=\sup_\Omega |f|\)，\(G=\max_{\partial\Omega}|g|\)，取

\[
\phi(x)=\frac{M}{2n}(d^2-|x-x_0|^2).
\]

则 \(-\Delta\phi=M\)。因此

\[
-\Delta(u-\phi)=f-M\le0.
\]

由最大值原理，

\[
\max_{\bar\Omega}(u-\phi)=\max_{\partial\Omega}(u-\phi).
\]

又 \(\phi\ge0\)，\(\phi\le Md^2/(2n)\)，故

\[
\max_{\bar\Omega}u\le G+\frac{Md^2}{2n}.
\]

对 \(-u\) 同理可得

\[
\max_{\bar\Omega}|u|\le G+\frac{Md^2}{2n}
\le C(n,d)(G+M).
\]

### 举一反三

1. 若 \(f=0\)，则 \(\|u\|_\infty\le\|g\|_\infty\)，这就是调和函数的最大值原理。
2. 若 \(g=0\)，则 \(\|u\|_\infty\le C\|f\|_\infty\)。
3. 若算子是 \(-\Delta u+cu=f\)，且 \(c\ge0\)，估计通常更容易，因为 \(cu\) 有利于最大值原理。

---

## 7. Green 函数与表示公式

### 知识点

Dirichlet Green 函数 \(G(x,y)\) 满足

\[
\begin{cases}
-\Delta_xG(x,y)=\delta_y, & x\in\Omega,\\
G(x,y)=0, & x\in\partial\Omega.
\end{cases}
\]

若

\[
\begin{cases}
-\Delta u=f, & x\in\Omega,\\
u=g, & x\in\partial\Omega,
\end{cases}
\]

则表示公式为

\[
u(x)=\int_{\partial\Omega}g(y)\partial_{n_y}G(x,y)\,dS_y
+\int_\Omega f(y)G(x,y)\,dy.
\]

### 考点

- 写 Green 函数定义。
- 推导表示公式。
- 会解释 \(\delta\) 的作用。

### 例题 7

推导上面的 Green 函数表示公式。

**答案：**
固定 \(x\in\Omega\)，令 \(v(y)=G(x,y)\)。由 Green 第二公式，

\[
\int_\Omega(u\Delta_yG-G\Delta_yu)\,dy
=\int_{\partial\Omega}(u\partial_{n_y}G-G\partial_{n_y}u)\,dS_y.
\]

因为 \(G=0\) on \(\partial\Omega\)，边界项变为

\[
\int_{\partial\Omega}g(y)\partial_{n_y}G(x,y)\,dS_y.
\]

又

\[
-\Delta_yG(x,y)=\delta_x(y),\qquad -\Delta u=f,
\]

整理得

\[
u(x)=\int_{\partial\Omega}g(y)\partial_{n_y}G(x,y)\,dS_y
+\int_\Omega f(y)G(x,y)\,dy.
\]

### 举一反三

1. 若 \(f=0\)，公式退化为边界积分表示：
   \[
   u(x)=\int_{\partial\Omega}g(y)\partial_{n_y}G(x,y)\,dS_y.
   \]
2. 若 \(g=0\)，公式退化为体积分表示：
   \[
   u(x)=\int_\Omega f(y)G(x,y)\,dy.
   \]
3. 若题目问 Poisson 核，本质上是把 \(\partial_{n_y}G(x,y)\) 写成显式核函数。

---

## 8. Hopf 引理

### 知识点

Hopf 引理描述边界严格最大值/最小值处的法向导数符号。

典型形式：若 \(u\) 在边界点 \(x_0\) 取得严格最大值，且满足合适椭圆不等式，则

\[
\partial_nu(x_0)>0
\]

或根据方程方向得到相反符号。

### 考点

- 简答叙述。
- 证明题中作为最大值原理的加强版使用。
- 注意“严格最大值”“内球条件”“外法向”。

### 例题 8

若 \(u\) 在边界点 \(x_0\) 取得严格最大值，为什么可期待 \(\partial_nu(x_0)>0\)？

**答案：**
从区域内部靠近边界最大点时，函数值上升到最大值。沿外法向继续向外看，函数增长方向对应正外法向导数。严格证明需要构造障碍函数并使用最大值原理。

### 举一反三

1. 若在边界取得严格最小值，通常得到 \(\partial_nu(x_0)<0\)。
2. 若最大值不是严格的，Hopf 结论可能失效。
3. 若区域边界不满足内球条件，也不能直接套用标准 Hopf 引理。

---

## 9. 能量估计

### 知识点

对

\[
-\Delta u=f
\]

常取测试函数 \(\varphi=u\)、\(u^+\)、\(\eta^2u\)。基本流程：

1. 方程乘测试函数并积分。
2. 积分分部。
3. 让边界项为 0。
4. 用 Cauchy-Schwarz 与 Young 不等式。
5. 必要时用 Poincare/Friedrichs 不等式。

### 考点

- 会写“乘测试函数、积分分部”的骨架。
- 会说明边界项为什么消失。
- 会用 Young 不等式吸收项。

### 例题 9

设 \(u=0\) on \(\partial\Omega\)，且 \(-\Delta u=f\)。证明能量估计骨架。

**答案：**
两边乘 \(u\) 并积分：

\[
\int_\Omega(-\Delta u)u\,dx=\int_\Omega fu\,dx.
\]

积分分部且 \(u=0\) on \(\partial\Omega\)，得

\[
\int_\Omega|\nabla u|^2\,dx=\int_\Omega fu\,dx.
\]

由 Cauchy-Schwarz 与 Young 不等式，

\[
\int_\Omega fu\,dx\le \frac12\int_\Omega f^2\,dx+\frac12\int_\Omega u^2\,dx.
\]

再由 Poincare 不等式 \(\int u^2\le C\int|\nabla u|^2\)，可得到 \(\|\nabla u\|_2\) 被 \(\|f\|_2\) 控制的估计。

### 举一反三

1. 做局部估计时取 \(\varphi=\eta^2u\)，会出现 \(\nabla\eta\) 项。
2. 做非负性证明时取 \(\varphi=u^-=\max\{-u,0\}\)。
3. 做一侧估计时取 \(u^+=\max\{u,0\}\)。

---

## 10. 最后一页背诵清单

1. \(\nabla\times\nabla\varphi=0\)，\(\nabla\cdot(\nabla\times F)=0\)。
2. \(\int_\Omega\operatorname{div}F=\int_{\partial\Omega}F\cdot n\)。
3. Green 第一公式：
   \[
   \int_\Omega\nabla u\cdot\nabla v
   =-\int_\Omega v\Delta u+\int_{\partial\Omega}v\partial_nu.
   \]
4. Green 第二公式：
   \[
   \int_\Omega(u\Delta v-v\Delta u)
   =\int_{\partial\Omega}(u\partial_nv-v\partial_nu).
   \]
5. Neumann 相容条件：
   \[
   \int_\Omega f+\int_{\partial\Omega}g=0.
   \]
6. Dirichlet 唯一性：两个解相减，对 \(w\) 和 \(-w\) 用最大值原理。
7. 最大模估计：构造 \(\phi=A(d^2-|x-x_0|^2)\)，使 \(-\Delta\phi\ge\|f\|_\infty\)。
8. Green 函数定义：
   \[
   -\Delta_xG(x,y)=\delta_y,\qquad G=0\text{ on }\partial\Omega.
   \]
9. 表示公式：
   \[
   u(x)=\int_{\partial\Omega}g\partial_nG+\int_\Omega fG.
   \]
10. 能量估计：乘测试函数，积分分部，边界项消失，Cauchy/Young/Poincare。

