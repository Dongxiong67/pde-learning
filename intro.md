# PDE 学习站

> 用「资源 → 梳理 → 输出 → 测试 → 迭代」五步法系统学习偏微分方程，全部原始资料在线可读。

## 为什么做这个

学习 PDE 的过程中，容易陷入"公式看了就忘、证明懂了不会写、题做了就错"的循环。这个仓库的目的是把学习过程**结构化**：

1. **资源** — 收集教材、板书、参考资料
2. **梳理** — 按章节把概念、定理、方法串成体系
3. **输出** — 提炼解题模板、典型证明套路
4. **测试** — 通过习题、模拟卷检验掌握程度
5. **迭代** — 错题本 + 学习日志，持续修正认知

并在最后增设 **原始资料** 章节，把所有课本、板书、逐字稿、课堂纪要全部上线，方便随时查阅原文。

## 学习主线

PDE 的核心主线是：

$$\text{存在性} \quad+\quad \text{唯一性} \quad+\quad \text{稳定性} \quad+\quad \text{正则性}$$

| 问题 | 工具 | 典型方法 |
|---|---|---|
| 存在性 | 基本解、Green 函数、Poisson 核 | 表示公式、变分法 |
| 唯一性 | 极值原理、能量法 | 两个解作差 |
| 稳定性 | 最大模估计、比较原理 | 边界/右端扰动控制 |
| 正则性 | 平均值性质、导数估计 | 调和函数光滑性 |

## 章节导览

### 📚 基础学习路径

| 章节 | 内容 | 适合场景 |
|------|------|---------|
| [资源](01_resources/index) | 教材推荐、参考资料 | 入门准备 |
| [梳理](02_synthesis/index) | 知识地图、各章梳理 | 系统学习 |
| [输出](03_output/index) | 解题模板、定理证明、一页纸总结 | 复习提炼 |
| [测试](04_test/index) | 习题库、模拟卷、复习速查卡 | 检验掌握 |
| [迭代](05_iteration/index) | 错题本、学习心得、学习日志 | 持续改进 |

### 🔬 数值实验

| Notebook | 内容 |
|----------|------|
| [热方程 FDM](notebooks/01_heat_equation) | 一维热方程有限差分实现 |
| [Poisson 迭代法](notebooks/02_poisson_jacobi) | Jacobi / Gauss-Seidel / SOR 对比 |

### 📖 原始资料（在线阅读原文）

| 资料 | 说明 |
|------|------|
| [课堂板书](06_rawmaterials/blackboard) | Ch1-Ch3 全章节板书图片 + PDF 下载 |
| [课本与讲义](06_rawmaterials/textbooks) | 周蜀林教材、习题解答、Evans 参考 |
| [课堂逐字稿](06_rawmaterials/transcript) | 20 万字课堂录音全文转写，16 主题分段 |
| [课堂纪要](06_rawmaterials/classroom_notes) | 精简版课堂要点记录 |
| [老师讲义深度挖掘](06_rawmaterials/teacher-lecture-notes) | 课堂纪要与北大教材对照分析 |

## 如何使用

- **从零开始**：按左侧导航顺序阅读
- **复习备考**：直接跳转到 [解题模板](03_output/templates)、[复习速查卡](04_test/review-cheatsheet) 和 [期中复习](04_test/midterm-review)
- **查阅原文**：打开 [原始资料](06_rawmaterials/index) 章节，下载课本 PDF 或在线阅读逐字稿
- **动手实践**：打开 [数值实验](notebooks/index) 中的 Jupyter Notebook
- **搜索关键词**：使用站点搜索功能（左侧导航栏顶部）或浏览器 Ctrl+F

---

*参考教材：周蜀林《偏微分方程》、L.C. Evans《Partial Differential Equations》*
