# PDE 复习总库

> 浓缩版 PDE 复习精华，覆盖考试核心考点、公式模板和证明套路。
> 原始文件：`PDE复习总库_合并版.txt`

---

## 总纲：考试结构与方法论

### PDE 考试本质

考试不是考记忆，而是三件事：

1. **模板识别能力**（最重要）
2. **公式条件反射**
3. **标准证明套路复现**

### 高频考点结构

**第一类：基础题**
- PDE 阶数判断
- 线性 / 半线性 / 拟线性 / 非线性
- Laplace / Poisson / Heat / Wave / KdV 识别
- grad / div / curl / Δ
- 向量恒等式

**第二类：计算题**
- 球面法向导数
- 径向函数
- 散度公式
- Green 公式

**第三类：证明题**
- 唯一性 → 作差 + 最大值原理
- 稳定性 → 作差 + 估计
- Neumann → 积分 + 散度定理
- 最大模 → 障碍函数
- Green 函数 → Green 第二公式
- 能量估计 → 分部积分

---

## 第一章：基础概念与分类

### PDE 阶数

$$\text{阶数} = \text{最高阶偏导数的阶数}$$

### 方程分类

| 类型 | 定义 |
|------|------|
| 线性 | 所有 $u$ 及导数一次出现 |
| 半线性 | 最高阶线性 |
| 拟线性 | 最高阶线性但系数依赖 $u$ 或 $\nabla u$ |
| 完全非线性 | 最高阶非线性 |

### 常见方程

| 方程 | 表达式 |
|------|--------|
| Laplace | $\Delta u = 0$ |
| Poisson | $-\Delta u = f$ |
| Heat | $u_t - \Delta u = 0$ |
| Wave | $u_{tt} - \Delta u = 0$ |
| KdV | $u_t + uu_x + u_{xxx} = 0$ |
| Burgers | $u_t + uu_x = 0$ |

---

## 向量分析与计算工具

### 基本算子

$$\nabla u = (u_x, u_y, u_z)$$

$$\text{div}\, F = \sum \partial_i F_i$$

$$\Delta u = \text{div}(\nabla u)$$

$$\text{curl}\, F = \nabla \times F$$

### 核心恒等式

$$\text{curl}(\text{grad}\, \varphi) = 0$$

$$\text{div}(\text{curl}\, F) = 0$$

### 球面法向

$$n = \frac{x}{|x|}$$

### 径向函数公式

$$u = \psi(|x|)$$

$$\nabla u = \psi'(r) \frac{x}{r}$$

### 径向散度公式

$$\text{div}(f(r)x) = n f(r) + r f'(r)$$

---

## 第二章：位势方程核心模板

### 核心方程

Poisson 方程：$-\Delta u = f$

Laplace 方程：$\Delta u = 0$

### 三大主线

**最大值体系**
平均值 → 最大值原理 → 唯一性

**Green 体系**
基本解 → Green 函数 → 表示公式

**能量体系**
乘 $u$ → 分部积分 → $L^2$ 估计

### 唯一性模板

$$w = u_1 - u_2$$

$$-\Delta w = 0$$

$$w|_{\partial \Omega} = 0$$

$$\Rightarrow w = 0$$

---

## Green 公式与 Green 函数体系

### Green 公式（散度定理）

$$\int_\Omega \text{div}\, F \, dx = \int_{\partial \Omega} F \cdot n \, dS$$

### Green 第二公式

$$\int_\Omega (u\Delta v - v\Delta u) \, dx = \int_{\partial \Omega} (u \partial_n v - v \partial_n u) \, dS$$

### Green 函数思路

$$-\Delta u = f$$

$$\Rightarrow \text{Green 第二公式}$$

$$\Rightarrow \text{表示解}$$

---

## 最大值原理与比较原理

### 弱最大值原理

$$\max_{\overline{\Omega}} u = \max_{\partial \Omega} u$$

### 强最大值原理

内部取最大值 $\Rightarrow$ 常数

### 比较原理

$$u \leq v \quad \text{on } \partial \Omega$$

$$-\Delta u \leq -\Delta v$$

$$\Rightarrow u \leq v \quad \text{in } \Omega$$

### 最大模估计技巧

- $u - \varphi$
- $-u - \varphi$
- $\Rightarrow$ 最大值原理

---

## Neumann 与相容条件

### Neumann 问题

$$\begin{cases}
-\Delta u = f & \text{in } \Omega \\
\partial_n u = g & \text{on } \partial \Omega
\end{cases}$$

### 相容条件

$$\int_\Omega f \, dx + \int_{\partial \Omega} g \, dS = 0$$

---

## 能量估计体系

### 标准步骤

1. 方程两端乘 $u$
2. 在 $\Omega$ 上积分
3. 分部积分
4. 应用 Cauchy / Young 不等式

### 核心结果

$$\int_\Omega |\nabla u|^2 dx \leq \int_\Omega f u \, dx$$

---

## 热方程（第三章）核心公式

### 热方程

$$u_t - a^2 \Delta u = f$$

### 热核（基本解）

$$G(x,t) = (4\pi t)^{-n/2} \exp\left(-\frac{|x|^2}{4t}\right)$$

### 解的表示

$$u = G * \varphi + \int_0^t G * f \, ds$$

---

## 波动方程核心公式

### 波动方程

$$u_{tt} - a^2 \Delta u = 0$$

### 核心概念

- 能量守恒
- 唯一性
- 特征传播

---

## 证明题模板大全

| 题型 | 套路 |
|------|------|
| 唯一性 | $w = u_1 - u_2 \to -\Delta w = 0 \to$ 最大值原理 |
| 稳定性 | $w = u_1 - u_2 \to$ 估计 |
| Neumann | 积分 + 散度定理 |
| Green 函数 | Green 第二公式 |
| 能量估计 | 乘 $u$ + 分部积分 |

---

## 公式速查表

- $\nabla u$, $\text{div}\, F$, $\Delta u$, $\text{curl}\, F$
- $\text{div}(f(r)x) = nf + rf'$
- $\nabla \psi = \psi'(r) x / r$
- Green 公式
- Green 第二公式
- 最大值原理

---

## 学习建议

更多详细内容请参考：
- [知识梳理](../02_synthesis/index)：系统梳理各章节知识点
- [证明模板](../03_output/proofs)：完整定理证明
- [一页纸总结](../03_output/summaries)：章节速览
- [习题库](../04_test/exercise-bank)：举一反三练习题
- [模拟考试](../04_test/mock-exams)：全真模拟测试
