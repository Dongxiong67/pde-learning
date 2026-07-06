# 模拟卷

## 期中模拟卷一

### 一、填空（每题 3 分，共 15 分）

1. 方程 $u_t - \Delta(u^\gamma) = 0$（$\gamma > 1$）是 \_\_\_ 阶 \_\_\_ 型方程。

2. 设 $\varphi \in C^2(\mathbb{R}^3)$，则 $\nabla \times (\nabla \varphi) = \_\_\_$。

3. 设 $F \in C^2(\mathbb{R}^3; \mathbb{R}^3)$，则 $\nabla \cdot (\nabla \times F) = \_\_\_$。

4. 径向函数 $u(x) = e^{-|x|^2}$ 在 $|x|=R$ 处的外法向导数为 \_\_\_。

5. KdV 方程的形式是 \_\_\_，它是 \_\_\_ 阶方程。

---

### 二、简答（每题 5 分，共 15 分）

1. 简述偏微分方程的适定性问题包含哪三个方面。

2. 写出 Green 第一公式和 Green 第二公式。

3. 什么是 Dirichlet 问题？什么是 Neumann 问题？

---

### 三、计算（每题 10 分，共 20 分）

1. 设 $u(x) = |x|^2$ in $\mathbb{R}^n$，求 $\Delta u$。

2. 设 $\Omega = B(0,R)$，用散度定理计算 $\int_{\partial\Omega} x \cdot n \, dS$。

---

### 四、证明（每题 10 分，共 50 分）

1. 设 $u \in C^2(\Omega) \cap C(\overline{\Omega})$ 满足
   $$
   \begin{cases}
   -\Delta u = f & \text{in } \Omega \\
   \partial_n u = g & \text{on } \partial\Omega
   \end{cases}
   $$
   证明：$\int_\Omega f \, dx + \int_{\partial\Omega} g \, dS = 0$。

2. 证明 Dirichlet 问题
   $$
   \begin{cases}
   -\Delta u = f & \text{in } \Omega \\
   u = g & \text{on } \partial\Omega
   \end{cases}
   $$
   的解在 $C^2(\Omega) \cap C(\overline{\Omega})$ 中唯一。

3. 叙述并证明调和函数的强最大值原理（$c = 0$ 情形）。

4. 设 $u \in C^2(\Omega) \cap C(\overline{\Omega})$ 满足 $-\Delta u = f$ in $\Omega$，$u = g$ on $\partial\Omega$。
   证明存在常数 $C = C(n, \operatorname{diam}\Omega)$，使得
   $$\|u\|_{L^\infty(\Omega)} \le C\left(\|g\|_{L^\infty(\partial\Omega)} + \|f\|_{L^\infty(\Omega)}\right).$$

5. 设 $u \in C^2(\Omega) \cap C(\overline{\Omega})$ 满足
   $$
   \begin{cases}
   -\Delta u = f & \text{in } \Omega \\
   u = 0 & \text{on } \partial\Omega
   \end{cases}
   $$
   证明：$\int_\Omega |\nabla u|^2 dx \le C \int_\Omega f^2 dx$，并说明常数 $C$ 依赖什么。

---

## 答案与评分点

（详见复习包中的 03_模拟卷_答案与评分点.md）
