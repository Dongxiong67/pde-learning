# PDE Learning Station · 偏微分方程学习站

> 用「资源 → 梳理 → 输出 → 测试 → 迭代」五步法系统学习偏微分方程。
> 在线阅读：<https://Dongxiong67.github.io/pde-learning/>

## 五阶段学习框架

| 阶段 | 目录 | 内容 |
|---|---|---|
| 📚 资源 | `01_resources/` | 教材、板书、课堂纪要、延伸阅读 |
| 🧩 梳理 | `02_synthesis/` | 按章节知识梳理、知识地图、概念体系 |
| ✍️ 输出 | `03_output/` | 解题模板、典型证明、章节总结 |
| 🧪 测试 | `04_test/` | 复习包、习题库、模拟卷 |
| 🔄 迭代 | `05_iteration/` | 错题本、学习心得、学习日志 |

## 数值实验

`notebooks/` 目录包含可运行的 Jupyter Notebook：

- `01_heat_equation.ipynb` — 一维热传导方程有限差分数值解与可视化

## 本地构建

```bash
# 安装
pip install jupyter-book

# 构建
jupyter-book build .

# 查看
open _build/html/index.html
```

## 部署

推送到 `main` 分支后，GitHub Actions 自动构建并部署到 GitHub Pages。

---

*参考教材：周蜀林《偏微分方程》、L.C. Evans《Partial Differential Equations》*
