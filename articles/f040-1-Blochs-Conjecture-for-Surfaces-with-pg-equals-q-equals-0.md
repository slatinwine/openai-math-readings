---
layout: default
title: "Bloch's conjecture for surfaces with p_g=0"
family: "040"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Bloch's conjecture for surfaces with p_g=0

> 结果族 040：Bloch's conjecture for complex surfaces　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了 Bloch 猜想：`@@M@@p_g=0@@` 的光滑连通射影复曲面上，Albanese 映射 `@@M@@\mathrm{CH}_0(S)^0\to\mathrm{Alb}(S)(\mathbb C)@@` 是同构；核心新定理是 `@@M@@p_g=q=0@@` 时 `@@M@@\mathrm{CH}_0(S)\cong\mathbb Z@@`，且不附带任何曲面构造假设。

## 问题背景

对光滑射影曲面 `@@M@@S@@`，Chow 群 (Chow group) `@@M@@\mathrm{CH}_0(S)@@` 是零循环 (zero-cycle) 模有理等价 (rational equivalence) 得到的群。Mumford 1968 年证明：只要几何亏格 (geometric genus) `@@M@@p_g(S)>0@@`，这个群模等价就是"无限维"的；Bloch 随后猜想其逆——当 `@@M@@p_g(S)=0@@` 时，Albanese 映射 `@@M@@\mathrm{alb}_S:\mathrm{CH}_0(S)^0\to\mathrm{Alb}(S)(\mathbb C)@@` 应是同构。Bloch–Kas–Lieberman 解决了 Kodaira 维数 (Kodaira dimension) 小于 2 的全部情形，剩下一般型 (general type) 曲面：此时 `@@M@@p_g=0@@` 自动迫使 `@@M@@q=0@@`，猜想化为"度映射完全决定零循环"。此前所有证明都要借助具体曲面的额外结构——群作用与商曲面（Inose–Mizukami、Barlow、Bauer）、超越动机 (transcendental motive) 消没（Pedrini–Weibel）或曲线族的对应作用（Voisin）。本文给出第一个不依赖此类结构的统一证明。

## 主要结果

**定理（原文 Theorem 1.1）**：设 `@@M@@S@@` 是 `@@M@@\mathbb C@@` 上光滑连通射影曲面且 `@@M@@p_g(S)=q(S)=0@@`，则度映射 `@@M@@\deg:\mathrm{CH}_0(S)\to\mathbb Z@@` 是整系数同构——任意两个复点有理等价；定理不假设极小性、基本群条件或特定曲面构造。

结合经典定理即得完整猜想（Corollary 1.2）：`@@M@@p_g(S)=0@@` 时 `@@M@@\mathrm{alb}_S@@` 是同构，一般型情形先用 Noether 公式推出 `@@M@@q=0@@`。另有动机 (Chow motive) 推论（Corollary 1.3）：`@@M@@p_g=0@@` 时 `@@M@@h(S)_{\mathbb Q}@@` 在 Kimura 意义下有限维且 `@@M@@t_2(S)=0@@`；若更有 `@@M@@q=0@@`，则 `@@M@@h(S)_{\mathbb Q}\simeq\mathbf 1\oplus\mathbb L^{\oplus b_2(S)}\oplus\mathbb L^2@@`，于是对一切 `@@M@@m,n@@`，`@@M@@S^m@@` 与点的 Hilbert 概形 (Hilbert scheme) `@@M@@S^{[n]}@@` 均为纯 Tate motive，有理 Chow 群由上同调类完全决定。

## 证明思路

整个证明围绕一个目标：在 `@@M@@X\times X@@` 的 Chow 群里构造对角线关系 `@@M@@0=c[\Delta_X]+\Gamma@@`（`@@M@@c\ne0@@`），其中 `@@M@@\Gamma@@` 是外积 (external product) 循环之和。对角线作为对应 (correspondence) 是零循环上的恒等算子，而余维数总和为 2 的外积对应都零化零度零循环，故 `@@M@@c\ne0@@` 立即给出 `@@M@@\mathrm{CH}_0(X)^0\otimes\mathbb Q=0@@`。先做双有理 (birational) 约化：爆破 (blowup) 不改变 `@@M@@p_g,q@@` 与整系数 `@@M@@\mathrm{CH}_0@@`，故可设在极小一般型曲面上，此时 `@@M@@1\le K^2\le9@@`、`@@M@@b_2=10-K^2@@`。

关系来自 Quot 概形 (Quot scheme) 上的虚拟局部化 (virtual localization)：考虑 `@@M@@L_1\oplus L_2@@` 的秩零商、行列式固定为除子 `@@M@@D@@`，两个直和项赋相反环面权 `@@M@@\pm t@@`，并用导出模空间的行列式纤维在基点处归一化，以构造相容的完美阻碍理论 (perfect obstruction theory)。在两个输出曲面因子上各插入一次二阶陈特征后做等变度数分析：该类所含 `@@M@@t@@` 的幂次为负而类本身无负幂，故其余维数 2 分量必为零；虚拟局部化把同一个类写成固定点贡献之和，即得所需关系。

固定点贡献呈"有效除子 `@@M@@\times@@` 零维子概形"型。计算时作者改造 Ellingsrud–Göttsche–Lehn 的嵌套 Hilbert 概形 (nested Hilbert scheme) 递推，但全程不积分两个输出因子：递推把点理想逐个换成剩余点图像，最后按"相等对角线"图的连通分量分类——连住两个输出的分量给出 `@@M@@[\Delta_X]@@` 的倍数（即系数 `@@M@@c_*@@`），分开的分量给出外积。此选择规则是普适的，只依赖相交数与陈数，可跨曲面比较。

检测 `@@M@@c\ne0@@` 分两支。当 `@@M@@K^2\le8@@`：用幺模格 (unimodular lattice) 分类与特征向量 (characteristic vector) 构造与 `@@M@@K@@` 正交、平方为负的实上同调类 `@@M@@\alpha@@`；以 `@@M@@\alpha\boxtimes\alpha@@` 配对关系，与 `@@M@@\alpha@@` 正交的项贡献 `@@M@@c_*\alpha^2@@`，其余项经 Hodge 指数定理的数值界排除后只剩配对为正 `@@M@@(\alpha H)^2@@` 的零点长度项且至少出现一个，故 `@@M@@0=c\alpha^2+\sum(\alpha H)^2@@` 强迫 `@@M@@c>0@@`。当 `@@M@@K^2=9@@`：相交格秩为 1，取 `@@M@@D=3K@@` 后仅 `@@M@@(3K,0)@@`、`@@M@@(2K,K)@@` 两型贡献；在同陈数的 Cartwright–Steger 曲面（`@@M@@p_g=q=1@@`）上，借 Chang–Kiem 除子余截面 (divisor cosection) 与 Kiem–Li 局部化得 `@@M@@c_{\mathrm{out}}=s\,c_{\mathrm{mid}}@@`（`@@M@@s>0@@`），而长度 2 的 Hilbert 概形直接计算给出 `@@M@@c_{\mathrm{mid}}=12@@`，故 `@@M@@c=12(s+\tau_X)>0@@`。

最后，有理消失使整系数类成为挠 (torsion)，Roitman 挠定理连同 `@@M@@q=0@@`（Albanese 簇平凡）将其消灭；非一般型情形由 Bloch–Kas–Lieberman 定理覆盖。

## 可信度与备注

本篇验证状态为"暂无形式化证明"：核心论证涉及导出模空间上的行列式理论与虚拟局部化（原论文第 3–5 节），技术性极强，请以社区核验为准，OpenAI 官方亦声明"未经形式化的结果可能有问题"。按结果族 040 的界定，完整 Bloch 猜想由本文的 `@@M@@p_g=q=0@@` 新定理与 Bloch–Kas–Lieberman 经典定理拼接而成。论文还明确把 Guletskii、Banerjee 的同期预印本称为"已提出的证明"，并指出本文独有之处在于对角线关系取自 Quot 概形的虚拟局部化。所依赖的工具（Marian–Oprea–Pandharipande、EGL、Toën–Vaquié 等）均出自成熟文献，但新组合的正确性仍待专家审查。

{% endraw %}
