# 模拟卷

## 期中模拟卷一

> 仿上次命题风格。默认 $\Omega \subset \mathbb{R}^n$（$n \ge 2$）为有界光滑区域，$n$ 为单位外法向，函数光滑到足以使用混合偏导交换与积分分部。

### 一、填空题（每空 2 分，共 12 分）

1. 对于非线性方程 $u_t - \Delta(u^\gamma) = 0$（$\gamma > 1$），其最高阶为 \_\_\_ 阶；该方程常称为 \_\_\_ 方程。

2. 对于方程 $u_t + uu_x + u_{xxx} = 0$，其最高阶为 \_\_\_ 阶；该方程常称为 \_\_\_ 方程。

3. 若 $\varphi \in C^2(\mathbb{R}^3)$，则 $\nabla \times (\nabla \varphi) = $ \_\_\_。

4. 若 $F \in C^2(\mathbb{R}^3; \mathbb{R}^3)$，则 $\nabla \cdot (\nabla \times F) = $ \_\_\_。

5. Green 第一公式：$\int_\Omega \nabla u \cdot \nabla v \, dx = $ \_\_\_ $+ \int_{\partial\Omega} v \, \partial_n u \, dS$。

6. Neumann 问题 $-\Delta u = f$ in $\Omega$，$\partial_n u = g$ on $\partial\Omega$ 的相容条件为 $\int_\Omega f \, dx + \int_{\partial\Omega}$ \_\_\_ $\, dS = 0$。

### 二、简答题（每题 6 分，共 18 分）

1. 写出 Green 第二公式，并说明它最常用来推导哪两类结论（各写 1 条即可）。

2. 给出 Dirichlet Green 函数 $G(x,y)$（针对 $-\Delta$）的定义（写出满足的 PDE 与边界条件）。

3. 写出强最大值原理的一个典型表述（针对 $Lu = -\Delta u + c(x)u$，$c \ge 0$），并说明它如何推出 Dirichlet 问题的唯一性。

### 三、计算题（每题 10 分，共 20 分）

1. 设 $u(x) = e^{-3|x|}$，并令 $n(x) = x/|x|$ 为 $\partial B(0,R) \subset \mathbb{R}^3$ 上的外法向。计算在 $|x|=R$ 上的法向导数 $\partial_n u(x)$。

2. 设向量场 $F(x) = x = (x_1, \dots, x_n)$。计算 $\int_{\partial B(0,R)} F \cdot n \, dS$。

### 四、证明题（每题 20 分，共 40 分）

1. **（相容条件）** 设 $u \in C^2(\Omega) \cap C^1(\overline{\Omega})$ 满足
   $$
   \begin{cases}
   -\Delta u = f(x), & x \in \Omega \\
   \partial_n u = g(x), & x \in \partial\Omega
   \end{cases}
   $$
   证明：$\int_\Omega f(x) \, dx + \int_{\partial\Omega} g(x) \, dS = 0$。

2. **（最大模估计，仿上次期中）** 设 $u \in C^2(\Omega) \cap C(\overline{\Omega})$ 满足
   $$
   \begin{cases}
   -\Delta u = f(x), & x \in \Omega \\
   u = g(x), & x \in \partial\Omega
   \end{cases}
   $$
   其中 $f \in C(\overline{\Omega})$，$g \in C(\partial\Omega)$。设 $d = \operatorname{diam}(\Omega)$。证明：存在常数 $C = C(n, d) > 0$，使得
   $$\max_{\overline{\Omega}} |u| \le C \left( \max_{\partial\Omega} |g| + \sup_{\Omega} |f| \right).$$
   提示：可取某点 $x_0 \in \overline{\Omega}$，构造二次函数障碍 $\varphi(x) = A(d^2 - |x-x_0|^2)$ 并应用最大值原理。

### 五、综合题（12 分）

设 $\Omega$ 存在 Dirichlet Green 函数 $G(x,y)$。对任意满足
$$
\begin{cases}
-\Delta u = f & \text{in } \Omega \\
u = g & \text{on } \partial\Omega
\end{cases}
$$
的解 $u$，推导表示公式
$$u(x) = \int_{\partial\Omega} g(y) \, \partial_{n_y} G(x,y) \, dS_y + \int_\Omega f(y) \, G(x,y) \, dy.$$

---

## 期中模拟卷一 · 答案与评分点

### 一、填空题答案

| 题号 | 答案 |
|---|---|
| 1 | 2；多孔介质（porous medium）方程（也可写"退化抛物型方程"） |
| 2 | 3；KdV（Korteweg–de Vries）方程 |
| 3 | $0$ |
| 4 | $0$ |
| 5 | $-\int_\Omega v \, \Delta u \, dx$ |
| 6 | $g$ |

---

### 二、简答题答案

#### 1) Green 第二公式 + 用途

**公式**：
$$\int_\Omega (u \Delta v - v \Delta u) \, dx = \int_{\partial\Omega} (u \, \partial_n v - v \, \partial_n u) \, dS$$

**常用用途**（写到两条即可，每条 3 分）：
- 推导 Neumann/Dirichlet 问题的必要条件或唯一性（配合最大值原理）
- 推导 Green 函数表示公式、Poisson 核表示公式

**评分点**：
- 体积分 integrand 的符号顺序不能写反
- 边界项必须是 $u \partial_n v - v \partial_n u$

#### 2) Dirichlet Green 函数定义

对固定 $y \in \Omega$，函数 $G(\cdot, y)$ 满足：
$$
\begin{cases}
-\Delta_x G(x,y) = \delta_y & \text{in } \Omega \\
G(x,y) = 0 & \text{on } \partial\Omega
\end{cases}
$$
并且 $x \ne y$ 时 $G(\cdot, y)$ 在 $\Omega$ 内调和。

**评分点**：
- 写清楚 delta 的位置（$\delta_y$）
- 写清楚边界条件是 0（Dirichlet）

#### 3) 强最大值原理 + 唯一性

**典型表述**：
若 $u \in C^2(\Omega) \cap C(\overline{\Omega})$，$c(x) \ge 0$，且
$$Lu = -\Delta u + c(x)u \le 0 \quad \text{in } \Omega$$
那么 $u$ 的最大值只能在边界取到；若最大值在 $\Omega$ 内某点取到且该最大值非负，则 $u$ 在 $\Omega$ 上为常数。

**推出唯一性**：
- 若 $u, v$ 都解同一 Dirichlet 问题，则 $w = u - v$ 满足 $Lw = 0$ 且 $w = 0$ on $\partial\Omega$
- 对 $w$ 与 $-w$ 用最大值原理得 $\max_{\overline{\Omega}} w \le 0$ 且 $\max_{\overline{\Omega}} (-w) \le 0$
- 得 $w \equiv 0$，即 $u \equiv v$

**评分点**：说明对 $w$ 与 $-w$ 都要用一次。

---

### 三、计算题答案

#### 1) 径向函数法向导数

设 $r = |x|$，$u(x) = e^{-3r}$，则
$$\nabla u = u'(r) \frac{x}{r}, \qquad u'(r) = -3 e^{-3r}$$

在 $|x| = R$ 上，外法向 $n = x/R = x/r$。因此
$$\partial_n u = \nabla u \cdot n = u'(R) = -3 e^{-3R}$$

**评分点**：
- 写出 $n = x/|x|$（2 分）
- 写出 $\nabla u = u'(r) x/r$（4 分）
- 得出 $-3 e^{-3R}$（4 分）

#### 2) $\int_{\partial B(0,R)} x \cdot n \, dS$

在 $\partial B(0,R)$ 上，$n = x/|x| = x/R$，所以 $x \cdot n = |x|^2/R = R$。
$$\int_{\partial B(0,R)} x \cdot n \, dS = \int_{\partial B(0,R)} R \, dS = R \cdot |\partial B(0,R)|$$

**也可用散度定理**（更通用）：
- $\operatorname{div} x = n$（维数）
$$\int_{\partial B(0,R)} x \cdot n \, dS = \int_{B(0,R)} \operatorname{div} x \, dx = \int_{B(0,R)} n \, dx = n \cdot |B(0,R)|$$

两种写法等价，因为 $|\partial B(0,R)| = n |B(0,R)| / R$。

**评分点**：给出一种完整推导即可（建议散度定理法）。

---

### 四、证明题答案

#### 1) Neumann 相容条件

对 $-\Delta u = f$ 在 $\Omega$ 上积分：
$$\int_\Omega (-\Delta u) \, dx = \int_\Omega f \, dx$$

用散度定理/Green 第一公式（取测试函数 1）：
$$\int_\Omega (-\Delta u) \, dx = -\int_{\partial\Omega} \partial_n u \, dS$$

代入边界条件 $\partial_n u = g$：
$$-\int_{\partial\Omega} g \, dS = \int_\Omega f \, dx \quad \Longrightarrow \quad \int_\Omega f \, dx + \int_{\partial\Omega} g \, dS = 0$$

**评分点**：
- 用到"测试函数 1"或散度定理（8 分）
- 正确处理符号（8 分）
- 写清楚边界条件替换（4 分）

#### 2) 最大模估计（障碍函数 + 最大值原理）

设 $M = \sup_\Omega |f|$，$G = \max_{\partial\Omega} |g|$，$d = \operatorname{diam}(\Omega)$。

取任意 $x_0 \in \overline{\Omega}$，定义
$$\varphi(x) = A(d^2 - |x - x_0|^2), \qquad A = \frac{M}{2n}$$

则 $\Delta |x - x_0|^2 = 2n$，所以
$$-\Delta \varphi = -A \Delta(d^2 - |x-x_0|^2) = A \cdot 2n = M \ge f, \quad \text{从而 } -\Delta(u - \varphi) \le 0$$

令 $w = u - \varphi$。由最大值原理：
$$\max_{\overline{\Omega}} w = \max_{\partial\Omega} w$$

注意边界上 $|x - x_0| \le d$，故 $\varphi|_{\partial\Omega} \ge 0$。于是
$$\max_{\overline{\Omega}} u \le \max_{\overline{\Omega}} w + \max_{\overline{\Omega}} \varphi = \max_{\partial\Omega} w + \max_{\overline{\Omega}} \varphi \le \max_{\partial\Omega} u + \max_{\overline{\Omega}} \varphi \le G + A d^2$$

同理对 $-u$ 重复一次（或取 $\tilde{\varphi}$），得到
$$\max_{\overline{\Omega}} |u| \le G + A d^2 = G + \frac{M}{2n} d^2 \le C(n, d) (G + M)$$

取 $C(n, d) = \max\{1, d^2/(2n)\}$ 即可。

**评分点**：
- 正确构造 $\varphi$ 并算出 $-\Delta \varphi = M$（8 分）
- 正确写出对 $w = u - \varphi$ 的最大值原理应用（6 分）
- 处理边界项并得到 $\max u$ 的界（4 分）
- 对 $-u$ 再做一次得到 $\max |u|$（2 分）

---

### 五、综合题答案：Green 函数表示公式

对固定 $x \in \Omega$，视 $y$ 为变量，取 $v(y) = G(x, y)$。

由 Green 第二公式：
$$\int_\Omega \big(u(y) \Delta_y G(x,y) - G(x,y) \Delta_y u(y)\big) \, dy = \int_{\partial\Omega} \big(u \, \partial_{n_y} G - G \, \partial_{n_y} u\big) \, dS_y$$

利用 Dirichlet Green 函数边界条件 $G(x,y) = 0$（$y \in \partial\Omega$），边界项化为
$$\int_{\partial\Omega} u(y) \, \partial_{n_y} G(x,y) \, dS_y = \int_{\partial\Omega} g(y) \, \partial_{n_y} G(x,y) \, dS_y$$

又因 $-\Delta_y G(x,y) = \delta_x(y)$，得 $\Delta_y G(x,y) = -\delta_x(y)$，故
$$\int_\Omega u(y) \Delta_y G(x,y) \, dy = -\int_\Omega u(y) \delta_x(y) \, dy = -u(x)$$

同时 $-\Delta u = f \Rightarrow \Delta u = -f$，所以
$$-\int_\Omega G(x,y) \Delta_y u(y) \, dy = -\int_\Omega G(x,y) (-f(y)) \, dy = \int_\Omega f(y) G(x,y) \, dy$$

把以上三步合并并移项即得
$$u(x) = \int_{\partial\Omega} g(y) \, \partial_{n_y} G(x,y) \, dS_y + \int_\Omega f(y) G(x,y) \, dy$$

**评分点**：
- 选 $v = G(x, \cdot)$ 并写出 Green 第二公式（4 分）
- 用到 $G|_{\partial\Omega} = 0$（3 分）
- 用到 $-\Delta G = \delta$ 与 $-\Delta u = f$ 的符号（5 分）
