---
layout: default
title: "Positive scalar curvature and uniform codimension-two width"
family: "336"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Positive scalar curvature and uniform codimension-two width

> 结果族 336：Spectral scalar curvature, Urysohn width, and macroscopic dimension　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

想象把一大团揉皱的纸收进展示架：只要纸面每一处的鼓包程度都不低于一条底线，整团纸就能被连续压扁、挂到一个薄了两层的骨架上，每个挂点下只垂着一小撮纸。这篇论文证明的正是这件事：曲率条件会逼着高维空间在宏观上"瘦"掉两个维度。

**关键词卡片**

- 标量曲率（scalar curvature）：空间每点平均弯曲程度的数值，越大越弯；Scal ≥ 1 即处处不低于基准弯度。
- 单纯复形（simplicial complex）：由点、线段、三角形等拼成的骨架，维数是所用拼块的最高维数。
- 纤维（fiber）：把整个空间映射到骨架后，落在骨架同一点上的全部原像，即挂点下垂着的那一撮。
- 宏观维度（macroscopic dimension）：忽略小于某个尺度的细节后，空间"看起来"的维数。
- 万有覆盖（universal cover）：把空间里的环路全部摊开后得到的单连通大空间。

**看个具体例子**

把主定理代入 n = 4：任何 Scal ≥ 1 的完备无边四维流形，都存在到二维骨架的连续映射，且每根纤维的直径 ≤ C₄（只依赖维数的常数）；曲率更强、Scal ≥ σ² 时，界还按比例缩到 C₄/σ。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<circle cx="90" cy="70" r="5" fill="#345"/>
<circle cx="130" cy="50" r="5" fill="#345"/>
<circle cx="160" cy="85" r="5" fill="#345"/>
<circle cx="70" cy="115" r="5" fill="#345"/>
<circle cx="115" cy="125" r="5" fill="#345"/>
<circle cx="85" cy="165" r="5" fill="#345"/>
<circle cx="140" cy="170" r="5" fill="#345"/>
<circle cx="175" cy="130" r="5" fill="#345"/>
<text x="70" y="212" font-size="16" fill="#345">n 维流形</text>
<text x="55" y="236" font-size="14" fill="#678">标量曲率 ≥ 1</text>
<line x1="215" y1="120" x2="325" y2="120" stroke="#345" stroke-width="3"/>
<polygon points="340,112 360,120 340,128" fill="#345"/>
<text x="228" y="100" font-size="14" fill="#345">连续映射 f</text>
<g stroke="#345" stroke-width="3">
<line x1="395" y1="55" x2="525" y2="85"/>
<line x1="385" y1="115" x2="530" y2="60"/>
<line x1="405" y1="70" x2="495" y2="185"/>
<line x1="385" y1="160" x2="530" y2="150"/>
</g>
<circle cx="452" cy="102" r="6" fill="#c33"/>
<line x1="452" y1="108" x2="452" y2="150" stroke="#c33" stroke-width="4"/>
<text x="385" y="215" font-size="16" fill="#345">n−2 维骨架</text>
<text x="370" y="238" font-size="14" fill="#c33">纤维直径 ≤ C_n</text>
</svg>

</div>

**为什么值得关心**

它把"局部弯 ⇒ 全局瘦"这一 Gromov 提出近三十年的直觉，在所有 n ≥ 4 量化成精确定理，并顺带推出正曲率闭流形的万有覆盖宏观维度 ≤ n − 2、闭非球面流形不容许正标量曲率度量。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

在每个 `@@M@@n\ge4@@` 证明 Gromov 标量曲率猜想的量化连续形式：`@@M@@\mathrm{Scal}\ge1@@` 的完备无边 `@@M@@n@@` 维流形可连续映到 `@@M@@n-2@@` 维复形，整根纤维直径只依赖 `@@M@@n@@`；并推出闭正标量曲率流形的万有覆盖在一切 `@@M@@n\ge2@@` 有连续宏观维度 `@@M@@\le n-2@@` 等系论。

## 问题背景

标量曲率下界是局部条件，Gromov 的宏观维度（macroscopic dimension）纲领（1996）预测它有全局后果：在受控尺度上流形应坍缩两个维度；量化版进一步要求映射到余二维多面体、且整根纤维的直径有界。此前三维有 Gromov–Lawson、Liokumovich–Maximo、Liokumovich–Wang 等水平集估计；非球面障碍（aspherical obstruction）在四、五维由 Chodosh–Li 与 Gromov 得到；spin 情形需强 Novikov 猜想（Bolotov、Bolotov–Dranishnikov 等），且这些都是万有覆盖上的定性结论。Kumar–Sen 还证明固定尺度宏观标量曲率不足以给出此类宽度界，说明逐点条件不可再弱化。本文对任意完备流形给出只依赖维数的定量定理，不设定向、spin、有界几何假设。

## 主要结果

主定理：对每个整数 `@@M@@n\ge4@@` 存在有限常数 `@@M@@C_n@@`，凡 `@@M@@\mathrm{Scal}_g\ge1@@` 的连通完备无边光滑 `@@M@@n@@`-流形 `@@M@@(M,g)@@` 都有连续映射 `@@M@@f:M\to K@@` 到维数至多 `@@M@@n-2@@` 的单纯复形，使整根纤维（fiber）`@@M@@\diam_g f^{-1}(y)\le C_n@@`，即 `@@M@@\UW_{n-2}(M,g)\le C_n@@`；若 `@@M@@\mathrm{Scal}\ge\sigma^2@@`，界为 `@@M@@C_n/\sigma@@`。系论一：闭流形的填充半径（filling radius）`@@M@@\le C_n/(2\sigma)@@`，即 Gromov 猜想 `@@M@@A^-@@` 在 `@@M@@n\ge4@@` 的闭流形情形。系论二：闭正标量曲率流形（`@@M@@n\ge2@@`）的万有覆盖的连续宏观维度（continuous macroscopic dimension）`@@M@@\le n-2@@`。系论三：`@@M@@n\ge4@@` 的闭非球面流形不容许正标量曲率度量。

## 证明思路

证明由两块独立输入拼成。几何拉伸块：以带二次预算 `@@M@@V(t)=t^2+T^2@@` 的压力律驱动规定平均曲率（prescribed mean curvature）图方程，在紧支撑内把选定集合对的距离放大固定倍数；曲率损失由固定背景度量的迹（trace）下降支付，并在一轮内对可数个标签逐级抵消（telescope），故总预算不随标签数增长。逐轮更换工作尺度恢复储备，对数翘曲（log warp）细分把漂移型标量下界 `@@M@@\mathcal D(h,t)=\mathrm{Scal}+2\Delta t-|dt|^2\ge2/5@@` 转换成有限圆积上的真标量曲率。

切割块是核心创新：每次切割同时保留两个"体侧"（外接柱形末端）与一面低一维的"墙"（wall），全部片段（packet）带相容乘积端与记录原位置的坍缩映射；归纳不变量只要求在 `@@M@@m@@` 维片段上、于"至少 `@@M@@m-1@@` 个未决标签"聚集处保持正稳定化标量曲率，各标签配有极点型压力剖面 `@@M@@2|\nabla\mu_j|\le a_r\mu_j^2+\Pi_j@@` 与强制核。处理一个标签时以加权周长减压力体积的极小化产生"真切割"，维数 `@@M@@\ge8@@` 时它可有奇点；在奇点附近用额外压力剖面做"屏蔽"，使未决标签在危险区被强制决定，费用由 Hardy 估计、体–柱缝紧性、集中位势的最大值估计支付；带闸正则化再把真切割换成光滑墙，并由正上解添上每组 399 个新圆因子，把二次型优势转成逐点标量不等式。可数标签靠"整片段有限例外数据"处理：径向首切后每个整片段只有有限个标签与翘曲非常数，被动标签的位势是空间常数且被精确复现。若 `@@M@@n-1@@` 面墙相交，会得到完备一维片段，其翘曲标量公式强迫 `@@M@@\arctan@@` 的导数有负常数下界，在长于 `@@M@@2\pi/\sqrt{\lambda_r}@@` 的区间上积分便与反正切的有界性矛盾，故墙的交重数 `@@M@@\le n-2@@`。

最后把柱形压缩回原流形的窄领域，得到位移 `@@M@@<1@@` 的坍缩映射 `@@M@@q@@` 与符号坐标 `@@M@@t_i\in[0,1]@@`：在强制集上取 `@@M@@0@@` 或 `@@M@@1@@`，过渡区含于重数 `@@M@@\le n-2@@` 的墙邻域；阶梯三角剖分给出到 `@@M@@n-2@@` 维复形的连续映射。同一纤维的两点共享某个等于 `@@M@@1@@` 的坐标，二者的 `@@M@@q@@` 像便落在同一外球，故 `@@M@@d_g<4D+2=C_n@@`。

## 可信度与备注

本文是结果族 336 的基座：两篇十月姊妹篇把本文结论分别推广到谱条件 `@@M@@-4\Delta+\mathrm{Scal}\ge1@@`（`@@M@@n\ge4@@`）与三维图宽度，其中高维谱篇直接引用本文的分区定理作为拓扑输入。主结果暂无 Lean 形式化证明，请以社区核验为准；按 OpenAI 官方声明，未经形式化的结果可能有问题。非球面系论另有同批"有理非本质性"论文给出独立证明；填充半径与宏观维度系论分别沿用 Gromov 的比较原理与 `@@M@@A^+\Rightarrow B@@` 论证。

{% endraw %}
