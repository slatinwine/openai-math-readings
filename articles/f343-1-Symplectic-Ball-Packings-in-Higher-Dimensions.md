---
layout: default
title: "Symplectic Ball Packings in Higher Dimensions"
family: "343"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Symplectic Ball Packings in Higher Dimensions

> 结果族 343：Symplectic ball packing in higher dimensions　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

往箱子里塞球，直觉上只看总体积；但辛几何的"魔箱"多一条怪规矩——任何两球大小之和不得超过箱子大小，哪怕体积富余也白搭。这篇论文证明：从实六维开始，规矩就只有"体积"和"两球"这两条，再无隐藏关卡；实四维则远比这复杂，存在一整族更细的填充障碍。

**关键词卡片**

- 辛嵌入（symplectic embedding）：保住面积尺结构、不折叠不撕开的塞球方式。
- 容量（capacity）：辛球的大小刻度，等于 π 乘以半径平方。
- 体积障碍（volume obstruction）：所有球的体积之和必须小于箱子体积。
- Gromov 两球障碍（two-ball obstruction）：任意两球容量之和不得超过箱子容量，源自 1985 年 Gromov 的探针方法。
- 伪全纯曲线（pseudoholomorphic curve）：探测辛刚性的"探针曲面"。

**看个具体例子**

主定理代入实六维（n = 3）、箱子容量 R = 1：两个容量 0.49 的球满足体积条件 `@@M@@0.49^3+0.49^3\approx 0.24<1@@` 与两球条件 `@@M@@0.49+0.49=0.98<1@@`，必能辛嵌入；换成两个 0.51 的球，体积更小（`@@M@@\approx 0.27<1@@`），但 `@@M@@0.51+0.51=1.02>1@@`，必塞不进。两个条件缺一不可：体积是常识，两球条件则是辛世界独有的刚性。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<circle cx="210" cy="140" r="105" fill="#eef4ff" stroke="#345" stroke-width="3"/>
<circle cx="172" cy="118" r="42" fill="#ffffff" stroke="#c33" stroke-width="3"/>
<circle cx="248" cy="172" r="42" fill="#ffffff" stroke="#c33" stroke-width="3"/>
<text x="130" y="112" font-size="13" fill="#c33">R1 = 0.49</text>
<text x="218" y="180" font-size="13" fill="#c33">R2 = 0.49</text>
<text x="150" y="268" font-size="15" fill="#345">箱子容量 R = 1</text>
<text x="355" y="72" font-size="14" fill="#345">塞得进：</text>
<text x="355" y="97" font-size="14" fill="#345">0.49³ + 0.49³ ≈ 0.24 &lt; 1</text>
<text x="355" y="122" font-size="14" fill="#345">0.49 + 0.49 = 0.98 &lt; 1</text>
<text x="355" y="160" font-size="14" fill="#c33">换成两个 0.51 的球：</text>
<text x="355" y="185" font-size="14" fill="#c33">体积仍小，但 1.02 &gt; 1，</text>
<text x="355" y="210" font-size="14" fill="#c33">怎么摆都塞不进</text>
</svg>

</div>

**为什么值得关心**

正面解决 Siegel–Yao 猜想 A：高维辛球填充的判定从此化为两条初等不等式，与四维的复杂迷宫形成鲜明对照；论文三种情形共用同一套"比较—填充"机制，几何模型取自射影空间中曲线的退化。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

论文证明：实维数至少 6 时，容量为 `@@M@@R_1,\ldots,R_k@@` 的有限个闭辛球可两两不交地辛嵌入容量 `@@M@@R@@` 的开球，当且仅当 `@@M@@\sum_i R_i^n<R^n@@` 且 `@@M@@R_i+R_j<R@@`。这正面解决了 Siegel–Yao 猜想 A：高维辛球填充的刚性恰由体积与 Gromov 两球障碍完全刻画。

## 问题背景

辛球填充（symplectic ball packing）问：标准辛球到底能"塞"进多大的球？Gromov 在 1985 年用伪全纯曲线（pseudoholomorphic curve）方法证明了两球障碍：容量 `@@M@@R_1,R_2@@` 的两个球嵌入容量 `@@M@@R@@` 的球，必须 `@@M@@R_1+R_2\le R@@`——这是体积完全看不到的辛刚性（symplectic rigidity）。实四维情形后来被发现还存在大量更细的填充障碍，判定问题至今复杂。2025 年 Siegel 与 Yao 提出猜想 A，断言在 `@@M@@2n\ge6@@` 的高维，体积条件加上两球条件就是全部障碍。此前 Biran、Buse–Hind、Buse–Hind–Opshtein 等人的填充稳定性（packing stability）定理只覆盖等球或容量一致很小的情形，任意容量、任意有限个球的完整判据一直缺位。

## 主要结果

主定理：对一切整数 `@@M@@n\ge3@@`、`@@M@@k\ge1@@` 及正实容量 `@@M@@R,R_1,\ldots,R_k@@`，存在辛嵌入 `@@M@@\bigsqcup_{i=1}^k B^{2n}(R_i)\hookrightarrow\operatorname{Int}B^{2n}(R)@@`，当且仅当 `@@M@@\sum_{i=1}^k R_i^n<R^n@@` 且对每对 `@@M@@i\ne j@@` 有 `@@M@@R_i+R_j<R@@`。容量（capacity）定义为 `@@M@@\pi@@` 乘以欧氏半径的平方，嵌入定义在闭源球的开邻域上——"闭源、开目标"的约定解释了严格不等号。第一个不等式是体积障碍，第二个是 Gromov 两球障碍；必要性平凡，论文的全部工作在充分性。

## 证明思路

先把目标归一化为容量 1；由两球条件至多一个球容量 `@@M@@\ge1/2@@`，于是分三种情形。全部容量 `@@M@@<1/2@@` 时，在 `@@M@@\mathbb{P}^n@@` 中取 `@@M@@n-1@@` 个二次超曲面的完全交（complete intersection）曲线 `@@M@@C@@`，其亏格（genus）`@@M@@g(C)=1+(n-3)2^{n-2}\ge1@@`；沿 `@@M@@C@@` 做到法锥的退化（deformation to the normal cone），得到以 `@@M@@C@@` 为底、以向下多面体（downward polytope）`@@M@@\Delta@@` 约束的环面域为纤维的模型，其极限面积廓为 `@@M@@H_0(p)=2^{n-1}(1-2\sum p_j)@@`。大球且 `@@M@@n\ge4@@` 时，先在爆破（blowup）`@@M@@\Bl_o\mathbb{P}^n@@` 上以类 `@@M@@H-aE@@` 预留中心球，把其余的球装进外层球壳，几何模型由"先取超平面、再取其中完全交曲线"的两级法锥构造给出。六维（`@@M@@n=3@@`）最精巧：此时平面二次曲线亏格为零，提供不了填充引理所需的环柄，作者改用过两个标记点的平面三次曲线（亏格 1），通过三次曲线族的退化算得极限底面积 `@@M@@H_0(p)=9(b-p_1-p_2)-2(s-p_1-p_2)_+@@`，其中 `@@M@@s=1-a@@`、`@@M@@b=(2-a)/3@@`，两个标记点各贡献一个被扣除的对数质量，再配合严格保持矩 `@@M@@p_1@@` 的辛平行迁移与一次较低水平的 Kähler 切割（symplectic cut）实现该模型。

三种情形此后共用同一机制。令 `@@M@@P(p)=H_0(p)-\sum_i(r_i-\sum_jp_j)_+@@`，体积条件恰好化为 `@@M@@P@@` 有正的平均值。哈密顿比较引理利用凸函数的坐标向递增重排（increasing rearrangement）保持积分的性质，使 `@@M@@F\mapsto R(\lambda F-P)@@` 成为压缩映射，其不动点给出一致间隙；嵌套平面圆盘的哈密顿映射再以小于该间隙的误差实现重排，最终得到环面函数 `@@M@@K@@` 与哈密顿微分同胚 `@@M@@q@@`，使 `@@M@@(K-P)\circ q<K@@`。曲面填充引理随即在底曲面的环柄上取两个横截环圈与一个具非零周期的闭一形式，把上述严格不等式转化为互不相交的"层"，每层恰容纳一个球；相对 Moser 论证把填充拉回原模型并保持边界条件。最后经法锥迁移命题，把紧填充送回 `@@M@@\mathbb{P}^n\setminus H_\infty@@`——它辛同胚于容量 1 的开球。

## 可信度与备注

本文暂无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。本结果族（343）目前仅此一篇手稿，暂无姊妹篇直接互证；论文内部由比较引理、曲面填充引理与几何迁移命题层层衔接，三种情形共用同一套"比较—填充"机制，结构自洽。证明大量使用标准工具（Bertini 定理、Koszul 分解、Moser 方法、辛切割、相对 Serre 消没），均附证明或明确文献出处，便于专家逐层核查。

{% endraw %}
