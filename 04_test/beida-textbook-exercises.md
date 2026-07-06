# 期中复习总包：按北大课本顺序的深度分析、考法预测与题库

> 课本：周蜀林《偏微分方程》，北京大学出版社。  
> 页码说明：课本正文第 1 页对应 PDF 第 11 页，所以 **PDF 页码 = 课本页码 + 10**。  
> 资料综合：北大课本目录、老师板书讲义、课堂纪要、上次期中残缺题、期中复习包、模拟卷与答案。

---

## 0. 先给结论：期中真正的命题重心

从上次期中残缺图片、复习包、课堂纪要和讲义来看，期中并不是平均考整本书，而是高度集中在：

1. **第一章基础概念与 Green 公式**：填空、简答、证明工具。
2. **第二章位势方程**：调和函数、基本解、Green 函数、Poisson 核、极值原理、最大模估计、能量估计。
3. **少量模型方程识别**：多孔介质方程、KdV 方程，来自第一章实例或课外补充。
4. **证明题高频模板**：Neumann 相容条件、Dirichlet 唯一性、Green 表示公式、最大模估计、能量估计。

老师讲课的深层主线是：

\[
\text{存在性} \quad+\quad \text{唯一性} \quad+\quad \text{稳定性} \quad+\quad \text{正则性}.
\]

对应工具：

| 问题 | 工具 | 典型考法 |
|---|---|---|
| 存在性 | 基本解、Green 函数、Poisson 核 | 写解公式、推表示公式 |
| 唯一性 | 极值原理、能量法 | 两个解作差 |
| 稳定性 | 最大模估计、比较原理 | 边界/右端扰动控制 |
| 正则性 | 平均值性质、导数估计、能量估计 | 说明调和函数光滑、导数估计 |

---

## 1. 课本页码与期中重要性总表

| 课本位置 | 课本页 | PDF 页 | 讲义/板书 | 课堂纪要 | 期中重要性 |
|---|---:|---:|---|---|---|
| 第 1 章 引言 | 1-16 | 11-26 | Ch1-1.1-1.2, Ch1-1.3 | 少量基础概念 | 中 |
| 1.1 PDE 基本概念 | 1-4 | 11-14 | Ch1-1.1-1.2 | 模型方程、阶数 | 高：填空 |
| 1.2 实例 | 5-10 | 15-20 | Ch1-1.1-1.2 | 多孔介质/KdV | 高：填空 |
| 1.3 适定性问题 | 11-14 | 21-24 | Ch1-1.3 | 存在唯一稳定 | 高：简答思想 |
| 第 2 章 位势方程 | 17-79 | 27-89 | Ch2 全部 | 课堂纪要核心 | 极高 |
| 2.1 调和函数 | 21-35 | 31-45 | Ch2~2.1 | 平均值、Harnack、导数估计 | 极高 |
| 2.2 基本解和 Green 函数 | 36-56 | 46-66 | Ch2-2.2 | 基本解、Green、Poisson | 极高 |
| 2.3 极值原理和最大模估计 | 57-65 | 67-75 | Ch2-2.3 | 弱/强极值、Hopf | 极高 |
| 2.4 能量模估计 | 66-67 | 76-77 | Ch2-2.4 | 能量估计动机 | 高 |
| 2.5 习题 | 68-79 | 78-89 | 周偏微分习题解答 | 与期中题型相连 | 高 |
| 第 3 章 热方程 | 80 起 | 90 起 | Ch3 板书 | 暂未成为纪要主线 | 中低，视考试范围 |

---

# 第一章 引言

## 1.1 偏微分方程的基本概念

**课本页码：** 课本 pp.1-4，PDF pp.11-14  
**讲义对应：** `Ch1-1.1-1.2`  
**期中定位：** 填空/简答基础，通常不出大证明。

### 1.1.1 知识点深讲

偏微分方程是未知多元函数及其偏导数之间的关系。课本这里重点建立符号：

\[
x=(x_1,\dots,x_n),\qquad u=u(x),\qquad u_{x_i}=\partial_i u.
\]

多重指标：

\[
\alpha=(\alpha_1,\dots,\alpha_n),\qquad
|\alpha|=\alpha_1+\cdots+\alpha_n,
\]

\[
D^\alpha u
=
\frac{\partial^{|\alpha|}u}
{\partial x_1^{\alpha_1}\cdots\partial x_n^{\alpha_n}}.
\]

常用算子：

\[
\nabla u=(u_{x_1},\dots,u_{x_n}),
\]

\[
\operatorname{div}F=\sum_{i=1}^n\partial_iF_i,
\]

\[
\Delta u=\operatorname{div}(\nabla u)=\sum_{i=1}^n u_{x_ix_i}.
\]

三维中：

\[
\operatorname{curl}F=\nabla\times F.
\]

### 1.1.2 考点分析

上次期中残缺图片中已经出现：

\[
\nabla\times(\nabla\varphi)=0,\qquad
\nabla\cdot(\nabla\times F)=0.
\]

这说明老师喜欢考“基础符号 + 秒杀恒等式”。不要写复杂展开，点出“二阶混合偏导可交换”即可。

### 1.1.3 例题与答案

**例 1：** 设 \(\varphi\in C^2(\mathbb R^3)\)，求 \(\nabla\times(\nabla\varphi)\)。

**答案：**
\[
\nabla\times(\nabla\varphi)=0.
\]
原因是二阶混合偏导可交换，例如 \(\partial_{xy}\varphi=\partial_{yx}\varphi\)。

**例 2：** 设 \(F\in C^2(\mathbb R^3;\mathbb R^3)\)，求 \(\nabla\cdot(\nabla\times F)\)。

**答案：**
\[
\nabla\cdot(\nabla\times F)=0.
\]

**例 3：** 判断 \(\Delta u=u_{x_1x_1}+\cdots+u_{x_nx_n}\) 是几阶算子。

**答案：** 二阶，因为最高出现二阶偏导。

### 1.1.4 举一反三

1. 若 \(u(x,y)=x^2y+y^3\)，则 \(\Delta u=u_{xx}+u_{yy}=2y+6y=8y\)。
2. 若 \(F(x,y,z)=(x^2,y^2,z^2)\)，则 \(\operatorname{div}F=2x+2y+2z\)。
3. 若 \(u(x)=|x|^2\) in \(\mathbb R^n\)，则 \(\Delta u=2n\)。
4. 若 \(u(x)=e^{a\cdot x}\)，则 \(\Delta u=|a|^2e^{a\cdot x}\)。

### 1.1.5 可能考法预测

- 填空：\(\nabla\times\nabla\varphi=\_\_\_\)。
- 填空：\(\operatorname{div}(\operatorname{curl}F)=\_\_\_\)。
- 简答：为什么这两个恒等式成立？
- 计算：给一个简单 \(u\)，求 \(\Delta u\)。

---

## 1.2 实例

**课本页码：** 课本 pp.5-10，PDF pp.15-20  
**讲义对应：** `Ch1-1.1-1.2`  
**期中定位：** 上次期中已经考过方程识别，仍然高频。

### 1.2.1 知识点深讲

课本用实例介绍 PDE。期中不是要你深入求解这些非线性方程，而是识别：

1. 最高阶；
2. 方程名称；
3. 大致类型。

上次期中残缺图出现：

\[
u_t-\Delta(u^\gamma)=0,\qquad \gamma>1.
\]

它是多孔介质方程，最高阶为 2 阶，通常归为退化抛物型/非线性扩散方程。

另一个：

\[
u_t+uu_x+u_{xxx}=0.
\]

这是 KdV 方程，最高阶为 3 阶，非线性色散方程。

### 1.2.2 考点分析

考“阶数”时，对所有变量一起看最高阶导数：

- \(u_t\) 是一阶；
- \(\Delta(u^\gamma)\) 含空间二阶导；
- \(u_{xxx}\) 是三阶。

注意：\(\Delta(u^\gamma)\) 不是简单的 \(\gamma u^{\gamma-1}\Delta u\)，它展开还含 \(|\nabla u|^2\) 项，但最高阶仍是 2 阶。

### 1.2.3 例题与答案

**例 1：** 判断 \(u_t-\Delta(u^\gamma)=0\) 的最高阶和名称。

**答案：** 最高阶为 2 阶；多孔介质方程；退化抛物型非线性扩散方程。

**例 2：** 判断 \(u_t+uu_x+u_{xxx}=0\) 的最高阶和名称。

**答案：** 最高阶为 3 阶；KdV 方程；非线性色散方程。

**例 3：** 判断 \(-\Delta u=f\) 的类型。

**答案：** 二阶椭圆型方程，称为 Poisson 方程。

**例 4：** 判断 \(\Delta u=0\) 的类型。

**答案：** 二阶椭圆型方程，解称为调和函数。

### 1.2.4 举一反三

1. \(u_t-\Delta u=0\)：热方程，二阶，抛物型。
2. \(u_{tt}-\Delta u=0\)：波动方程，二阶，双曲型。
3. \(u_t+u_x=0\)：一阶输运方程。
4. \(u_t-\operatorname{div}(a(x)\nabla u)=0\)：二阶抛物型，若 \(a>0\)。
5. \(\det D^2u=f\)：Monge-Ampere 方程，二阶，完全非线性。

### 1.2.5 可能考法预测

上次考过仍可能再考，因为这是低成本得分题：

- “写出方程阶数和名称。”
- “该方程是否线性/非线性？”
- “它属于椭圆、抛物、双曲还是色散型？”

---

## 1.3 适定性问题

**课本页码：** 课本 pp.11-14，PDF pp.21-24  
**讲义对应：** `Ch1-1.3`，后续所有章节都围绕它展开。  
**课堂纪要对应：** 老师反复说“存在性、唯一性、稳定性”。  
**期中定位：** 简答思想题、证明题背景。

### 1.3.1 知识点深讲

Hadamard 适定性包含：

1. 解存在；
2. 解唯一；
3. 解连续依赖于数据，即稳定性。

第二章位势方程里，每个工具都对应适定性的一部分：

- Poisson 核/Green 函数：构造解，解决存在性；
- 最大值原理：证明唯一性；
- 最大模估计：证明稳定性；
- 导数估计/能量估计：分析正则性。

### 1.3.2 例题与答案

**例 1：** 说明 Dirichlet 问题的稳定性是什么意思。

**答案：** 若边界值或右端项发生小扰动，解也只发生小扰动。例如调和 Dirichlet 问题中，若 \(u_1,u_2\) 分别对应边界值 \(g_1,g_2\)，则
\[
\|u_1-u_2\|_{L^\infty(\Omega)}
\le
\|g_1-g_2\|_{L^\infty(\partial\Omega)}.
\]

**例 2：** 为什么唯一性常用“两个解作差”？

**答案：** 因为线性方程下差函数满足齐次方程和齐次边界条件，再用最大值原理或能量法证明差函数为零。

### 1.3.3 举一反三

1. 如果存在性没有保证，唯一性只表示“至多一个解”。
2. 如果唯一性失败，反问题或 Neumann 问题常会出现“差一个常数”。
3. Neumann 问题需要相容条件，这是存在性的必要条件。

---

# 第二章 位势方程

第二章是期中核心。课本前言也说这一章重点介绍 \(\mathbb R^n\) 上调和函数及其性质、基本解、Green 函数、极值原理和最大模估计。老师课堂纪要几乎全部围绕这一章展开。

---

## 2.1 调和函数

**课本页码：** 课本 pp.21-35，PDF pp.31-45  
**讲义对应：** `Ch2~2.1-1`, `Ch2-2.1-2(1)`  
**课堂纪要对应：** 调和函数定义与性质、调和函数导数估计定理、能量估计与调和函数性质。  
**期中定位：** 极高。平均值性质、极值原理、导数估计和唯一性都从这里来。

### 2.1.1 核心概念

调和函数：

\[
\Delta u=0.
\]

Poisson 方程：

\[
-\Delta u=f.
\]

Dirichlet 问题：

\[
\begin{cases}
-\Delta u=f, & x\in\Omega,\\
u=g, & x\in\partial\Omega.
\end{cases}
\]

Neumann 问题：

\[
\begin{cases}
-\Delta u=f, & x\in\Omega,\\
\partial_nu=g, & x\in\partial\Omega.
\end{cases}
\]

### 2.1.2 平均值性质

若 \(u\) 调和，则：

\[
u(x)=\fint_{\partial B(x,r)}u\,dS
=\fint_{B(x,r)}u\,dy.
\]

老师讲法重点：

1. 半径 \(r\) 出现在积分区域；
2. 用变量替换变成单位球/单位球面；
3. 对 \(r\) 求导；
4. 用 \(\Delta u=0\) 或散度定理证明导数为 0；
5. 再令 \(r\to0\)，得到平均值等于 \(u(x)\)。

### 2.1.3 平均值性质的考法

**例 1：** 若 \(u\) 调和且在内部点 \(x_0\) 取得最大值，证明 \(u\) 在 \(x_0\) 附近为常数。

**答案：** 对足够小的球 \(B(x_0,r)\)，平均值公式给出
\[
u(x_0)=\fint_{B(x_0,r)}u(y)\,dy.
\]
因为 \(u(y)\le u(x_0)\)，平均值等于最大值只能说明 \(u(y)=u(x_0)\) 在球内成立。由连续性可得局部常数。

**举一反三：**

1. 若 \(u\) 在连通区域内部取最大值，则 \(u\) 全域常数。
2. 若 \(u\) 在内部取最小值，同理 \(u\) 全域常数。
3. 若 \(u\) 非常数调和，则最大值和最小值只能在边界取得。

### 2.1.4 Harnack 不等式

课堂纪要中老师提到 Harnack：非负调和函数在有界连通区域中最大值和最小值相差不会太大。

核心理解：

\[
\sup_K u\le C\inf_K u,
\]

其中 \(K\Subset\Omega\)，\(u\ge0\)，\(\Delta u=0\)。

考试若问，写条件比写常数更重要：

- 非负；
- 调和；
- 内部紧子集；
- 常数依赖区域距离和维数。

### 2.1.5 调和函数导数估计

课堂纪要对此讲得极细。核心公式：

\[
|D^\alpha u(x)|
\le
\frac{C_{n,k}}{R^{n+k}}
\int_{B(x,R)}|u(y)|\,dy,
\qquad |\alpha|=k.
\]

深层意义：

1. 调和函数自动 \(C^\infty\)；
2. 内部导数由函数平均大小控制；
3. 靠近边界时估计变差；
4. 这是 PDE 中“内部估计”的原型。

#### 证明拆解

**第一步 \(k=0\)：**

由平均值公式：
\[
|u(x)|\le \fint_{B(x,R)}|u(y)|\,dy.
\]

**第二步 \(k=1\)：**

因为 \(\Delta u=0\)，所以
\[
\Delta(\partial_i u)=\partial_i(\Delta u)=0.
\]
即 \(\partial_i u\) 仍调和。对 \(\partial_i u\) 用平均值公式，再把 \(\partial_i u\) 写成某个向量场的散度，利用散度定理，把体积分变成球面积分，最后对半径积分。

**第三步 一般 \(k\)：**

设 \(|\alpha|=k\)，可写
\[
D^\alpha u=\partial_iD^\beta u,\qquad |\beta|=k-1.
\]
对 \(D^\beta u\) 用归纳假设，并使用嵌套球：
\[
y\in B(x,tR),\quad z\in B(y,(1-t)R)
\Rightarrow z\in B(x,R).
\]

### 2.1.6 例题与答案

**例 2：** 证明调和函数的一阶导数仍调和。

**答案：**
\[
\Delta(u_{x_i})=\partial_{x_i}(\Delta u)=\partial_{x_i}0=0.
\]

**例 3：** 若 \(u\) 在 \(B(0,2)\) 调和，估计 \(|\nabla u(0)|\) 应由什么控制？

**答案：** 由导数估计：
\[
|\nabla u(0)|\le C_n\int_{B(0,1)}|u(y)|\,dy
\]
或
\[
|\nabla u(0)|\le C_n\|u\|_{L^\infty(B(0,1))}.
\]

**例 4：** 若 \(u\) 在 \(B(0,R)\) 调和且 \(|u|\le M\)，证明
\[
|\nabla u(0)|\le \frac{C_nM}{R}.
\]

**答案：** 由导数估计：
\[
|\nabla u(0)|
\le
\frac{C}{R^{n+1}}\int_{B(0,R)}|u|
\le
\frac{C}{R^{n+1}}MR^n
=\frac{C M}{R}.
\]

### 2.1.7 举一反三题库

**题 1：** 若 \(u\) 在 \(B(0,R)\) 调和，求 \(u(0)\) 与球面平均的关系。  
**答：**
\[
u(0)=\frac{1}{|\partial B_R|}\int_{\partial B_R}u\,dS.
\]

**题 2：** 若 \(u\) 在 \(B(0,R)\) 调和，且 \(u=0\) on \(\partial B_R\)，证明 \(u\equiv0\)。  
**答：** 最大值原理给出 \(\max u\le0\)，对 \(-u\) 用最大值原理得 \(-u\le0\)，所以 \(u=0\)。

**题 3：** 若 \(u\ge0\) 调和，能否在内部一点为 0 而不恒为 0？  
**答：** 不能。若 \(u(x_0)=0\)，这是非负函数的内部最小值，由强极值原理 \(u\equiv0\)。

**题 4：** 若 \(u\) 调和，\(u^2\) 是否调和？  
**答：** 一般不是。
\[
\Delta(u^2)=2|\nabla u|^2+2u\Delta u=2|\nabla u|^2.
\]
除非 \(\nabla u=0\)。

**题 5：** 若 \(u,v\) 调和，则 \(u+v\) 是否调和？  
**答：** 是，因为 Laplace 算子线性。

**题 6：** 若 \(u\) 调和，\(\partial_i u\) 是否调和？  
**答：** 是，前提是 \(u\) 足够光滑；调和函数实际自动光滑。

---

## 2.2 基本解和 Green 函数

**课本页码：** 课本 pp.36-56，PDF pp.46-66  
**讲义对应：** `Ch2-2.2-1(1)`, `Ch2-2.2-2(1)`  
**课堂纪要对应：** 镜像对称与拉格拉斯方程、数学积分与极限讨论、Green 函数推导、Poisson 核。  
**期中定位：** 极高，尤其 Green 函数定义和表示公式。

### 2.2.1 基本解

老师从径向解讲起。设

\[
u(x)=v(r),\qquad r=|x|.
\]

则

\[
\Delta u=v''(r)+\frac{n-1}{r}v'(r).
\]

调和方程变为：

\[
v''+\frac{n-1}{r}v'=0.
\]

解得：

- \(n=2\)：\(v(r)=C\log r+C_2\)；
- \(n\ge3\)：\(v(r)=Cr^{2-n}+C_2\)。

因此基本解可取：

\[
\Gamma(x)=
\begin{cases}
-\dfrac{1}{2\pi}\log|x|, & n=2,\\[6pt]
\dfrac{1}{n(n-2)\alpha_n}|x|^{2-n}, & n\ge3,
\end{cases}
\]

并满足分布意义下

\[
-\Delta\Gamma=\delta_0.
\]

### 2.2.2 基本解考法

**例 1：** 推导径向 Laplace 公式。

**答案：** 若 \(u(x)=v(r)\)，则
\[
u_{x_i}=v'(r)\frac{x_i}{r}.
\]
继续求导并求和得：
\[
\Delta u=v''(r)+\frac{n-1}{r}v'(r).
\]

**例 2：** 求 \(n\ge3\) 时径向调和函数的一般形式。

**答案：**
\[
v''+\frac{n-1}{r}v'=0.
\]
令 \(w=v'\)，则
\[
w'+\frac{n-1}{r}w=0.
\]
解得
\[
w=Cr^{1-n}.
\]
积分得
\[
v=C_1r^{2-n}+C_2.
\]

**例 3：** 为什么基本解不是普通意义下处处满足 \(-\Delta\Gamma=0\)？

**答案：** 它在 \(x=0\) 有奇性。对 \(x\ne0\)，\(\Gamma\) 调和；在分布意义下，原点贡献一个 Dirac 源：
\[
-\Delta\Gamma=\delta_0.
\]

### 2.2.3 Green 函数

Dirichlet Green 函数满足：

\[
\begin{cases}
-\Delta_xG(x,y)=\delta_y, & x\in\Omega,\\
G(x,y)=0, & x\in\partial\Omega.
\end{cases}
\]

理解：

\[
G(x,y)=\Gamma(x-y)-H(x,y),
\]

其中 \(H\) 是调和修正项，用来使边界值变成 0。

### 2.2.4 Green 表示公式

若

\[
\begin{cases}
-\Delta u=f, & x\in\Omega,\\
u=g, & x\in\partial\Omega,
\end{cases}
\]

则

\[
u(x)=
\int_{\partial\Omega}g(y)\partial_{n_y}G(x,y)\,dS_y
+\int_\Omega f(y)G(x,y)\,dy.
\]

证明模板：

1. 固定 \(x\)，把 \(y\) 当变量；
2. 取 \(v(y)=G(x,y)\)；
3. 用 Green 第二公式：
\[
\int_\Omega(u\Delta v-v\Delta u)
=
\int_{\partial\Omega}(u\partial_nv-v\partial_nu);
\]
4. 用 \(G=0\) 消去边界项；
5. 用 \(-\Delta G=\delta\) 和 \(-\Delta u=f\) 得公式。

### 2.2.5 Poisson 核

球上 Dirichlet 问题可用 Poisson 核表示：

\[
u(x)=\int_{\partial B_R}P_R(x,y)g(y)\,dS_y.
\]

核的结构：

\[
P_R(x,y)\sim
\frac{R^2-|x|^2}{R|x-y|^n},
\qquad y\in\partial B_R.
\]

常数依赖 \(\alpha_n=|B_1|\)。考试更可能考结构与用途，而非复杂常数。

### 2.2.6 例题与答案

**例 4：** 写出 Dirichlet Green 函数定义。

**答案：**
\[
\begin{cases}
-\Delta_xG(x,y)=\delta_y, & x\in\Omega,\\
G(x,y)=0, & x\in\partial\Omega.
\end{cases}
\]
且 \(x\ne y\) 时 \(G(\cdot,y)\) 调和。

**例 5：** 若 \(f=0\)，Green 表示公式变成什么？

**答案：**
\[
u(x)=\int_{\partial\Omega}g(y)\partial_{n_y}G(x,y)\,dS_y.
\]

**例 6：** 若 \(g=0\)，Green 表示公式变成什么？

**答案：**
\[
u(x)=\int_\Omega f(y)G(x,y)\,dy.
\]

**例 7：** 为什么推导 Green 公式时要固定 \(x\)，把 \(y\) 当变量？

**答案：** 因为 \(G(x,y)\) 对 \(y\) 满足 \(-\Delta_yG(x,y)=\delta_x(y)\)，Green 第二公式是在积分变量 \(y\) 上使用的。

### 2.2.7 举一反三题库

**题 1：** 求 \(\Delta |x|^2\)。  
**答：** \(\Delta |x|^2=2n\)。

**题 2：** 求 \(\Delta r^\alpha\)，其中 \(r=|x|\)。  
**答：**
\[
\Delta r^\alpha=\alpha(\alpha+n-2)r^{\alpha-2},\quad r>0.
\]

**题 3：** 找出 \(\alpha\)，使 \(r^\alpha\) 在 \(\mathbb R^n\setminus\{0\}\) 调和。  
**答：**
\[
\alpha(\alpha+n-2)=0,
\]
所以 \(\alpha=0\) 或 \(\alpha=2-n\)。

**题 4：** \(n=2\) 时为什么出现 \(\log r\)？  
**答：** 因为径向 ODE 给出 \(v'=C/r\)，积分得 \(v=C\log r+C_2\)。

**题 5：** Green 函数和 Green 公式有什么区别？  
**答：** Green 公式是积分恒等式；Green 函数是满足特定 PDE 和边界条件的核函数，用于表示解。

**题 6：** 为什么 \(G=0\) on \(\partial\Omega\) 很重要？  
**答：** 它使 Green 第二公式边界项中的 \(G\partial_nu\) 消失，从而只剩已知边界值 \(g\)。

**题 7：** 若 \(\Omega=B_R\)，Poisson 核可以看成什么？  
**答：** 可以看成 \(\partial_{n_y}G(x,y)\) 的显式形式。

---

## 2.3 极值原理和最大模估计

**课本页码：** 课本 pp.57-65，PDF pp.67-75  
**讲义对应：** `Ch2-2.3(2)`  
**课堂纪要对应：** 弱极值原理证明、Hopf 引理、强极值原理。  
**期中定位：** 证明题核心。

### 2.3.1 弱极值原理

典型算子：

\[
Lu=-\Delta u+c(x)u,\qquad c(x)\ge0.
\]

若 \(Lu\le0\)，则 \(u\) 的最大值由边界控制。

内部最大点的二阶条件：

\[
\nabla u(x_0)=0,\qquad D^2u(x_0)\le0,\qquad \Delta u(x_0)\le0.
\]

若 \(u(x_0)\ge0\)，则

\[
Lu(x_0)=-\Delta u(x_0)+c(x_0)u(x_0)\ge0.
\]

这与 \(Lu<0\) 矛盾。

### 2.3.2 非严格不等式的处理

若只有 \(Lu\le0\)，老师讲义中通过辅助函数扰动：

\[
w=u+\varepsilon\phi
\]

让

\[
Lw<0.
\]

最后令 \(\varepsilon\to0\)。

这就是“障碍函数/辅助函数”的核心作用。

### 2.3.3 比较原理

若

\[
Lu\le Lv\quad\text{in }\Omega,
\qquad
u\le v\quad\text{on }\partial\Omega,
\]

则

\[
u\le v\quad\text{in }\Omega.
\]

证明：令 \(w=u-v\)，则 \(Lw\le0\)，且 \(w\le0\) on \(\partial\Omega\)，用最大值原理。

### 2.3.4 Dirichlet 唯一性

若 \(u,v\) 都解同一 Dirichlet 问题，令 \(w=u-v\)，则

\[
Lw=0,\qquad w=0\text{ on }\partial\Omega.
\]

对 \(w\) 和 \(-w\) 分别用最大值原理，得 \(w=0\)。

### 2.3.5 最大模估计

对

\[
\begin{cases}
-\Delta u=f, & x\in\Omega,\\
u=g, & x\in\partial\Omega,
\end{cases}
\]

常见结论：

\[
\|u\|_{L^\infty(\Omega)}
\le
C(n,\operatorname{diam}\Omega)
\left(
\|g\|_{L^\infty(\partial\Omega)}
+
\|f\|_{L^\infty(\Omega)}
\right).
\]

障碍函数：

\[
\phi(x)=A(d^2-|x-x_0|^2),\qquad A=\frac{\|f\|_\infty}{2n}.
\]

因为：

\[
-\Delta\phi=\|f\|_\infty.
\]

### 2.3.6 Hopf 引理

若函数在边界点严格取得最大值，则外法向导数有严格符号。老师讲义的证明使用球壳和径向障碍函数。

关键计算：

若 \(V(x)=\psi(|x|)\)，则

\[
\partial_nV\big|_{|x|=R}=\psi'(R).
\]

这就是为什么计算题经常考径向函数法向导数。

### 2.3.7 例题与答案

**例 1：** 证明 Dirichlet 问题唯一性。

**答案：** 设 \(u,v\) 是两个解，令 \(w=u-v\)。则
\[
-\Delta w=0,\qquad w=0\text{ on }\partial\Omega.
\]
最大值原理给 \(w\le0\)。对 \(-w\) 用最大值原理得 \(-w\le0\)，所以 \(w=0\)。

**例 2：** 证明比较原理。

**答案：** 令 \(w=u-v\)，则 \(Lw\le0\)，且 \(w\le0\) on \(\partial\Omega\)。由最大值原理，\(w\le0\)，即 \(u\le v\)。

**例 3：** 设 \(-\Delta u=f\)，\(u=g\)，证明最大模估计。

**答案：** 令 \(M=\|f\|_\infty\)，\(G=\|g\|_\infty\)，\(d=\operatorname{diam}\Omega\)。取
\[
\phi(x)=\frac{M}{2n}(d^2-|x-x_0|^2).
\]
则 \(-\Delta\phi=M\)。令 \(w=u-\phi\)，得
\[
-\Delta w=f-M\le0.
\]
最大值原理：
\[
\max u\le G+\frac{Md^2}{2n}.
\]
对 \(-u\) 同理，得
\[
\|u\|_\infty\le G+\frac{Md^2}{2n}.
\]

### 2.3.8 举一反三题库

**题 1：** 若 \(-\Delta u\le0\)，\(u\le0\) on \(\partial\Omega\)，证明 \(u\le0\)。  
**答：** 由最大值原理，最大值在边界，故 \(\max_{\bar\Omega}u\le0\)。

**题 2：** 若 \(-\Delta u\ge0\)，\(u\ge0\) on \(\partial\Omega\)，证明 \(u\ge0\)。  
**答：** 对 \(-u\) 用上一题。

**题 3：** 若 \(u\) 调和且 \(u\ge0\) on \(\partial\Omega\)，证明 \(u\ge0\) in \(\Omega\)。  
**答：** 最小值原理，或对 \(-u\) 用最大值原理。

**题 4：** 若 \(u,v\) 调和且 \(u\le v\) on \(\partial\Omega\)，证明 \(u\le v\)。  
**答：** 对 \(w=u-v\) 用最大值原理。

**题 5：** 若 \(u\) 在内部取得正最大值，且 \(-\Delta u+cu<0\)，\(c\ge0\)，证明矛盾。  
**答：** 内部最大点有 \(\Delta u\le0\)，所以 \(-\Delta u+cu\ge0\)，矛盾。

**题 6：** 若 \(u\) 在边界严格最大，Hopf 引理说明什么？  
**答：** 在适当条件下，外法向导数 \(\partial_nu>0\)。

**题 7：** 为什么强极值原理需要连通性？  
**答：** 若区域不连通，一个分支上常数最大，另一个分支可不同，不能推出全域常数。

**题 8：** 强极值原理中最大值点集为什么是闭集？  
**答：** \(O=\{u=M\}=u^{-1}(\{M\})\)，连续函数的闭集原像是闭集。

---

## 2.4 能量模估计

**课本页码：** 课本 pp.66-67，PDF pp.76-77  
**讲义对应：** `Ch2-2.4`  
**课堂纪要对应：** 能量估计与调和函数性质。  
**期中定位：** 高，通常考基础能量法，不太可能考最复杂单调性。

### 2.4.1 知识点深讲

老师说得很清楚：点态估计不总是好做，尤其更一般或非线性 PDE 中，常转向积分估计。

典型能量：

\[
\int_\Omega u^2\,dx,\qquad
\int_\Omega|\nabla u|^2\,dx.
\]

基本模板：

1. 方程乘测试函数；
2. 积分；
3. Green 第一公式/积分分部；
4. 边界项消失或估计；
5. Cauchy-Schwarz、Young、Poincare。

### 2.4.2 基础例题

**例 1：** 设
\[
\begin{cases}
-\Delta u=f, & x\in\Omega,\\
u=0, & x\in\partial\Omega.
\end{cases}
\]
证明能量恒等式。

**答案：** 两边乘 \(u\) 积分：
\[
\int_\Omega(-\Delta u)u\,dx=\int_\Omega fu\,dx.
\]
积分分部且 \(u=0\) on \(\partial\Omega\)，得
\[
\int_\Omega|\nabla u|^2\,dx=\int_\Omega fu\,dx.
\]

**例 2：** 继续证明 \(\|\nabla u\|_2\le C\|f\|_2\)。

**答案：**
\[
\int|\nabla u|^2=\int fu
\le \|f\|_2\|u\|_2.
\]
由 Poincare：
\[
\|u\|_2\le C\|\nabla u\|_2.
\]
所以
\[
\|\nabla u\|_2^2\le C\|f\|_2\|\nabla u\|_2,
\]
即
\[
\|\nabla u\|_2\le C\|f\|_2.
\]

### 2.4.3 举一反三题库

**题 1：** 若 \(-\Delta u+cu=f\)，\(u=0\)，\(c\ge0\)，写出能量等式。  
**答：**
\[
\int|\nabla u|^2+\int cu^2=\int fu.
\]

**题 2：** 若 \(-\Delta u=0\)，\(u=0\) on \(\partial\Omega\)，用能量法证明 \(u=0\)。  
**答：**
\[
\int|\nabla u|^2=0,
\]
所以 \(\nabla u=0\)，\(u\) 常数；边界为 0，故 \(u=0\)。

**题 3：** 做局部能量估计常用什么测试函数？  
**答：** \(\eta^2u\)，其中 \(\eta\) 是截断函数。

**题 4：** 处理非负性常用什么测试函数？  
**答：** \(u^-=\max\{-u,0\}\) 或 \(u^+=\max\{u,0\}\)。

**题 5：** 为什么能量估计可证明稳定性？  
**答：** 对两个解作差，差函数满足以数据差为右端的方程，能量估计可用数据差控制解差。

---

## 2.5 习题与期中出题映射

**课本页码：** 课本 pp.68-79，PDF pp.78-89  
**资料对应：** `周偏微分习题解答_整理版.pdf`、期中复习包。  
**期中定位：** 老师可能从习题中抽模板改造。

### 2.5.1 必刷题型 1：相容条件

**题：** 设
\[
\begin{cases}
-\Delta u=f, & x\in\Omega,\\
\partial_nu=g, & x\in\partial\Omega.
\end{cases}
\]
证明必要条件：
\[
\int_\Omega f\,dx+\int_{\partial\Omega}g\,dS=0.
\]

**答案：**
\[
\int_\Omega f=\int_\Omega(-\Delta u)
=-\int_{\partial\Omega}\partial_nu
=-\int_{\partial\Omega}g.
\]

所以
\[
\int_\Omega f+\int_{\partial\Omega}g=0.
\]

**变形 1：** 若 \(\partial_nu=0\)，则必须 \(\int_\Omega f=0\)。  
**变形 2：** 若方程写 \(\Delta u=f\)，符号要变为 \(\int_\Omega f=\int_{\partial\Omega}g\)。  
**变形 3：** Neumann 解唯一性只能差一个常数。

### 2.5.2 必刷题型 2：Green 表示公式

**题：** 推导
\[
u(x)=\int_{\partial\Omega}g\partial_nG+\int_\Omega fG.
\]

**答案：** 固定 \(x\)，对 \(u(y)\) 与 \(G(x,y)\) 用 Green 第二公式，利用
\[
G=0,\quad -\Delta G=\delta,\quad -\Delta u=f.
\]

**变形：**

1. \(f=0\)：只剩边界项；
2. \(g=0\)：只剩体积分；
3. 半空间/球：\(\partial_nG\) 写成 Poisson 核。

### 2.5.3 必刷题型 3：最大模估计

**题：** 证明
\[
\|u\|_\infty\le C(\|g\|_\infty+\|f\|_\infty).
\]

**答案：** 用二次障碍函数
\[
\phi=A(d^2-|x-x_0|^2),
\quad A=\frac{\|f\|_\infty}{2n}.
\]

**变形：**

1. 若 \(f=0\)，得到 \(\|u\|_\infty\le\|g\|_\infty\)。
2. 若 \(g=0\)，得到 \(\|u\|_\infty\le C\|f\|_\infty\)。
3. 若有 \(+cu\)，\(c\ge0\)，最大值原理仍可用。

### 2.5.4 必刷题型 4：球面法向导数

**题：** \(u(x)=e^{-3|x|}\)，求 \(\partial_nu\) on \(\partial B_R\)。

**答案：**
\[
\partial_nu=-3e^{-3R}.
\]

**变形：**

1. \(u=|x|^m\)，\(\partial_nu=mR^{m-1}\)。
2. \(u=\log|x|\)，\(\partial_nu=1/R\)。
3. \(u=|x|^{2-n}\)，\(\partial_nu=(2-n)R^{1-n}\)。

---

# 第三章 热方程（期中低概率补充）

**课本页码：** 第三章从课本 p.80 起，PDF p.90 起。  
**目录重点：** 3.1 初值问题 p.83，Fourier 变换 p.83，基本解 p.95；3.2 混合问题和 Green 函数 p.101；3.3 极值原理和最大模估计 p.117。  
**讲义：** 有 Ch3 板书，但现有课堂纪要主线主要集中在第二章。  
**期中判断：** 如果老师明确讲到 Ch3，则可能考 Fourier 变换、热核、热方程最大值原理；否则作为低概率扩展。

### 3.1 可能考点

1. 热方程：
\[
u_t-\Delta u=0.
\]
2. 基本解/热核：
\[
\Phi(x,t)=\frac{1}{(4\pi t)^{n/2}}e^{-|x|^2/(4t)},\quad t>0.
\]
3. 初值问题表示：
\[
u(x,t)=\int_{\mathbb R^n}\Phi(x-y,t)g(y)\,dy.
\]
4. 最大值原理：热方程最大值在抛物边界上取得。

### 3.2 低概率例题

**例：** 写出热方程全空间初值问题的解公式。

**答案：**
\[
u(x,t)=\int_{\mathbb R^n}
\frac{1}{(4\pi t)^{n/2}}
e^{-|x-y|^2/(4t)}
g(y)\,dy.
\]

**举一反三：**

1. 若 \(g\ge0\)，则 \(u\ge0\)。
2. 若 \(g\) 有界，则 \(\|u(\cdot,t)\|_\infty\le\|g\|_\infty\)。
3. 热核积分为 1，所以它是平均化核。

---

# 4. 按题型整理的高密度题库

## 4.1 填空题

1. \(\nabla\times(\nabla\varphi)=\_\_\_\)。  
**答：** 0。

2. \(\nabla\cdot(\nabla\times F)=\_\_\_\)。  
**答：** 0。

3. \(u_t-\Delta(u^\gamma)=0\) 最高阶为 \(\_\_\_\)。  
**答：** 2。

4. \(u_t+uu_x+u_{xxx}=0\) 称为 \(\_\_\_\)。  
**答：** KdV 方程。

5. Green 第一公式中：
\[
\int_\Omega\nabla u\cdot\nabla v
=\_\_\_+\int_{\partial\Omega}v\partial_nu.
\]
**答：**
\[
-\int_\Omega v\Delta u.
\]

6. Neumann 相容条件：
\[
\int_\Omega f+\int_{\partial\Omega}\_\_\_=0.
\]
**答：** \(g\)。

7. \(\Delta |x|^2=\_\_\_\)。  
**答：** \(2n\)。

8. \(\partial B_R\) 上单位外法向为 \(\_\_\_\)。  
**答：** \(n=x/R\)。

9. \(n=2\) 时 Laplace 基本解含 \(\_\_\_\)。  
**答：** \(\log|x|\)。

10. \(n\ge3\) 时 Laplace 基本解形如 \(\_\_\_\)。  
**答：** \(C|x|^{2-n}\)。

## 4.2 简答题

**题 1：** 写 Green 第二公式。  
**答：**
\[
\int_\Omega(u\Delta v-v\Delta u)
=
\int_{\partial\Omega}(u\partial_nv-v\partial_nu).
\]

**题 2：** 写 Dirichlet Green 函数定义。  
**答：**
\[
-\Delta_xG(x,y)=\delta_y,\quad G=0\text{ on }\partial\Omega.
\]

**题 3：** 说明最大值原理如何推出唯一性。  
**答：** 两个解作差，差函数满足齐次方程和零边界；对差函数及其相反数用最大值原理，得到差为零。

**题 4：** 为什么 Neumann 问题要相容条件？  
**答：** 对方程积分并用散度定理，右端体积分必须等于边界通量的负值。

**题 5：** Green 函数与基本解的关系是什么？  
**答：** Green 函数是基本解加上/减去调和修正项，使其满足边界条件。

## 4.3 计算题

**题 1：** 求 \(\partial_n e^{-a|x|}\) on \(\partial B_R\)。  
**答：**
\[
-ae^{-aR}.
\]

**题 2：** 求 \(\int_{\partial B_R}x\cdot n\,dS\)。  
**答：**
\[
n|B_R|=R|\partial B_R|.
\]

**题 3：** 求 \(\Delta |x|^\alpha\)。  
**答：**
\[
\alpha(\alpha+n-2)|x|^{\alpha-2}.
\]

**题 4：** 求径向调和函数 \(u=v(r)\) 满足的 ODE。  
**答：**
\[
v''+\frac{n-1}{r}v'=0.
\]

**题 5：** 若 \(u=|x|^{2-n}\)，\(n\ge3\)，求 \(\partial_nu\) on \(\partial B_R\)。  
**答：**
\[
(2-n)R^{1-n}.
\]

## 4.4 证明题

**题 1：Neumann 相容条件。**  
答案见 2.5.1。

**题 2：Dirichlet 唯一性。**  
答案见 2.3.7。

**题 3：Green 表示公式。**  
答案见 2.2.4。

**题 4：最大模估计。**  
答案见 2.3.7。

**题 5：能量估计。**  
答案见 2.4.2。

**题 6：调和函数内部最大值推出常数。**  
**答：** 平均值性质或强极值原理。

**题 7：比较原理。**  
**答：** 对 \(u-v\) 用最大值原理。

**题 8：基本解径向推导。**  
**答：** 用 \(u=v(r)\) 把 \(\Delta u=0\) 化成 ODE，解出 \(\log r\) 或 \(r^{2-n}\)。

---

# 5. 最后冲刺：按优先级复习

## 必须会完整书写

1. Green 第一、第二公式。
2. Neumann 相容条件证明。
3. Dirichlet 唯一性证明。
4. Green 函数表示公式推导。
5. 最大模估计的障碍函数证明。
6. 能量估计基础模板。

## 必须会计算

1. 球面外法向 \(n=x/R\)。
2. 径向函数梯度与法向导数。
3. \(\Delta |x|^2=2n\)。
4. \(\Delta r^\alpha=\alpha(\alpha+n-2)r^{\alpha-2}\)。
5. 径向 Laplace ODE。

## 必须会解释

1. 为什么调和函数有平均值性质。
2. 为什么平均值性质推出最大值原理。
3. 为什么基本解有奇点。
4. 为什么 Green 函数要修正边界。
5. 为什么最大值原理要求 \(c\ge0\)。
6. 为什么 Hopf 引理关心外法向导数。
7. 为什么能量估计适合更一般 PDE。

## 考前一页公式

\[
\int_\Omega\operatorname{div}F=\int_{\partial\Omega}F\cdot n.
\]

\[
\int_\Omega\nabla u\cdot\nabla v
=-\int_\Omega v\Delta u+\int_{\partial\Omega}v\partial_nu.
\]

\[
\int_\Omega(u\Delta v-v\Delta u)
=\int_{\partial\Omega}(u\partial_nv-v\partial_nu).
\]

\[
u(x)=\fint_{\partial B(x,r)}u\,dS=\fint_{B(x,r)}u\,dy.
\]

\[
\Gamma(x)=
\begin{cases}
-\frac1{2\pi}\log|x|, & n=2,\\
\frac{1}{n(n-2)\alpha_n}|x|^{2-n}, & n\ge3.
\end{cases}
\]

\[
-\Delta_xG(x,y)=\delta_y,\qquad G=0\text{ on }\partial\Omega.
\]

\[
u(x)=\int_{\partial\Omega}g\partial_nG+\int_\Omega fG.
\]

\[
\int_\Omega f+\int_{\partial\Omega}g=0.
\]

\[
\|u\|_\infty\le C(\|g\|_\infty+\|f\|_\infty).
\]

