---
layout: default
title: "Constructible tame Hecke eigensheaves in positive characteristic"
family: "014"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Constructible tame Hecke eigensheaves in positive characteristic

> 结果族 014：Restricted geometric Langlands, global Arthur enhancements, and generic Ramanujan　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

在正特征代数闭域上，论文对单连通单群 `@@M@@G@@` 构造了带 Borel 水平结构的非零 perverse Hecke 本征层，其特征值是标点处温和正则单幂、整体 Zariski 稠密的 `@@M@@\ell@@`-adic 局部系统，且奇异支集含于抛物型幂零锥——补上了几何朗兰兹纲领中带分歧存在性问题在正特征的关键一环。

## 问题背景

几何朗兰兹纲领 (geometric Langlands program) 预言：代数曲线上 `@@M@@G@@`-丛模叠的层范畴应等价于对偶群 `@@M@@\Gd@@` 的局部系统范畴，自动侧的对象称为 Hecke 本征层 (Hecke eigensheaf)。Drinfeld 的秩二构造与 Laumon 的一般线性群纲领开创了这一方向；FGV 把 `@@M@@\mathrm{GL}_n@@` 的非分歧存在性化为消没定理并由 Gaitsgory 证明；Beilinson–Drinfeld 借 Hitchin 系统的量子化处理了特征零一般约化群的 oper 参数。但当局部系统带分歧 (ramified) 时，必须在标点处配置水平结构 (level structure)，本征层的存在性在正特征下此前几乎空白：特征零 de Rham 设置中 Færgeman 对正则奇异参数构造了凝聚本征层，但其正则全纯性与 perverse 性只是期待；Yun 的刚性方法从自守数据反推特征值，并非对给定局部系统构造层。正特征还多出一重障碍——`@@M@@p@@` 与群的李代数结构相互纠缠（不变型退化、幂零轨道分裂异常等），这正是本文四条特征假设要精确控制的对象。

## 主要结果

设 `@@M@@k=\overline{\mathbb F}_q@@` 特征 `@@M@@p@@`，`@@M@@E=\overline{\mathbb Q}_\ell@@`，`@@M@@\ell\ne p@@`；`@@M@@X@@` 为亏格 `@@M@@\ge2@@` 的光滑射影曲线，带标点 `@@M@@x@@`，`@@M@@U=X\setminus\{x\}@@`；`@@M@@G@@` 是分裂、单、单连通群，`@@M@@B\subset G@@` 为 Borel 子群，`@@M@@\Gd@@` 为对偶伴随群。特征 `@@M@@p@@` 须满足四条李论假设：`@@M@@G@@`-不变对称型限制到每个 Levi 子群 (Levi subgroup) 的李代数中心仍非退化 (H1)；每个 Levi 的 Chevalley 限制同构成立 (H2)；半单元素的模式中心化子都是 Levi (H3)；扩域上每个幂零元素都落入某抛物子群单幂根 (unipotent radical) 的李代数 (H4)。不要求 `@@M@@p@@` 与 Weyl 群阶互素。

参数 `@@M@@\sigma@@` 是连续同态 `@@M@@\rho:\pi_1^{\mathrm{et}}(U)\to\Gd(L)@@`（`@@M@@L/\mathbb Q_\ell@@` 有限），像 Zariski 稠密；它在 `@@M@@x@@` 处杀死野惯性群 (wild inertia)，温惯性 (tame inertia) 经 `@@M@@\mathbb Z_\ell(1)@@` 作用，边界单株形如 `@@M@@\rho(\gamma)=\exp(t_\ell(\gamma)N)@@`，其中 `@@M@@N@@` 正则幂零 (regular nilpotent)，即 `@@M@@\dim Z_{\Gd}(N)=\rk(\Gd)@@`——此即"温和正则单幂单株"。

主定理：在丛叠 `@@M@@\cA=\Bun_{G,B,x}(X)@@`（标点处带 Borel 约化的 `@@M@@G@@`-丛）上存在非零的局部可构造 (locally constructible) perverse 层 (perverse sheaf) `@@M@@M@@`，其奇异支集 (singular support) 含于抛物型全局幂零锥 `@@M@@\Lambda_{\mathrm{par}}@@`（余切向量由带留数条件的 Higgs 场表示，锥由通有幂零者组成），且对任意腿集 `@@M@@I@@` 与表示 `@@M@@(V_i)@@` 有本征同构
`@@M@@D\Hecke_{I,(V_i)}(M)\simeq M\boxtimes\mathop{\boxtimes}_{i\in I}(V_i)_\sigma,@@`
与张量单位、卷积、腿置换及熔合 (fusion) 相容，包括腿碰撞对角线。

## 证明思路

证明沿"特征零构造、两次特殊化"推进。先在特征零获得非分歧本征复形：由 Gaitsgory–Raskin 的限制性等价 `@@M@@\mathrm{Shv}_{\mathrm{Nilp}}(\Bun_G(C))\simeq\IndCoh_{\mathrm{Nilp}}(\Loc^{\mathrm{restr}}_{\Gd}(C))@@`，在稠密参数处取谱侧天穹层；稠密性使参数不可约、`@@M@@\Gd@@` 伴随使自同构群平凡，切复形计算表明该点是光滑形式圆盘，故天穹层是紧对象且谱奇异支集为零，拉回自动侧即得紧的、局部有界可构造的本征复形。再以"退化到分离节点"制造水平结构：把两份 `@@M@@(X,x)@@` 在标点处粘成节点曲线并光滑化，在均衡扭转节点模型上规定稳定子型，闭纤维丛叠等价于 `@@M@@[\mathcal A_1^+\times\mathcal A_2^+/T]@@`，其中 `@@M@@\mathcal A_i^+@@` 是标点处带 `@@M@@R_u(B)@@`（或相反 Borel）约化的增强旗丛叠；第二支取边界单株互逆的参数，两者的有限商在根叠 (root stack) 上粘成有限平展扭转，经真 henselian 不变性提升到一般纤维，连通性论证保证提升后参数仍稠密。临近循环 (nearby cycles) 把本征复形送到特殊纤维，而非零性是最难点：先用 Drinfeld–Simpson 式一致化 (uniformization)（单连通半单群在仿射曲线上的丛平凡）把非零茎塞进真有界 Hecke 空间延伸到闭纤维，再由"特殊化探测"定理（若 `@@M@@\Psi F=0@@`，则非零茎轨迹的闭包不遇特殊纤维）反证非零；探测的核心是一次"双子 Hecke 修正加投影二次曲面恢复"的局部计算，配合幂零锥维数界做同时超曲面切割。得到 `@@M@@\mathcal A_1^+@@` 上的本征复形后取 perverse 上同调：一般 Hecke 函子并不 perverse 正合，作者经 Nadler–Yun 的 Betti 谱作用 (spectral action)，在单株点 `@@M@@y\in\Gd^{2g}@@` 的闭自由轨道处取标架并局部化不变函数，使固定点 Hecke 函子成为恒等函子的有限直和，截断于是保持整个本征系统。最后经环面下降去掉增强：中心层 (central sheaves) 的 Dhillon–Taylor 万有单株迹恒等式把增强单株等同为参数边界单株，边界单幂迫使每条茎上的增强单株单幂，环面的 Poincaré 对偶保证 `@@M@@q_!@@` 非零，得到特征零、普通 Borel 水平的 perverse 本征层。第二次特殊化换特征：把曲线与参数连同其有限格约化提升到混合特征的真族，几何临近循环给出 `@@M@@k@@` 上的层 `@@M@@M@@`；非零性与奇异支集复用上述两个探测论证，即得主定理。

## 可信度与备注

按任务元信息，本文主结果暂无形式化证明，请以社区核验为准。它是结果族 014 的成员：姊妹篇《The Restricted Geometric Langlands Equivalence in Positive Characteristic》在同一组四条特征假设下证明限制性几何朗兰兹等价，本文的幂零探测与特殊化探测技术同源于 AGKRRV、Gaitsgory–Raskin 的全支集纲领及同批非分歧论文，并显式以特征零等价为输入；两篇在正特征下互相印证同一套李论假设的充分性。按 OpenAI 官方声明，未经形式化的结果可能存在问题，读者引用前宜核对证明细节。

{% endraw %}
