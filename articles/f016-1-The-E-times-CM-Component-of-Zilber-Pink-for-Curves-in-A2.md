---
layout: default
title: "The E×CM component of Zilber–Pink for curves in A2"
family: "016"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The E×CM component of Zilber–Pink for curves in A2

> 结果族 016：Zilber–Pink in abelian varieties and the Siegel threefold　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

`@@M@@\mathcal A_2@@` 是阿贝尔曲面（带主极化）的三维"参数大厅"。厅里悬着一批特殊曲线：那些曲面上有一个椭圆因子带复乘（自对称超出常态）的轨迹。三维空间里两条随机曲线几乎永远不相遇；本文证明一条真正一般的曲线只会有限次擦到这些特殊曲线——Zilber–Pink 猜想的这一分量被无条件拿下。

**关键词卡片**

- Siegel 三维簇 (Siegel threefold `@@M@@\mathcal A_2@@`)：主极化阿贝尔曲面的模空间，维数为三
- Hodge 一般 (Hodge generic)：曲线不落在任何真特殊子簇里，即"真正的一般"
- 复乘 (CM, complex multiplication)：椭圆曲线的自同态比常态多出一套虚二次整数
- 同源 (isogeny)：保持加法结构的"近似同构"
- Galois 轨道 (Galois orbit)：一个代数点在全部共轭下的集合；轨道大＝朋友多

**看个具体例子**

核心是"朋友数"下界的数字版。对混合点 `@@M@@s@@`（其曲面同源于 `@@M@@E\times F@@`，`@@M@@F@@` 带 CM），记复杂度 `@@M@@\mathfrak c(s)=\max\{N(s),\,|\mathrm{disc}\,\mathrm{End}(F)|\}@@`（`@@M@@N(s)@@` 是乘积到 `@@M@@A_s@@` 的最小同源次数），定理断言 `@@M@@\#(\mathrm{Gal}(\overline{\mathbb Q}/K)\cdot s)\ge c\,\mathfrak c(s)^{1/42}@@`：点越复杂，共轭朋友至少按 `@@M@@1/42@@` 次幂增多。朋友涨得够快，配上 Pila–Zannier 式计数，无限多个混合点便无处藏身。证明的心脏是一场力量对比——周期定理给出的 `@@M@@n^{4/3}@@` 恰好压过高度估计中的线性 `@@M@@n@@`，最终合并出 `@@M@@\mathfrak c(s)\ll d^{42}@@`、轨道下界。

**为什么值得关心**

此前该分量只在曲线触及边界等附加假设下已知；本文的轨道下界对整个混合轨迹一致成立，一举拆掉全部附加条件。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文无条件证明了 Siegel 三维丛 `@@M@@\mathcal A_2@@` 中 Zilber–Pink 猜想的 `@@M@@E\times@@`CM 分量：Hodge 一般的代数曲线上，对应阿贝尔曲面同源于"至少一个因子带复乘的椭圆曲线乘积"的点只有有限多个，不需要任何边界或约化假设。

## 问题背景

Zilber–Pink 猜想属于"非预期相交"（unlikely intersection）纲领：它源自 Zilber 对半阿贝尔簇上非典型相交的猜想，由 Pink 推广到混合 Shimura 簇。本文的舞台 `@@M@@\mathcal A_2@@` 是主极化阿贝尔曲面（principally polarized abelian surface）的粗模空间，维数为三；其中余维至少为二的特殊子簇（special subvariety，即 Shimura 特殊子簇及其 Hecke 平移）包含全部 `@@M@@E\times@@`CM 曲线——一个椭圆因子自由变化，另一个带复乘（CM，complex multiplication）。三维空间里曲线与余维二子簇的预期相交维数为负，相交本不该发生，猜想断言这类例外交点有限。此前 Daw 与 Orr 只在曲线闭包交到 Baily–Borel 边界零维 stratum 的假设下证得此分量，或将其化为一个待证的 Galois 轨道下界；Papas 的结果则要求纤维处处有好约化、超奇异位置一致有界等条件。本文补出了整个混合轨迹（mixed locus）的轨道下界，从而去掉全部附加假设。

## 主要结果

主定理（Theorem 1.1）：设 `@@M@@C\subset\mathcal A_2@@` 是 `@@M@@\overline{\mathbb Q}@@` 上既约、不可约的闭代数曲线，且 Hodge 一般（Hodge generic），即不含于任何真特殊子簇，则集合 `@@M@@\{s\in C(\overline{\mathbb Q}):A_s\ \text{同源于}\ E_1\times E_2,\ \text{至少一个}\ E_i\ \text{带 CM}\}@@` 有限。这里同源（isogeny）不必保持极化，一切同源次数、虚二次域与自同态阶（endomorphism order）都允许，双因子皆 CM 的情形也包括。核心中间结果是 Galois 轨道下界（Theorem 1.2）：对每个混合点 `@@M@@s@@`，即 `@@M@@A_s@@` 同源于一条 CM 椭圆曲线与一条非 CM 椭圆曲线之积，有 `@@M@@\#(\operatorname{Gal}(\overline{\mathbb Q}/K)\cdot s)\ge c\,\mathfrak c(s)^{1/42}@@`，其中 `@@M@@\mathfrak c(s)=\max\{N(s),|\operatorname{disc}\operatorname{End}(F)|\}@@`，`@@M@@N(s)@@` 为椭圆乘积到 `@@M@@A_s@@` 的同源最小次数。

## 证明思路

全文沿 Pila–Zannier 路线展开：Daw–Orr 已建立"轨道具有多项式下界⇒混合点有限"的几何—计数蕴含，本文的任务是证明轨道下界，论证由两个算术输入的力量对比决定。

第一个输入是固定曲线上的高度估计：`@@M@@h(j_E)\ll_C n(1+\sqrt D)@@`，其中 `@@M@@D=|\operatorname{disc}\operatorname{End}(F)|@@`。先由 Daw–Orr 的乘积同源描述（Lemma 3.1）：混合主极化曲面含唯一的椭圆子簇 `@@M@@E@@`（非 CM）与 `@@M@@F@@`（CM），加法诱导次数为 `@@M@@n^2@@` 的典范同源 `@@M@@E\times F\to A@@`，拉回极化是乘积极化的 `@@M@@n@@` 倍，核是同构 `@@M@@\theta:F[n]\to E[n]@@` 的图像。再证退化长度公式（Lemma 3.2）：当 `@@M@@E@@` 在有限位 `@@M@@v@@` 是 Tate 曲线时，秩一退化长度 `@@M@@\ell(A)=\log|j_E|_v/n@@`，即粘合指标把退化长度稀释了 `@@M@@n@@` 倍；证明用半阿贝尔单值化对同源的函子性——环面间映射是同构、周期格映射乘子为 `@@M@@n@@`——由赋值配对的函子性得 `@@M@@n\ell(A)=\ell(E\times F)=\log|j_E|_v@@`。然后借助 Faltings–Chai 与 Lan 的积分环面紧致化，把 `@@M@@\ell(A)@@` 与边界除子的模型局部高度一致比较（Lemma 3.3），在曲线上用高度机器拼接；关键在于上界中 `@@M@@h(j_E)@@` 的系数只有 `@@M@@O(1/n)@@`，`@@M@@n@@` 充分大时被吸收，只剩线性于 `@@M@@n@@` 的项。曲线不碰边界时由紧性直接得 `@@M@@h(j_E)\ll n@@`；阿基米德处用 Grothendieck 单值描述（SGA 7）与 Schur 补把边界高度控制在 `@@M@@1+\rho(A)^{-2}@@`，而 `@@M@@\rho(A)^{-2}\le ny_F+y_E/n@@`。

第二个输入是三维簇上的本质周期（Proposition 5.1）。单靠 `@@M@@E\times F@@` 压不住 `@@M@@n@@`，于是复制非 CM 因子：用指标 `@@M@@b=[\Lambda_F:\mathcal O f]@@` 把两个点 `@@M@@\theta^{-1}(be_i/n)@@` 写成自同态作用于挠点的像，商去相应图像，得到同源于 `@@M@@E^2\times F@@` 的阿贝尔三簇 `@@M@@B@@`；向量 `@@M@@\omega=(be_1,be_2,f)/n@@` 是 `@@M@@B@@` 的周期，且因 `@@M@@E@@` 出现两次、`@@M@@e_1,e_2@@` 整线性无关，它不落入任何真阿贝尔子簇的李代数，是本质周期（essential period）。再以权重约 `@@M@@y^2,1,y@@` 的加权极化平衡 `@@M@@E@@` 的两个长短悬殊的周期，Gaudron–Rémond 周期定理（Masser–Wüstholz 理论的任意极化形式）给出 `@@M@@n^{4/3}\ll(b^2+1)d\max\{1,h_{\mathrm F}(B),\log\deg_L B\}@@`——`@@M@@n^{4/3}@@` 恰好压过高度估计中的线性 `@@M@@n@@`。

最后合并各估计：Siegel 类数界给出 `@@M@@D\ll d^4@@`，代入得 `@@M@@n^{4/3}\ll nd^7@@`，即 `@@M@@n\ll d^{21}@@`、`@@M@@\mathfrak c(s)\ll d^{42}@@`；结合 `@@M@@d\ll[K(s):K]@@` 便得轨道下界。混合点的有限性由修正版 Daw–Orr 蕴含给出，双 CM 情形交给 `@@M@@\mathcal A_2@@` 的 André–Oort 定理（Pila–Tsimerman、Tsimerman）。

## 可信度与备注

暂无形式化证明，OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。本文采用 Daw–Orr 的修正预印本（arXiv:1902.10483v4），脚注说明该文验证了 Orr–Schnell 修正约化理论输入所需的 Cartan 稳定性条件；Siegel 类数界是潜在非有效的，Remark 2.3 指出可借助同批 OpenAI"拟黎曼假设"预印本使这一输入有效化，但全文对轨道常数与有限性不作有效性声明。族内姊妹篇《The abelian Zilber–Pink conjecture》证明一般阿贝尔簇上的版本，《Quaternionic division points on curves in the Siegel threefold》处理四元数除法点分量；本篇的 `@@M@@E\times@@`CM 分量与四元数分量、André–Oort 定理合并，即得 `@@M@@\mathcal A_2@@` 中 Hodge 一般曲线的完整 Zilber–Pink。

{% endraw %}
