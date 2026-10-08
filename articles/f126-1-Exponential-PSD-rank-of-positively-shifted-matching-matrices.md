---
layout: default
title: "Exponential PSD rank of positively shifted matching matrices"
family: "126"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Exponential PSD rank of positively shifted matching matrices

> 结果族 126：Exponential semidefinite complexity of perfect matching　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

皮影戏的秘密:在幕布后摆一个简单的物件,调整角度,让影子恰好是复杂图案。数学里也有这招——用高维空间里一个"好说话"的几何体,投影出低维的复杂形状。论文问:描述"完美匹配"的那个复杂多面体,能不能由一个小物件投影出来?答案:不能,物件必须指数级大。

**关键词卡片**

- 完美匹配(perfect matching):把图上全部顶点两两配对的方案。
- 匹配多面体(matching polytope):所有匹配方案的加权混合填成的几何体,边面极多。
- 半定提升(semidefinite lift):把多面体表示成高维半正定锥切片的投影,是比线性表述更灵活的"皮影戏"。
- PSD 秩(PSD rank):这种表示所需的最小维度,越小越省料。
- 松弛矩阵(slack matrix):多面体的"体检表",其 PSD 秩恰好等于最小提升规模。

**看个具体例子**

论文的矩阵:行是奇割(奇数个顶点的集合 `@@M@@U@@`),列是完美匹配 `@@M@@M@@`,元素为 `@@M@@|M\cap\delta(U)|-1+\rho@@`。取 `@@M@@K_6@@`、`@@M@@U=\{1,2,3\}@@` 看两个匹配:

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="280" y="24" text-anchor="middle" font-size="16" fill="#333">K₆ 上的奇割 U={1,2,3} 与两种完美匹配</text><text x="280" y="48" text-anchor="middle" font-size="13" fill="#c0392b">红边 = 穿过割 δ(U)、连接 U 内外的边;虚线框标出 U 与其补</text><rect x="48" y="80" width="56" height="168" rx="28" fill="none" stroke="#888" stroke-dasharray="6,5"/><rect x="196" y="80" width="56" height="168" rx="28" fill="none" stroke="#888" stroke-dasharray="6,5"/><text x="76" y="72" text-anchor="middle" font-size="13" fill="#888">U</text><text x="224" y="72" text-anchor="middle" font-size="13" fill="#888">U 补</text><line x1="76" y1="104" x2="76" y2="164" stroke="#666" stroke-width="2.5"/><line x1="76" y1="224" x2="224" y2="104" stroke="#c0392b" stroke-width="3"/><line x1="224" y1="164" x2="224" y2="224" stroke="#666" stroke-width="2.5"/><circle cx="76" cy="104" r="16" fill="#fff" stroke="#333" stroke-width="2"/><circle cx="76" cy="164" r="16" fill="#fff" stroke="#333" stroke-width="2"/><circle cx="76" cy="224" r="16" fill="#fff" stroke="#333" stroke-width="2"/><circle cx="224" cy="104" r="16" fill="#fff" stroke="#333" stroke-width="2"/><circle cx="224" cy="164" r="16" fill="#fff" stroke="#333" stroke-width="2"/><circle cx="224" cy="224" r="16" fill="#fff" stroke="#333" stroke-width="2"/><text x="76" y="109" text-anchor="middle" font-size="13">1</text><text x="76" y="169" text-anchor="middle" font-size="13">2</text><text x="76" y="229" text-anchor="middle" font-size="13">3</text><text x="224" y="109" text-anchor="middle" font-size="13">4</text><text x="224" y="169" text-anchor="middle" font-size="13">5</text><text x="224" y="229" text-anchor="middle" font-size="13">6</text><rect x="308" y="80" width="56" height="168" rx="28" fill="none" stroke="#888" stroke-dasharray="6,5"/><rect x="456" y="80" width="56" height="168" rx="28" fill="none" stroke="#888" stroke-dasharray="6,5"/><text x="336" y="72" text-anchor="middle" font-size="13" fill="#888">U</text><text x="484" y="72" text-anchor="middle" font-size="13" fill="#888">U 补</text><line x1="336" y1="104" x2="484" y2="104" stroke="#c0392b" stroke-width="3"/><line x1="336" y1="164" x2="484" y2="164" stroke="#c0392b" stroke-width="3"/><line x1="336" y1="224" x2="484" y2="224" stroke="#c0392b" stroke-width="3"/><circle cx="336" cy="104" r="16" fill="#fff" stroke="#333" stroke-width="2"/><circle cx="336" cy="164" r="16" fill="#fff" stroke="#333" stroke-width="2"/><circle cx="336" cy="224" r="16" fill="#fff" stroke="#333" stroke-width="2"/><circle cx="484" cy="104" r="16" fill="#fff" stroke="#333" stroke-width="2"/><circle cx="484" cy="164" r="16" fill="#fff" stroke="#333" stroke-width="2"/><circle cx="484" cy="224" r="16" fill="#fff" stroke="#333" stroke-width="2"/><text x="336" y="109" text-anchor="middle" font-size="13">1</text><text x="336" y="169" text-anchor="middle" font-size="13">2</text><text x="336" y="229" text-anchor="middle" font-size="13">3</text><text x="484" y="109" text-anchor="middle" font-size="13">4</text><text x="484" y="169" text-anchor="middle" font-size="13">5</text><text x="484" y="229" text-anchor="middle" font-size="13">6</text><text x="150" y="272" text-anchor="middle" font-size="14" fill="#333">匹配 A={12,34,56}:穿割 1 条 → 表项 ρ</text><text x="410" y="272" text-anchor="middle" font-size="14" fill="#333">匹配 B={14,25,36}:穿割 3 条 → 表项 2+ρ</text></svg>

</div>

匹配穿过奇割的次数必为奇数(1、3、5……),所以矩阵元素都非负。主定理:这张表的 PSD 秩至少 `@@M@@2^{cn}@@`,于是完美匹配多面体的任何精确半定提升,规模都至少 `@@M@@2^{c_0 n}@@`。

**为什么值得关心**

线性表述的指数下界早已知晓,但"半定投影会不会更省"是 Rothvoss 提出的悬案;本文给出否定答案,为"用扩展模型高效求解匹配问题"的设想划出了理论边界。

> 暂无形式化证明(AI 结果待核验)

## 一句话结论

对任意固定的 `@@M@@0<\rho<1@@`，奇割—完美匹配矩阵 `@@M@@|M\cap\delta(U)|-1+\rho@@` 的实半定秩（PSD rank）至少为 `@@M@@2^{cn}@@`；因此完全图完美匹配多面体的任何精确半定提升（semidefinite lift）规模必为指数级，负面回答了 Rothvoss 的"多项式规模半定提升"问题。

## 问题背景

扩展表述（extended formulation）用高维凸集的投影紧凑描述复杂多面体。Yannakakis 的非负分解框架与 Rothvoß 2014 年的工作证明完美匹配多面体（perfect matching polytope）`@@M@@P_n@@` 的任何线性表述都有指数规模，但换成正半定锥仿射切片的投影（半定提升）可能更省，线性下界不自动排除它。Gouveia–Parrilo–Thomas 的锥分解定理把最小半定提升规模等同于松弛矩阵（slack matrix）的 PSD 秩，"匹配是否有多项式规模半定提升"由此悬而未决。此前仅有对称情形（Braun 等）与非负秩（Braun–Pokutta）的指数下界；Kaniewski–Lee–de Wolf 还给出容许误差 `@@M@@2^{-\sqrt{n/2}}@@` 的亚指数近似分解，可见精确性必须严苛对待。本文的分离泛函承袭 Grigoriev 针对 Tseitin 矛盾的低度泛函。

## 主要结果

主定理：存在 `@@M@@c>0@@`，对每个固定 `@@M@@0<\rho<1@@` 有 `@@M@@n_0(\rho)@@`，偶数 `@@M@@n\ge n_0@@` 时 `@@M@@\rank_{psd} A_n(\rho)\ge 2^{cn}@@`。行标为 `@@M@@K_n@@` 的奇数大小顶点集 `@@M@@U@@`（奇割，odd cut），列标为完美匹配 `@@M@@M@@`，元素 `@@M@@|M\cap\delta(U)|-1+\rho@@`（`@@M@@\delta(U)@@` 为割集）；完美匹配穿过奇集的次数为正奇数，矩阵非负。PSD 秩是最小的 `@@M@@r@@`，使存在实对称半正定因子 `@@M@@F_U,G_M\in\R^{r\times r}@@` 满足 `@@M@@A_{U,M}=\tr(F_UG_M)@@`。端点 `@@M@@\rho=1@@` 有 `@@M@@\binom n2@@` 规模对角分解，指数下界到不了它。推论：`@@M@@A_n(0)@@` 与 Edmonds 描述（度等式+非负性+奇割不等式）的松弛矩阵 `@@M@@T_n(0)@@` 的 PSD 秩均为 `@@M@@2^{c_0n}@@`，故 `@@M@@P_n@@` 的每个精确半定提升规模至少 `@@M@@2^{c_0n}@@`。给 `@@M@@A_n(0)@@` 因子追加标量块即得 `@@M@@A_n(\rho)@@` 分解，故 `@@M@@\rank_{psd} A_n(\rho)\le\rank_{psd} A_n(0)+1@@`，平移版蕴含未平移版。

## 证明思路

反证法，循 Lee–Raghavendra–Steurer 路线以低度分离泛函对付平方和，难点是把匹配问题传输到奇偶系统并处理正平移。

先造分离泛函。以 `@@M@@d=100@@` 个随机完美匹配的并构造 `@@M@@t@@` 点 `@@M@@d@@`-正则二部扩展图（expander）`@@M@@H@@`，割满足 `@@M@@|\delta_H(W)|\ge\beta d\min\{|W|,t-|W|\}@@`。给各顶点指定总和为奇的奇偶位 `@@M@@b_i@@`，则满足各处奇偶约束的位指派 `@@M@@y@@` 必有某边两端不同，故 `@@M@@f_\epsilon(y)=\sum_e\mathbf 1_{\{y_{u,e}\ne y_{v,e}\}}-\epsilon@@` 严格正。但论文在块 Fourier 特征（Fourier character）上定义线性泛函 `@@M@@\mathcal D@@`：若 `@@M@@p@@` 的关联像是割且块度（block degree）`@@M@@\le 2D@@`（`@@M@@D=\lfloor t/1000\rfloor@@`），就用扩展性选唯一小侧 `@@M@@S(p)@@` 并给 `@@M@@\chi_p@@` 赋值 `@@M@@(-1)^{\sum_{i\in S(p)}b_i}@@`，否则为零。各割陪集上 `@@M@@\mathcal D(\chi_p\chi_{p'})@@` 是秩一半正定块，故对块度 `@@M@@\le D@@` 的 `@@M@@g@@` 有 `@@M@@\mathcal D(g^2)\ge0@@`，而 `@@M@@\mathcal D(f_\epsilon)=-\epsilon<0@@`。

再把奇偶系统嵌入匹配：把 `@@M@@H@@` 每个顶点换成 `@@M@@k@@` 个顶点的胞（`@@M@@k@@` 为先固定的常数），奇割行取每胞中规定奇偶的子集，列匹配每胞留 `@@M@@d@@` 个端子、其余顶点胞内配对，辅助边连接对应端子；局部限制使胞内对割位相等，于是 `@@M@@|M\cap\delta(U)|-1+\rho=f(y)@@` 精确成立。若存在规模 `@@M@@r\le 2^t@@` 的分解，先以 `@@M@@\log\det@@` 势归一化迹，再对行因子作限制平均，得 `@@M@@\tr(\overline F_m(y)G_{M(m)})=f(y)@@`。

最后证明小分解迫使 `@@M@@f@@` 接近低块度平方和（sum of squares），靠三个组件：局部平均引理借置换对称性（非常特征空间维数 `@@M@@\ge k/2@@`）与迹估计得方差压缩 `@@M@@O(k^{-1/4}\sqrt{\log k})@@`；正交分裂引理以 Helstrom 型谱投影把 `@@M@@L@@` 个 PSD 矩阵分入正交子空间；乘积平滑定理逐坐标归纳，以直和堆叠实现新平均、控制新频率重叠并分配分支，势每步至多翻倍。于是可选 `@@M@@m@@` 使 `@@M@@\overline F_m=\sum_q H_q^{\mathsf T}H_q@@` 且加权 Fourier 质量极小；把每分支截断到中心邻域 `@@M@@\mathrm{dist}\le D@@`，弃量被指数权重压至 `@@M@@n(4L)^{-2t}@@`，故 `@@M@@f_*@@` 一致逼近 `@@M@@f@@`。乘以 `@@M@@\chi_q@@` 把保留频率平移到块度 `@@M@@\le D@@` 而平方不变（支撑平移原理），故 `@@M@@\mathcal D(f_*)\ge0@@`；但范数界给出 `@@M@@|\mathcal D(f-f_*)|\to0@@`，与 `@@M@@\mathcal D(f)=-\epsilon@@` 矛盾。故 `@@M@@r>2^t\ge 2^{n/(2k)}@@`。

## 可信度与备注

本文是结果族 126 的主定理载体，本批次该族仅此一篇。局部平均、正交分裂、乘积平滑三个组件独立成节，可单独核验与复用，增强可信度。按任务元信息，主结果暂无 Lean 形式化证明；OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。

{% endraw %}
