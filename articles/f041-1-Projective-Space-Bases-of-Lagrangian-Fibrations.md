---
layout: default
title: "Projective-space bases of Lagrangian fibrations"
family: "041"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Projective-space bases of Lagrangian fibrations

> 结果族 041：Hyperkähler SYZ and projective-space bases　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

想象一个 `@@M@@2n@@` 维、对称性极高的"水晶世界"，它可以整体压扁，投影到一片 `@@M@@n@@` 维的底座上，每根纤维都是 `@@M@@n@@` 维环面。底座长什么样？此前只在部分已知类型里核实过。本文证明：无论哪种超凯勒流形，底座只能是射影空间 `@@M@@\mathbb P^n@@`——最标准、最干净的 `@@M@@n@@` 维舞台。

**关键词卡片**

- 超凯勒流形（irreducible holomorphic symplectic manifold）：对称性比卡拉比–丘还高的基本几何对象。
- 拉格朗日纤维化（Lagrangian fibration）：把 `@@M@@2n@@` 维空间压成 `@@M@@n@@` 维底座、纤维为环面型的投影。
- 射影空间 `@@M@@\mathbb P^n@@`（projective space）：由齐次坐标描述的最标准舞台。
- 正规射影簇（normal projective variety）：允许温和奇点的合格底座。
- 阿贝尔簇（abelian variety）：高维环面，纤维的一般形状。

**看个具体例子**

`@@M@@n=1@@`：底座是一条曲线，定理说只能是 `@@M@@\mathbb P^1@@`——与 `@@M@@K3@@` 曲面椭圆纤维化的经典事实吻合。`@@M@@n=2@@`：四维空间压扁后底座必为 `@@M@@\mathbb P^2@@`。旧结论多依赖具体形变类型逐一核对，本文不要求底座光滑、不限形变类型，一刀切地宣告唯一候选人。证明分两步走：先排除"不是有限群商"的坏奇点，再消灭商奇点处的稳定子，最后借用 Hwang 的光滑情形定理收尾。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="30" text-anchor="middle" font-size="15" fill="#334455">拉格朗日纤维化：底座只能是 Pⁿ</text>
  <ellipse cx="140" cy="110" rx="38" ry="13" fill="#eef4fa" stroke="#4a90c4" stroke-width="2"/>
  <ellipse cx="240" cy="110" rx="38" ry="13" fill="#eef4fa" stroke="#4a90c4" stroke-width="2"/>
  <ellipse cx="340" cy="110" rx="38" ry="13" fill="#eef4fa" stroke="#4a90c4" stroke-width="2"/>
  <ellipse cx="440" cy="110" rx="38" ry="13" fill="#eef4fa" stroke="#4a90c4" stroke-width="2"/>
  <text x="140" y="88" font-size="12" fill="#4a90c4">环面纤维</text>
  <line x1="140" y1="123" x2="140" y2="200" stroke="#8899aa" stroke-width="1.5"/>
  <line x1="240" y1="123" x2="240" y2="200" stroke="#8899aa" stroke-width="1.5"/>
  <line x1="340" y1="123" x2="340" y2="200" stroke="#8899aa" stroke-width="1.5"/>
  <line x1="440" y1="123" x2="440" y2="200" stroke="#8899aa" stroke-width="1.5"/>
  <rect x="60" y="200" width="460" height="14" fill="#e8e0ee" stroke="#8878a0" stroke-width="1.5"/>
  <text x="280" y="242" text-anchor="middle" font-size="14" fill="#6a5a8a">底座 B ≅ Pⁿ（唯一可能的舞台）</text>
  <text x="280" y="266" text-anchor="middle" font-size="13" fill="#666666">总空间 X 为 2n 维超凯勒，纤维是 n 维环面</text>
</svg>

</div>

**为什么值得关心**

底座被钉死为 `@@M@@\mathbb P^n@@`，等于为超凯勒几何的 SYZ 镜像对称纲领拆掉了最大的一块路障，也是分类这些流形的必修一步。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
证明了紧不可约全纯辛凯勒流形上射影拉格朗日纤维化的正规射影基必是射影空间 `@@M@@\PP^n@@`，对一切维数与形变类型成立，完全解决了"射影空间基猜想"（projective-space base conjecture）。

## 问题背景
不可约全纯辛流形（irreducible holomorphic symplectic, IHS）是复几何中仅次于 Calabi–Yau 的一类基本极小模型，其上射影映射的结构由 Matsushita 的经典定理制约：任何非平凡纤维化的基维数必为 `@@M@@n=\dim X/2@@`，光滑一般纤维是阿贝尔簇（abelian variety），即所谓拉格朗日纤维化（Lagrangian fibration）；Greb–Lehn 进一步证明基是射影的。自然的问题——"基是否必同构于 `@@M@@\PP^n@@`"——就是射影空间基猜想。Hwang 在基光滑时证明结论，Greb–Lehn 推广到紧凯勒情形，所以问题被归结为基可能有何种奇点。此前无光滑性假设的结论仅限 `@@M@@K3^{[n]}@@`、广义 Kummer、`@@M@@\mathrm{OG6}@@`、`@@M@@\mathrm{OG10}@@` 等形变类型（借 Debarre–Huybrechts–Macrì–Voisin 的迷向除子定理），四维情形由 Ou 与 Huybrechts–Xu 合作排除，Müller–Xu 2026 给出若干局部判据；Shen–Yin 已算出基的交点上同调（intersection cohomology）与 `@@M@@\PP^n@@` 的有理 Betti 数一致，但这不足以给出光滑性。

## 主要结果
主定理：设 `@@M@@n\geq1@@`，`@@M@@X@@` 为 `@@M@@2n@@` 维紧 IHS 凯勒流形，带辛形式 `@@M@@\sigma@@`；`@@M@@f:X\to B@@` 是具有连通纤维的射影满全纯映射，`@@M@@B@@` 是 `@@M@@n@@` 维正规射影簇（normal projective variety），且每条纤维的每个既约分支都是 `@@M@@n@@` 维、`@@M@@\sigma@@` 在其光滑部分限制为零。则 `@@M@@B\simeq\PP^n_{\mathbb{C}}@@`。定理不假设 `@@M@@B@@` 光滑、不要求 `@@M@@b_2(X)@@` 的额外下界、不限制形变类型。附带推论：由 Kim–Oguiso–Shinder 与 Kamenova–Verbitsky 的定理，`@@M@@f@@` 没有余维一的多重纤维（multiple fibers）。

## 证明思路
证明分两大阶段。第一阶段排除"非商芽"：假设 `@@M@@B@@` 有一个不是光滑芽的有限群商的奇点，先用有限局部覆盖与反余切张量（reflexive cotangent tensors）识别局部结构，构造出一个维数小于 `@@M@@n@@` 的非空闭正规射影层化子空间 `@@M@@S_0\subset B@@`，其上带有记录有限稳定子群（stabilizer）的光滑 Deligne–Mumford 叠 `@@M@@\cS@@`。核心是数值障碍 `@@M@@\chi_{\mathrm{top}}(S_0)=0@@`：把 `@@M@@S_0@@` 的欧拉示性数经拉回到 `@@M@@X@@` 后与局部图像上的交错余切贡献相比较；为此约化到正特征，用 Frobenius 增长与 Riemann–Roch 逼出相关数值为零，张量识别用 Deligne 判别法，底变换公式依赖 Hodge 模的正像的严格性与分解定理。再证此障碍必然被违反。由引理 `@@M@@b_2(X)\geq4@@`，分三种情形：若 `@@M@@b_2\geq5@@`，先用 Matsushita 形变定理并在整个邻近 `@@M@@e@@`-Hodge 轨迹上把所有形变目标与原 `@@M@@B@@` 等同（建立在 Verbitsky 退化 twistor 构造及 Bogomolov–Déev–Verbitsky、Soldatenkov–Verbitsky 的工作之上），得到固定基族；其中的周期（period）变化迫使 `@@M@@\cS@@` 的 Hodge 上同调为对角型，于是 `@@M@@\chi_{\mathrm{top}}(S_0)=\sum_p h^{p,p}(\cS)>0@@`，矛盾。若 `@@M@@b_2=4@@` 且极化光滑纤维族等族（isotrivial），分叉与反射论证把可能的层化子空间压缩到一条椭圆曲线，其上负线丛的联络给出矛盾。若 `@@M@@b_2=4@@` 且有变化，则借助姊妹篇的强 SYZ 定理与单值（monodromy）有限指数引理，在射影小形变 `@@M@@X'@@` 上同时造出两个拉格朗日纤维化 `@@M@@f':X'\to B@@` 与 `@@M@@g:X'\to C@@`（`@@M@@g@@` 有非零极化变化），再用 `@@M@@g@@` 的单值群与 Donagi–Markman 对称周期三次型（配 Deligne 不变部分定理）迫使同样的对角 Hodge 结论，仍得矛盾。故 `@@M@@B@@` 只有商奇点。

第二阶段消灭商奇点的稳定子：把 `@@M@@f'@@` 限制到 `@@M@@g@@` 的光滑纤维 `@@M@@A@@` 上，混合 Fujiki 公式使 `@@M@@f'^*H|_A@@` 的最高自交为正，故在阿贝尔簇 `@@M@@A@@` 上丰富，`@@M@@f'|_A@@` 有限满，从而得到阿贝尔簇对 `@@M@@B@@` 的有限覆盖 `@@M@@p:A\to B@@`。在 `@@M@@B@@` 的典范光滑栈上，正像恒等式产生一个平移向量，它在每个非平凡稳定子的不动轨迹上的投影处处非零；考察有限关系 `@@M@@\mathcal R=A\times_{\mathfrak B}A@@` 的差像：取差像维数极大的含非平凡自同构的分量，极化与分叉论证又产生差像维数更大的分量，矛盾。故 `@@M@@B@@` 光滑，最后套用 Hwang 定理得 `@@M@@B\simeq\PP^n@@`。

## 可信度与备注
本文暂无形式化证明。其关键输入——非零 nef 迷向线丛的半丰富性（定理 1.1）与极化族引理——正来自同族姊妹篇 The strong hyperkähler SYZ conjecture，两篇互为支柱：姊妹篇提供 SYZ 型纤维化的存在性，本篇把它推进为基的结构定理。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
