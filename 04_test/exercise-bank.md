# 习题库

按章节分类的典型习题，每题附简要答案与思路。来源于课堂纪要、复习提纲与北大课本习题。

---

## Ch1 基础概念

### 1.1 PDE 阶数与算子

**题 1：** 判断 $u_t - \Delta(u^\gamma) = 0$（$\gamma > 1$）的最高阶与类型。

**答：** 最高阶为 2 阶（$\Delta(u^\gamma)$ 含空间二阶导）；多孔介质方程；退化抛物型非线性扩散方程。

**题 2：** 判断 $u_t + u u_x + u_{xxx} = 0$ 的最高阶与类型。

**答：** 最高阶为 3 阶；KdV 方程；非线性色散方程。

**题 3：** 判断 $-\Delta u = f$ 的类型。

**答：** 二阶椭圆型方程，Poisson 方程。

**题 4：** 判断 $\Delta u = 0$ 的类型。

**答：** 二阶椭圆型方程，解称为调和函数。

**题 5：** 判断 $\det D^2 u = f$ 的类型。

**答：** 二阶完全非线性方程，Monge-Ampère 方程。

### 1.2 向量分析恒等式

**题 6：** 设 $\varphi \in C^2(\mathbb{R}^3)$，求 $\nabla \times (\nabla \varphi)$。

**答：** $0$。原因：二阶混合偏导可交换，例如 $\partial_{xy} \varphi = \partial_{yx} \varphi$。

**题 7：** 设 $F \in C^2(\mathbb{R}^3; \mathbb{R}^3)$，求 $\nabla \cdot (\nabla \times F)$。

**答：** $0$。同样由二阶混合偏导交换性。

**题 8：** 设 $u(x,y) = x^2 y + y^3$，求 $\Delta u$。

**答：** $u_{xx} = 2y$，$u_{yy} = 6y$，故 $\Delta u = 8y$。

**题 9：** 设 $F(x,y,z) = (x^2, y^2, z^2)$，求 $\operatorname{div} F$。

**答：** $2x + 2y + 2z$。

**题 10：** 设 $u(x) = |x|^2$ in $\mathbb{R}^n$，求 $\Delta u$。

**答：** $\Delta |x|^2 = 2n$。

**题 11：** 设 $u(x) = e^{a \cdot x}$，求 $\Delta u$。

**答：** $\Delta u = |a|^2 e^{a \cdot x}$。

### 1.3 球面计算与散度定理

**题 12：** 球面 $\partial B(0,R)$ 的单位外法向是什么？

**答：** $n(x) = x / |x| = x / R$。

**题 13：** 设 $u(x) = e^{-3|x|}$，求 $\partial_n u$ 在 $\partial B(0,R)$ 上的值。

**答：** 令 $r = |x|$，$u = \psi(r) = e^{-3r}$，$\psi'(r) = -3 e^{-3r}$。故 $\partial_n u = \psi'(R) = -3 e^{-3R}$。

**题 14：** 设 $u(x) = |x|^2$，求 $\partial_n u|_{|x|=R}$。

**答：** $\psi(r) = r^2$，$\psi'(r) = 2r$，故 $\partial_n u = 2R$。

**题 15：** 设 $u(x) = \ln |x|$，求 $\partial_n u|_{|x|=R}$。

**答：** $\psi'(r) = 1/r$，故 $\partial_n u = 1/R$。

**题 16：** 设 $F(x) = x$，求 $\int_{\partial B(0,R)} F \cdot n \, dS$。

**答：** 由散度定理，$\int_{\partial B_R} x \cdot n \, dS = \int_{B_R} \operatorname{div} x \, dx = n |B_R|$。

**题 17：** 默写散度定理、Green 第一公式、Green 第二公式。

**答：**

散度定理：$\int_\Omega \operatorname{div} F \, dx = \int_{\partial\Omega} F \cdot n \, dS$。

Green 第一公式：$\int_\Omega \nabla u \cdot \nabla v \, dx = -\int_\Omega v \Delta u \, dx + \int_{\partial\Omega} v \partial_n u \, dS$。

Green 第二公式：$\int_\Omega (u \Delta v - v \Delta u) \, dx = \int_{\partial\Omega} (u \partial_n v - v \partial_n u) \, dS$。

### 1.4 适定性

**题 18：** Hadamard 适定性包含哪三条？

**答：** 解存在、解唯一、解连续依赖于数据（稳定性）。

**题 19：** 为什么唯一性证明常用"两个解作差"？

**答：** 线性方程下，差函数满足齐次方程与齐次边界，便于用最大值原理或能量法证明差为零。

**题 20：** Dirichlet 问题的稳定性是什么意思？

**答：** 若 $u_1, u_2$ 分别对应边界值 $g_1, g_2$，则 $\|u_1 - u_2\|_{L^\infty(\Omega)} \le \|g_1 - g_2\|_{L^\infty(\partial\Omega)}$。

---

## Ch2 位势方程

### 2.1 调和函数与平均值性质

**题 1：** 若 $u$ 在 $B(0,R)$ 调和，求 $u(0)$ 与球面平均的关系。

**答：** $u(0) = \frac{1}{|\partial B_R|} \int_{\partial B_R} u \, dS$。

**题 2：** 若 $u$ 在 $B(0,R)$ 调和，且 $u = 0$ on $\partial B_R$，证明 $u \equiv 0$。

**答：** 最大值原理给出 $\max u \le 0$；对 $-u$ 用最大值原理得 $-u \le 0$，故 $u = 0$。

**题 3：** 若 $u \ge 0$ 调和，能否在内部一点为 0 而不恒为 0？

**答：** 不能。$u(x_0) = 0$ 是非负函数的内部最小值，由强极值原理 $u \equiv 0$。

**题 4：** 若 $u$ 调和，$u^2$ 是否调和？

**答：** 一般不是。$\Delta(u^2) = 2|\nabla u|^2 + 2u \Delta u = 2|\nabla u|^2$，除非 $\nabla u = 0$。

**题 5：** 若 $u, v$ 调和，$u + v$ 是否调和？

**答：** 是。Laplace 算子线性：$\Delta(u+v) = \Delta u + \Delta v = 0$。

**题 6：** 若 $u$ 调和，$\partial_i u$ 是否调和？

**答：** 是。$\Delta(\partial_i u) = \partial_i(\Delta u) = 0$。

**题 7：** 若 $u$ 调和且在内部点 $x_0$ 取得最大值，证明 $u$ 在 $x_0$ 附近为常数。

**答：** 对小球 $B(x_0, r)$ 用平均值公式：$u(x_0) = \fint_{B(x_0,r)} u(y) \, dy$。积分平均等于最大值，故球内 $u(y) = u(x_0)$ a.e.，由连续性得局部常数。

**题 8：** 若 $u$ 在 $B(0,2)$ 调和，估计 $|\nabla u(0)|$ 应由什么控制？

**答：** 由导数估计：$|\nabla u(0)| \le C_n \int_{B(0,1)} |u(y)| \, dy$ 或 $|\nabla u(0)| \le C_n \|u\|_{L^\infty(B(0,1))}$。

**题 9：** 若 $u$ 在 $B(0,R)$ 调和且 $|u| \le M$，证明 $|\nabla u(0)| \le C_n M / R$。

**答：** 由导数估计
$$|\nabla u(0)| \le \frac{C}{R^{n+1}} \int_{B(0,R)} |u| \le \frac{C}{R^{n+1}} M R^n = \frac{C M}{R}.$$

**题 10：** 若 $u$ 调和，且在连通区域 $\Omega$ 内部取最大值，证明 $u$ 为常数。

**答：** 由平均值公式推出局部常数，再由连通性推出全域常数。

**题 11：** 为什么 Harnack 不等式要求"非负"？

**答：** 非负条件让上下界互控：$\sup_K u \le C \inf_K u$。若允许变号，常数 $C$ 无法统一控制。

**题 12：** 为什么导数估计中会出现 $R^{-n-k}$？

**答：** $R^{-n}$ 来自球体积平均（除以 $|B_R| \sim R^n$）；$R^{-k}$ 来自 $k$ 阶求导的尺度。

### 2.2 基本解与 Green 函数

**题 1：** 求 $\Delta |x|^2$。

**答：** $2n$。

**题 2：** 求 $\Delta r^\alpha$，其中 $r = |x|$。

**答：** $\Delta r^\alpha = \alpha(\alpha + n - 2) r^{\alpha - 2}$，$r > 0$。

**题 3：** 找出 $\alpha$，使 $r^\alpha$ 在 $\mathbb{R}^n \setminus \{0\}$ 调和。

**答：** $\alpha(\alpha + n - 2) = 0$，故 $\alpha = 0$ 或 $\alpha = 2 - n$。

**题 4：** $n = 2$ 时为什么出现 $\log r$？

**答：** 径向 ODE 给出 $v' = C/r$，积分得 $v = C \log r + C_2$。

**题 5：** 推导径向 Laplace 公式。

**答：** 若 $u(x) = v(r)$，$u_{x_i} = v'(r) x_i / r$。继续求导并求和：
$$\Delta u = v''(r) + \frac{n-1}{r} v'(r).$$

**题 6：** 写出 $n \ge 3$ 时径向调和函数的一般形式。

**答：** $v'' + \frac{n-1}{r} v' = 0$。令 $w = v'$，得 $w' + \frac{n-1}{r} w = 0$，解 $w = C r^{1-n}$。积分：$v = C_1 r^{2-n} + C_2$。

**题 7：** 写出 Dirichlet Green 函数定义。

**答：**
$$\begin{cases} -\Delta_x G(x,y) = \delta_y, & x \in \Omega \\ G(x,y) = 0, & x \in \partial\Omega \end{cases}$$
且 $x \ne y$ 时 $G(\cdot, y)$ 调和。

**题 8：** Green 函数和 Green 公式有什么区别？

**答：** Green 公式是积分恒等式（散度定理的推论）；Green 函数是满足特定 PDE 与边界条件的核函数，用于表示解。

**题 9：** 为什么 $G = 0$ on $\partial\Omega$ 很重要？

**答：** 它使 Green 第二公式边界项中 $G \partial_n u$ 消失，从而只剩已知边界值 $g$。

**题 10：** 若 $f = 0$，Green 表示公式变成什么？

**答：** $u(x) = \int_{\partial\Omega} g(y) \partial_{n_y} G(x,y) \, dS_y$。

**题 11：** 若 $g = 0$，Green 表示公式变成什么？

**答：** $u(x) = \int_\Omega f(y) G(x,y) \, dy$。

**题 12：** 为什么推导 Green 公式时要固定 $x$，把 $y$ 当变量？

**答：** 因为 $G(x,y)$ 对 $y$ 满足 $-\Delta_y G(x,y) = \delta_x(y)$，Green 第二公式是在积分变量 $y$ 上使用的。

**题 13：** 球 $B_R$ 的 Poisson 核结构是什么？

**答：** $P_R(x,y) = \frac{R^2 - |x|^2}{n \alpha_n R |x - y|^n}$，$y \in \partial B_R$。

**题 14：** 若 $\Omega = B_R$，Poisson 核可以看成什么？

**答：** $\partial_{n_y} G(x,y)$ 的显式形式。

**题 15：** 写出 Green 函数的分解 $G = \Gamma - H$，并解释 $H$ 的作用。

**答：** $G(x,y) = \Gamma(x-y) - H(x,y)$，其中 $H$ 对 $x$ 调和，用于把边界值修正为 0。

**题 16：** Green 函数的对称性 $G(x,y) = G(y,x)$ 的物理意义是什么？

**答：** $y$ 点处单位源在 $x$ 处的影响 = $x$ 点处单位源在 $y$ 处的影响（互易性）。

### 2.3 极值原理与最大模估计

**题 1：** 若 $-\Delta u \le 0$，$u \le 0$ on $\partial\Omega$，证明 $u \le 0$。

**答：** 最大值在边界，故 $\max_{\bar\Omega} u \le 0$。

**题 2：** 若 $-\Delta u \ge 0$，$u \ge 0$ on $\partial\Omega$，证明 $u \ge 0$。

**答：** 对 $-u$ 用上一题。

**题 3：** 若 $u$ 调和且 $u \ge 0$ on $\partial\Omega$，证明 $u \ge 0$ in $\Omega$。

**答：** 最小值原理，或对 $-u$ 用最大值原理。

**题 4：** 若 $u, v$ 调和且 $u \le v$ on $\partial\Omega$，证明 $u \le v$ in $\Omega$。

**答：** 对 $w = u - v$ 用最大值原理。

**题 5：** 若 $u$ 在内部取得正最大值，且 $-\Delta u + c u < 0$，$c \ge 0$，证明矛盾。

**答：** 内部最大点 $x_0$ 处 $\nabla u(x_0) = 0$，$D^2 u(x_0) \le 0$，$\Delta u(x_0) \le 0$。若 $u(x_0) \ge 0$，则 $-\Delta u(x_0) + c(x_0) u(x_0) \ge 0$，与 $<0$ 矛盾。

**题 6：** 若 $u$ 在边界严格最大，Hopf 引理说明什么？

**答：** 在内球条件下，外法向导数 $\partial_n u(x_0) > 0$。

**题 7：** 为什么强极值原理需要连通性？

**答：** 若区域不连通，一个分支上常数最大，另一个分支可不同，不能推出全域常数。

**题 8：** 强极值原理中最大值点集为什么是闭集？

**答：** $O = \{x : u(x) = M\} = u^{-1}(\{M\})$，$\{M\}$ 闭，$u$ 连续，闭集原像为闭集。

**题 9：** 写出 Dirichlet 问题唯一性证明。

**答：** 设 $u, v$ 都是解，令 $w = u - v$。则 $-\Delta w = 0$，$w = 0$ on $\partial\Omega$。最大值原理给 $w \le 0$；对 $-w$ 用最大值原理得 $-w \le 0$，故 $w = 0$。

**题 10：** 写出最大模估计的障碍函数构造。

**答：** 令 $M = \|f\|_\infty$，$G = \|g\|_\infty$，$d = \operatorname{diam}\Omega$。取
$$\phi(x) = \frac{M}{2n}(d^2 - |x - x_0|^2).$$
则 $-\Delta \phi = M$。令 $w = u - \phi$，$-\Delta w = f - M \le 0$。最大值原理：$\max u \le G + M d^2 / (2n)$。对 $-u$ 同理，得 $\|u\|_\infty \le G + M d^2 / (2n)$。

**题 11：** 为什么要构造辅助函数 $w = u + \varepsilon \phi$？

**答：** 把非严格不等式 $Lu \le 0$ 变成严格不等式 $Lw < 0$，从而触发弱极值原理；最后令 $\varepsilon \to 0$ 回到 $u$。

**题 12：** Hopf 引理证明中，为什么用径向障碍函数 $V(x) = |x|^\alpha - R^\alpha$？

**答：** 关键性质：(1) $V = 0$ 在外边界；(2) $V < 0$ 在球壳内部；(3) $LV$ 符号可由 $\alpha$ 控制；(4) $\nabla V$ 在边界与法向一致，法向导数 $\partial_n V = \psi'(R)$ 可显式计算。

### 2.4 Neumann 相容条件

**题 1：** 写出 Neumann 问题相容条件。

**答：** $\int_\Omega f \, dx + \int_{\partial\Omega} g \, dS = 0$。

**题 2：** 证明 Neumann 相容条件。

**答：** 对 $-\Delta u = f$ 在 $\Omega$ 积分：$-\int_\Omega \Delta u \, dx = \int_\Omega f \, dx$。散度定理：$-\int_\Omega \Delta u \, dx = -\int_{\partial\Omega} \partial_n u \, dS$。代入 $\partial_n u = g$：$-\int_{\partial\Omega} g \, dS = \int_\Omega f \, dx$，即 $\int_\Omega f + \int_{\partial\Omega} g = 0$。

**题 3：** 若 $\partial_n u = 0$，相容条件变成什么？

**答：** $\int_\Omega f \, dx = 0$。

**题 4：** 若 $-\Delta u = 1$，$\partial_n u = 0$，在有界区域上是否有解？

**答：** 通常无解，因为 $\int_\Omega 1 \, dx = |\Omega| \ne 0$。

**题 5：** Neumann 问题解是否唯一？

**答：** 不唯一，差一个常数。若 $u_1, u_2$ 都是解，则 $u_1 - u_2$ 调和且 $\partial_n(u_1 - u_2) = 0$，由能量法可证 $u_1 - u_2 \equiv \text{const}$。

### 2.5 能量估计

**题 1：** 设 $u = 0$ on $\partial\Omega$，$-\Delta u = f$，证明能量恒等式。

**答：** 两边乘 $u$ 积分：$\int_\Omega (-\Delta u) u \, dx = \int_\Omega f u \, dx$。分部且 $u|_{\partial\Omega} = 0$：$\int_\Omega |\nabla u|^2 \, dx = \int_\Omega f u \, dx$。

**题 2：** 承上题，给出 $\|\nabla u\|_{L^2}$ 的估计。

**答：** 由 Cauchy-Schwarz 与 Young 不等式：
$$\int_\Omega f u \, dx \le \frac{1}{2} \int_\Omega f^2 \, dx + \frac{1}{2} \int_\Omega u^2 \, dx.$$
再用 Poincaré 不等式 $\int u^2 \le C \int |\nabla u|^2$，吸收到左边：
$$\|\nabla u\|_{L^2}^2 \le C \|f\|_{L^2}^2.$$

**题 3：** 做局部估计时取什么测试函数？

**答：** $\varphi = \eta^2 u$，其中 $\eta$ 为截断函数。会出现 $\nabla \eta$ 项（Caccioppoli 型估计）。

**题 4：** 做非负性证明时取什么测试函数？

**答：** $\varphi = u^- = \max\{-u, 0\}$。

**题 5：** 做一侧估计时取什么测试函数？

**答：** $\varphi = u^+ = \max\{u, 0\}$。

**题 6：** 写出 Friedrichs 不等式与 Poincaré 不等式。

**答：**
- Friedrichs：若 $u|_{\partial\Omega} = 0$，$\int_\Omega |u|^2 \le C \int_\Omega |\nabla u|^2$。
- Poincaré：$\int_\Omega |u - u_\Omega|^2 \le C \int_\Omega |\nabla u|^2$，$u_\Omega = \fint_\Omega u$。

**题 7：** 能量法如何证明 Neumann 问题解的唯一性（差一个常数）？

**答：** 设 $u_1, u_2$ 都是解，令 $w = u_1 - u_2$。则 $-\Delta w = 0$，$\partial_n w = 0$。两边乘 $w$ 积分，Green 第一公式：$\int |\nabla w|^2 = \int_{\partial\Omega} w \partial_n w = 0$。故 $\nabla w = 0$，$w$ 为常数。

**题 8：** 稳定性证明中如何对两个解作差？

**答：** 设 $u_1, u_2$ 分别对应 $(f_1, g_1), (f_2, g_2)$。令 $w = u_1 - u_2$，则 $-\Delta w = f_1 - f_2$，$w = g_1 - g_2$ on $\partial\Omega$。对 $w$ 做能量估计，得到 $\|w\|$ 由 $\|f_1 - f_2\|$ 与 $\|g_1 - g_2\|$ 控制。

---

## Ch3 热方程

### 3.1 基本解与初值问题

**题 1：** 写出热方程的基本解。

**答：** $\Phi(x,t) = \frac{1}{(4\pi t)^{n/2}} e^{-|x|^2/(4t)}$，$t > 0$。

**题 2：** 写出热方程初值问题的解公式。

**答：** $u(x,t) = \int_{\mathbb{R}^n} \Phi(x-y, t) g(y) \, dy$，$g$ 为初值。

**题 3：** 热方程的基本解为什么 $t \to 0^+$ 时趋向 $\delta$？

**答：** 它在 $t \to 0^+$ 时集中在 $x = 0$ 处，积分恒为 1，故分布意义下趋近 Dirac。

### 3.2 极值原理与最大模估计

**题 4：** 写出热方程的极值原理。

**答：** 若 $u_t - \Delta u = 0$ 在 $\Omega_T = \Omega \times (0, T]$，则 $\max_{\overline{\Omega_T}} u = \max_{\Gamma} u$，其中 $\Gamma$ 为抛物边界（底边 + 侧边）。

**题 5：** 热方程极值原理与调和函数极值原理的区别？

**答：** 热方程最大值在抛物边界取得，包含初始时刻 $t = 0$ 和侧边 $\partial\Omega \times [0,T]$；调和函数只在空间边界 $\partial\Omega$ 取得。

### 3.3 能量估计

**题 6：** 写出热方程的能量恒等式。

**答：** 两边乘 $u$ 积分，分部：
$$\frac{1}{2} \frac{d}{dt} \int_\Omega u^2 \, dx + \int_\Omega |\nabla u|^2 \, dx = \int_\Omega f u \, dx.$$

**题 7：** 由能量恒等式得到什么估计？

**答：** 对时间积分并用 Young 不等式：
$$\sup_{0 \le t \le T} \int_\Omega u^2 + \int_0^T \int_\Omega |\nabla u|^2 \le C \left( \int_\Omega g^2 + \int_0^T \int_\Omega f^2 \right).$$

---

## Ch4 波动方程

### 4.1 一维波动方程

**题 1：** 写出一维波动方程的 d'Alembert 公式。

**答：** $u(x,t) = \frac{1}{2}[g(x+t) + g(x-t)] + \frac{1}{2} \int_{x-t}^{x+t} h(y) \, dy$，$g$ 为初位移，$h$ 为初速度。

**题 2：** 一维波速是什么？

**答：** $c = 1$（标准形式 $u_{tt} - u_{xx} = 0$）。

### 4.2 高维波动方程

**题 3：** 三维波动方程的 Kirchhoff 公式是什么？

**答：** 
$$u(x,t) = \frac{\partial}{\partial t} \left[ \frac{1}{4\pi t} \int_{\partial B(x,t)} g(y) \, dS_y \right] + \frac{1}{4\pi t} \int_{\partial B(x,t)} h(y) \, dS_y.$$

**题 4：** Huygens 原理在几维成立？

**答：** 严格 Huygens 原理（信号无尾波）在奇数维 $n \ge 3$ 成立；偶数维不成立（有尾波）。

**题 5：** 波动方程是否有极值原理？

**答：** 没有。波动方程解可以振荡，最大值不在边界取得。

**题 6：** 波动方程的能量是什么？

**答：** $E(t) = \frac{1}{2} \int_\Omega (u_t^2 + |\nabla u|^2) \, dx$。无外力时 $E(t)$ 守恒。

---

## 综合题

**题 1：** 设 $u$ 在 $B(0,1)$ 调和，$u(0) = 1$，$|u| \le 2$。给出 $|\nabla u(0)|$ 的估计。

**答：** 由导数估计：$|\nabla u(0)| \le C_n \|u\|_{L^\infty(B(0,1/2))} \le 2 C_n$。

**题 2：** 设 $-\Delta u = f$ in $B_R$，$u = 0$ on $\partial B_R$。若 $\|f\|_{L^2} \le \varepsilon$，给出 $\|u\|_{L^\infty}$ 估计。

**答：** 由能量估计 $\|\nabla u\|_{L^2} \le C \|f\|_{L^2} \le C \varepsilon$。再由 Sobolev 嵌入 $H^2 \hookrightarrow C^0$（$n \le 3$）：$\|u\|_{L^\infty} \le C \varepsilon$。

**题 3：** 为什么说调和函数"刚性"很强？

**答：** 由平均值性质、Harnack 不等式、最大值原理、导数估计，调和函数被其边界值与平均值完全锁死，不能剧烈振荡。

**题 4：** 老师讲法的"四类 PDE 方法"是什么？

**答：** (1) 平均值方法；(2) 积分表示方法（基本解/Green/Poisson 核）；(3) 比较/极值方法；(4) 能量方法。

**题 5：** 写出 PDE 适定性与 Ch2 工具的对应。

**答：**
- 存在性 ← Green 函数、Poisson 核
- 唯一性 ← 极值原理、能量法
- 稳定性 ← 最大模估计、比较原理
- 正则性 ← 平均值性质、导数估计、能量估计
