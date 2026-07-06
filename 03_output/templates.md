# 解题模板

> 把常见题型抽成可以直接套用的骨架。
> 考试时先识别题型，再套对应模板。

---

## A. 填空 / 简答模板

### A1. 求阶数 + 方程分类

**步骤**：
1. 找最高阶导数 → 阶数
2. 判断线性/半线性/拟线性/完全非线性
3. 说出方程名称或类型

**例子**：
- $u_t - \Delta(u^\gamma) = 0$：2 阶，退化抛物型（多孔介质方程）
- $u_t + uu_x + u_{xxx} = 0$：3 阶，非线性色散方程（KdV）

### A2. 向量分析恒等式

前提：$\varphi \in C^2$，$F \in C^2$（保证混合偏导可交换）

- $\nabla \times (\nabla \varphi) = 0$
- $\nabla \cdot (\nabla \times F) = 0$

**写法**：一句话点明"二阶混合偏导可交换"即可。

---

## B. 计算题模板

### B1. 球面外法向 + 径向函数的法向导数

设 $\partial B(0,R)$ 上外法向：$n(x) = \frac{x}{|x|} = \frac{x}{R}$

若 $u(x) = \psi(|x|)$ 为径向函数：
- $\nabla u(x) = \psi'(|x|) \cdot \frac{x}{|x|}$
- 在 $|x|=R$ 上：$\partial_n u = \psi'(R)$

**典型例子**：$u(x) = e^{-3|x|}$
- $\psi(r) = e^{-3r}$，$\psi'(r) = -3e^{-3r}$
- $\partial_n u|_{|x|=R} = -3e^{-3R}$

### B2. 散度定理换积分

看到 $\int_\Omega \operatorname{div} F$ 或 $\int_\Omega \Delta u$（本质是 $\operatorname{div}(\nabla u)$）：

$$\int_\Omega \Delta u \, dx = \int_{\partial\Omega} \partial_n u \, dS$$

这类题常和"相容条件/必要条件"一起出。

---

## C. 证明题模板（最关键）

### C1. Neumann 相容条件 ⭐必考级

**题型**：
$$
\begin{cases}
-\Delta u = f & \text{in } \Omega \\
\partial_n u = g & \text{on } \partial\Omega
\end{cases}
$$
证明：$\int_\Omega f + \int_{\partial\Omega} g = 0$

**骨架（三行）**：
1. 积分：$\int_\Omega (-\Delta u) \, dx = \int_\Omega f \, dx$
2. 散度定理：$\int_\Omega (-\Delta u) \, dx = -\int_{\partial\Omega} \partial_n u \, dS$
3. 代入边界条件：$-\int_{\partial\Omega} g \, dS = \int_\Omega f \, dx \Rightarrow$ 结论

**评分点**：写清楚外法向的 $\partial_n$，用到散度定理/Green 第一公式。

### C2. 最大值原理 + 唯一性

**题型 1：证明 Dirichlet 问题唯一性**

骨架：
1. 设 $u, v$ 都是解，令 $w = u - v$
2. 得到 $Lw = 0$ in $\Omega$，且 $w = 0$ on $\partial\Omega$
3. 由最大值原理：$\max_{\overline{\Omega}} w = \max_{\partial\Omega} w = 0$，同理 $\min = 0$
4. 所以 $w \equiv 0$

**题型 2：最大值只能在边界**

骨架（反证）：
- 假设在内点达到最大值，利用 $D^2 u(x_0) \le 0 \Rightarrow \Delta u(x_0) \le 0$
- 与 $Lu \le 0$（或严格 $<0$）矛盾
- 推出最大值在边界或 $u$ 常数

### C3. 最大模估计（障碍函数法）⭐核心

**典型结论**：若 $-\Delta u = f$ in $\Omega$，$u = g$ on $\partial\Omega$，则
$$\|u\|_{L^\infty(\Omega)} \le C \left( \|g\|_{L^\infty(\partial\Omega)} + \|f\|_{L^\infty(\Omega)} \right)$$

**套路**：
1. 设 $d = \operatorname{diam}(\Omega)$，取任意 $x_0 \in \overline{\Omega}$
2. 构造 $\varphi(x) = A(d^2 - |x-x_0|^2)$，让 $-\Delta \varphi \ge \|f\|_\infty$
3. 令 $w = u - \varphi$，使得 $-\Delta w \le 0$
4. 对 $w$ 用最大值原理：$\max_{\overline{\Omega}} w = \max_{\partial\Omega} w$
5. 把边界上 $w$ 与 $g$、$\varphi$ 的界代回

**评分点**：$\varphi$ 选 $|x|^2$ 最好用（$\Delta$ 后是常数）；常数 $C$ 写"与 $n, d$ 有关"即可。

### C4. Hopf 引理

**看到关键词**：边界取到严格最大/最小值、证明法向导数符号

**模板**：
1. 写清楚算子与不等式方向（如 $-\Delta u + cu < 0$）
2. 取障碍函数 $v$（球域用 $v = |x|^\alpha - R^\alpha$ 最常见）
3. $w = u + \varepsilon v$，使得 $Lw < 0$ 且边界比较成立
4. 用最大值原理推出 $w$ 不可能在边界点取最大值，矛盾
5. 得到 $\partial_n u(x_0) > 0$

### C5. Green 函数表示公式（推导题）

**题型**：给定 $-\Delta u = f, \, u = g$，推导
$$u(x) = \int_{\partial\Omega} g \, \partial_n G + \int_\Omega f \, G$$

**模板**：
1. 写 Green 第二公式：$\int_\Omega (u\Delta v - v\Delta u) = \int_{\partial\Omega}(u\partial_n v - v\partial_n u)$
2. 取 $v(y) = G(x,y)$（固定 $x$，把 $y$ 当变量）
3. 用 $-\Delta_y G(x,y) = \delta_x$，且 $G(x,y) = 0$ 在边界
4. 消掉边界项中的 $v$，用 $\delta$ 的性质 $\int u(y)\delta_x(y) dy = u(x)$
5. 得到表示公式

**评分点**：说明 $G$ 的边界为 0；说明 $\delta$ 函数的作用。

---

## D. 能量估计模板

**题型**：对 $-\Delta u = f$（或 $-\Delta u + cu = f$），证明 $\int |\nabla u|^2 \le \cdots$

**常用测试函数**：
- $u$ — 最基础
- $u^+ = \max(u,0)$ — 处理一侧估计
- $\eta^2 u$（$\eta$ 截断函数）— 局部估计

**骨架（以 $-\Delta u = f$ 为例）**：
1. 两边乘测试函数 $\varphi$ 并积分：$\int (-\Delta u)\varphi = \int f\varphi$
2. 分部：$\int \nabla u \cdot \nabla \varphi - \int_{\partial\Omega} \varphi \partial_n u = \int f\varphi$
3. 选 $\varphi$ 让边界项为 0（如 $u|_{\partial\Omega} = 0$ 或 $\eta$ 支撑在内部）
4. 用 Cauchy-Schwarz / Young 不等式把 RHS 吸收到 LHS
5. 若需要把 $\int |u|^2$ 用 $\int |\nabla u|^2$ 控制，引 Friedrichs / Poincaré
