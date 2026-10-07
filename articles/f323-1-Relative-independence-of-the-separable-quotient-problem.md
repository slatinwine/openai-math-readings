---
layout: default
title: "Relative independence of the separable quotient problem"
family: "323"
discipline: "Functional analysis"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Relative independence of the separable quotient problem

> 结果族 323：Independence of the separable quotient problem　·　学科：Functional analysis　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了经典的可分商问题独立于 ZFC：当连续统实值可测时，每个无穷维 Banach 空间都有可分无穷维商；而在连续统假设下存在反例。对密度恰为 `@@M@@\aleph_1@@` 的空间，独立性只需 ZFC 自身相容即得。

## 问题背景

无穷维 Banach 空间显然都含可分无穷维闭子空间，但商的对应问题——可分商问题（separable quotient problem）——却悬置数十年，传统上归于 Banach 与 Mazur；据 Brech 考证，它未见于 Banach 1932 年专著，最早书面表述出自 Rosenthal 1969 年论文。Johnson–Rosenthal（1972）证明可分空间总有带 Schauder 基的无穷维商；Argyros–Dodos–Kanellopoulos（2008）肯定了对偶空间的情形。集合论方面，Saxon 与 Sánchez Ruiz 证明范数密度小于 `@@M@@\mathfrak b@@`（`@@M@@\mathbb N^{\mathbb N}@@` 中按最终占优无界族的最小基数）时答案肯定；其余正面结果也都依赖密度下界或大基数假设。但"对所有空间"是否成立，ZFC 始终无法裁决——本文证明它确实不可裁决。

## 主要结果

对 `@@M@@\mathbb F\in\{\mathbb R,\mathbb C\}@@`，设 `@@M@@\mathrm{SQ}_{\mathbb F}@@` 为断言：每个 `@@M@@\mathbb F@@` 上的无穷维 Banach 空间 `@@M@@X@@` 都容许一个到可分无穷维 Banach 空间上的有界线性满射；由开映射定理，等价于存在闭子空间 `@@M@@M@@` 使商 `@@M@@X/M@@` 可分且无穷维。主定理是两条 ZFC 内可证的蕴涵：(i) 若连续统 `@@M@@\mathfrak c=2^{\aleph_0}@@` 实值可测（real-valued measurable），即 `@@M@@\mathcal P(\mathfrak c)@@` 上有单点为零、对小于 `@@M@@\mathfrak c@@` 的不交族可加的概率测度，则 `@@M@@\mathrm{SQ}_{\mathbb F}@@` 成立；(ii) 若连续统假设 CH 成立，则 `@@M@@\mathrm{SQ}_{\mathbb F}@@` 失败。配合 Solovay 的力迫保持定理（由可测基数可造实值可测连续统的模型）与 Gödel 可构造宇宙 `@@M@@L@@`（CH 模型），即得：只要"ZFC 加一个可测基数"相容，`@@M@@\mathrm{SQ}_{\mathbb F}@@` 就独立于 ZFC，且实、复两域同时成立。对密度恰为 `@@M@@\aleph_1@@` 的空间版本，正反两方向的相容性都只需 ZFC 相容：正方向用 Martin 公理（`@@M@@\mathrm{MA}_{\aleph_1}@@` 给出 `@@M@@\mathfrak b>\aleph_1@@`，配 Saxon–Sánchez Ruiz 判据），负方向用本文反例——其密度恰为 `@@M@@\aleph_1@@`，是最小可能的非可分密度。

## 证明思路

全文枢纽是一个判据：对闭子空间 `@@M@@F\subset X^*@@` 定义赋值映射 `@@M@@R_F:X\to F^*@@`，`@@M@@(R_Fx)(f)=f(x)@@`。文中证明 `@@M@@X@@` 有可分无穷维商，当且仅当存在无穷维闭 `@@M@@F@@` 使 `@@M@@R_F(X)@@` 范数可分（`@@M@@F@@` 还可取可分）。正反两构造以相反方式使用它。

正方向设反例为 `@@M@@X@@`，取可分无穷维 `@@M@@E\subset X^*@@`。由 Hagler–Johnson 定理的推论，`@@M@@X^*@@` 一旦含无条件基序列（unconditional basic sequence）即得可分商，故 `@@M@@E@@` 不含 `@@M@@\ell_1@@`。先证赋值像 `@@M@@R_E(B_X)@@` 的密度必达最大值 `@@M@@\mathfrak c@@`：若存在更小的稠密集，用 Dvoretzky 定理逐行构造欧氏块，再用测度把 `@@M@@\mathfrak c@@` 等测度地分入行内坐标，使 `@@M@@\sum_n|y(g_n)|@@` 对每个 `@@M@@y@@` 几乎处处收敛；`@@M@@\mathfrak c@@`-可加性保证小于 `@@M@@\mathfrak c@@` 个余零集可相交，公共点给出基本列，其赋值映射满射到可分空间——产生可分商，矛盾。再经超穷枚举与 Hahn–Banach 分离得半规范化泛函族，它在每点几乎必然取零。最后是 Borel 编码：由 Odell–Rosenthal 定理，`@@M@@E^{**}@@` 中元素都是 `@@M@@E@@` 中序列的弱星极限，将其编码为 `@@M@@E^{\mathbb N}@@` 中序列后，只需在 Polish 空间上用普通 Fubini 定理验证有序取样的有限抑制估计（无需幂集测度的积分交换定理），再对角选取无穷序列，得 `@@M@@X^*@@` 中的无条件基序列，矛盾。

负方向在 CH 下进行。先在 `@@M@@\Gamma=\omega_1@@` 上以 Gowers–Maurey 式特殊序列与 James 树式路径泛函定义范数，使对偶空间 `@@M@@E=X_0^*@@` 的每个无穷维子空间上都有不可数条两两分离的路径泛函限制；再利用 CH（路径仅 `@@M@@\aleph_1@@` 条）把全部路径编码进坐标，造出范数至多 `@@M@@1/10@@` 的小扰动算子 `@@M@@B@@`，取 `@@M@@X=\ker(Q-B)@@` 更换预对偶，则 `@@M@@X^*\simeq E@@` 且路径陪集落在 `@@M@@B(X)@@` 的闭包中。对任何可分无穷维 `@@M@@F\subset X^*@@`，坐标赋值限制可分而路径限制不可数分离，赋值像遂不可分，判据排除一切可分无穷维商。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，请以社区核验为准；作者称给出了完整构造与全部估计。正、负两方向共用同一赋值判据，互为印证；但负方向的组合编码与预对偶扰动论证链条极长。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
