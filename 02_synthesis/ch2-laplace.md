# 第二章 位势方程（Laplace / Poisson）

> 这是 PDE 学习的核心章节，期中考试的重中之重。
>
> **三条主线**：最大值原理体系、Green 函数体系、能量估计体系。

---

## 2.0 三个基本问题框架

1. **调和函数（Harmonic）**：$\Delta u = 0$
2. **位势方程（Poisson）**：$-\Delta u = f$
3. **Dirichlet 边值问题**：
   $$
   \begin{cases}
   -\Delta u = f & \text{in } \Omega \\
   u = g & \text{on } \partial\Omega
   \end{cases}
   $$

**Neumann 边值问题**：
$$
\begin{cases}
-\Delta u = f & \text{in } \Omega \\
\partial_n u = g & \text{on } \partial\Omega
\end{cases}
$$
（注意：Neumann 问题解不唯一，差一个常数；且需满足相容条件）

---

## 2.1 调和函数与平均值性质

### 平均值性质（球面版与球体版）

若 $u$ 在 $\Omega$ 内调和，则对任意球 $B(x,r) \subset\subset \Omega$：

**球面平均**：
$$u(x) = \frac{1}{|\partial B(x,r)|} \int_{\partial B(x,r)} u \, dS =: \fint_{\partial B(x,r)} u \, dS$$

**球体平均**：
$$u(x) = \frac{1}{|B(x,r)|} \int_{B(x,r)} u(y) \, dy =: \fint_{B(x,r)} u \, dy$$

**逆定理**也成立：连续函数满足平均值性质 $\Rightarrow$ 调和。（可用于反证法证明非调和）

### 平均值性质的证明思路

老师讲法的关键技巧：
1. 通过变量替换把变动半径 $r$ 变成单位球
2. 让 $r$ 进入被积函数
3. 对 $r$ 求导
4. 用 $\Delta u = 0$ 或散度定理证明导数为 0
5. 令 $r \to 0$ 得到平均值等于 $u(x)$

### 平均值性质 → 强最大值原理

**关键论证**：若 $u$ 在内部点 $x_0$ 取得最大值，对小球 $B(x_0, r)$：
$$u(x_0) = \fint_{B(x_0,r)} u(y) \, dy$$

但积分平均等于最大值，只能说明球内几乎处处 $u(y) = u(x_0)$（否则平均严格小于最大值）。由连续性推出局部常数，再由连通性推出全域常数。

**注意**：区域"连通"不是装饰条件，它用于从局部常数推进到全域常数。

### Harnack 不等式

对非负调和函数 $u \ge 0$ 在 $\Omega$ 内，对任意紧集 $K \Subset \Omega$：

$$\sup_K u \le C \inf_K u$$

其中 $C = C(n, K, \Omega)$。

**深层意义**：非负调和函数在有界连通区域中不能一处很大、一处很小——它不能剧烈振荡。

**考试写法**：条件比常数更重要——非负、调和、内部紧子集、常数依赖区域距离和维数。

### 调和函数导数估计定理

**核心公式**：
$$|D^\alpha u(x)| \le \frac{C_{n,k}}{R^{n+k}} \int_{B(x,R)} |u(y)| \, dy, \qquad |\alpha| = k$$

**深层意义**：
1. 调和函数自动 $C^\infty$（事实上是实解析的）
2. 内部导数由稍大球上的 $L^1$ 信息控制
3. 越靠近边界，估计越差（$R$ 不能超过到边界的距离）
4. 这是 PDE 中"内部估计"的原型

**证明结构**（老师讲得很细，考试喜欢抽其中一步）：

- **$k=0$**：就是平均值公式取绝对值
- **$k=1$**：因 $\Delta u = 0$，故 $\Delta(\partial_i u) = \partial_i(\Delta u) = 0$，即 $\partial_i u$ 仍调和。对 $\partial_i u$ 用平均值公式，再把 $\partial_i u$ 写成某个向量场的散度，用散度定理把体积分变成球面积分，最后对半径 $s \in (0, R)$ 积分
- **一般 $k$**：数学归纳法。设 $|\alpha| = k$，写 $D^\alpha u = \partial_i D^\beta u$，$|\beta| = k-1$，对 $D^\beta u$ 用归纳假设，用嵌套球控制区域

**嵌套球技巧**：
$$y \in B(x, tR), \quad z \in B(y, (1-t)R) \Rightarrow z \in B(x, R)$$

证明：$|z-x| \le |z-y| + |y-x| < (1-t)R + tR = R$。

### 推论速查

| 结论 | 来源 |
|---|---|
| 调和函数 $C^\infty$ | 任意阶导数有内部估计 |
| 调和函数实解析 | 更精细的展开 |
| 强最大值原理 | 平均值性质 + 反证 |
| 内部导数估计 | 平均值 + 散度定理 |
| Harnack 不等式 | 平均值 + 链式论证 |

---

## 2.2 基本解与 Green 函数

### 基本解（Fundamental Solution）

满足 $-\Delta \Gamma = \delta_0$（分布意义）：

- $n \ge 3$：$\Gamma(x) = \frac{1}{n(n-2)\alpha_n} |x|^{2-n}$
- $n = 2$：$\Gamma(x) = -\frac{1}{2\pi} \ln|x|$
- $n = 1$：$\Gamma(x) = -\frac{1}{2}|x|$

其中 $\alpha_n$ 是 $n$ 维单位球体积。

### Green 函数（Dirichlet）

对固定 $y \in \Omega$，函数 $G(x,y)$ 满足：

$$
\begin{cases}
-\Delta_x G(x,y) = \delta_y & \text{in } \Omega \\
G(x,y) = 0 & \text{on } \partial\Omega
\end{cases}
$$

**分解**：$G(x,y) = \Gamma(x-y) - H(x,y)$，其中 $H$ 对 $x$ 调和，用于把边界值修正为 0。

### 对称性

$G(x,y) = G(y,x)$（物理意义：$y$ 点处单位源在 $x$ 处的影响 = $x$ 点处单位源在 $y$ 处的影响）

### 表示公式

若 $u \in C^2(\Omega) \cap C(\overline{\Omega})$ 解 Dirichlet 问题：

$$
u(x) = \int_{\partial\Omega} g(y) \, \partial_{n_y} G(x,y) \, dS_y + \int_\Omega f(y) \, G(x,y) \, dy
$$

### Poisson 核（显式情形）

**球 $B_R$ 的 Poisson 核**：
$$P_R(x,\xi) = \frac{R^2 - |x|^2}{n\alpha_n R \, |x-\xi|^n}, \quad \xi \in \partial B_R$$

**半空间 $\mathbb{R}^n_+$ 的 Poisson 核**：
$$K(x,y) = \frac{2 x_n}{n\alpha_n |x-y|^n}, \quad y \in \partial\mathbb{R}^n_+$$

---

## 2.3 最大值原理与比较原理

### 强最大值原理

设 $u \in C^2(\Omega) \cap C(\overline{\Omega})$，$c(x) \ge 0$ 在 $\Omega$ 上。

若 $Lu = -\Delta u + c(x)u \le 0$（或 $\ge 0$），且 $u$ 在 $\Omega$ 内达到非负最大值（或非正最小值），则 $u$ 为常数。

**特别地**：若 $c \equiv 0$ 且 $\Delta u = 0$，则 $\max_{\overline{\Omega}} u = \max_{\partial\Omega} u$。

### 弱最大值原理

即使不满足"内点达到"，也有：最大值在边界上取得。

### 比较原理

若 $Lu \le Lv$ in $\Omega$，且 $u \le v$ on $\partial\Omega$，则 $u \le v$ in $\Omega$。

### 直接推论（考试高频）

1. **Dirichlet 问题唯一性**：令 $w = u-v$，则 $Lw = 0$，$w|_{\partial\Omega} = 0$，由最大值原理 $w \equiv 0$。
2. **最大模估计 / 先验估计**：$\|u\|_{L^\infty}$ 被 $\|g\|_{L^\infty}$ 和 $\|f\|_{L^\infty}$ 控制。

---

## 2.4 Hopf 引理

当最大值在边界处"严格发生"时，可推出法向导数符号。

**球域版本**：
- 若 $u \in C^2(B_R) \cap C(\overline{B_R})$，$c > 0$
- 且 $-\Delta u + cu < 0$ in $B_R$
- 若 $u$ 在边界点 $x_0 \in \partial B_R$ 取到最大值，且该值严格大于内点值
- 则 $\partial_n u(x_0) > 0$（外法向）

**证明套路**：构造障碍函数 $v$（常用 $v = |x|^\alpha - R^\alpha$ 或 $v = e^{k|x|^2}$），令 $w = u + \varepsilon v$，用最大值原理逼出矛盾。

---

## 2.5 最大模估计（障碍函数法）

**典型结论**：若 $-\Delta u = f$ in $\Omega$，$u = g$ on $\partial\Omega$，则存在 $C = C(n, \operatorname{diam}\Omega)$：

$$\|u\|_{L^\infty(\Omega)} \le C \left( \|g\|_{L^\infty(\partial\Omega)} + \|f\|_{L^\infty(\Omega)} \right)$$

**障碍函数构造套路**：
1. 设 $d = \operatorname{diam}(\Omega)$，取任意 $x_0 \in \overline{\Omega}$
2. 构造 $\varphi(x) = A(d^2 - |x-x_0|^2)$，使得 $-\Delta \varphi \ge \|f\|_\infty$
3. 令 $w = u - \varphi$，使得 $-\Delta w \le 0$
4. 对 $w$ 用最大值原理：$\max_{\overline{\Omega}} w = \max_{\partial\Omega} w$
5. 把边界上 $w$ 与 $g$、$\varphi$ 的界代回，即得估计

---

## 2.6 Neumann 问题的相容条件

**问题**：
$$
\begin{cases}
-\Delta u = f & \text{in } \Omega \\
\partial_n u = g & \text{on } \partial\Omega
\end{cases}
$$

**必要条件**（也是充分条件，在适当空间中）：

$$\int_\Omega f \, dx + \int_{\partial\Omega} g \, dS = 0$$

**证明骨架**：
1. 对 $-\Delta u = f$ 在 $\Omega$ 积分：$-\int_\Omega \Delta u \, dx = \int_\Omega f \, dx$
2. 散度定理：$-\int_\Omega \Delta u \, dx = -\int_{\partial\Omega} \partial_n u \, dS$
3. 代入边界条件：$-\int_{\partial\Omega} g \, dS = \int_\Omega f \, dx$
4. 移项即得结论

**注意**：解不唯一，差一个常数。

---

## 2.7 能量估计

### 基本思路

对 $Lu = f$，取测试函数 $\varphi$，两边乘 $\varphi$ 并积分分部，得到 $\int |\nabla u|^2$ 的估计。

### 常用测试函数

| 测试函数 | 用途 |
|---|---|
| $u$ | 最基础的全局能量估计 |
| $u^+ = \max(u, 0)$ | 处理一侧估计 |
| $\eta^2 u$（$\eta$ 为截断函数） | 局部能量估计（Caccioppoli 型） |
| $(u - k)^+$ | 水平集估计 |

### 标准能量估计

对 $-\Delta u = f$ in $\Omega$，$u = 0$ on $\partial\Omega$：

1. 两边乘 $u$ 积分：$\int_\Omega (-\Delta u) u = \int_\Omega f u$
2. 分部：$\int_\Omega |\nabla u|^2 - \int_{\partial\Omega} u \partial_n u = \int_\Omega f u$
3. 边界项为 0（$u|_{\partial\Omega} = 0$）
4. Cauchy-Schwarz + Young：$\int f u \le \frac{1}{2} \int |\nabla u|^2 + \frac{C}{2} \int f^2$
5. 吸收到左边：$\int |\nabla u|^2 \le C \int f^2$

### 配套工具

- **Friedrichs 不等式**：若 $u|_{\partial\Omega} = 0$，则 $\int_\Omega |u|^2 \le C \int_\Omega |\nabla u|^2$
- **Poincaré 不等式**：$\int_\Omega |u - u_\Omega|^2 \le C \int_\Omega |\nabla u|^2$

---

## 2.8 变分法（Dirichlet 原理）

对 Dirichlet 问题（$f = 0$）：
- 固定边界值 $g$，考虑集合 $M_g = \{ u \in H^1(\Omega) : u|_{\partial\Omega} = g \}$
- 最小化 Dirichlet 泛函：$J(u) = \int_\Omega |\nabla u|^2 \, dx$
- 极小元满足 Euler–Lagrange：$\Delta u = 0$（弱形式 $\Rightarrow$ 强形式在正则性下成立）

**物理意义**：调和函数使"能量"最小。

---

## 本章小结

| 体系 | 核心工具 | 解决的问题 |
|---|---|---|
| 平均值体系 | 均值性质、Harnack | 正则性、导数估计 |
| Green 函数体系 | 基本解、表示公式 | 存在性、显式解 |
| 最大值原理体系 | 比较原理、Hopf | 唯一性、最大模估计 |
| 能量法体系 | 分部积分、不等式 | 唯一性、稳定性、弱解存在性 |
