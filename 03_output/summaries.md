# 章节总结

每章一页纸的核心总结，便于考前快速回顾。

---

## Ch1 引言 一页纸

### 核心概念

| 概念 | 内容 |
|---|---|
| PDE 阶数 | 最高阶偏导数阶数 |
| 算子 | $\nabla u$, $\operatorname{div} F$, $\Delta u$, $\operatorname{curl} F$ |
| 调和函数 | $\Delta u = 0$ |
| 适定性 | 存在性 + 唯一性 + 稳定性 |

### 必背恒等式

- $\nabla \times (\nabla \varphi) = 0$
- $\nabla \cdot (\nabla \times F) = 0$
- 散度定理：$\int_\Omega \operatorname{div} F = \int_{\partial\Omega} F \cdot n$
- Green 第一公式：$\int_\Omega \nabla u \cdot \nabla v = -\int_\Omega v \Delta u + \int_{\partial\Omega} v \partial_n u$
- Green 第二公式：$\int_\Omega (u \Delta v - v \Delta u) = \int_{\partial\Omega}(u \partial_n v - v \partial_n u)$

### 模型方程识别

| 方程 | 阶数 | 类型 |
|---|---|---|
| $u_t - \Delta(u^\gamma) = 0$ | 2 | 退化抛物（多孔介质） |
| $u_t + u u_x + u_{xxx} = 0$ | 3 | 色散（KdV） |
| $-\Delta u = f$ | 2 | 椭圆（Poisson） |
| $\Delta u = 0$ | 2 | 椭圆（Laplace） |
| $u_t - \Delta u = 0$ | 2 | 抛物（热方程） |
| $u_{tt} - \Delta u = 0$ | 2 | 双曲（波动） |

### 球面计算

- 外法向：$n = x / R$
- 径向函数法向导数：$\partial_n \psi(|x|)|_{|x|=R} = \psi'(R)$
- 例：$u = e^{-3|x|} \Rightarrow \partial_n u|_{\partial B_R} = -3 e^{-3R}$

---

## Ch2 位势方程 一页纸

> **期中重中之重**。三条主线：平均值体系、Green 函数体系、最大值原理体系、能量法体系。

### 2.1 调和函数

**平均值性质**：
$$u(x) = \fint_{\partial B(x,r)} u \, dS = \fint_{B(x,r)} u \, dy$$

**导数估计**：
$$|D^\alpha u(x)| \le \frac{C_{n,k}}{R^{n+k}} \int_{B(x,R)} |u|, \quad |\alpha| = k$$

**Harnack**：$\sup_K u \le C \inf_K u$（$u \ge 0$ 调和，$K \Subset \Omega$）

### 2.2 基本解与 Green 函数

**基本解**：
- $n \ge 3$：$\Gamma(x) = \frac{1}{n(n-2)\alpha_n} |x|^{2-n}$
- $n = 2$：$\Gamma(x) = -\frac{1}{2\pi} \ln |x|$
- 满足 $-\Delta \Gamma = \delta_0$（分布意义）

**Green 函数**：$-\Delta_x G = \delta_y$，$G = 0$ on $\partial\Omega$，$G(x,y) = G(y,x)$

**表示公式**：
$$u(x) = \int_{\partial\Omega} g \partial_{n_y} G \, dS_y + \int_\Omega f G \, dy$$

**Poisson 核（球）**：$P_R(x,y) = \frac{R^2 - |x|^2}{n \alpha_n R |x - y|^n}$

### 2.3 极值原理

**弱最大值原理**：$Lu \le 0 \Rightarrow \max_{\overline\Omega} u = \max_{\partial\Omega} u$

**强最大值原理**：内部取最大 $\Rightarrow u$ 常数（需 $\Omega$ 连通）

**Hopf 引理**：边界严格最大 $\Rightarrow \partial_n u(x_0) > 0$（需内球条件）

**比较原理**：$Lu \le Lv$ in $\Omega$，$u \le v$ on $\partial\Omega \Rightarrow u \le v$ in $\Omega$

### 2.4 最大模估计

$$\|u\|_\infty \le C(n, \operatorname{diam}\Omega)(\|g\|_\infty + \|f\|_\infty)$$

**障碍函数**：$\phi(x) = \frac{M}{2n}(d^2 - |x - x_0|^2)$，$-\Delta \phi = M$

### 2.5 Neumann 相容条件

$$\int_\Omega f + \int_{\partial\Omega} g = 0$$

（必要条件，解不唯一，差常数）

### 2.6 能量估计

$$\int_\Omega |\nabla u|^2 \le C \int_\Omega f^2$$（$u = 0$ on $\partial\Omega$）

**工具链**：乘 $u$ → 分部 → Cauchy-Schwarz → Young → Poincaré

### 适定性对应

| 问题 | 工具 |
|---|---|
| 存在性 | Green 函数、Poisson 核 |
| 唯一性 | 极值原理、能量法 |
| 稳定性 | 最大模估计、比较原理 |
| 正则性 | 平均值、导数估计、能量 |

### 五个证明模板

1. Neumann 相容条件（散度定理）
2. Dirichlet 唯一性（两解作差 + 最大值原理）
3. Green 表示公式（Green 第二公式 + $G = 0$ + $\delta$）
4. 最大模估计（二次障碍函数）
5. 能量估计（乘测试函数 + Young + Poincaré）

---

## Ch3 热方程 一页纸

### 基本解

$$\Phi(x, t) = \frac{1}{(4\pi t)^{n/2}} e^{-|x|^2/(4t)}, \quad t > 0$$

### 初值问题解

$$u(x, t) = \int_{\mathbb{R}^n} \Phi(x - y, t) g(y) \, dy$$

### 极值原理

最大值在抛物边界 $\Gamma = (\overline\Omega \times \{0\}) \cup (\partial\Omega \times [0, T])$ 取得。

### 能量恒等式

$$\frac{1}{2} \frac{d}{dt} \int_\Omega u^2 + \int_\Omega |\nabla u|^2 = \int_\Omega f u$$

### 能量估计

$$\sup_{0 \le t \le T} \int u^2 + \int_0^T \int |\nabla u|^2 \le C\left(\int g^2 + \int_0^T \int f^2\right)$$

### 与 Ch2 对比

| 项目 | 调和方程 | 热方程 |
|---|---|---|
| 极值原理边界 | 空间边界 $\partial\Omega$ | 抛物边界 $\Gamma$ |
| 基本解奇点 | $|x|^{2-n}$（空间） | $t^{-n/2} e^{-|x|^2/(4t)}$（时空） |
| 正则性 | $C^\infty$ 自动 | $C^\infty$ 自动（$t > 0$） |
| 能量 | 静态 $\int |\nabla u|^2$ | 动态 $\int u^2 + \int |\nabla u|^2$ |

---

## Ch4 波动方程 一页纸

### 一维 d'Alembert 公式

$$u(x, t) = \frac{1}{2}[g(x+t) + g(x-t)] + \frac{1}{2} \int_{x-t}^{x+t} h(y) \, dy$$

### 三维 Kirchhoff 公式

$$u(x, t) = \frac{\partial}{\partial t}\left[\frac{1}{4\pi t} \int_{\partial B(x,t)} g \, dS_y\right] + \frac{1}{4\pi t} \int_{\partial B(x,t)} h \, dS_y$$

### 二维降维法

由三维 Kirchhoff 通过"降维法"得到二维解公式（积分在球面投影到圆盘上）。

### Huygens 原理

- 严格 Huygens（无尾波）：奇数维 $n \ge 3$ 成立
- 非严格 Huygens（有尾波）：偶数维成立

### 能量守恒

$$E(t) = \frac{1}{2} \int_\Omega (u_t^2 + |\nabla u|^2) \, dx, \qquad \frac{dE}{dt} = 0$$（无外力）

### 与 Ch2/Ch3 对比

| 方程 | 极值原理 | 能量守恒 | Huygens |
|---|---|---|---|
| 调和 | 有 | — | — |
| 热方程 | 有（抛物边界） | 衰减 | — |
| 波动 | 无 | 守恒 | 奇维严格 |

### 适定性

- 存在性：显式公式
- 唯一性：能量法
- 稳定性：能量估计
- 有限传播速度：$|x - x_0| \le t$（信号不超过波速）

---

## 总览：四类方程对比

| 方程 | 类型 | 极值原理 | 基本解 | 能量 |
|---|---|---|---|---|
| Laplace | 椭圆 | 有（空间边界） | $|x|^{2-n}$ | $\int |\nabla u|^2$ |
| 热方程 | 抛物 | 有（抛物边界） | $t^{-n/2} e^{-|x|^2/(4t)}$ | $\int u^2 + \int |\nabla u|^2$ |
| 波动 | 双曲 | 无 | $\delta(t^2 - |x|^2)$ | $\int u_t^2 + \int |\nabla u|^2$ |
| 输运 | 一阶 | 无 | $\delta(x - ct)$ | — |
