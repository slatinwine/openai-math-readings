---
layout: default
title: "Rationality of the Canonical Unramified Arthur Filtration"
family: "014"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Rationality of the Canonical Unramified Arthur Filtration

> 结果族 014：Restricted geometric Langlands, global Arthur enhancements, and generic Ramanujan　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

用一把带无理数刻度的尺子搭好一排书架，事后却发现：每层隔板的位置都恰好落在整数格点上。这篇论文就是数论版的这一幕：自守函数空间上有一套用 `@@M@@\ell@@`-进工具搭出的、层层嵌套的"滤过"结构，作者证明这套结构其实完全定义在有理数 `@@M@@\mathbb Q@@` 之上——解决了 Gaitsgory–Lafforgue–Raskin 的有理性猜想。

**关键词卡片**

- 滤过（filtration）：把空间排成逐层嵌套、越来越大的子空间序列，像滤网从细到粗。
- 幂零轨道（nilpotent orbit）：李代数中幂零元素按共轭关系分出的"标签"，用来给每一层命名。
- `@@M@@\ell@@`-进系数（`@@M@@\ell@@`-adic coefficients）：几何朗兰兹里代替复数系使用的系数系统，本定理证明可降回有理数。
- 有理性（rationality）：结构能由有理系数的方程与基定义，本领域判别"结构是否本源"的标尺。
- 奇异支集（singular support）：AGKRRV 引入的几何量，编码表示偏离温和的"Arthur 方向"。

**看个具体例子**

玩具版滤过：`@@M@@\{0\}\subset@@`（一条直线）`@@M@@\subset\mathbb R^2@@`。有理性问的是：每层能否由"坐标全为有理数"的向量张成？例如由 `@@M@@(1,\sqrt2)@@` 张成的直线就不是有理的。主定理的结论是 `@@M@@E\otimes_{\mathbb Q}(\mathcal A_{\mathbb Q}\cap\mathcal F_Y)\cong\mathcal F_Y@@`：把 `@@M@@\ell@@`-进滤层交回有理数、再重新扩张，严丝合缝、一分不差。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="34" font-size="15" text-anchor="middle">Arthur 滤过：逐层嵌套，每层都定义在 ℚ 上</text>
  <rect x="60" y="58" width="440" height="182" fill="none" stroke="#345" stroke-width="2"/>
  <text x="76" y="80" font-size="13">全部函数空间</text>
  <rect x="100" y="96" width="360" height="128" fill="none" stroke="#567"/>
  <text x="116" y="116" font-size="13">较大轨道的层</text>
  <rect x="150" y="132" width="260" height="80" fill="none" stroke="#789"/>
  <text x="166" y="152" font-size="13">较小轨道的层</text>
  <rect x="200" y="166" width="150" height="36" fill="#fdf6e3" stroke="#9ab"/>
  <text x="275" y="189" font-size="13" text-anchor="middle">{0}（最温和）</text>
  <text x="280" y="262" font-size="14" text-anchor="middle">定理：每一层都能用有理系数的基张成（GLR 有理性猜想成立）</text>
</svg>

</div>

**为什么值得关心**

两套来源迥异的构造（`@@M@@\ell@@`-进范畴迹与有理函数空间）竟能在 `@@M@@\mathbb Q@@` 上完全对齐——这种"意外的有理性"通常预示更深的算术结构，且结论覆盖非尖点部分、无需尖点性假设。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

在受限几何朗兰兹理论的特征假设下，证明分裂半单群的非分歧（unramified）自守函数空间上按幂零轨道（nilpotent orbit）递增的典范 Arthur 滤过（canonical Arthur filtration）定义在 `@@M@@\mathbb Q@@` 上，正面解决 Gaitsgory–Lafforgue–Raskin 的有理性猜想，且无需尖点性或 Hecke 有限性假设。

## 问题背景

Arthur 的自守猜想用参数中一个额外的代数 `@@M@@\mathrm{SL}_2@@` 因子刻画表示偏离温和性（temperedness）的程度。在几何朗兰兹纲领中，Arinkin–Gaitsgory 引入幂零奇异支集（nilpotent singular support）来编码这一"Arthur 方向"，AGKRRV 六位作者进一步在有限域曲线上建立了配套的受限局部系统栈（restricted local-system stack）与幂零自守范畴。Gaitsgory–Lafforgue–Raskin（与 Kazhdan 合作）据此在自守函数空间上构造出按幂零轨道递增的典范滤过，并猜想（GLR 猜想 2.7.3）它应当定义在 `@@M@@\mathbb Q@@` 上。卡点在于两套结构来源不同：滤过经 `@@M@@\ell@@`-adic 范畴的奇异支集与范畴迹（categorical trace）定义，系数在 `@@M@@E=\overline{\mathbb Q}_\ell@@` 中；而函数空间本身带有自然的 `@@M@@\mathbb Q@@`-形式。此外，文献中支集迹的集中与单射此前依附于一条未证明的 GLR 猜想 2.1.5，本文必须另行建立。

## 主要结果

设 `@@M@@X/\mathbb F_q@@` 为光滑投影几何连通曲线，`@@M@@G/\mathbb F_q@@` 分裂、连通、半单，并设四条 Lie 论特征假设成立：李代数上有 `@@M@@H@@`-不变非退化对称双线性型，且它在每个 Levi 子群李代数的中心上仍非退化；每个 Levi 满足 Chevalley 型同构 `@@M@@k_0[\mathfrak m]^M\simeq k_0[\mathfrak t_M]^{W_M}@@`；半单元的概形论中心化子均为 Levi 子群；任何域扩张下的幂零元均落在某个在该域上定义的抛物子群的幂零根基中。令 `@@M@@S@@` 为 `@@M@@X@@` 上 `@@M@@G@@`-丛同构类之集，`@@M@@\mathcal A_L=L^{(S)}@@` 为有限支撑函数空间；`@@M@@\mathcal C=\mathrm{Shv}_{\mathrm{Nilp}}(\mathrm{Bun}_G(\overline X),E)@@` 为带全局幂零奇异支集条件的层范畴，`@@M@@\Phi@@` 为几何 Frobenius 推前。受限几何朗兰兹等价 `@@M@@\mathcal C\simeq\mathrm{IndCoh}_{\widehat{\mathcal N}}(Z)@@`（`@@M@@Z@@` 为受限局部系统栈中出现的连通分支之并）把闭 `@@M@@\mathrm{Ad}(\widehat G)@@`-不变子集 `@@M@@Y\subset\widehat{\mathcal N}@@`（`@@M@@\widehat{\mathcal N}@@` 为对偶李代数的幂零锥）的支集范畴 `@@M@@\mathcal C_Y@@` 对应到 `@@M@@\mathrm{IndCoh}_Y(Z)@@`——注意 `@@M@@Y@@` 约束的是奇异方向，即伴随局部系统的水平截面 `@@M@@A@@` 取值于 `@@M@@Y@@`，而非函数本身的支集。结合迹—函数同构 `@@M@@\mathrm{Tr}(\Phi,\mathcal C)\simeq\mathcal A_E@@`，定义滤过 `@@M@@\mathcal F_Y\mathcal A_E=\mathrm{im}\bigl[H^0\mathrm{Tr}(\Phi,\mathcal C_Y)\to\mathcal A_E\bigr]@@`。主定理断言：对每个 `@@M@@\ell\ne\operatorname{char}(\mathbb F_q)@@` 与每个闭不变 `@@M@@Y@@`，映射 `@@M@@E\otimes_{\mathbb Q}(\mathcal A_{\mathbb Q}\cap\mathcal F_Y\mathcal A_E)\xrightarrow{\ \sim\ }\mathcal F_Y\mathcal A_E@@` 是同构，即整个滤过带有 `@@M@@\mathbb Q@@`-形式。定理覆盖全部有限支撑函数（含非尖点部分），不需要 `@@M@@X(\mathbb F_q)@@` 非空；文中还证明这些有理子空间与 `@@M@@\ell@@` 无关，且在非分歧尖点子空间上恰等于姊妹篇的有理 Arthur 轨道直和项之和。

## 证明思路

证明沿"二次模型、紧 Weil 迹类、双线性测度判据、有理下降"四步推进。第一步把每个 Frobenius 不变的谱分量换成显式的二次矩映射（moment map）模型：先由 Deligne 的纯性（purity）给半单参数配上权零 Weil 提升，使 Frobenius 特征值按 `@@M@@q^{w/2}@@` 分层分离；再在加框分量的唯一闭轨道处完备化，用"有限协变式恢复"保证局部有限的有理信息在完备化中不丢失；核心的非共振（nonresonance）引理利用权严格错开（`@@M@@q^{-(n-1)/2}\neq1@@`，容许 Jordan 块）把 Frobenius 作用共轭为线性、把微分压成二次，而 Baker–Campbell–Hausdorff 展开识别出该二次障碍正是矩映射 `@@M@@\mu:V\to\mathfrak j^*@@`（`@@M@@V=H^1(\overline X,\widehat{\mathfrak g}_\sigma)@@`）。于是 `@@M@@Z_\sigma\simeq[(\mu^{-1}(0))^\wedge/J]@@`，奇异点为满足 `@@M@@\mu(x)=0@@`、`@@M@@zx=0@@` 的点对 `@@M@@(x,z)@@`，`@@M@@Y@@`-支集即 `@@M@@z@@` 在 `@@M@@\widehat{\mathfrak g}@@` 中的像落入 `@@M@@Y@@`。第二步证明支集迹的集中与张成：先用有限 Koszul 提升消去不变基上的支集（外代数给出非零因子 `@@M@@\det(1-F_U)@@`），再用逆搬运作用在 `@@M@@(x,z)@@` 上的点权 `@@M@@(1,-2)@@` 收缩扭 bar 复形（twisted bar complex），只剩权零的半单 Clifford 系数范畴，故迹集中于零度、由真实紧 Weil 对象的类张成；局部化的上纤维列沿有限轨道滤过逐层拼装。第三步建立双线性判据：配对 `@@M@@[f,g]=\sum_b f(b)g(b)/|\mathrm{Aut}(b)|@@` 经 AGKRRV 的非标准自守对偶把 Hecke 矩阵系数 `@@M@@[T_Df,g]@@` 化为 `@@M@@\mathrm{RHom}@@` 上的超迹；以局部上同调（local cohomology）沿幂零轨道分层，法向对称幂与切向多项式均按几何率衰减，汇成唯一的有限复测度 `@@M@@\nu_{f,g}@@`，满足 `@@M@@[T_Df,g]=\int_B\chi_D\,d\nu_{f,g}@@`，且 `@@M@@f\in\mathcal F_Y\mathcal A_{\mathbb C}@@` 当且仅当对一切 `@@M@@g@@` 有 `@@M@@\operatorname{supp}(\nu_{f,g})\subset B_Y@@`，其中 `@@M@@B_o=\{[\lambda_e(\sqrt r)s]\}@@` 是由 `@@M@@\mathrm{SL}_2@@` 三元组定义的两两不交紧集。非抵消有两道保险：顶轨道上的普适密度处处非零、可用有限特征的一致逼近消去，只剩半单系数范畴的非退化配对；边界轨道的环境伴随秩严格下降、紧集互不相交，非零类必被某个测试函数测到。第四步有理下降：判据右端只涉及点计数的 Hecke 算子、有理栈权与同一批紧集，对每个抽象同构 `@@M@@E\simeq\mathbb C@@` 都相同，故滤过在 `@@M@@\mathrm{Aut}(E/\mathbb Q)@@` 下不变；再用有限坐标的行阶梯论证（该群的不动域为 `@@M@@\mathbb Q@@`）得 `@@M@@E\otimes_{\mathbb Q}(W\cap\mathcal A_{\mathbb Q})\cong W@@`，完成主定理。

## 可信度与备注

本文为 OpenAI 生成的手稿，主结果暂无形式化证明，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。文章的框架性输入——受限朗兰兹等价、谱支集相容性、迹—函数同构、非标准对偶——分别引自 GR、Raskin、AGKRRV 系列并在文中明确标注出处，自身贡献（二次模型、测度判据、非抵消与下降论证）给出了完整证明。族内姊妹篇互相支撑：《Ramanujan–Arthur Decompositions》在平凡水平证明 GLR 猜想 3.4.5/3.4.6 并给出有理轨道直和分解，本文推论把滤过在尖点子空间上与这些直和项等同；《Global Arthur Enhancements》则在该分解假设下构造整体 Arthur 增强。

{% endraw %}
