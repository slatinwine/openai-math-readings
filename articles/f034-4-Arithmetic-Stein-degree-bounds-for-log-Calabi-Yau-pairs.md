---
layout: default
title: "Arithmetic Stein-degree bounds for log Calabi–Yau pairs"
family: "034"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Arithmetic Stein-degree bounds for log Calabi–Yau pairs

> 结果族 034：Log abundance for compact Kähler spaces under logarithmic Iitaka subadditivity　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
证明 Birkar 的 Stein 度猜想（收缩到点情形）对普通 `@@M@@\mathbb Q@@`-对成立：特征零域上射影 log Calabi–Yau 对中，系数不小于 `@@M@@t@@` 的边界素分量在底域上的常量域次数被仅依赖维数与 `@@M@@t@@` 的整数 `@@M@@N(d,t)@@` 一致控制。

## 问题背景

对域 `@@M@@k@@` 上的真整簇 `@@M@@S@@`，Stein 度 (Stein degree) 定义为 `@@M@@\operatorname{sdeg}(S/\Spec k)=\dim_k H^0(S,\mathcal O_S)@@`，它度量结构态射的"有限部分"，即使维数固定也可能很大。Birkar（2026）对 log Calabi–Yau 纤维化提出 Stein 度一致性猜想；Birkar–Qu 已在代数闭的特征零域上证明规范化版本。但在任意特征零域上，边界分量还可能携带有限的"算术"扩张，必须一并控制。本文对更强的不变量 `@@M@@c(S/k)=[k_S:k]@@`（`@@M@@k@@` 在 `@@M@@k(S)@@` 中的相对代数闭包次数，即几何分量的个数）给出一致界——这既是猜想的收缩到点情形，也是族内姊妹篇处理一般 lc 指数与有效饭高纤维化时的关键算术输入。

## 主要结果

**定理**：对每个整数 `@@M@@d\ge1@@` 与实数 `@@M@@t>0@@`，存在 `@@M@@N(d,t)\ge1@@`，使得对任何特征零域 `@@M@@k@@` 上的射影 log canonical `@@M@@\mathbb Q@@`-对 `@@M@@(X,B)@@`——`@@M@@X@@` 正规整、`@@M@@H^0(X,\mathcal O_X)=k@@`、`@@M@@B@@` 有效、`@@M@@K_X+B\sim_{\mathbb Q}0@@`、`@@M@@\dim X=d@@`——只要素分量 `@@M@@S@@` 的系数不小于 `@@M@@t@@`，就有
`@@M@@Dc(S/k)=[k_S:k]\le N(d,t)，@@`
从而 `@@M@@\operatorname{sdeg}(S/\Spec k)\le\dim_k H^0(S^\nu,\mathcal O_{S^\nu})=c(S/k)\le N(d,t)@@`，其中 `@@M@@S^\nu@@` 是正规化。界只依赖 `@@M@@d@@` 与 `@@M@@t@@`，与域 `@@M@@k@@`、原始系数分母、被提取除子的个数等一切个体数据无关。曲线情形可显式给出 `@@M@@N(1,t)=\lceil2/t\rceil@@`。

## 证明思路

对 `@@M@@d@@` 归纳，且在每个维数同时证明一切阈值。曲线情形中 `@@M@@B@@` 有效非零迫使 `@@M@@X\cong\mathbb P^1@@`、`@@M@@\deg B=2@@`，直接得界。高维先做算术准备：Borisov–Alexeev–Borisov (BAB) 有界性给出 `@@M@@\epsilon@@`-lc Fano 簇的有界嵌入；数值平凡线丛在 klt 奇性下平凡（klt 消没加 Riemann–Roch），故 Pic 群是秩有界的自由阿贝尔群，其 Galois 作用有限、阶有界（模 `@@M@@3@@` 约化单射），于是有界次扩张 `@@M@@F/k@@` 固定极化类；再用行列式构造 `@@M@@L^{\otimes r}\otimes(\det H^0(L))^{-1}@@` 把"类不变"提升为"线丛下降"。配合有界分辨率（层数与第二 Betti 数有界）以及"单正规交叉对的 log 典范位 (lc place) 由层 (stratum) 与整权唯一决定"这一组合事实，得到核心命题：有界 `@@M@@\epsilon@@`-lc Fano 簇上对数差异 (log discrepancy) 小于 `@@M@@1@@` 的除子赋值的 Galois 轨道一致有界。

主证明如下：取 `@@M@@\mathbb Q@@`-因子 klt 模型并选定 `@@M@@b<t@@`，用带缩放的 MMP 让 `@@M@@S@@` 在某个 Mori 纤维化 `@@M@@X_1\to Z_1@@` 上相对丰富。若 `@@M@@\dim Z_1>0@@`，则 `@@M@@S@@` 水平，限制到一般纤维由低维归纳即得。若 `@@M@@Z_1=\Spec k@@`，先用 Bertini 一般成员论证把有界补下降到 `@@M@@k@@` 上，得指数 `@@M@@n=n(d,b)@@` 与 `@@M@@C_1\ge bS_1@@`；令 `@@M@@\epsilon=1/n@@`，提取全部对数差异小于 `@@M@@\epsilon@@` 的赋值得到 `@@M@@\epsilon@@`-lc 的 `@@M@@X_2@@`，再跑 MMP 得 Mori 纤维化 `@@M@@X_3\to Z@@`，此时 `@@M@@v_S@@` 的差异至多 `@@M@@1-b<1@@`。若 `@@M@@Z@@` 为点，`@@M@@X_3@@` 是 `@@M@@\epsilon@@`-lc Fano，用上述轨道命题即得。若 `@@M@@\dim Z>0@@`：把 `@@M@@v_S@@` 实现为 Fano 型模型上的素除子 `@@M@@P@@`，`@@M@@P@@` 水平时仍由归纳处理；`@@M@@P@@` 垂直时，此前 `@@M@@\pi^*S_1@@` 的有效性与大性迫使某个系数为一的例外分量 `@@M@@E_3@@` 水平，先以阈值 `@@M@@1@@` 的归纳控制其常量域，再跑 `@@M@@(-P)@@`-负的 MMP 使 `@@M@@mP'=f^*T@@`，保证 `@@M@@E@@` 与 `@@M@@P'@@` 相交。在 `@@M@@E^\nu@@` 上做保留指标 `@@M@@n@@` 的除子粘合 (adjunction)：交点素除子 `@@M@@J@@` 在差分 (different) 中的系数至少 `@@M@@1/n@@`，由 `@@M@@d-1@@` 维、阈值 `@@M@@1/n@@` 的归纳控制其常量域，域塔相乘合并两个界。最后在 `@@M@@\bar k@@` 上数关联：`@@M@@P'@@` 的几何分量构成单一 Galois 轨道，每个都包含 `@@M@@J@@` 的某个共轭的像，而每个像处系数至少 `@@M@@b@@` 的分量至多 `@@M@@2/b@@` 个（归结为 klt 曲面奇点的商奇性并爆破计数），得 `@@M@@c(S/k)\le\frac2b\,M_{<d}(1)\,N(d-1,1/n)@@`。四种情形取最大值，最终只依赖 `@@M@@d,t@@`。

## 可信度与备注

本文暂无 Lean 形式化证明，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。它正是族内姊妹篇引用的 [SD]：《Uniform Pluricanonical Iitaka Fibrations》在从 klt 对降到一般 lc 对时，正是用本定理控制 Stein 因子分解中有限映射的度。证明策略跟随 Birkar–Qu 的双有理框架（MMP、有界补、BAB 有界性），新意在于把几何有界性转化为 Galois 轨道控制，以及垂直分量情形下"大性逼出系数一水平分量"的降维处理。`@@M@@N(d,t)@@` 为存在性结果，无显式数值。

{% endraw %}
