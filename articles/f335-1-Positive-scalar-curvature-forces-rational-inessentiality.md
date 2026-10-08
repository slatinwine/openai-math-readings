---
layout: default
title: "Positive scalar curvature forces rational inessentiality"
family: "335"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Positive scalar curvature forces rational inessentiality

> 结果族 335：Gromov's integral scalar-curvature bound for simplicial volume　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

想象给封闭空间"充气"：正标量曲率相当于每个点都往外鼓，像球面那样。四十多年前 Gromov 与 Lawson 猜想：有一类"摊开后没有洞"的空间（比如高维环面），无论怎么设计量长规则都充不起来。本文证明了这个猜想——不需要 spin、基本群或维数上限等任何附加假设，并进一步说：这类空间就算只要求"不瘪"（曲率非负），也只剩完全平坦一条路。

**关键词卡片**

- 标量曲率（scalar curvature）：每一点的平均弯曲度；球面为正，马鞍面为负
- 正标量曲率度量（positive scalar curvature metric）：处处严格外鼓的量长规则
- 非对称流形（aspherical manifold）：万有覆盖可缩的封闭空间，如环面——"摊平后没有洞"
- 分类映射（classifying map）：把流形送到其基本群的分类空间的标准映射
- 有理非本质（rationally inessential）：分类映射把有理基本类打到零——空间不"本质地"缠绕自己的基本群

**看个具体例子**

主定理的数字版：若 `@@M@@\mathrm{Scal}\ge\kappa\gt0@@`，则 `@@M@@(c_M)_*[M]=0\in H_n(B\pi_1(M);\mathbb Q)@@`。代入 `@@M@@M=T^n@@`（`@@M@@n@@` 维环面，万有覆盖是可缩的 `@@M@@\mathbb R^n@@`）：它不容许处处正曲率的度量；更强地，`@@M@@T^n@@` 上任何 `@@M@@\mathrm{Scal}\ge0@@` 的度量都必平坦——这正是刚性推论。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="20" y="35" font-size="16" fill="#333">充得起 vs 充不起</text>
<ellipse cx="140" cy="140" rx="80" ry="50" fill="none" stroke="#333" stroke-width="2"/>
<ellipse cx="140" cy="148" rx="32" ry="16" fill="none" stroke="#333" stroke-width="2"/>
<text x="55" y="225" font-size="14" fill="#333">环面 Tⁿ（覆盖可缩）</text>
<text x="85" y="250" font-size="14" fill="#c33">正曲率：无解</text>
<circle cx="400" cy="140" r="60" fill="none" stroke="#333" stroke-width="2"/>
<ellipse cx="400" cy="140" rx="60" ry="18" fill="none" stroke="#999" stroke-dasharray="5 4"/>
<text x="345" y="225" font-size="14" fill="#333">球面（覆盖不可缩）</text>
<text x="365" y="250" font-size="14" fill="#343">正曲率：可行</text>
</svg>

</div>

**为什么值得关心**

它一举解决了 Gromov–Lawson 非对称猜想，扫清了此前各路线的 spin、维数与基本群限制；其"非负曲率⇒单纯体积为零"的推论，正是姊妹篇定量积分不等式的关键输入。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了有理本质 (rationally essential) 闭流形不容许正标量曲率度量，从而解决 Gromov–Lawson 非对称猜想：闭非对称流形上非负标量曲率度量必平坦、实单纯体积为零——全程无需 spin、基本群或维数限制。

## 问题背景

哪些闭流形容许正标量曲率 (positive scalar curvature) 度量，是黎曼几何的核心问题。Schoen–Yau 用稳定极小超曲面做降维，Gromov–Lawson 用 Dirac 算子与可放大性 (enlargeability) 给出经典障碍；Chodosh–Li 在 2024 年用广义肥皂泡把非对称障碍推进到 4、5 维。Gromov 与 Lawson 在 1983 年前后猜测：闭的非对称 (aspherical，即万有覆盖可缩) 流形不容许正标量曲率度量。Hanke 在 2011 年把它提炼为更一般的同调形式——有理本质流形不容许正标量曲率；Gromov 与 Yau 也先后陈述过这一同调障碍。此前的各条路线分别受制于 spin 条件、极小超曲面正则性（维数 `@@M@@\le 7@@`）或基本群假设，始终无法在全部维数、全部群上一举成立。

## 主要结果

**主定理**：设 `@@M@@M^n@@`（`@@M@@n\ge 2@@`）为闭连通定向光滑流形。若 `@@M@@M@@` 容许严格正标量曲率的黎曼度量，则分类映射 (classifying map) `@@M@@c_M:M\to B\pi_1(M)@@` 把有理基本类打到零：`@@M@@(c_M)_*[M]=0\in H_n(B\pi_1(M);\mathbb{Q})@@`，即 `@@M@@M@@` 是**有理非本质** (rationally inessential) 的。定理不需要 spin、万有覆盖 spin 或基本群假设，群可含挠、分类空间可以没有有限维模型。四个推论：(1) **Gromov–Lawson 非对称猜想**：闭光滑非对称流形（可否定向皆可）不容许正标量曲率度量；(2) **刚性**：闭非对称流形上的非负标量曲率度量必平坦 (flat)；(3) **目标映射障碍**：若存在到闭非对称流形 `@@M@@N@@` 的非零度连续映射，则 `@@M@@M@@` 不容许处处严格正的标量曲率，特别地连通和 `@@M@@N\#P@@` 亦然；(4) **单纯体积消失**：正维数的闭定向光滑流形若有非负标量曲率度量，则其实单纯体积 `@@M@@\|M\|=0@@`。

## 证明思路

反证，设 `@@M@@\mathrm{Scal}\ge\kappa\gt 0@@` 且 `@@M@@M@@` 有理本质。第一步构造比较数据与局部度数：在充分大的词度量比较尺度 `@@M@@R@@` 处，借助带 `@@M@@\Gamma@@`-主覆盖的辅助流形得到覆盖 `@@M@@X\to M\times C@@`，检测闭上链在 `@@M@@X@@` 上给出紧支撑上同调类；相对对偶与有理实现产生闭参数流形 `@@M@@A@@`，与 `@@M@@X@@` 作纤维积得 `@@M@@Z=X\times_C A@@`。其上的紧支撑映射 `@@M@@G:Z\to\mathbb{R}^q@@` 满足 `@@M@@\deg(G,\Omega,0)\ne 0@@`、在 `@@M@@\partial\Omega@@` 上 `@@M@@\|G\|_\infty\gt 3@@`，且沿纤维方向 `@@M@@\max_i|dG_i|\le J/R@@`、`@@M@@\log q\le JR@@`，常数 `@@M@@J@@` 与 `@@M@@R@@` 无关。第二步做图缩短 (shortening)：给每个坐标配一个反比扭曲圆 (warped circle)，图变形沿该坐标微分的方向放大纤维度量并释放有利的标量项，再用非线性椭圆方程把坐标替换成微分更短的新坐标；处理全部 `@@M@@q@@` 个坐标的一轮称为一"趟" (pass)。关键在于各坐标造成的逆度量减少在 `@@M@@n@@` 维纤维余切空间上望远镜式叠加，总迹不超过 `@@M@@n@@`、与坐标个数无关，从而避免付出 `@@M@@q@@` 倍标量代价。逐趟把 `@@M@@L@@` 除以 4、`@@M@@w@@` 除以 2，坐标误差与标量损失均为可求和级数，总纤维标量损失 `@@M@@O((2+\log q)R^{-2})=O(R^{-1})@@` 被 `@@M@@\kappa@@` 吸收；同时在参数流形上放大度量压小参数方向微分，最终得到 `@@M@@Z\times\T^{kq}@@` 上标量曲率 `@@M@@\ge\kappa/2@@` 的稳定化度量，以及映到 `@@M@@S^q@@`、紧集外常值的非零度映射 `@@M@@F_k@@`，其微分按 `@@M@@4^{-k}@@` 指数缩小。第三步制造与圆圈个数无关的障碍：拉回球面中固定的环面管道得紧带 `@@M@@W@@`，加倍并保留圆因子，得到映到 `@@M@@S^1\times\T^{q-1}\times\T^{kq}@@` 的非零度闭流形；圆因子的常值放大是局部等距、不损失标量曲率，故 Cecchini–Schick 局部环面定理（`@@M@@2\pi\epsilon\ge\sqrt\chi\,\mathrm{Length}(J)@@`，无 spin、无维数上限）给出的阈值 `@@M@@\delta(q,\kappa/2)@@` 不依赖圆圈总数 `@@M@@kq@@`。先取 `@@M@@R@@` 足够大以固定 `@@M@@q@@` 与全部比较数据，再取 `@@M@@k@@` 足够大使 `@@M@@F_k@@` 的微分低于阈值，与该障碍矛盾，定理得证。推论 (2) 另走一步：约化引理给出正标量曲率或 Ricci 平凡二择一，后者经 Cheeger–Gromoll 分裂定理与可缩性排除非平凡分裂因子，故度量平坦。

## 可信度与备注

本文是本家族"定性"的一半：其推论 (4)（非负标量曲率 `@@M@@\Rightarrow@@` 实单纯体积为零）正是姊妹篇《An integral scalar curvature bound for real simplicial volume》整个定量论证唯一引用的外部结果，两篇互相咬合成 Gromov 猜想（定性消失 + 定量积分不等式）的完整证明。终局几何工具是已发表的 Cecchini–Schick 局部环面定理，其余构造均为本文新创。两篇均无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
