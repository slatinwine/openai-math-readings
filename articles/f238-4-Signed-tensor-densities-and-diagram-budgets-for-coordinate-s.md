---
layout: default
title: "Signed tensor densities and diagram budgets for the Thorp shuffle"
family: "238"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Signed tensor densities and diagram budgets for the Thorp shuffle

> 结果族 238：Optimal logarithmic mixing of the Thorp shuffle　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了对 `@@M@@2^d@@` 张牌的 Thorp 洗牌，存在绝对常数 `@@M@@L@@`，使 `@@M@@L@@` 次坐标扫掠后整副牌的置换密度与均匀律的平方 `@@M@@L^2@@` 距离趋于零，混合时间（mixing time）为 `@@M@@\Theta(d)@@` 次物理洗牌，与支撑集下界同阶，最优阶就此落定。

## 问题背景

Thorp 洗牌源于 Thorp 1973 年对 Faro 洗牌的研究：把 `@@M@@N=2^d@@` 张牌对半分开、两两配对、用独立的公平硬币决定每对是否交换。在二进制位置 `@@M@@\{0,1\}^d@@` 上，一次物理洗牌是 `@@M@@(x_1,\ldots,x_d)\mapsto(x_2,\ldots,x_d,x_1+\xi)@@`；剥离确定性坐标旋转后，一次"坐标扫掠"（coordinate sweep）依次访问 `@@M@@d@@` 个坐标方向，恰等于 `@@M@@d@@` 次物理洗牌。单张牌一次扫掠后就均匀，但各牌共享开关，其联合置换律会残留所有单牌检验都看不见的信息。此前最好的上界是 Morris 2013 年的 `@@M@@O(d^3)@@` 物理洗牌（更早还有 `@@M@@O(d^{44})@@`、`@@M@@O(d^{29})@@` 与对一切偶数牌数的 `@@M@@O((\log N)^4)@@`），而硬币数只给出下界 `@@M@@2d-O(1)@@`，中间隔着数个多项式因子。本文在对称群 `@@M@@S_n@@` 的每个不可约表示（irreducible representation）中直接控制这份联合信息，把上界压到 `@@M@@O(d)@@`。

## 主要结果

论文用两类"张量颜色"加一个"标出余部"来刻画表示：偶色描述杨图（Young diagram）的长行，奇色描述长列且交换张量因子时带符号，余部由若干带不同标记的位置表示，其尺寸以熵节省计入界。设 `@@M@@u+v+l=n@@`，`@@M@@\alpha\vdash u@@`、`@@M@@\beta\vdash v@@`、`@@M@@\gamma\vdash l@@`，若带号张量积 `@@M@@V_\alpha\otimes V_{\beta^{\mathrm t}}\otimes V_\gamma@@` 出现在 `@@M@@V_\lambda@@` 限制到子群 `@@M@@S_u\times S_v\times S_l@@` 的分解中（只要求出现，不要求重数为一），定义未归一化熵 `@@M@@F(\alpha,\beta)=\sum_{i:\alpha_i>0}\alpha_i\log\frac{u+v}{\alpha_i}+\sum_{j:\beta_j>0}\beta_j\log\frac{u+v}{\beta_j}@@`。主定理断言：存在只依赖固定常数的整数 `@@M@@r@@`，对一切 `@@M@@d@@`、一切 `@@M@@\lambda\vdash n=2^d@@`、一切如上出现，有 `@@M@@\log\bigl(D_\lambda\operatorname{Tr}(B_n^*B_n)^r\bigr)\le\eta_d F(\alpha,\beta)+g_n(l)@@`，其中 `@@M@@B_n@@` 是扫掠的平均算子，`@@M@@D_\lambda@@` 是 Specht 模（Specht module）维数，`@@M@@g_n(l)=\max\{0,\kappa_d\,l\log n-l\log(n/l)\}@@`。关键的 `@@M@@-l\log(n/l)@@` 项意味着标出位置越稀疏越省钱。推论：存在绝对正整数 `@@M@@L@@` 使全置换密度 `@@M@@f_{d,L}@@` 满足 `@@M@@\mathbb E_{U_{S_n}}|f_{d,L}-1|^2\to0@@`，且对初始牌序一致；同时 `@@M@@t_{\mathrm{mix}}(d)=\Theta(d)@@`。论文还由此得到一个近似均匀的置换采样器，其输出每个坐标只需对共享随机源做 `@@M@@O(\log n)@@` 次自适应查询。

## 证明思路

收缩有两个来源。第一个处理"稀疏表示"：当 `@@M@@\lambda@@` 的第一行长为 `@@M@@n-k@@` 且 `@@M@@k@@` 很小时，分支法则（branching rule）把 `@@M@@V_\lambda@@` 嵌入有序 `@@M@@k@@` 元组空间；先对子集交错求和，使中心化的核在遭遇图（encounter graph）有孤立顶点——某张牌不与任何别的牌共享开关——时恒为零；剩下的非负核经一次往返实验转化为"第二趟无孤立点"的概率，再用带权图上按有根平面森林计数的权和估计，压到 `@@M@@e^{O(k)}(2dk/n)^{k/4}@@` 量级。第二个来源处理其余表示：把坐标近似对半分组，位置排成矩形，第一个子扫掠在列内、第二个在行内；两套子群的表示分解互不交换，因此必须控制两个张量型空间之间的夹角。角度估计在每条线上取一个迹为一的正定矩阵，在保拢单群上平均其张量幂，使之支配到指定带号型的投影；平均列密度提供逆平方根，把行内格子统一归一化，使单格子因子在整个矩形上的均值至多为一；移除 `@@M@@l@@` 个格子的代价至多 `@@M@@e^l@@`，而全局类型的熵节省被保留。带标记的位置贡献另一路局部输入：行移动再列移动要把一个命名点送回原格，除非两步都固定该点（论文的 marked-grid 示意），故迹把群代数系数限制到点稳定子群，其正性的正则迹因子恰是下降阶乘（falling factorial）的倒数；对标记位置求和仍保留父界所需的熵项。最后，由于扫掠算子非正规，作者用 Araki–Lieb–Thirring 不等式对矩递归，用 Schatten–Hölder 不等式传到重复前向扫掠；选取无余部且 `@@M@@F(\alpha,\beta)\le C_0\log D_\lambda@@` 的出现，即得 `@@M@@D_\lambda@@` 的负幂，再用 Diaconis–Shahshahani 有限群 Fourier 分析对全部 `@@M@@\lambda@@` 求和完成推论。下界则来自硬币串计数：`@@M@@t@@` 次物理洗牌的支撑至多 `@@M@@2^{tn/2}@@` 个置换，远小于 `@@M@@n!@@`。

## 可信度与备注

本文主结果暂无形式化证明，请以社区核验为准。它是结果族 238 中的一条独立路线：姊妹篇《Conditional coordinate sweeps and analytic transfer》的主结果已 Lean 形式化，《A strict four-row permanent inequality and permutation moments》用 permanent 不等式独立逼近，三者共同支撑 `@@M@@\Theta(d)@@` 这一最优阶。论文后半部还给出多条替代机制（降算子、协方差、调和元组耦合、钩预算等）互相印证。按 OpenAI 官方声明，未经形式化的结果可能有问题，阅读时宜以形式化版本与社区核验为准。

{% endraw %}
