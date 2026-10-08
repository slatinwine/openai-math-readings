---
layout: default
title: "Filtered chromatic splitting at generic primes"
family: "318"
discipline: "Topology"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Filtered chromatic splitting at generic primes

> 结果族 318：Chromatic splitting: filtrations and counterexamples　·　学科：Topology　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

Hopkins 的色谱分裂猜想曾预言：球面在相邻两个"色度高度"之间的搭接部分，能像拆乐高一样干脆利落地分成 2ⁿ 块。后来发现高度三根本拆不开。这篇论文给出修正版答案：清单上的 2ⁿ 块零件一块不少，照样能按固定顺序逐层揭开，只是层与层之间的胶水被如实保留——拆不成一堆散件，但能一层层掀开看。

**关键词卡片**

- 色谱分裂猜想（chromatic splitting conjecture）：断言重叠 `@@M@@L_{n-1}L_{K(n)}S@@` 分裂成 2ⁿ 块低高度局部球面之楔和的猜想。
- 局部化（K(n)-localization）：只保留第 n 层色度信息的手术；`@@M@@L_{n-1}@@` 则保留前 n−1 层。
- 滤过（filtration）：按固定顺序逐层剥开的塔 `@@M@@0=F_0\to F_1\to\cdots\to F_{2^n}\cong X@@`。
- 余纤维（cofiber）：映射的"锥"；滤过每升一层掉出来的正是那块零件。
- 典范单位（canonical localization unit）：对象进入自身局部化的标准入场映射。

**看个具体例子**

n=3、p≥5 时 2³=8 层，自下而上依次是：L₂S、Σ⁻¹L₂S、Σ⁻³L₁S、Σ⁻⁴L₁S、Σ⁻⁵HQ_p、Σ⁻⁶HQ_p、Σ⁻⁸HQ_p、Σ⁻⁹HQ_p——两块高度二、两块高度一、四块有理，块数与位移全对上猜想的清单；第一层到顶的复合恰是典范单位。定理对一切 n≥1、p>n+1 成立，但明确不给楔和分解：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="280" y="30" text-anchor="middle" font-size="18" fill="#222">n = 3、p ≥ 5：八层有序滤过（自下而上）</text>
<rect x="210" y="44" width="220" height="20" fill="#e8e8e8" stroke="#222"/>
<text x="320" y="59" text-anchor="middle" font-size="13" fill="#222">Σ⁻⁹ HQ_p</text>
<rect x="210" y="68" width="220" height="20" fill="#e8e8e8" stroke="#222"/>
<text x="320" y="83" text-anchor="middle" font-size="13" fill="#222">Σ⁻⁸ HQ_p</text>
<rect x="210" y="92" width="220" height="20" fill="#e8e8e8" stroke="#222"/>
<text x="320" y="107" text-anchor="middle" font-size="13" fill="#222">Σ⁻⁶ HQ_p</text>
<rect x="210" y="116" width="220" height="20" fill="#e8e8e8" stroke="#222"/>
<text x="320" y="131" text-anchor="middle" font-size="13" fill="#222">Σ⁻⁵ HQ_p</text>
<rect x="210" y="140" width="220" height="20" fill="#d5d5e8" stroke="#222"/>
<text x="320" y="155" text-anchor="middle" font-size="13" fill="#222">Σ⁻⁴ L₁S</text>
<rect x="210" y="164" width="220" height="20" fill="#d5d5e8" stroke="#222"/>
<text x="320" y="179" text-anchor="middle" font-size="13" fill="#222">Σ⁻³ L₁S</text>
<rect x="210" y="188" width="220" height="20" fill="#c8dcc8" stroke="#222"/>
<text x="320" y="203" text-anchor="middle" font-size="13" fill="#222">Σ⁻¹ L₂S</text>
<rect x="210" y="212" width="220" height="20" fill="#c8dcc8" stroke="#222"/>
<text x="320" y="227" text-anchor="middle" font-size="13" fill="#222">L₂S（第一层）</text>
<line x1="186" y1="46" x2="186" y2="134" stroke="#666" stroke-width="2"/>
<line x1="186" y1="142" x2="186" y2="182" stroke="#666" stroke-width="2"/>
<line x1="186" y1="190" x2="186" y2="230" stroke="#666" stroke-width="2"/>
<text x="90" y="94" font-size="14" fill="#666">有理（4 块）</text>
<text x="84" y="166" font-size="14" fill="#666">高度 1（2 块）</text>
<text x="84" y="214" font-size="14" fill="#666">高度 2（2 块）</text>
<line x1="460" y1="238" x2="460" y2="254" stroke="#222" stroke-width="2"/>
<polygon points="454,252 466,252 460,262" fill="#222"/>
<text x="474" y="256" font-size="13" fill="#666">逐层装配</text>
</svg>

</div>

**为什么值得关心**

在"强分裂已被推翻"的废墟上抢救出猜想的正确内核：碎片清单全对、只是黏合不可忽略——为色谱分裂指明了正确的弱化形式。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明当 `@@M@@n\geq1@@`、素数 `@@M@@p\gt n+1@@` 时，色谱重叠对象 `@@M@@L_{n-1}L_{K(n)}S_p^\wedge@@` 具有 `@@M@@2^n@@` 个阶段的有序滤过，逐层余纤维恰为强色谱分裂猜想预言的全部局部球面碎片，且保留黏合映射——碎片清单正确，只是未必能裂成楔和。

## 问题背景

稳定同伦论按"高度"分层：Morava `@@M@@K@@`-理论（Morava `@@M@@K@@`-theory）`@@M@@K(n)@@` 的局部化切割球面谱，而断裂方块（fracture square）把相邻高度粘合起来，其中最关键的搭接部分是重叠对象 `@@M@@L_{n-1}L_{K(n)}S@@`。Hopkins 的色谱分裂猜想（chromatic splitting conjecture，由 Hovey 于 1993 年记录）预言这个重叠分裂成 `@@M@@2^n@@` 块低高度局部球面的楔和。已知：高度一成立；高度二在 `@@M@@p\gt3@@` 由 Hopkins 依据 Shimomura–Yabe 的计算给出、`@@M@@p=3@@` 由 Goerss–Henn–Mahowald 证明、`@@M@@p=2@@` 被 Beaudry 推翻（Beaudry–Goerss–Henn 随后给出带 Moore 谱项的修正版）。高度三以上长期悬置，而本结果族的姊妹篇更证明高度三的强分裂在 `@@M@@p\geq5@@` 时干脆是错的。于是正确的问题变成：猜想的"碎片清单"还剩多少是对的？本文的回答是：清单本身完好，只是不能要求楔和分解或单位映射的收缩。

## 主要结果

记 `@@M@@S=S_p^\wedge@@`（`@@M@@p@@`-完备球面谱）、`@@M@@D=L_{K(n)}S@@`、`@@M@@X_{n,p}=L_{n-1}D@@`。对正整数有限子集 `@@M@@I@@` 记 `@@M@@d(I)=\sum_{i\in I}(2i-1)@@`。主定理：当 `@@M@@n\geq1@@` 且 `@@M@@p\gt n+1@@` 时，存在 `@@M@@\{1,\dots,n\}@@` 全部子集的一个排序 `@@M@@I_1,\dots,I_{2^n}@@`（`@@M@@I_1=\varnothing@@`，且 `@@M@@\max I_j@@` 关于 `@@M@@j@@` 不减），以及 `@@M@@E(n-1)@@`-局部 `@@M@@S@@`-模范畴中的滤过 `@@M@@0=F_0\to F_1\to\cdots\to F_{2^n}\xrightarrow{\simeq}X_{n,p}@@`，使第 `@@M@@j@@` 层余纤维为：空集对应 `@@M@@L_{n-1}S@@`，非空 `@@M@@I@@` 对应 `@@M@@\Sigma^{-d(I)}L_{n-\max I}S@@`；且第一阶段到 `@@M@@X_{n,p}@@` 的复合恰是典范局部化单位（canonical localization unit）。定理还给出"同时乘积基"（simultaneous product bases）：一组统一选定的类 `@@M@@y_i\in\pi_{1-2i}D@@`，使得对每个 `@@M@@1\leq t\lt n@@`，由乘积 `@@M@@y_I@@` 给出的映射 `@@M@@\bigvee_{I\subseteq\{1,\dots,n-t\}}\Sigma^{-d(I)}S\to D@@` 经 `@@M@@L_{K(t)}@@` 局部化后都是等价。以高度三（`@@M@@p\geq5@@`）为例，八层依次为 `@@M@@L_2S,\ \Sigma^{-1}L_2S,\ \Sigma^{-3}L_1S,\ \Sigma^{-4}L_1S,\ \Sigma^{-5}H\Qp,\ \Sigma^{-6}H\Qp,\ \Sigma^{-8}H\Qp,\ \Sigma^{-9}H\Qp@@`。须强调：定理不断言经典楔和分解，也不分裂单位映射——黏合映射被完整保留在滤过中。

## 证明思路

证明沿两条独立主线推进，最后在下降谱序列处汇合。第一条是代数系数主线：在高度 `@@M@@t@@` 的检验中，取特征 `@@M@@p@@` 形变层上的环 `@@M@@A_t=k[[x_t,\dots,x_{n-1}]]@@` 与 `@@M@@B_t=A_t[1/x_t]@@`，再取标记连通高度 `@@M@@t@@` 形式群（connected height-`@@M@@t@@` formal group）的有限覆盖之代数并 `@@M@@\mathcal B_{n,t}@@`。论文把 `@@M@@\mathcal B_{n,t}@@` 上的连续上同调与紧支撑（compact support）上同调联系起来：有限标记塔用 Fargues–Fontaine 曲线上的向量丛扩张描述，其规范化转移（transfer）在不变体积坐标下的转置恰为 Frobenius；随后以按 `@@M@@(n,n-t)@@` 归纳的三段式论证（紧有限性、借保留横截形变去除极点界的边界步骤、满框架塔的行滤过）建立系数有限性。第二条是常值类主线：在 Morava 稳定子群 `@@M@@P_n@@`（不变量 `@@M@@1/n@@` 的除环之极大序的单位群）上构造整球面上链类 `@@M@@u_i\in\pi_{1-2i}C^*_{\mathrm{cts}}(P_n;S)@@`，用 Huber–Kings 调节子与 Huber–Soergel 体积计算做整规范化，使其模 `@@M@@p@@` Hurewicz 像 `@@M@@\xi_i@@` 的外积非零；关键系数定理断言 `@@M@@H^*_{\mathrm{cts}}(P_n;\mathcal B_{n,t})\cong\bigwedge_k(e_1,\dots,e_{n-t})@@`，`@@M@@e_i\mapsto\xi_i\cdot1@@`，同一组秩 `@@M@@n@@` 的类对所有 `@@M@@t@@` 同时起作用。汇合处是 Morava 下降（Morava descent）：先把 `@@M@@D@@` 写成 Amitsur 分解的全极限，再与剩余理论 `@@M@@\kappa_t@@`（`@@M@@E_t@@` 中正则列 `@@M@@p,u_1,\dots,u_{t-1}@@` 的迭代余纤维，`@@M@@\pi_*\kappa_t=k[v^{\pm1}]@@`）作普通 smash；平坦性与有限基变换把谱序列 `@@M@@E_2@@` 页识别为 `@@M@@\kappa_{t,r}\otimes_k H^s_{\mathrm{cts}}(P_n;\mathcal B_{n,t})@@`，类 `@@M@@u_i@@` 下降为 `@@M@@y_i\in\pi_{1-2i}D@@`，其相容提升迫使所有微分消失，于是同一族乘积映射在每个高度 `@@M@@t@@` 都是 `@@M@@K(t)@@`-等价。最后是装配判据（滤过准则）：按 `@@M@@\max I@@` 递减逐块剥离，每块恰好杀掉商对象最高的色谱层，剩下有理商的维数由 Barthel–Schlank–Stapleton–Weinstein 定理（`@@M@@\pi_*L_{K(n)}S\otimes\mathbb{Q}\cong\bigwedge_{\Qp}(\zeta_1,\dots,\zeta_n)@@`，`@@M@@|\zeta_i|=1-2i@@`）锁定；把这些商映射拉回 `@@M@@X_{n,p}@@` 即得滤过，拉回方块自动保留连接映射，无需选取零伦。碎片总数 `@@M@@2+\sum_{j=2}^{n-1}2^{j-1}+2^{n-1}=2^n@@`，恰好对上猜想的指标模式。

## 可信度与备注

本文主结果暂无形式化证明，请以社区核验为准。它与本族另两篇互为支撑：高度三显式滤过篇把 `@@M@@n=3@@` 情形独立构造出来并识别全部黏合映射，有理障碍篇则证明高度三强分裂在 `@@M@@p\geq5@@` 失败——三者合起来刻画了"楔和分裂已死、有序滤过犹存"的完整图景。按 OpenAI 官方声明，未经形式化的结果可能有问题，阅读时宜保持审慎。

{% endraw %}
