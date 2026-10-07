---
layout: default
title: "Fontaine–Mazur modularity at the prime 2"
family: "010"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Fontaine–Mazur modularity at the prime 2

> 结果族 010：Unrestricted pro-modularity at the prime two　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

每个奇的、二维、在有限个素数外非分歧、在 2 处 de Rham 且 Hodge–Tate 权重互异的 2-adic 伽罗瓦表示，都在相差一个 Tate 扭转的意义下来自经典尖点特征形式。这解决了 `@@M@@\mathbb Q@@` 上正则二维奇 Fontaine–Mazur 猜想在 `@@M@@p=2@@` 的最后情形，且对剩余表示不作任何限制。

## 问题背景

Fontaine–Mazur 猜想（1995）断言：满足适当有限性与局部条件的不可约 `@@M@@p@@`-adic 伽罗瓦表示必源自代数几何。在 `@@M@@\mathbb Q@@` 上的二维奇情形（odd，即复共轭的行列式为 `@@M@@-1@@`），它化为模性断言：这类表示应来自经典尖点特征形式（cuspidal eigenform）——Deligne 早已从模形式构造出此类伽罗瓦表示。Wiles 与 Taylor–Wiles 的形变理论处理了剩余表示绝对不可约时的模性提升（modularity lifting），而 Serre 猜想（已由 Khare–Wintenberger 与 Kisin 证明，特征 2 亦在内）恰好提供这一起点。但当剩余表示可约乃至标量时，连"模性种子"都需另行构造：经 Skinner–Wiles、Allen、Pan、Zhang、Tung 等推进，奇素数情形已解决，`@@M@@p=2@@` 只剩整体剩余表示为标量或可约这一最顽固情形——难点在于迹（trace）不记录剩余扩张类，而整体可约轨迹又大到足以切断连通性论证。

## 主要结果

主定理（Theorem 1.1）：设 `@@M@@r:G_{\mathbb Q}\to\GL_2(\overline{\mathbb Q}_2)@@` 连续、不可约、奇、在有限多个素数之外非分歧，且限制在 `@@M@@G_{\mathbb Q_2}@@` 上 de Rham 并有两个互异的 Hodge–Tate 权重（即正则，regular）。则 `@@M@@r@@` 同构于某个经典尖点特征形式附带的二维 2-adic 伽罗瓦表示的 Tate 扭转（Tate twist）。定理覆盖包括标量与可约在内的一切剩余表示，不需要剩余像绝对不可约或几乎可解等任何附加假设。结合 Pan 与 Zhang 的奇素数结果，正则二维奇 Fontaine–Mazur 模性于是对所有素数成立；论文还指出，本定理为 Hilbert 第十问题在 `@@M@@\mathbb Q@@` 上不可判定性的证明提供权 2 模性输入。

## 证明思路

证明分三阶段（论文图 1）。第一阶段解决"出现"（occurrence）：把目标连同所需形变族放进定义在公共可解全实扩张 `@@M@@F@@`（偶次数、在 2 处完全分裂）上的同一条 pro-模（pro-modular）轨迹。核心是局部化传播定理：若特征 2 曲线 `@@M@@C@@` 本身潜在 pro-模、其泛表示非虚可解（virtually solvable）且在允许的非 dyadic 素数处局部像有限，则含 `@@M@@C@@` 的每个不可约闭轨迹都潜在 pro-模。其证明把 Taylor–Wiles 辅助素数与 Kisin 拼接（patching）搬到 Laurent 级数剩余域上：没有有限剩余域的紧性，便以"有限 jet"（对极大理想幂的截断）加超幂极限做拼接，用均匀 Artin–Rees 界保持旧的形变作用，再借 Khare–Wintenberger 式特征 2 行列式扭转与二次符号缠绕算子把支撑传到每个局部分量。种子分两头供给：绝对不可约剩余表示用 Serre 模性；可约者用 Billerey–Menares 型 Eisenstein 差 `@@M@@f(\tau)-f(\ell\tau)@@` 构造经典尖点提升。全新的关键构造是"标记线"：在少数 dyadic 位记录局部不变直线，取剩余纤维中标记线与一切整体不变线横截（transverse）的开子集，Selmer 维数计算使整体可约轨迹小到无法切断这些卡；Grothendieck 连通性定理给出分量链，传播定理逐段跨越，把模性传到含目标的整个轨迹。

第二阶段是"经典化"（classicality），从完备形式中提取经典向量。若 `@@M@@r|_{G_{\mathbb Q_2}}@@` 不可约，Colmez–Dospinescu–Paškūnas 的全素数 p-adic 局部 Langlands 对应直接给出局部代数（locally algebraic）向量。若局部可约，先用 Bloch–Kato 秩一公式选出回旋指数较大的不变线，把其特征 `@@M@@\eta_1@@` 作为参数记录；构造下三角不变、`@@M@@U@@` 算子幂零作用的"普通挠模"，其对偶在权空间上有限。选取稠密权点，经规范化扭转后，表示的回旋指数化为 `@@M@@\{1,0\}@@`，其对偶权重为 `@@M@@\{0,1\}@@`，恰好满足 Thorne 无剩余假设的普通（ordinary）潜在结晶模性定理，得到稠密经典点并确定诱导序；有限联合像论证迫使该族在权空间上有限且支配。再经特征向量特化（联合纯量商、Pontryagin 对偶与 Tate 模）取出真实本征向量，用"多项式轨道"引理（Vandermonde 反演与 Gauss 分解）直接证明它局部代数，绕开"代数向量与特化可交换"这一未证断言。

第三阶段是下降：由 Jacquet–Langlands 得到 `@@M@@F@@` 上的正则代数尖点自守表示，沿素数次循环扩张的可解塔逐级下降，每级以 Hecke 特征扭转消除与目标的有限特征偏差，最终得到 `@@M@@\mathbb Q@@` 上的经典尖点特征形式，Tate 扭转由原始权重决定。值得强调：全程对目标在 2 处不加普通或潜在结晶限制——普通族只出现于中间构造。

## 可信度与备注

本篇是结果族 010 的收官之作：姊妹篇《Unrestricted pro-modularity at the prime two》给出无 de Rham 假设的完备 Hecke 代数出现定理，姊妹篇《The Dimension of the Two-Adic Hecke Algebra at Odd Level》证明 Emerton 维数猜想在 `@@M@@p=2@@` 的情形，三篇共享同一套"完备 Hecke 出现加维数控制"机制，本篇在其上叠加经典化与下降得到最终模性。暂无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。论文对 Colmez 局部对应、Paškūnas–Tung 块有限性、Thorne 定理等外部输入均注明出处，证明骨架完整。

{% endraw %}
