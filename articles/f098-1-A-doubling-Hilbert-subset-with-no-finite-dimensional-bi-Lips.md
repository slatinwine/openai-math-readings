---
layout: default
title: "A doubling Hilbert subset with no finite-dimensional bi-Lipschitz embedding"
family: "098"
discipline: "Convex and metric geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A doubling Hilbert subset with no finite-dimensional bi-Lipschitz embedding

> 结果族 098：Compact counterexamples to bi-Lipschitz dimension reduction　·　学科：Convex and metric geometry　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

有限维空间里的点集有个好性质叫"加倍"：放大任何局部，细节都装得进固定数量的小格——每个球都能被至多 `@@M@@\lambda@@` 个半径减半的球盖住。Lang 与 Plaut 猜想：无穷维 Hilbert 空间里的加倍点集，是否也总能忠实地压平进某个有限维？这篇论文造出一个加倍点集，证明它永远压不平——猜想得到否定回答。

**关键词卡片**

- 加倍空间（doubling metric space）：任何球都能被至多 `@@M@@\lambda@@` 个半径减半的球覆盖；`@@M@@\lambda@@` 叫加倍常数。
- 双 Lipschitz 嵌入（bi-Lipschitz embedding）：距离的拉伸与压缩都被控制在固定倍数内的放入方式。
- 失真（distortion）：嵌入后最大拉伸与最小压缩之比。
- 雪花化（snowflaking）：把距离换成 `@@M@@d^\alpha@@` 后必可嵌入有限维（Assouad 定理），但本文处理的是原始距离。

**看个具体例子**

反例的"数字版"：点集 `@@M@@S@@` 住在 `@@M@@\ell_2@@` 里，加倍常数 `@@M@@\le76800@@`（来自 `@@M@@300\times16^2@@` 的分层计数），但对任何维数 `@@M@@k@@`、任何有限失真 `@@M@@D@@`，都不存在双 Lipschitz 嵌入 `@@M@@S\to\R^k@@`。构造按尺度分层：第 `@@M@@j@@` 层条纹宽 `@@M@@r_j=1000^{-j}@@`，水平与垂直地周期染色，点在其基点所在颜色条带内取一个位移方向。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <rect x="10" y="60" width="130" height="120" fill="none" stroke="#345" stroke-width="1.5"/>
  <line x1="10" y1="90" x2="140" y2="90" stroke="#345"/>
  <line x1="10" y1="120" x2="140" y2="120" stroke="#345"/>
  <line x1="10" y1="150" x2="140" y2="150" stroke="#345"/>
  <line x1="42" y1="60" x2="42" y2="180" stroke="#678" stroke-dasharray="3 3"/>
  <line x1="75" y1="60" x2="75" y2="180" stroke="#678" stroke-dasharray="3 3"/>
  <line x1="107" y1="60" x2="107" y2="180" stroke="#678" stroke-dasharray="3 3"/>
  <rect x="230" y="60" width="130" height="120" fill="none" stroke="#345" stroke-width="1.5"/>
  <line x1="230" y1="75" x2="360" y2="75" stroke="#345"/>
  <line x1="230" y1="90" x2="360" y2="90" stroke="#345"/>
  <line x1="230" y1="105" x2="360" y2="105" stroke="#345"/>
  <line x1="230" y1="120" x2="360" y2="120" stroke="#345"/>
  <line x1="230" y1="135" x2="360" y2="135" stroke="#345"/>
  <line x1="230" y1="150" x2="360" y2="150" stroke="#345"/>
  <line x1="230" y1="165" x2="360" y2="165" stroke="#345"/>
  <rect x="440" y="60" width="110" height="120" fill="none" stroke="#345" stroke-width="1.5"/>
  <line x1="440" y1="69" x2="550" y2="69" stroke="#345"/>
  <line x1="440" y1="78" x2="550" y2="78" stroke="#345"/>
  <line x1="440" y1="87" x2="550" y2="87" stroke="#345"/>
  <line x1="440" y1="96" x2="550" y2="96" stroke="#345"/>
  <line x1="440" y1="105" x2="550" y2="105" stroke="#345"/>
  <line x1="440" y1="114" x2="550" y2="114" stroke="#345"/>
  <line x1="440" y1="123" x2="550" y2="123" stroke="#345"/>
  <line x1="440" y1="132" x2="550" y2="132" stroke="#345"/>
  <line x1="440" y1="141" x2="550" y2="141" stroke="#345"/>
  <line x1="440" y1="150" x2="550" y2="150" stroke="#345"/>
  <line x1="440" y1="159" x2="550" y2="159" stroke="#345"/>
  <line x1="440" y1="168" x2="550" y2="168" stroke="#345"/>
  <line x1="440" y1="177" x2="550" y2="177" stroke="#345"/>
  <line x1="145" y1="120" x2="222" y2="120" stroke="#c00" stroke-width="2"/>
  <path d="M 225 120 L 214 114 L 214 126 Z" fill="#c00"/>
  <text x="148" y="104" font-size="12" fill="#c00">放大1000倍</text>
  <line x1="365" y1="120" x2="432" y2="120" stroke="#c00" stroke-width="2"/>
  <path d="M 435 120 L 424 114 L 424 126 Z" fill="#c00"/>
  <text x="364" y="104" font-size="12" fill="#c00">放大1000倍</text>
  <text x="10" y="40" font-size="14" fill="#123">第 j 层：条纹宽 r_j=1000^(-j)，水平＋垂直地染 N_j 色</text>
  <text x="10" y="205" font-size="14" fill="#123">点只在基点所在颜色条带内取一个位移方向；</text>
  <text x="10" y="227" font-size="14" fill="#123">相邻层尺度比 1000，逐层接力；总加倍常数 ≤76800，</text>
  <text x="10" y="249" font-size="14" fill="#123">却不能忠实压平进任何有限维空间</text>
</svg>

</div>

**为什么值得关心**

它否定地回答了 Lang–Plaut 问题（哪怕集合是紧的），并推出每个无穷维 Banach 空间都有这类紧反例：局部简单，远不足以保证全局可降维。

> 已 Lean 形式化

## 一句话结论

论文构造实 `@@M@@\ell_2@@` 中固定的加倍（doubling）子集 `@@M@@S@@`，其加倍常数不超过 `@@M@@76800@@`，却不能以任何有限失真（distortion）双 Lipschitz 嵌入任何有限维欧氏空间，对 Lang–Plaut 问题给出否定回答；并推出每个无穷维 Banach 空间都有此类紧反例。

## 问题背景

一个度量空间称为加倍的（doubling），若存在常数 `@@M@@\lambda@@` 使每个球都能被至多 `@@M@@\lambda@@` 个半径减半的球覆盖；有限维欧氏空间的子集自动满足。Lang 与 Plaut（2001）问：Hilbert 空间的每个加倍子集是否都能双 Lipschitz 嵌入某个有限维欧氏空间？Gupta–Krauthgamer–Lee 也在算法降维语境下独立提出此问。肯定方向有 Assouad 定理：把距离换成雪花化（snowflaking）后的 `@@M@@d^\alpha@@`（`@@M@@0<\alpha<1@@`）便可嵌入，Naor–Neiman 还证明目标维数可只依赖加倍常数，但这些都不处理原始距离。否定方向上，Lafforgue–Naor 等对 `@@M@@p>2@@` 的 `@@M@@L_p@@` 构造了加倍反例，Hilbert 情形长期悬置；Schioppa 曾宣布解决，后因对偶论证存疑而撤稿。

## 主要结果

主定理：存在实 `@@M@@\ell_2@@` 的固定子集 `@@M@@S@@`（取诱导 Hilbert 距离），加倍常数至多 `@@M@@76800@@`，且对任意正整数 `@@M@@k@@` 与任意有限失真 `@@M@@D@@`，都不存在双 Lipschitz 嵌入 `@@M@@S\to\R^k@@`。因此，只依赖加倍常数的"维数加失真"联合界对所有加倍 Hilbert 子集不可能成立。两个推论推广之：其一，利用规范化高斯级数，同一度量空间等距实现于每个 `@@M@@L_p([0,1];\R)@@`（`@@M@@1\le p<\infty@@`），顺带回答 Lafforgue–Naor 记录为公开的 `@@M@@1<p\le2@@` 情形；其二，借助 Dvoretzky 定理，每个无穷维实 Banach 空间都含紧集（compact set）`@@M@@K_B@@`，加倍常数有万有上界 `@@M@@\Lambda=1+6\lambda^8@@`，且不能双 Lipschitz 嵌入任何有限维赋范空间——Hilbert 空间内的紧集同样如此。

## 证明思路

构造独立于任何目标映射。取 `@@M@@\mathcal H=\R^2\oplus\bigoplus_j\R^{N_j}@@`（等距于 `@@M@@\ell_2@@`）与急减尺度 `@@M@@r_j=1000^{-j}@@`：第 `@@M@@j@@` 层把平面按宽 `@@M@@r_j@@` 的水平条带与宽 `@@M@@W_jr_j@@` 的垂直条带周期地染成 `@@M@@N_j@@` 色，每个数对 `@@M@@(N_j,W_j)@@` 无限次重现。点 `@@M@@(p,w)@@` 只在有限层取位移 `@@M@@w_j=r_je_{j,i}@@`，且须基点 `@@M@@p@@` 落在该色条带内。加倍性靠尺度分层：半径 `@@M@@t@@` 处粗层（`@@M@@r_j>t@@`）坐标冻结、中间层至多一层（相邻尺度比为 1000）且标签不足 300、细层贡献小于 `@@M@@t/32@@`，底面分成 `@@M@@16^2@@` 格即得 `@@M@@300\cdot16^2=76800@@`。

反证时把嵌入 `@@M@@f@@`（失真 `@@M@@D@@`、下常数规范化为 1）切成"页"（sheet）：固定位移模式、让基点变动，`@@M@@F_w(p)=f(p,w)@@` 是 `@@M@@\R^2@@` 开集上的 `@@M@@D@@`-Lipschitz 映射。由 Rademacher 定理与 Lebesgue 点，把所有页在好点（good point）处的 `@@M@@(\|F_x\|^2,\|F_y\|^2)@@` 取闭包得紧集 `@@M@@K@@`，再取字典序最大值 `@@M@@(A,B)@@`（先第一坐标、再第二坐标）。紧性引理表明：若取值于 `@@M@@K@@` 的可测对到 `@@M@@A@@` 的平均亏差趋于零，则第二坐标均值上极限不超过 `@@M@@B@@`。

固定 `@@M@@N>(1+2D)^k@@`。对每个 `@@M@@n@@`，先选近乎极值的页与好点，再用重现的 `@@M@@(N,n)@@` 层在误差极小的方块内铺出周期块（period block，宽 `@@M@@Nnr@@`、高 `@@M@@Nr@@`，含每色一行一列）；添加颜色 `@@M@@i@@` 的位移得新页 `@@M@@F_i@@`，且 `@@M@@\|F_i-F\|\le Dr@@`。能量估计是各向异性的：水平方向沿整行积分得端点差 `@@M@@\le 2Dr@@`，配合方差恒等式给出带因子 `@@M@@n^2@@`（补偿长为 `@@M@@Nnr@@` 的行）的均方变差趋于零；垂直方向先借宽 `@@M@@nr@@` 条带把所选页的水平导数均方逼向 `@@M@@A@@`，紧性引理随即给出垂直均方范数 `@@M@@\le B@@`（无需速率），最终垂直变差亦趋于零。

收官是交叉点悖论：在能量最小的周期块上，由 Fubini 定理为每色各选一条误差小的行与列，绝对连续性使相对偏移 `@@M@@h_i=(F_i-F)/r@@` 在线上振幅 `@@M@@\omega_n\to0@@`。颜色 `@@M@@i@@` 的行与颜色 `@@M@@m@@` 的列交点处两个位移同时合法，源点距离恰为 `@@M@@\sqrt2\,r@@`，下 Lipschitz 界给出 `@@M@@\|h_i-h_m\|\ge\sqrt2@@`；沿线输送后得 `@@M@@N@@` 个落在半径 `@@M@@D@@` 球内、两两距离大于 1 的向量，与体积估计 `@@M@@N\le(1+2D)^k@@` 矛盾。Banach 推论先以乘积紧性造出有限反例，再由 Dvoretzky 定理放入任意 Banach 空间并收缩为紧集。

## 可信度与备注

据任务文件，主结果已有 Lean 形式化证明；两个推论仅用高斯级数、Dvoretzky 定理与紧性等标准工具，与主定理共同构成结果族 098 的骨架。按 OpenAI 官方声明，未经形式化的结果可能存在问题，其余细节应以社区核验为准。

{% endraw %}
