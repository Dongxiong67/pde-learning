# 第四章 波动方程

## 4.1 一维波动方程与 d'Alembert 公式

### 方程形式

$$u_{tt} - a^2 u_{xx} = 0, \quad x \in \mathbb{R}, \quad t > 0$$

初值条件：

$$u(x, 0) = \varphi(x), \quad u_t(x, 0) = \psi(x)$$

### d'Alembert 公式

$$u(x, t) = \frac{1}{2}[\varphi(x-at) + \varphi(x+at)] + \frac{1}{2a}\int_{x-at}^{x+at} \psi(s) \, ds$$

**物理意义**：解是初位移的左右传播平均值，加上初速度在特征区间上的积分。

### 特征线

- 右行特征线：$x - at = \text{const}$
- 左行特征线：$x + at = \text{const}$
- 依赖区间：$[x-at, x+at]$
- 影响区域：由特征线围成的锥形区域

---

## 4.2 高维波动方程

### 三维波动方程

$$u_{tt} - a^2 \Delta u = 0, \quad x \in \mathbb{R}^3$$

初值条件：$u(x, 0) = \varphi(x)$, $u_t(x, 0) = \psi(x)$

### Kirchhoff 公式（球面平均法）

$$u(x, t) = \frac{\partial}{\partial t}\left[\frac{1}{4\pi a^2 t} \int_{|y-x|=at} \varphi(y) \, dS_y\right] + \frac{1}{4\pi a^2 t} \int_{|y-x|=at} \psi(y) \, dS_y$$

**Huygens 原理**（三维）：解在 $(x, t)$ 处的值只依赖球面 $|y-x| = at$ 上的初值，而非整个球内。信号无残留，传播清晰。

### 二维波动方程（降维法）

$$u(x_1, x_2, t) = \frac{\partial}{\partial t}\left[\frac{1}{2\pi a} \int_{|y-x| \leq at} \frac{\varphi(y)}{\sqrt{a^2 t^2 - |y-x|^2}} \, dy\right] + \frac{1}{2\pi a} \int_{|y-x| \leq at} \frac{\psi(y)}{\sqrt{a^2 t^2 - |y-x|^2}} \, dy$$

**与三维的区别**：二维解依赖整个圆盘内的初值（而非只依赖圆周），信号有残留（波尾现象）。

---

## 4.3 能量方法

### 能量守恒

对于齐次波动方程 $u_{tt} - a^2 \Delta u = 0$，定义能量：

$$E(t) = \frac{1}{2} \int_{\mathbb{R}^n} (u_t^2 + a^2 |\nabla u|^2) \, dx$$

**性质**：$\frac{dE}{dt} = 0$，即能量守恒。

### 唯一性证明

设 $u_1, u_2$ 都是解，令 $w = u_1 - u_2$，则 $w$ 满足齐次方程零初值。由能量守恒：

$$E(t) = E(0) = 0 \Rightarrow w_t = 0, \nabla w = 0 \Rightarrow w \equiv 0$$

### 有限传播速度

**物理意义**：波动方程的信号以有限速度 $a$ 传播，不会瞬间传播到远处。

**数学表述**：若初值在 $|x| > R$ 时为零，则解在 $(x, t)$ 处的值仅依赖 $|y| \leq R + at$ 范围内的初值。

---

## 4.4 边值问题与分离变量

### 有界弦的振动

$$u_{tt} - a^2 u_{xx} = 0, \quad 0 < x < L, \quad t > 0$$

边界条件：$u(0, t) = u(L, t) = 0$

初值条件：$u(x, 0) = \varphi(x)$, $u_t(x, 0) = \psi(x)$

### 分离变量解

$$u(x, t) = \sum_{n=1}^{\infty} \left[A_n \cos\left(\frac{n\pi a t}{L}\right) + B_n \sin\left(\frac{n\pi a t}{L}\right)\right] \sin\left(\frac{n\pi x}{L}\right)$$

其中：

$$A_n = \frac{2}{L} \int_0^L \varphi(x) \sin\left(\frac{n\pi x}{L}\right) dx, \quad B_n = \frac{2}{n\pi a} \int_0^L \psi(x) \sin\left(\frac{n\pi x}{L}\right) dx$$

---

## 4.5 本章核心结论速查

| 结论 | 公式 | 应用场景 |
|------|------|---------|
| d'Alembert 公式 | $u = \frac{1}{2}[\varphi(x-at)+\varphi(x+at)] + \frac{1}{2a}\int_{x-at}^{x+at}\psi$ | 一维无界弦 |
| Kirchhoff 公式 | 球面平均 | 三维无界 |
| 降维法 | 圆盘积分 | 二维无界 |
| 能量守恒 | $E = \frac{1}{2}\int(u_t^2 + a^2|\nabla u|^2)$ | 唯一性证明 |
| 有限传播速度 | 信号速度 $\leq a$ | 物理意义 |
| 分离变量 | $\sum (A_n \cos + B_n \sin) \sin$ | 有界弦 |

---

## 学习建议

- **重点掌握**：d'Alembert 公式（必考）、能量方法证明唯一性
- **理解关键**：Huygens 原理在三维成立但二维不成立的原因
- **参考板书**：本课程暂无波动方程板书，建议参考 [周蜀林教材](../06_rawmaterials/textbooks) 第四章
- **练习方向**：用 d'Alembert 公式求解具体初值问题，验证能量守恒
