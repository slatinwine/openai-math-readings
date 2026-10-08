---
layout: default
title: "Universality of critical quench autocorrelations in the Sherrington--Kirkpatrick model"
family: "227"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Universality of critical quench autocorrelations in the Sherrington--Kirkpatrick model

> 结果族 227：Critical SK autocorrelation processes and dynamics across the temperature transition　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

一杯热水突然扔进冰水（"淬火"），它多久、以什么方式恢复平静？论文给"玻璃态磁铁"做了同样的体检：让上百万个随机取向的小磁针从完全混乱的状态出发开始演化，测量它们对初始状态的记忆如何衰减。结论：记忆按精确标度衰减，且极限与内部耦合的微观细节完全无关。

**关键词卡片**

- SK 自旋玻璃（Sherrington–Kirkpatrick model）：`@@M@@n@@` 个 `@@M@@\pm1@@` 自旋两两耦合、耦合系数随机带正负的全连接模型。
- 淬火（quench）：从简单的非平衡初态（这里是独立公平自旋）出发，在固定温度下演化。
- 自相关（autocorrelation）：系统此刻与稍早构型的平均相似度，是"记忆"的度量。
- 临界慢化（critical slowing down）：临界温度 `@@M@@\beta=1@@` 处记忆时间随 `@@M@@n@@` 发散，正确的观测窗口是 `@@M@@n^{2/3}@@`。
- 普适性（universality）：高斯与 `@@M@@\pm1@@`（Rademacher）两类耦合给出完全相同的极限定律。

**看个具体例子**

标度关系是公式卡：时间以 `@@M@@T_n=n^{2/3}@@` 为单位、幅度乘 `@@M@@n^{1/3}@@`，即淬火自相关 `@@M@@B_{n,J}(s,t)=n^{-2/3}\sum_i\mathbb E[\sigma_i(sT_n)\sigma_i((s{+}t)T_n)]@@`。代入 `@@M@@n=10^6@@`：一步"宏观时间"对应 `@@M@@10^4@@` 次自旋更新，相关幅度要放大 100 倍才能看清极限曲线。两个极限函数的关系如下图：等待时间 `@@M@@s\to\infty@@` 时，淬火极限 `@@M@@B_g(s,\cdot)@@` 弛豫回平稳极限 `@@M@@A_g@@`。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><line x1="70" y1="225" x2="500" y2="225" stroke="#333" stroke-width="2"/><path d="M512,225 l-12,-6 l0,12 z" fill="#333"/><line x1="70" y1="225" x2="70" y2="50" stroke="#333" stroke-width="2"/><path d="M70,38 l-6,12 l12,0 z" fill="#333"/><path d="M70,55 C160,85 240,135 500,200" fill="none" stroke="#333" stroke-width="3" stroke-dasharray="8 6"/><path d="M70,95 C160,125 240,165 500,218" fill="none" stroke="#c0392b" stroke-width="3"/><line x1="310" y1="190" x2="310" y2="162" stroke="#666" stroke-width="2"/><path d="M310,154 l-5,10 l10,0 z" fill="#666"/><text x="320" y="205" font-size="13">等待 s→∞</text><text x="352" y="138" font-size="13">A：平稳极限(虚线)</text><text x="412" y="245" font-size="13">B：淬火(实线)</text><text x="200" y="255" font-size="13">滞后 t（宏观时间）</text><text x="12" y="115" font-size="13">相关强度</text></svg>

</div>

**为什么值得关心**

它首次严格刻画了临界点处非平衡起点的动力学极限：极限由初态选定，并随等待时间弛豫回平稳极限，与数值物理的长期猜想相印证。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了 SK 自旋玻璃在临界温度 `@@M@@\beta=1@@` 处，从独立均匀自旋"淬火"（quench）出发的两点自相关函数与平稳自相关函数联合收敛到同一个随机泛函极限，且该极限对高斯与拉德马赫（Rademacher）两类耦合普适；淬火极限随等待时间增长弛豫回平稳极限。

## 问题背景

Sherrington 与 Kirkpatrick 在 1975 年提出这个全连接自旋玻璃模型，它是理解无序系统慢弛豫的标杆。"淬火"指让系统从简单的非平衡初态（如独立公平自旋）出发，再在给定温度下演化。在临界温度 `@@M@@\beta=1@@` 处，弛豫时间随系统尺寸发散，`@@M@@n^{2/3}@@` 尺度的临界窗口成为正确的观测尺度：Billoire–Campbell 的数值实验早已猜测平稳自相关形如 `@@M@@n^{-1/3}F(t/n^{2/3})@@`，而 Sompolinsky–Zippelius、Cugliandolo–Kurchan 的动力学平均场理论只处理软自旋且取极限次序不同。此前姊妹篇（平稳情形的临界定理）只解决了平衡态起点；非平衡淬火起点的极限是否存在、由什么选定，一直没有严格结果。难点在于：临界处谱边缘本身是随机的（GOE 边缘过程），而淬火初态在窗口内到达的"入口律"可能依赖边缘之外的额外随机性。

## 主要结果

模型为零场 SK 的 Gibbs 测度 `@@M@@\pi_{n,J}(\sigma)\propto\exp\{n^{-1/2}\sum_{i<j}J_{ij}\sigma_i\sigma_j\}@@`，每个格点配速率为一的热浴（heat-bath）时钟。记 `@@M@@T_n=n^{2/3}@@`，定义平稳自相关 `@@M@@A_{n,J}(t)=n^{-2/3}\sum_i\langle\sigma_i,P^J_{tT_n}\sigma_i\rangle_{\pi_{n,J}}@@` 与淬火自相关 `@@M@@B_{n,J}(s,t)=n^{-2/3}\sum_i\mathbb E_{\nu_n}^J[\sigma_i(sT_n)\sigma_i((s+t)T_n)]@@`，其中 `@@M@@\nu_n@@` 是均匀初态，`@@M@@s@@` 为等待时间、`@@M@@t@@` 为滞后。定理证明：无论耦合 `@@M@@J_{ij}@@` 取高斯还是 `@@M@@\{\pm1\}@@` 上的拉德马赫律，`@@M@@(A_{n,J},B_{n,J})@@` 在紧集上一致依律收敛到同一对随机函数 `@@M@@(A_g,B_g)@@`。这里 `@@M@@g@@` 是 GOE 上边缘过程（edge process，即 `@@M@@n^{2/3}(2-\lambda_a)@@` 的联合极限），`@@M@@\Pi_g@@` 是由它构造的条件边缘测度（conditioned edge measure），`@@M@@S_t^g=e^{-tc_*H_g}@@` 是对应 Dirichlet 形式生成的马尔可夫半群，`@@M@@c_*@@` 是确定的微观系数。淬火极限由密度族 `@@M@@h_s^g@@`（满足 `@@M@@h_{s+t}^g=S_t^g h_s^g@@`）给出，`@@M@@B_g(s,t)=\sum_a\int h_s^g x_a (S_t^g x_a)\,d\Pi_g@@`；当 `@@M@@s\downarrow0@@` 时 `@@M@@h_s^g\Pi_g@@` 在乘积拓扑下弱收敛到 `@@M@@\delta_0@@`，当 `@@M@@s\to\infty@@` 时 `@@M@@B_g(s,\cdot)@@` 一致趋近平稳极限 `@@M@@A_g@@`。

## 证明思路

证明先做一个谱分离：高斯情形下给相互作用矩阵补一条 GOE 对角线不改变 Gibbs 测度，于是在特征向量坐标系 `@@M@@x_a=n^{-1/3}\langle u_a,\sigma\rangle@@` 下有恒等式 `@@M@@n^{-2/3}\sigma\cdot\sigma'=\sum_a x_a(\sigma)x_a(\sigma')@@`，从而 `@@M@@B_{n,J}(s,t)=\sum_a\mu[w_s x_a P^J_{tT_n}x_a]@@`，其中 `@@M@@w_s@@` 是时刻 `@@M@@sT_n@@` 的相对密度——这把"淬火到达的律"与"之后的弛豫"拆开。第一步做预热（warming）估计：用尺度 `@@M@@p@@` 的嵌套高斯观测把特征值截断在 `@@M@@2-p^2@@`，配合熵的反证论证，在紧阈值 `@@M@@k_p=np^3@@` 之上得到对一切初态一致的密度与核控制。第二步用有限马尔可夫预解式压缩界住平稳松弛能量定理中的优化子，得到子序列上的强半群收敛，产出由 `@@M@@S_t^g@@` 演化的正时间密度族——但它可能仍含 `@@M@@g@@` 之外的随机性。第三步是关键的入口律选定（entrance selection）：证明权重 `@@M@@p_i(x)=x_i^2/(2r_iM_g(x))@@` 沿某序列逃离每个固定有限集这一条件唯一确定密度族；技术上通过角坐标 SDE 消去公共投影与漂移，将平方约束化为一个标量 Volterra 方程，再用带停时的耦合论证压缩映射式地证明固定 `@@M@@g@@` 的唯一性与 `@@M@@\delta_0@@` 边界，最后可测地从 `@@M@@g@@` 构造出该族。最后用 Chatterjee 的元素替换（entry replacement）做无序比较：两类耦合对归一化相互作用的前三阶导数匹配，四阶导数必须带消失因子，配合静态重叠尾估计与转移区间二叉树上的正反条件估计，把联合迹律迁移到拉德马赫情形。

## 可信度与备注

本文主结果尚无 Lean 形式化证明，属于 OpenAI 以"论文级证明"标准发布的预印本，官方声明未经形式化的结果可能存在问题，请以社区核验为准。它的平稳输入（条件边缘测度、闭形式与系数 `@@M@@c_*@@`）直接取自同族姊妹篇《Functional universality of critical SK autocorrelations》，两文互相咬合：姊妹篇给出平衡态极限，本文在其上叠加淬火入口律的选定与弛豫，构成结果族 227 在临界点的完整动力学图景。

{% endraw %}
