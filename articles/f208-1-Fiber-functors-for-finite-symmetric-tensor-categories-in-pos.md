---
layout: default
title: "Fiber functors for finite symmetric tensor categories in positive characteristic"
family: "208"
discipline: "Algebra"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Fiber functors for finite symmetric tensor categories in positive characteristic

> 结果族 208：Finite symmetric tensor categories and the Verlinde tower　·　学科：Algebra　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了 Benson–Etingof–Ostrik 猜想的有限情形：特征 \(p>0\) 的代数闭域上，任何有限对称张量范畴都容许到某层高阶 Verlinde 范畴 \(\mathrm{Ver}_{p^n}(k)\) 的纤维函子，且首次覆盖特征 \(2\)，为正特征张量范畴补上统一"坐标系"。

## 问题背景

特征零中 Deligne 定理断言：适度增长的对称张量范畴都有到超向量空间的纤维函子 (fiber functor)，因而都是超群表示。正特征下该图景失效：Etingof–Ostrik 的 Frobenius 函子一般不正合，Benson–Etingof 的特征 \(2\) 反例又催生了 Benson–Etingof–Ostrik 的高阶 Verlinde 塔 \(\mathrm{Ver}_p\subset\mathrm{Ver}_{p^2}\subset\cdots\)（2023），并猜想适度增长 (moderate growth) 的对称张量范畴都落入塔的并。此前仅知融合范畴等特例；本文彻底解决有限 (finite) 情形，含最棘手的 \(p=2\)。

## 主要结果

**主定理**：对任意素数 \(p\)、特征 \(p\) 的代数闭域 \(k\) 与有限对称张量范畴 \(\mathcal C\)（\(k\)-线性 Abel、刚性、对称幺半、有限多单对象、足够射影），存在 \(n\ge1\) 与 \(k\)-线性、正合、忠实、强对称幺半函子 \(\mathcal C\to\operatorname{Ver}_{p^n}(k)\)；层数 \(n\) 可依赖于 \(\mathcal C\)。\(\operatorname{Ver}_{p^n}\) 由 \(SL_2\) 挠量模 (tilting module) 商掉 Steinberg 模生成的张量理想所得，\(\operatorname{Ver}_2\simeq\operatorname{Vec}\)、\(\operatorname{Ver}_3\simeq\operatorname{sVec}\)，高层不再半单。

**受限挠量定理**（独立表示论贡献）：将 \(E_r=(\mathbb Z/p)^r\) 嵌入 \(SL_2\) 的上幺幂子群并记限制为 \(R\)，则对每个 \(kE_r\)-模 \(D\) 存在挠量 \(SL_2\)-模 \(T\) 使 \(R(\operatorname{St}_{r-1})\otimes D\cong R(T)\)，完整证明了 Coulembier–Flake 的受限挠量猜想（此前仅知秩一与 \(p=r=2\) 等特例）。

**推论**：与 Benson–Etingof–Ostrik 的子范畴分类结合，完全分类了有限不可压缩 (incompressible) 范畴——恰为各层 \(\operatorname{Ver}_{p^m}\)、其偶分支 \(\operatorname{Ver}_{p^m}^+\)，及 \(p\ge5\) 时的 \(\operatorname{Vec},\operatorname{sVec}\)；特征 \(2\) 中到塔并 \(\operatorname{Ver}_{2^\infty}\) 的纤维函子本质唯一；并由广义 Tannaka 对偶重建为有限层内部群概形的表示。

## 证明思路

证明分四步。**第一步：受限挠量定理**。对 \(kE_r\)-模 \(D\)（\(q=p^r\)），先用截断多项式插值把 \(D\) 提升为有理 \(\mathbb G_a\)-模，沿轨道映射作 \(G\)-等变向量丛延拓过原点；由 Steinberg 张量积定理与 BEO 引理的推广，原点纤维合成因子最高权 \(<q\)，张上 \(\operatorname{St}_{r-1}\) 后即为挠量模。核心的形式比较引理借 \(\operatorname{Ext}\) 消没（Cline–Parshall–Scott–van der Kallen）逐阶构造与 \(G\)-作用兼容的形式平凡化，限制到 \(U\)-固定直线后以环面元抵消参数缩放，再因 \(k\) 无穷把同构下降回 \(k\)，把原点纤维与 \(e_1\) 处纤维等同为 \(U\)-模。

**第二步：高阶 Frobenius 函子**。把第一步喂给 Coulembier–Flake 的高阶 Frobenius 机构，得可加、强对称幺半的 \(\Phi(X)=\Theta_{\mathcal C}(X^{\otimes q}):\mathcal C\to\mathcal C\boxtimes\operatorname{Ver}_{p^r}\)，它半线性（\(\Phi(af)=a^q\Phi(f)\)）且未必正合；若有射影生成元 \(P\) 使 \(\Theta(\operatorname{Hom}(P,P^{\otimes q}))\neq0\)，则 \(\Phi(P)\neq0\)，非零对象张量忠实并反映正合，\(\Phi\) 即正合。

**第三步：选秩与嵌入**。先取最小 \(r\) 使 \(M(r)=\operatorname{Hom}(P,P^{\otimes p^r})\) 作为 \(E_r\)-模非射影：若不然，范映射 (norm map) 判据与 Chouinard 定理给出 \(\omega(P^{\otimes d})\) 皆为 \(k\mathfrak S_d\)-射影，全对称化子 \(b_d\) 作用非零；但正特征下置换范畴的任何非零张量理想必含某个 \(b_d\)，与 \(\dim\operatorname{End}(P^{\otimes d})\) 至多指数增长矛盾。最小性保证 \(M(r)\) 对真子群限制皆射影，故其秩支撑 (rank support) 中点的坐标 \(\mathbb F_p\)-线性无关；受限 Steinberg 模的支撑恰由 \(\sum_i\alpha_i\lambda_i^{p^j}=0\)（\(0\le j\le r-2\)）刻画，用 Moore 矩阵可选线性无关的 \(\lambda_i\) 落在解中，使 \(R_\lambda(\operatorname{St}_{r-1})\otimes M\) 仍非射影，即形如 \(R_\lambda(T)\)，\(\Phi\) 正合。

**第四步：维数下降**。用标量输运 (scalar transport) 统一迭代半线性，得正合 \(\Psi_N:\mathcal C\to\mathcal C\boxtimes\mathcal W^{\boxtimes N}\)。借 Grothendieck 环模 \(p\) 同余比较 Frobenius–Perron 维数：\(\Phi(S)\) 的合成因子 \(A\boxtimes B\) 满足 \(d(A)\le d(S)\)，等号迫使 \(S\) 落入 Frobenius 精确 (Frobenius exact) 子范畴且 \(A\) 唯一，于是有向图中等权圈"吸收"一切路径，\(N\) 步后第一分量全落入 \(\mathcal C_{\mathrm{ex}}\) 的 Serre 闭包 \(\mathcal D\)。\(p>2\) 时 \(\mathcal D\) 有到 \(\operatorname{Ver}_p\) 的纤维函子，\(p=2\) 时由 Etingof–Gelaki 延拓定理得 \(\mathcal D\to\operatorname{Ver}_4^+\)；合并进单层 \(\operatorname{Ver}_{p^n}\)（\(n=\max(2,r)\)）并修正标量作用即得纤维函子。

## 可信度与备注

本文是 OpenAI 2026 年 9 月预印本，主结果暂无形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。证明骨架大量援引已发表文献（BEO 的塔与分类、Etingof–Ostrik 与 Coulembier–Flake 的 Frobenius 机构），自身新贡献集中在受限挠量定理与"最小秩 + 秩支撑选嵌入 + 维数下降"主线。主定理与既有分类结合，即得不可压缩分类、特征 \(2\) 唯一性与 Tannaka 重建；完整 BEO 猜想（非有限情形）仍开放。

{% endraw %}
