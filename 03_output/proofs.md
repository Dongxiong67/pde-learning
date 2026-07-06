# 典型证明

PDE 期中高频证明题的完整推导。每个证明都按"思路 → 详细步骤 → 关键技巧"组织。

---

## 证明 1：平均值性质（球面版）

**定理**：若 $u \in C^2(\Omega)$ 调和，则对任意 $B(x, r) \subset\subset \Omega$：

$$u(x) = \fint_{\partial B(x,r)} u \, dS = \frac{1}{|\partial B(x,r)|} \int_{\partial B(x,r)} u \, dS.$$

### 思路

老师讲法的关键技巧：通过变量替换把变动半径 $r$ 变成单位球面，让 $r$ 进入被积函数，然后对 $r$ 求导，用 $\Delta u = 0$ 证明导数为 0，最后令 $r \to 0$。

### 详细步骤

**第 1 步：变量替换到单位球面。**

定义
$$\phi(r) = \frac{1}{|\partial B(x,r)|} \int_{\partial B(x,r)} u(y) \, dS_y.$$

通过变量替换 $y = x + rz$，$|z| = 1$：

$$\phi(r) = \frac{1}{|\partial B_1|} \int_{\partial B_1} u(x + rz) \, dS_z.$$

**第 2 步：对 $r$ 求导。**

$$\phi'(r) = \frac{1}{|\partial B_1|} \int_{\partial B_1} \nabla u(x + rz) \cdot z \, dS_z.$$

注意到 $z = (y - x)/r$，$dS_y = r^{n-1} dS_z$，回到原变量：

$$\phi'(r) = \frac{1}{|\partial B(x,r)|} \int_{\partial B(x,r)} \partial_n u \, dS_y.$$

**第 3 步：用散度定理与 $\Delta u = 0$。**

由散度定理：
$$\int_{\partial B(x,r)} \partial_n u \, dS_y = \int_{B(x,r)} \Delta u \, dy = 0.$$

故 $\phi'(r) = 0$，即 $\phi(r)$ 为常数。

**第 4 步：令 $r \to 0$。**

由 $u$ 连续性，$\phi(r) \to u(x)$ 当 $r \to 0$。故 $\phi(r) = u(x)$。

### 关键技巧

1. 把变动区域 $B(x,r)$ 通过缩放变成单位球，让 $r$ 进入被积函数
2. 对 $r$ 求导后散度定理把球面积分转成体积分
3. 调和方程 $\Delta u = 0$ 让积分消失

---

## 证明 2：强最大值原理

**定理**：设 $u \in C^2(\Omega) \cap C(\overline{\Omega})$ 调和，$\Omega$ 连通。若 $u$ 在 $\Omega$ 内部达到最大值，则 $u$ 为常数。

### 思路

由平均值公式，内点最大值意味着局部常数；由连通性，局部常数推到全域常数。证明的关键是用开闭集论证。

### 详细步骤

**第 1 步：平均值公式给出局部常数。**

设 $u$ 在 $x_0 \in \Omega$ 取得最大值 $M = u(x_0)$。对小球 $B(x_0, r) \subset\subset \Omega$：

$$M = u(x_0) = \fint_{B(x_0,r)} u(y) \, dy.$$

由于 $u(y) \le M$，平均值等于最大值只能说明 $u(y) = M$ 几乎处处在 $B(x_0,r)$。由连续性，$u \equiv M$ 在 $B(x_0,r)$。

**第 2 步：构造最大值点集。**

令 $O = \{x \in \Omega : u(x) = M\}$。我们要证明 $O$ 既开又闭。

**第 3 步：$O$ 是闭集。**

$O = u^{-1}(\{M\})$，$\{M\}$ 是闭集，$u$ 连续，故 $O$ 闭。

**第 4 步：$O$ 是开集。**

若 $x_1 \in O$，则 $u(x_1) = M$。由第 1 步，存在小球 $B(x_1, r)$ 使 $u \equiv M$，故 $B(x_1, r) \subset O$。所以 $O$ 开。

**第 5 步：连通性给出全域常数。**

$\Omega$ 连通，$O$ 既开又闭且非空，故 $O = \Omega$，即 $u \equiv M$。

### 关键技巧

1. "区域连通"不是装饰条件——它从局部常数推进到全域常数
2. $O$ 是闭集靠连续性，$O$ 是开集靠平均值公式
3. 这是从平均值到极值原理的核心桥梁

---

## 证明 3：Hopf 引理（球域版本）

**定理**：设 $u \in C^2(B_R) \cap C(\overline{B_R})$，$-\Delta u + c(x) u < 0$ in $B_R$，$c \ge 0$。若 $u$ 在 $x_0 \in \partial B_R$ 取得最大值，且该最大值严格大于内点值，则 $\partial_n u(x_0) > 0$（外法向）。

### 思路

构造径向障碍函数 $V$，令 $W = u - u(x_0) + \varepsilon V$，用最大值原理逼出 $W$ 在 $x_0$ 处的方向导数符号。

### 详细步骤

**第 1 步：构造径向障碍函数。**

取
$$V(x) = |x|^\alpha - R^\alpha, \qquad \alpha > 0 \text{ 待定}.$$

性质：
- $V = 0$ 在 $\partial B_R$；
- $V < 0$ 在 $B_R \setminus \{0\}$；
- $\nabla V(x) = \alpha |x|^{\alpha - 2} x$，外法向 $n = x/R$，故 $\partial_n V|_{\partial B_R} = \alpha R^{\alpha - 1} > 0$。

**第 2 步：选 $\alpha$ 使 $LV < 0$。**

计算
$$-\Delta V = -\alpha(\alpha + n - 2) |x|^{\alpha - 2}.$$

取 $\alpha$ 足够大且 $\alpha + n - 2 > 0$（保证 $-\Delta V < 0$ 在 $B_R \setminus B_\rho$，其中 $B_\rho$ 是挖掉的小球）。

**第 3 步：构造 $W$。**

令 $W = u - u(x_0) + \varepsilon V$。在球壳 $B_R \setminus \overline{B_\rho}$ 上：
$$LW = Lu + \varepsilon LV < 0$$
（选 $\varepsilon$ 充分小，由 $LV$ 在紧集上严格负保证）。

**第 4 步：分析 $W$ 的最大值位置。**

- 在 $\partial B_\rho$ 上：$V$ 有界下界，$u < u(x_0)$（严格），故 $W < 0$（选 $\rho$ 足够小）。
- 在 $\partial B_R$ 上：$V = 0$，$W = u - u(x_0) \le 0$，且 $W(x_0) = 0$。

故 $W$ 在球壳上最大值在 $x_0$ 取得。

**第 5 步：方向导数。**

$W$ 在 $x_0$ 处沿外法向取得最大值，故 $\partial_n W(x_0) \ge 0$。但
$$\partial_n W(x_0) = \partial_n u(x_0) + \varepsilon \partial_n V(x_0) = \partial_n u(x_0) + \varepsilon \alpha R^{\alpha - 1}.$$

所以 $\partial_n u(x_0) \ge -\varepsilon \alpha R^{\alpha - 1}$。再令 $\varepsilon \to 0$，得 $\partial_n u(x_0) \ge 0$。

严格性需要额外论证（用 $u$ 在 $x_0$ 附近的严格小于性），最终得 $\partial_n u(x_0) > 0$。

### 关键技巧

1. 径向障碍函数 $V = |x|^\alpha - R^\alpha$：在外边界为 0，球壳内为负，法向导数可显式计算
2. 球壳区域避免原点处 $V$ 的奇异性
3. 选 $\alpha$ 让 $LV$ 符号可控
4. $W = u - u(x_0) + \varepsilon V$ 把"边界最大"翻译成"法向导数符号"

---

## 证明 4：Green 函数表示公式

**定理**：若 $u \in C^2(\Omega) \cap C(\overline{\Omega})$ 解 Dirichlet 问题
$$\begin{cases} -\Delta u = f & \text{in } \Omega \\ u = g & \text{on } \partial\Omega \end{cases}$$
则
$$u(x) = \int_{\partial\Omega} g(y) \partial_{n_y} G(x,y) \, dS_y + \int_\Omega f(y) G(x,y) \, dy.$$

### 思路

固定 $x$，把 $y$ 当变量，取 $v(y) = G(x, y)$，用 Green 第二公式。$G = 0$ on $\partial\Omega$ 让一个边界项消失，$-\Delta G = \delta$ 让体积分产生 $u(x)$。

### 详细步骤

**第 1 步：固定 $x$，取 $v(y) = G(x, y)$。**

注意 $-\Delta_y G(x, y) = \delta_x(y)$，即作为 $y$ 的函数，$G$ 在 $y = x$ 处有奇性。

**第 2 步：挖奇点。**

令 $\Omega_\varepsilon = \Omega \setminus \overline{B(x, \varepsilon)}$。在 $\Omega_\varepsilon$ 上 $G$ 调和（关于 $y$），可用 Green 第二公式：
$$\int_{\Omega_\varepsilon} (u \Delta_y G - G \Delta u) \, dy = \int_{\partial\Omega_\varepsilon} (u \partial_{n_y} G - G \partial_{n_y} u) \, dS_y.$$

**第 3 步：边界 $\partial\Omega$ 上的项。**

在 $\partial\Omega$ 上 $G = 0$，$u = g$，故贡献：
$$\int_{\partial\Omega} g(y) \partial_{n_y} G(x, y) \, dS_y.$$

**第 4 步：内边界 $\partial B(x, \varepsilon)$ 上的项。**

内边界的法向指向 $x$（即 $n_y = -(y-x)/\varepsilon$）。在 $\partial B(x, \varepsilon)$ 上 $G(x, y) \sim \Gamma(y - x) \sim c_n \varepsilon^{2-n}$（$n \ge 3$），故
$$\int_{\partial B(x, \varepsilon)} G \partial_{n_y} u \, dS_y \to 0 \quad (\varepsilon \to 0).$$

而
$$\int_{\partial B(x, \varepsilon)} u \partial_{n_y} G \, dS_y \to -u(x),$$
（因 $G$ 在 $y = x$ 处是 Dirac 源，归一化系数正好让边界积分趋于 $-u(x)$，负号来自法向反向）。

**第 5 步：体积项。**

在 $\Omega_\varepsilon$ 上 $\Delta_y G = 0$（已挖奇点），$-\Delta u = f$，故
$$\int_{\Omega_\varepsilon} (u \Delta_y G - G \Delta u) \, dy = \int_{\Omega_\varepsilon} G f \, dy \to \int_\Omega f(y) G(x, y) \, dy.$$

**第 6 步：合并。**

整理得
$$-u(x) = -\int_{\partial\Omega} g \partial_{n_y} G \, dS_y - \int_\Omega f G \, dy,$$
即
$$u(x) = \int_{\partial\Omega} g(y) \partial_{n_y} G(x,y) \, dS_y + \int_\Omega f(y) G(x,y) \, dy.$$

### 关键技巧

1. 固定 $x$ 把 $y$ 当变量，因为 $G$ 对 $y$ 满足 $-\Delta_y G = \delta_x$
2. 挖小球 $B(x, \varepsilon)$ 处理 $G$ 在 $y = x$ 处的奇性
3. $G = 0$ on $\partial\Omega$ 让 $G \partial_n u$ 边界项消失
4. 归一化系数让小球边界积分给出 $-u(x)$

### 退化情形

- $f = 0$：$u(x) = \int_{\partial\Omega} g \partial_{n_y} G \, dS_y$（纯边界表示）
- $g = 0$：$u(x) = \int_\Omega f G \, dy$（纯源项表示）

---

## 证明 5：最大模估计（障碍函数法）

**定理**：若 $-\Delta u = f$ in $\Omega$，$u = g$ on $\partial\Omega$，则存在 $C = C(n, \operatorname{diam}\Omega)$：
$$\|u\|_{L^\infty(\Omega)} \le C \left( \|g\|_{L^\infty(\partial\Omega)} + \|f\|_{L^\infty(\Omega)} \right).$$

### 思路

构造二次障碍函数 $\phi(x) = A(d^2 - |x - x_0|^2)$，让 $-\Delta \phi \ge \|f\|_\infty$，再对 $u - \phi$ 和 $-u - \phi$ 分别用最大值原理。

### 详细步骤

**第 1 步：记号与构造。**

令 $M = \|f\|_{L^\infty(\Omega)}$，$G = \|g\|_{L^\infty(\partial\Omega)}$，$d = \operatorname{diam}\Omega$。任取 $x_0 \in \overline\Omega$，构造
$$\phi(x) = \frac{M}{2n}(d^2 - |x - x_0|^2).$$

**第 2 步：验证 $-\Delta \phi = M$。**

因 $\Delta |x - x_0|^2 = 2n$，故
$$-\Delta \phi = -\frac{M}{2n} \cdot (-2n) = M.$$

**第 3 步：对 $w = u - \phi$ 用最大值原理。**

$$-\Delta w = -\Delta u + \Delta \phi = f - M \le 0.$$

由弱最大值原理：
$$\max_{\overline\Omega} w = \max_{\partial\Omega} w.$$

在 $\partial\Omega$ 上，$u = g$，$|x - x_0| \le d$，故 $\phi \ge 0$ 且 $\phi \le M d^2 / (2n)$。所以
$$w|_{\partial\Omega} = g - \phi \le G.$$

故 $\max_{\overline\Omega} w \le G$，即
$$u \le \phi + G \le \frac{M d^2}{2n} + G.$$

**第 4 步：对 $-u - \phi$ 同理。**

由 $-\Delta(-u) = f$，对 $-u$ 重复上一步：
$$-u \le \frac{M d^2}{2n} + G.$$

**第 5 步：合并。**

$$|u| \le \frac{M d^2}{2n} + G \le C(n, d)(M + G).$$

### 关键技巧

1. 二次函数 $|x - x_0|^2$ 的 Laplace 是常数 $2n$，便于精确控制 $-\Delta \phi$
2. 直径 $d = \operatorname{diam}\Omega$ 出现在最终常数里——这是为什么估计依赖区域大小
3. 对 $u - \phi$ 和 $-u - \phi$ 各做一次，得到绝对值估计

---

## 证明 6：能量估计

**定理**：若 $-\Delta u = f$ in $\Omega$，$u = 0$ on $\partial\Omega$，则
$$\int_\Omega |\nabla u|^2 \, dx \le C \int_\Omega f^2 \, dx.$$

### 思路

方程两边乘 $u$ 积分，分部让边界项消失（因为 $u = 0$ on $\partial\Omega$），得到 $\int |\nabla u|^2 = \int f u$，再用 Cauchy-Schwarz + Young + Poincaré 吸收 $u$ 项。

### 详细步骤

**第 1 步：乘 $u$ 积分。**

$$\int_\Omega (-\Delta u) u \, dx = \int_\Omega f u \, dx.$$

**第 2 步：分部积分。**

由 Green 第一公式：
$$\int_\Omega (-\Delta u) u \, dx = \int_\Omega |\nabla u|^2 \, dx - \int_{\partial\Omega} u \partial_n u \, dS.$$

边界项为 0（$u|_{\partial\Omega} = 0$），故
$$\int_\Omega |\nabla u|^2 \, dx = \int_\Omega f u \, dx.$$

**第 3 步：Cauchy-Schwarz。**

$$\int_\Omega f u \, dx \le \left(\int_\Omega f^2 \, dx\right)^{1/2} \left(\int_\Omega u^2 \, dx\right)^{1/2}.$$

**第 4 步：Young 不等式。**

$$ab \le \frac{a^2}{2} + \frac{b^2}{2},$$
故
$$\int_\Omega f u \, dx \le \frac{1}{2} \int_\Omega f^2 \, dx + \frac{1}{2} \int_\Omega u^2 \, dx.$$

**第 5 步：Poincaré/Friedrichs 不等式。**

由 $u|_{\partial\Omega} = 0$，Friedrichs 不等式给出
$$\int_\Omega u^2 \, dx \le C_P \int_\Omega |\nabla u|^2 \, dx.$$

**第 6 步：吸收。**

代入第 4 步：
$$\int_\Omega |\nabla u|^2 \le \frac{1}{2} \int f^2 + \frac{C_P}{2} \int |\nabla u|^2.$$

若 $C_P < 2$，直接吸收；一般地，把 $\frac{C_P}{2} \int |\nabla u|^2$ 移到左边：
$$\left(1 - \frac{C_P}{2}\right) \int |\nabla u|^2 \le \frac{1}{2} \int f^2.$$

更标准的写法是先吸收再整理：
$$\int |\nabla u|^2 \le C \int f^2.$$

### 关键技巧

1. 测试函数取 $u$：最简单也最常用，边界项消失
2. Green 第一公式把 $-\Delta u$ 转成 $|\nabla u|^2$
3. Young 不等式 "$ab \le a^2/2 + b^2/2$" 是吸收技巧的核心
4. Poincaré/Friedrichs 把 $u$ 的 $L^2$ 范数转成 $\nabla u$ 的 $L^2$ 范数

### 测试函数选择表

| 测试函数 | 用途 |
|---|---|
| $u$ | 基础全局能量估计 |
| $u^+ = \max(u, 0)$ | 一侧估计 |
| $\eta^2 u$（$\eta$ 截断） | 局部能量（Caccioppoli 型） |
| $(u - k)^+$ | 水平集估计 |
| $u^- = \max(-u, 0)$ | 非负性证明 |

---

## 证明 7：Dirichlet 问题唯一性

**定理**：Dirichlet 问题 $-\Delta u = f$ in $\Omega$，$u = g$ on $\partial\Omega$ 至多有一个 $C^2(\Omega) \cap C(\overline\Omega)$ 解。

### 详细步骤

设 $u, v$ 都是解，令 $w = u - v$。则
$$-\Delta w = 0 \text{ in } \Omega, \qquad w = 0 \text{ on } \partial\Omega.$$

由弱最大值原理：$\max_{\overline\Omega} w \le \max_{\partial\Omega} w = 0$，故 $w \le 0$。

对 $-w$ 同理（注意 $-w$ 也满足 $-\Delta(-w) = 0$，$-w = 0$ on $\partial\Omega$）：$\max_{\overline\Omega}(-w) \le 0$，即 $w \ge 0$。

故 $w \equiv 0$，即 $u \equiv v$。

### 关键技巧

- "两个解作差"是线性 PDE 唯一性证明的标准套路
- 对 $w$ 和 $-w$ 各用一次最大值原理，夹出 $w = 0$

---

## 证明 8：Neumann 相容条件

**定理**：若 $-\Delta u = f$ in $\Omega$，$\partial_n u = g$ on $\partial\Omega$ 有解，则
$$\int_\Omega f \, dx + \int_{\partial\Omega} g \, dS = 0.$$

### 详细步骤

**第 1 步**：对方程在 $\Omega$ 上积分
$$\int_\Omega (-\Delta u) \, dx = \int_\Omega f \, dx.$$

**第 2 步**：用散度定理
$$\int_\Omega (-\Delta u) \, dx = -\int_\Omega \operatorname{div}(\nabla u) \, dx = -\int_{\partial\Omega} \partial_n u \, dS.$$

**第 3 步**：代入边界条件
$$-\int_{\partial\Omega} g \, dS = \int_\Omega f \, dx.$$

**第 4 步**：移项
$$\int_\Omega f \, dx + \int_{\partial\Omega} g \, dS = 0.$$

### 关键技巧

- 散度定理把 $\int_\Omega \Delta u$ 转成 $\int_{\partial\Omega} \partial_n u$
- 符号方向：$-\Delta$ 对应 $-\partial_n$，别写反
- 这是必要条件；在适当函数空间中也是充分条件

---

## 证明 9：Neumann 问题解的唯一性（差一个常数）

**定理**：若 $u_1, u_2$ 都是 Neumann 问题的解，则 $u_1 - u_2 \equiv \text{常数}$。

### 详细步骤

令 $w = u_1 - u_2$，则
$$-\Delta w = 0 \text{ in } \Omega, \qquad \partial_n w = 0 \text{ on } \partial\Omega.$$

**第 1 步：乘 $w$ 积分。**
$$\int_\Omega (-\Delta w) w \, dx = 0.$$

**第 2 步：分部。**
$$\int_\Omega |\nabla w|^2 \, dx - \int_{\partial\Omega} w \partial_n w \, dS = 0.$$

**第 3 步：边界项消失。**
由 $\partial_n w = 0$ on $\partial\Omega$：
$$\int_\Omega |\nabla w|^2 \, dx = 0.$$

故 $\nabla w \equiv 0$，$w$ 为常数。

### 关键技巧

- Neumann 边界条件下，能量法只能给出"差一个常数"
- 这与最大值原理不同——后者对 Dirichlet 给出严格唯一性
