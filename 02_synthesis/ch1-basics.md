# 第一章 基本概念与向量分析工具箱

## 1.1 PDE 的基本概念

### 定义

偏微分方程（PDE）是未知多元函数 $u(x)$ 及其偏导数之间的关系。

- $x = (x_1, \dots, x_n)$ — 自变量
- $u = u(x)$ — 未知函数
- 阶数 = 最高阶偏导数的阶数

### 常用记号

多重指标 $\alpha = (\alpha_1, \dots, \alpha_n)$，$|\alpha| = \sum \alpha_i$：

$$D^\alpha u = \frac{\partial^{|\alpha|}u}{\partial x_1^{\alpha_1} \cdots \partial x_n^{\alpha_n}}$$

### 常用算子

| 算子 | 记号 | 定义 |
|---|---|---|
| 梯度 | $\nabla u$ | $(u_{x_1}, \dots, u_{x_n})$ |
| 散度 | $\operatorname{div} F$ | $\sum_i \partial_i F_i$ |
| 拉普拉斯 | $\Delta u$ | $\operatorname{div}(\nabla u) = \sum_i u_{x_i x_i}$ |
| 旋度（n=3） | $\operatorname{curl} F$ | $\nabla \times F$ |
| Hessian | $D^2 u$ | $(u_{x_i x_j})_{n \times n}$ |

### 方程分类

- **线性**：$u$ 及其所有导数都是一次的
- **半线性**：最高阶导数线性，低阶可以非线性
- **拟线性**：最高阶导数线性，但系数依赖 $u$ 或 $\nabla u$
- **完全非线性**：最高阶导数本身非线性

### 典型方程识别

| 方程 | 形式 | 类型 | 阶数 |
|---|---|---|---|
| Laplace | $\Delta u = 0$ | 椭圆 | 2 |
| Poisson | $-\Delta u = f$ | 椭圆 | 2 |
| Heat | $u_t - \Delta u = 0$ | 抛物 | 2 |
| Wave | $u_{tt} - \Delta u = 0$ | 双曲 | 2 |
| KdV | $u_t + uu_x + u_{xxx} = 0$ | 色散 | 3 |
| Porous medium | $u_t - \Delta(u^\gamma) = 0$ | 退化抛物 | 2 |
| Burgers | $u_t + uu_x = 0$ | 双曲（非线性） | 1 |

---

## 1.2 向量分析恒等式

**前提**：$\varphi \in C^2$，$F \in C^2$（保证二阶混合偏导可交换）。

$$\nabla \times (\nabla \varphi) = 0$$

$$\nabla \cdot (\nabla \times F) = 0$$

**理由**：二阶混合偏导可交换，即 $\partial_{xy}\varphi = \partial_{yx}\varphi$。

---

## 1.3 散度定理与 Green 公式

设 $\Omega \subset \mathbb{R}^n$ 光滑有界，$n$ 为外法向。

### 散度定理（Gauss）

$$\int_\Omega \operatorname{div} F \, dx = \int_{\partial\Omega} F \cdot n \, dS$$

### Green 第一公式

$$\int_\Omega \nabla u \cdot \nabla v \, dx = -\int_\Omega v \Delta u \, dx + \int_{\partial\Omega} v \partial_n u \, dS$$

### Green 第二公式

$$\int_\Omega (u \Delta v - v \Delta u) \, dx = \int_{\partial\Omega} (u \partial_n v - v \partial_n u) \, dS$$

### 用途

- 从 PDE 推积分恒等式（或反过来）
- 推导表示公式（Green 函数、Poisson 核）
- 能量估计（分部积分的基础）

---

## 1.4 球面与径向函数

### 球面外法向

在 $\partial B(0,R)$ 上：

$$n(x) = \frac{x}{|x|} = \frac{x}{R}$$

### 径向函数的梯度

若 $u(x) = \psi(|x|)$ 为径向函数：

$$\nabla u(x) = \psi'(|x|) \cdot \frac{x}{|x|}$$

在 $|x|=R$ 上的法向导数：

$$\partial_n u\big|_{|x|=R} = \nabla u \cdot n = \psi'(R)$$

### 径向散度恒等式

$$\operatorname{div}(f(r)x) = n f(r) + r f'(r)$$
