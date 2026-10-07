---
layout: default
title: "A Capacity Criterion for Four-State Potts Reconstruction on Trees"
family: "229"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Capacity Criterion for Four-State Potts Reconstruction on Trees

> 结果族 229：Exact three- and four-state reconstruction thresholds and four-state tree capacity　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
对 `@@M@@0<\lambda<1@@` 的铁磁四态 Potts 广播模型，证明在有界度确定性生根树上重构当且仅当树的带边阻 `@@M@@\lambda^{-2|e|}@@` 的 `@@M@@L^3@@` 容量为正：一个不依赖正则性或增长率假设的精确判据，连指数临界边界也能判定。

## 问题背景
正则树与泊松树上的重构阈值可由增长率 `@@M@@d\lambda^2@@` 刻画，但在任意形状的树（允许顶点只有零个或一个孩子、增长率恰在指数边界）上，单靠增长率无法判定。Evans–Kenyon–Peres–Schulman（2000）建立了广播与 Ising 模型、电容之间的联系；Pemantle–Peres（2010）用非线性容量刻画 Ising 临界判据：自由边界对应平方阻的 `@@M@@L^2@@` 容量、加号边界对应不平方阻的 `@@M@@L^3@@` 容量。四态 Potts 恰是谱阈值是否精确的边界情形（Sly 2011 证明 `@@M@@q\ge5@@` 失效；Mossel–Sly–Sohn 2025 覆盖大平均度的三、四态），且四态处二次修正项消失、高阶项起决定作用。本文给出四态模型在任意有界度树上的完整容量判据。

## 主要结果
设 `@@M@@T@@` 为每个顶点至多 `@@M@@B@@` 个孩子的无穷确定性生根树（对观察者已知），`@@M@@0<\lambda<1@@`，通道同四态 Potts。定义流到无穷（flow to infinity）：非负流 `@@M@@\theta@@` 在每个非根顶点处流入等于流出，其质量为根处流出总量；在约束"每条无穷射线 `@@M@@\xi@@` 上 `@@M@@\sum_{e\in\xi}(\lambda^{-2|e|}\theta(e))^2\le1@@`"下的最大流质量称为带边阻 `@@M@@\lambda^{-2|e|}@@` 的 `@@M@@L^3@@` 容量 `@@M@@\operatorname{Cap}_{3,\lambda}(T)@@`。主定理：重构优势极限 `@@M@@a_\infty(T,\lambda)>0@@` 当且仅当 `@@M@@\operatorname{Cap}_{3,\lambda}(T)>0@@`。与 Pemantle–Peres 的两个 Ising 判据相比，这里指数取 `@@M@@L^3@@` 而阻取平方的 `@@M@@\lambda^{-2|e|}@@`。排除 `@@M@@\lambda=1@@` 是本质的：单条无穷射线即可完美重构，但其容量为零。

## 证明思路
用二次信息 `@@M@@m=4\E|p-\unif|^2@@` 度量后验。关键输入是姊妹篇的封闭后验律类 `@@M@@\mathcal C@@` 及矩节省不等式：合并两个 `@@M@@\mathcal C@@` 中的实验时 `@@M@@m(\mu\star\nu)\le m(\mu)+m(\nu)-c(\E A^2m+m\E A^2)@@`，`@@M@@c=1/1000@@`。先证"重构 `@@M@@\Rightarrow@@` 容量为正"：对每个顶点 `@@M@@v@@` 取其后代信息的极限 `@@M@@m_v@@`，作变量替换 `@@M@@y_v=m_v+Km_v^3@@`，把分支处节省转化为即使在独生顶点处也有严格正节省（因子 `@@M@@r-r^3@@`，`@@M@@r=\lambda^2@@`）的非线性递推，再放大为 `@@M@@y_v\le r\sum_w y_w/\sqrt{1+2\delta y_w^2}@@`，这正是 Pemantle–Peres 容量递推的形式；据此逐边分配系数伸缩地构造流，沿射线求和与单调收敛给出势不超过 1、质量为正的容许流。反过来证"容量 `@@M@@\Rightarrow@@` 重构"：把容许流缩小 `@@M@@\epsilon@@` 倍，在每个深度 `@@M@@n@@` 的叶观测前额外加独立噪声，顶点 `@@M@@v@@` 处噪声参数取 `@@M@@t_v=\sqrt{X_v/3}@@`，其中 `@@M@@X_v=r^{-|v|}\Theta(v)@@` 是深度加权流；次可加性使传播信息保持在该流轮廓之下。为控制合并造成的信息损失，除 `@@M@@m@@` 外还跟踪带符号三阶矩 `@@M@@\tau=\E[x_1x_2x_3]@@`：在四态坐标下乘积公式中的混合二次项恰好抵消，剩余损失由三阶矩控制，而三阶矩沿边传播的因子是 `@@M@@\lambda^3@@` 而非 `@@M@@\lambda^2@@`。再按流采样一条射线，把累积损失化为单条路径上的和；两个传播因子的差留下可和核 `@@M@@\lambda^{j-i}@@`，容量约束控制路径平方和 `@@M@@\sum_jX_{v_j}^2\le Q\epsilon^2@@`。选取与深度无关的小 `@@M@@\epsilon@@` 使总损失至多 `@@M@@M/2@@`，从而每个深度都有 `@@M@@\widehat m_\rho\ge M/2@@`、`@@M@@a_n\ge M/16@@`，重构成立。整个论证不需要各分支规模可比，也不需要严格的指数增长不等式。

## 可信度与备注
本文与同族姊妹篇《The Reconstruction Threshold for the Ferromagnetic Four-State Potts Model》直接衔接：其封闭类与矩节省命题（命题 3.2）是本文的显式引用输入，本文其余论证全部在文内完成；同族三态论文则处理对称三态通道。主结果暂无形式化证明；本文自身的推导是解析的，但其核心输入在姊妹篇中由精确算术的多项式证书验证，请以社区核验为准。OpenAI 官方声明：未经形式化的结果可能有问题。

{% endraw %}
