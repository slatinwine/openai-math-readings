---
layout: default
title: "Modularity of elliptic curves over imaginary quadratic fields"
family: "030"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Modularity of elliptic curves over imaginary quadratic fields

> 结果族 030：Modularity of elliptic curves over imaginary quadratic fields　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明虚二次域上椭圆曲线的模性猜想（modularity conjecture）：任何虚二次域上的任何椭圆曲线都是模的，且逐位匹配局部参数，把有理数域上的 Wiles–BCDT 定理推广到所有虚二次域。

## 问题背景

模性是 Langlands 纲领的核心断言之一：椭圆曲线 \(E\) 的 \(l\)-进平展上同调 \(H^1_{\et}(E_{\overline K},\overline\Q_l)\) 应当来自 \(\GL_2(\A_K)\) 上某个自守表示（automorphic representation）的 Galois 实现，好约化处 Hecke 多项式须恢复约化曲线的点数，坏约化处须匹配含惯性与单项化的完整局部参数。在 \(\Q\) 上，Wiles 与 Taylor–Wiles 证明半稳定情形、Breuil–Conrad–Diamond–Taylor 完成全部，核心方法是从剩余 Galois 表示（residual Galois representation）提升自守性，Wiles 的 3–5 切换更展示了用带指定挠与局部行为的辅助曲线替换不合规剩余表示的技巧。在虚二次域上，相关上同调是 Bianchi 群作用于双曲三维空间的 Bianchi 形式（Bianchi forms），上同调出现在多个度数，Galois 表示的构造与提升都更难；Harris–Soudry–Taylor、Taylor、Harris–Lan–Taylor–Thorne、Scholze 逐步建立理论，Calegari–Geraghty 发展了多度数的 patching。位势模性（potential automorphy）定理虽已覆盖所有 CM 域上的椭圆曲线，但它允许扩张基域，原域上的模性始终是遗留问题。此前最强的精确结果属于 Caraiani–Newton：特征 3 或 5 剩余像假设下的模性、每个不含 \(\zeta_5\) 的 Galois CM 域上按高度计 \(100\%\) 的 Weierstrass 方程的模性，以及 \(X_0(15)(K)\) 秩为零时虚二次域上的全部椭圆曲线——本文正是要移除这些对曲线与域的剩余限制。

## 主要结果

主定理（Theorem 1.1）：设 \(K\) 为虚二次域、\(E/K\) 为椭圆曲线，则存在 \(\GL_2(\A_K)\) 上中心特征平凡、权为零的 isobaric 自守表示 \(\pi_E\)，使得对每个素数 \(l\) 与每个同构 \(\iota:\overline\Q_l\xrightarrow{\sim}\C\) 有 \(r_\iota(\pi_E)\simeq H^1_{\et}(E_{\overline K},\overline\Q_l)\)；在每个有限位 \(v\nmid l\)，Frobenius 半单化的 Weil–Deligne 表示（Weil–Deligne representation）满足 \(\iota\WD(H^1_{\et}(E)|_{G_{K_v}})^{\Fss}\simeq\rec_{K_v}(\pi_{E,v}\otimes|\det|_v^{-1/2})\)，即与 Tate 归一化的局部 Langlands 对应（local Langlands correspondence）逐位匹配；无穷远处的参数为 \(z\mapsto\diag(z/|z|,\overline z/|z|)\)。于是每个局部因子一致，且 \(L(E/K,s)=L(\pi_E,s-1/2)\)。若 \(E\) 无复乘（CM），\(\pi_E\) 是尖点表示（cuspidal representation）；有 CM 时由 Hecke 特征的自守诱导（automorphic induction）或 isobaric 和给出。

## 证明思路

先固定非 CM 的 \(E/K\)，由 Serre 开像定理取素数 \(p>100\) 使 \(E[p]\) 的伽罗瓦像含 \(\SL_2(\F_p)\)，令 \(n=3p\)、\(F=K(\mu_n)\)（交换 CM 域，且 \(\zeta_5\notin F\)）。再构造核心几何对象：在 \(E\) 的二次扭曲（quadratic twist）\(B_t\) 上取 Kummer 型循环覆盖 \(Y^n=f_t(Z)\)，其中 \(f_t\) 的除子为 \((S_t)-(-S_t)-n(R_t)+n(-R_t)\)、\(S_t=[n]R_t\)，得亏格 \(n\) 的曲线 \(C_n(t)\)，带旋转群 \(\mu_n\) 与翻转旋转的对合 \(w\)。各旋转特征分片 \(V_\theta=H^1(C_n)_\theta\) 都是秩二相容系统（compatible system），行列式 \(\eps_l^{-1}\)、Hodge–Tate 权 \(\{0,1\}\)；关键的巧合是三阶分片 \(V_\eta\) 恰为某椭圆曲线 \(A/F\) 的 \(H^1\)，平凡分片 \(V_1=H^1(B_t)\)。同调关于群环是自由模 \(H^1(C_n)\simeq\Z[\mu_n]^2\)（以"切开环面"的切缝基证明），因此在整格上赋值特征即得同余链 \(V_\eta\equiv\bmod p\ V_\chi\equiv\bmod 3\ V_\psi\equiv\bmod p\ V_1\)（\(\chi=\eta\psi\) 阶为 \(3p\)：阶 \(p\) 部分模 \(p\) 消失，阶 \(3\) 部分模 \(3\) 消失）。两个退化边界各司其职：在 \(R=O\) 处特殊纤维为紧型（compact type），Jacobian 极限是 \(E^n\)，由此可对全部特征分片同时强加局部约化类型；在 \(R_*=a/(2n)\) 处有 \(n\) 个节点，显式消失圈（vanishing cycles）\(\delta_i=\pm(a_i-a_{i+1})\) 经 Picard–Lefschetz 公式给出同一积分基下非对角元为 \(\pm(2-u-u^{-1})\) 的两个单项化算子，供给剩余表示的绝对不可约性与合适的 Frobenius 元。随后用两个特殊化论证选出好参数：局部域上有限挠的局部常数性加上与极限纤维 \(E^n\) 的足够深的挠比较，保证同时实现所有局部条件；对参数线从 \(K\) 到 \(\Q\) 的限制再用 Hilbert 不可约性（Hilbert irreducibility），使两个共轭族落入同一个有限单同调商，在分歧素之上的每个位保证剩余 genericity。最后传播并下降：以 \(V_\eta=H^1(A)\) 为种子，用 Caraiani–Newton 的模 \(5\) 椭圆起点定理得 \(A\) 的模性，再依序以系数素数 \(p,3,p\) 三次调用其提升定理，把自守性沿同余链传到 \(V_1=H^1(B_t)\)；每步所需的局部自守条件（零单项化，或 Steinberg 表示二次扭曲的 ordinarity）由 Varma 的局部–整体相容性在另一系数素数处读出，局部类型按 \(E\) 的约化类型（potentially good ordinary、Newton 斜率全为 \(1/2\)、potentially totally toric）与提升定理的两个分支逐一配对。因 \(F/K\) 交换，用素数度循环塔与循环基变换（cyclic base change）逐级下降，Schur 引理产生的特征差以有限阶 Hecke 特征消除，而 \(B_t\) 是 \(E\) 的二次扭曲，再扭回即得 \(\pi_E\)；CM 情形由复乘主定理与自守诱导单独处理。

## 可信度与备注

本结果族（030）仅此一篇手稿，家族主张完全依赖本文；其关键外部输入——Caraiani–Newton 的提升定理与剩余判据、HLTT/Scholze 的伽罗瓦表示构造、Varma 的局部–整体相容性、Arthur–Clozel 基变换——均为已发表文献。按任务标注主结果尚无 Lean 形式化证明；OpenAI 官方声明"未经形式化的结果可能有问题"，且手稿日期为 2026 年 10 月 4 日，全文正确性尚待社区核验。另注：本文的提升链只在奇素数处工作（种子用模 \(5\)，提升用 \(3\) 与大素数 \(p\)），素数 \(2\) 不在处理范围内；语料库中家族 010 的 Fontaine–Mazur 模性与无限制 pro-modularity 手稿恰以素数 \(2\) 为主题，与之互补。

{% endraw %}
