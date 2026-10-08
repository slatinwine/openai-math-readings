---
layout: default
title: "Polynomial removal fails for ordered binary matrices"
family: "190"
discipline: "Combinatorics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Polynomial removal fails for ordered binary matrices

> 结果族 190：Polynomial removal fails for ordered binary matrices　·　学科：Combinatorics　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

玩"找茬"：一张巨大的 0-1 表格里藏着许多与你手里模板一模一样的图案，问要改多少格才能毁掉所有图案？直觉说：如果非改很多格不可（离"干净"很远），图案一定多得随手可抓。本文造出一张固定的 `@@M@@66\times66@@` 模板，让这个直觉在"行列有顺序的 0-1 矩阵"世界里彻底失灵——所谓有序，就是拷贝里行与行的先后、列与列的先后都不能乱。

**关键词卡片**

- 有序拷贝（ordered copy）：保持行序、列序，且 0 与 1 都逐格对上的复制。
- 删除引理（removal lemma）：图论经典结论——离"无图案"很远，则图案数量巨大。
- 多项式界（polynomial bound）：图案数 `@@M@@\ge c\,\epsilon^C n^{2k}@@` 型下界；本文否定其存在。
- 采样测试器（tester）：随机抽若干行列、看子表是否含模板就下结论的算法。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="110" y="42" text-anchor="middle" font-size="14">模板本体 P</text>
<path d="M70 70 H150 V150 H70 Z M70 110 H150 M110 70 V150" fill="none" stroke="#222" stroke-width="1.5"/>
<text x="90" y="97" text-anchor="middle" font-size="14">1</text>
<text x="130" y="97" text-anchor="middle" font-size="14">0</text>
<text x="90" y="137" text-anchor="middle" font-size="14">1</text>
<text x="130" y="137" text-anchor="middle" font-size="14">1</text>
<text x="350" y="42" text-anchor="middle" font-size="14">宿主矩阵 A（示意 6×6）</text>
<path d="M260 60 V240 M290 60 V240 M320 60 V240 M350 60 V240 M380 60 V240 M410 60 V240 M440 60 V240 M260 60 H440 M260 90 H440 M260 120 H440 M260 150 H440 M260 180 H440 M260 210 H440 M260 240 H440" fill="none" stroke="#999" stroke-width="1"/>
<text x="275" y="80" text-anchor="middle" font-size="13">0</text>
<text x="305" y="80" text-anchor="middle" font-size="13">1</text>
<text x="335" y="80" text-anchor="middle" font-size="13">0</text>
<text x="365" y="80" text-anchor="middle" font-size="13">0</text>
<text x="395" y="80" text-anchor="middle" font-size="13">1</text>
<text x="425" y="80" text-anchor="middle" font-size="13">0</text>
<text x="275" y="110" text-anchor="middle" font-size="13">1</text>
<text x="305" y="110" text-anchor="middle" font-size="13">0</text>
<text x="335" y="110" text-anchor="middle" font-size="13">1</text>
<text x="365" y="110" text-anchor="middle" font-size="13">1</text>
<text x="395" y="110" text-anchor="middle" font-size="13">0</text>
<text x="425" y="110" text-anchor="middle" font-size="13">1</text>
<text x="275" y="140" text-anchor="middle" font-size="13">0</text>
<text x="305" y="140" text-anchor="middle" font-size="13">1</text>
<text x="335" y="140" text-anchor="middle" font-size="13">0</text>
<text x="365" y="140" text-anchor="middle" font-size="13">1</text>
<text x="395" y="140" text-anchor="middle" font-size="13">1</text>
<text x="425" y="140" text-anchor="middle" font-size="13">0</text>
<text x="275" y="170" text-anchor="middle" font-size="13">1</text>
<text x="305" y="170" text-anchor="middle" font-size="13">1</text>
<text x="335" y="170" text-anchor="middle" font-size="13">1</text>
<text x="365" y="170" text-anchor="middle" font-size="13">0</text>
<text x="395" y="170" text-anchor="middle" font-size="13">0</text>
<text x="425" y="170" text-anchor="middle" font-size="13">1</text>
<text x="275" y="200" text-anchor="middle" font-size="13">0</text>
<text x="305" y="200" text-anchor="middle" font-size="13">0</text>
<text x="335" y="200" text-anchor="middle" font-size="13">1</text>
<text x="365" y="200" text-anchor="middle" font-size="13">1</text>
<text x="395" y="200" text-anchor="middle" font-size="13">0</text>
<text x="425" y="200" text-anchor="middle" font-size="13">0</text>
<text x="275" y="230" text-anchor="middle" font-size="13">1</text>
<text x="305" y="230" text-anchor="middle" font-size="13">1</text>
<text x="335" y="230" text-anchor="middle" font-size="13">0</text>
<text x="365" y="230" text-anchor="middle" font-size="13">0</text>
<text x="395" y="230" text-anchor="middle" font-size="13">1</text>
<text x="425" y="230" text-anchor="middle" font-size="13">0</text>
<rect x="289" y="119" width="62" height="62" fill="none" stroke="#b03030" stroke-width="2.5" stroke-dasharray="7 5"/>
<text x="280" y="264" text-anchor="middle" font-size="13">有序拷贝：行序、列序保持，0 与 1 都要逐格对上</text>
</svg>

</div>

定理数字版：存在宿主矩阵 `@@M@@A_h@@`，改动比例至少 `@@M@@\epsilon_h=(386h+2)^{-2}@@` 才能变成"不含 `@@M@@H@@`"，但有序拷贝数不超过 `@@M@@\epsilon_h\,2^{-h}\,n^{132}@@`——随 `@@M@@h@@` 增大，任何 `@@M@@c\,\epsilon^C n^{132}@@` 型多项式下界都被击穿。

**为什么值得关心**

它否定了 2007 年起被反复陈述的多项式有序矩阵删除猜想，还连带表明固定精度的采样测试器需要超多项式的采样量。值得注意的是，定性版本依然成立：每个固定距离都有正的拷贝下界，爆炸的只是数量级——"定性成立、定量爆炸"的罕见标本。玄机在于：毁掉现有拷贝只需 `@@M@@2^h@@` 个格子，但这么一改会立刻造出新拷贝，任何彻底修复仍须改动至少 `@@M@@4^h@@` 个格子。

> 已 Lean 形式化

## 一句话结论

本文构造了一个固定的 `@@M@@66\times66@@` 0-1 矩阵 `@@M@@H@@`，并给出一列宿主矩阵：它们离不含 `@@M@@H@@` 很远，但所含 `@@M@@H@@` 的有序拷贝（ordered copy）密度低于任何多项式界，从而否定了有序二值矩阵的多项式删除引理猜想。

## 问题背景

图删除引理（removal lemma）断言：若图离 `@@M@@H@@`-free 至少 `@@M@@\epsilon@@` 远，则必含约 `@@M@@\delta n^{v(H)}@@` 个 `@@M@@H@@`；定量版本追问 `@@M@@\delta@@` 能否取成 `@@M@@\epsilon@@` 的幂（如 `@@M@@\delta\ge c\,\epsilon^C@@`）。把问题搬到带行序与列序的 0-1 矩阵上——拷贝须保持行、列各自的顺序，且 0 与 1 都要匹配——就得到多项式有序矩阵删除猜想：Alon–Fischer–Newman（2007）率先发问，Alon–Ben-Eliezer（2020 年问题 1.4）与 Gishboliner–Shapira 综述（猜想 4.5）明确陈述。定性版本已由 Alon–Ben-Eliezer–Fischer 证得：每个固定距离都有正的拷贝下界，但定量依赖未知。此前的非多项式下界例子都依赖宿主中的第三个符号，纯二值情形悬而未决。本文用单个 66 阶模式将其否定。

## 主要结果

论文显式给出 `@@M@@66\times66@@` 模式 `@@M@@H@@`：左上 `@@M@@64\times64@@` 块是"锚"（anchor）`@@M@@S@@`——除右下角嵌入全部 32 个五比特字的块外均为 `@@M@@S(u,v)=\mathbf 1[u\ne v]@@`；最末两行两列构成"本体"（body）`@@M@@P=\begin{pmatrix}1&0\\1&1\end{pmatrix}@@`。主定理：对每个 `@@M@@h\ge1@@`，取 `@@M@@n_h=(386h+2)2^h@@`、`@@M@@\epsilon_h=(386h+2)^{-2}@@`，存在 `@@M@@n_h\times n_h@@` 二值矩阵 `@@M@@A_h@@`，同时满足 `@@M@@\operatorname{dist}_H(A_h)\ge\epsilon_h@@`（改成 `@@M@@H@@`-free 至少须改动 `@@M@@\epsilon_h n_h^2@@` 个格子，且 0、1 两个方向都可改）与拷贝数不等式 `@@M@@N_H(A_h)/n_h^{132}\le\epsilon_h2^{-h}@@`。于是对任何常数 `@@M@@c,C>0@@`，沿此序列 `@@M@@N_H(A_h)/(\epsilon_h^C n_h^{132})\to0@@`，形如 `@@M@@N_H\ge c\,\epsilon^C n^{2k}@@` 的多项式界无从成立。附带推论：仅当采样子矩阵含 `@@M@@H@@` 才拒绝的典型行–列采样测试器（tester），要保持固定拒绝概率需 `@@M@@q\ge\exp(\Omega(\epsilon_h^{-1/2}))@@` 个采样，为超多项式。

## 证明思路

宿主 `@@M@@A_h@@` 的行列由深度 `@@M@@h@@` 的二叉树索引：每个内部结点在每根轴上挂一个"加"块与一个"减"块，叶层两块合一；再前置 `@@M@@6h@@` 组模式锚块与一个哑块（dummy），共 `@@M@@n=(386h+2)2^h@@` 个位置。证明分两半。

先证距离下界，即改动少于 `@@M@@m^2=4^h@@` 格必有拷贝。在每根轴上均匀选取一条根到叶路径及各锚块、哑块的代表；凡涉及锚、哑或根层的"受保护"格子，其行、列被同时选中的概率恰为 `@@M@@1/m^2@@`，对改动集 `@@M@@E@@` 作并界，`@@M@@|E|<m^2@@` 时必存在一次完全避开 `@@M@@E@@` 的选取。再假定改后的 `@@M@@B@@` 是 `@@M@@H@@`-free，则每个模式下本体 `@@M@@P@@` 被禁。而未动的根格子给出 `@@M@@B(x_0^+,y_0^+)=1@@` 与 `@@M@@B(x_0^-,y_0^-)=0@@`；`@@M@@V@@` 模式借哑列提供全 1 列，把值沿相邻行层下传，`@@M@@W@@` 模式再借哑行传入相邻列层。归纳到叶层时加、减两号共享同一格子，它须同时等于 1 与 0，矛盾。归一化即得 `@@M@@\operatorname{dist}_H\ge d_h^{-2}=\epsilon_h@@`。

再证拷贝上界：原矩阵里拷贝极少。关键是"锚刚性"——`@@M@@S@@` 右下角含全部 32 个五比特字，而变元行的 1 在每个类中呈后缀（suffix）分布，五个变元列上至多实现 27 个字，故任一拷贝在某根轴上必有超过 32 个锚位；结合 `@@M@@S@@` 前 32 行的高密度与不同模式锚块间的全 0 条目，逼出整个拷贝落在单一模式的锚组内，本体行列也落入该模式指定集合。最后逐一核查四种模式：序关系（子块夹在父块两块之间）与赋值规则 `@@M@@\mathbf 1[p\le q]@@`、`@@M@@\mathbf 1[p<q]@@` 处处与 `@@M@@P@@` 冲突，唯独叶层减号模式 `@@M@@p=q@@` 幸存——拷贝的 `@@M@@(65,65)@@` 格必落在仅含 `@@M@@m@@` 格的叶对角 `@@M@@\mathcal L_h@@` 上，故 `@@M@@N_H\le m\,n^{130}@@`，密度 `@@M@@\le 2^{-h}/d_h^2@@`。两半合并即得定理。

论文评注还点出玄机：全部原拷贝只须 `@@M@@2^h@@` 格即可命中，但把这些格子改成 0 会立刻造出新拷贝，任何修复仍须改动至少 `@@M@@4^h@@` 格——"命中集"（hitting set）与"修复"（repair）的鸿沟，正解释了既有正结果为何帮不上忙。

## 可信度与备注

本篇是结果族 190 的唯一手稿，主结果按任务元数据已配 Lean 形式化证明，正文距离与计数两半各自独立又互相咬合。它否定的是多项式版本猜想，定性删除引理不受影响，反而说明其定量依赖必不可多项式化。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本文主结果既已形式化，读者仍可对照原文核查显式构造。

{% endraw %}
