---
layout: default
title: "The Kirchberg–Rørdam character criterion"
family: "299"
discipline: "Operator algebras"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Kirchberg–Rørdam character criterion

> 结果族 299：The Kirchberg–Rørdam character criterion and infinite tensor-power Jiang–Su stability　·　学科：Operator algebras　·　验证状态：主结果已 Lean 形式化

## 一句话结论

证明 Kirchberg–Rørdam 特征标判据：非零单可分复 `@@M@@C^*@@`-代数吸收 Jiang–Su 代数 `@@M@@\mathcal Z@@`，当且仅当其范数中心序列代数对任意自由超滤子都无特征标；并推出无特征标代数的无穷极小张量幂必 `@@M@@\mathcal Z@@`-稳定。

## 问题背景

Jiang–Su 代数 `@@M@@\mathcal Z@@` 是 Elliott 分类纲领中的"无穷小"构件，Toms–Winter 的强自吸收（strongly self-absorbing）理论表明：张量吸收可以由中心序列代数（central-sequence algebra）中的拷贝来识别。Kirchberg 与 Rørdam 证明了单的可分 `@@M@@A@@` 是 `@@M@@\mathcal Z@@`-稳定的，当且仅当 `@@M@@F_\omega(A)@@` 含有同单位的、可分、无特征标、次齐次（subhomogeneous）的子代数。子代数无特征标显然迫使整个 `@@M@@F_\omega(A)@@` 无特征标，他们遂问：这一初等障碍是否已经充分（其文 Question 3.1；亦为 Schafhauser–Tikuisis–White 问题集的 Problem LXXX）？该问题对任意单可分代数发问，而此前的正则性判据——Robert–Tikuisis 的有限核维数（nuclear dimension）条件、Perera–Thiel–Vilalta 的纯性（purity）刻画——均需附加结构假设，这正是悬置多年的卡点。

## 主要结果

**主定理（Theorem 1.1）**：设 `@@M@@A@@` 为非零单的可分复 `@@M@@C^*@@`-代数，`@@M@@\omega@@` 为 `@@M@@\mathbb N@@` 上任意自由超滤子（free ultrafilter），则
`@@M@@DF_\omega(A)\ \text{无特征标}\quad\Longleftrightarrow\quad A\cong A\otimes_{\min}\mathcal Z,@@`
其中 `@@M@@A_\omega=\ell^\infty(\mathbb N,A)/\{(a_n):\lim_{n\to\omega}\|a_n\|=0\}@@`，`@@M@@F_\omega(A)=A_\omega\cap A'@@`，特征标（character）指到 `@@M@@\mathbb C@@` 的非零 *-同态。定理不假设核性、单性、迹、维数或比较性。

**有限构造（Theorem 1.2，主定理的核心成分）**：若 `@@M@@D@@` 为非零、单、无特征标的复 `@@M@@C^*@@`-代数，则存在 `@@M@@m\ge1@@` 与单 *-同态 `@@M@@I(2,3)\to D^{\otimes_{\max}m}@@`，其中维数下降代数（dimension-drop algebra）
`@@M@@DI(2,3)=\{f\in C([0,1],M_2\otimes M_3):\,f(0)\in M_2\otimes1_3,\ f(1)\in1_2\otimes M_3\}@@`
的不可约表示维数在两端为 2、3，在内部为 6，故其次齐次且无特征标——即便该同态有核，其像仍保持这两条性质。

**推论（Corollary 1.3，回答 Dadarlat–Toms 问题）**：设 `@@M@@D@@` 非零、单、可分、无特征标，则无穷极小张量幂 `@@M@@B=D^{\otimes_{\min}\infty}:=\varinjlim(D^{\otimes_{\min}n},\,x\mapsto x\otimes1_D)@@` 满足 `@@M@@B\cong B\otimes_{\min}\mathcal Z@@`，且包含 `@@M@@\mathcal Z@@` 的单拷贝。

## 证明思路

全文是"先有限构造、再接回中心序列"的两段式叙事。

第一步构造表示稳定的张量标签。`@@M@@D@@` 无特征标等价于自伴换位子生成的闭理想为全代数，否则取商得交换代数便有特征标；据此可选有限维实空间 `@@M@@V\subset D_{\mathrm{sa}}@@`，使 `@@M@@V@@` 在每个非零单表示下的像含不交换对。关键引理用 Sard 定理做维数计数：当 `@@M@@2^n>2mn+r-1@@` 时可取 `@@M@@x_1,\dots,x_r\in V^{\otimes_\mathbb R n}@@`，经逐腿秩至少为二的实线性映射后仍线性无关；配合交换冯·诺依曼因子乘法在代数张量积上的单射性，这些标签在极大张量幂的任何不可约表示（不必为空间型）中保持复线性无关。

第二步制造满的平方零元（square-zero element）。在 `@@M@@P_0=D\otimes_{\max}D^{\otimes n}\otimes_{\max}D^{\otimes n}@@` 中令 `@@M@@s=\sum_i v_i\otimes x_i\otimes1@@`，`@@M@@t=\sum_i v_i\otimes1\otimes x_i@@`，标签独立性迫使 `@@M@@[s,t]@@` 在每个不可约表示中非零。对 `@@M@@z=[s,[s,t]]@@`，若某表示下 `@@M@@\pi(z)\ge0@@`，则 `@@M@@\langle e^{i\lambda\pi(s)}\pi(t)e^{-i\lambda\pi(s)}\xi,\xi\rangle@@` 是全直线上的有界凹函数从而为常数，逼出 `@@M@@i\pi([s,t])=0@@` 的矛盾；故 `@@M@@z_+@@` 与 `@@M@@z_-@@` 皆满。取有限个"桥" `@@M@@c_i=z_-d_iz_+@@`，它们两两零乘且生成单位理想，再用第二组标签把桥捆成一个范数为一的满平方零元 `@@M@@w@@`。对 `@@M@@w@@` 作极分解得矩阵单元，经交换泛函微积分产生单同态 `@@M@@\eta:C\to P@@`（`@@M@@C@@` 为锥 `@@M@@C_0((0,1])\otimes M_2@@` 的单位化），其第一矩阵角 `@@M@@\eta(\iota e_{11})=|w|@@` 仍满。

第三步把锥升级为维数下降代数。`@@M@@C^{\otimes k}@@` 实现为立方体 `@@M@@[0,1]^k@@` 上带边界条件的矩阵值函数，翻转酉路径又给出单纯形上连续的单同态族 `@@M@@\theta_r:M_2\to M_2^{\otimes k}@@`，让 `@@M@@M_2@@` 在张量因子之间滑动。满性先给出比较常数 `@@M@@N@@`，辅助放大 `@@M@@R=P^{\otimes L}@@` 校正重数，立方体几何则造出正合等价（`@@M@@b_1=v_B^*v_B@@`，`@@M@@b_2=v_Bv_B^*@@`）的正交正压缩对，使亏值 `@@M@@1-b_1-b_2@@` 集中于原点附近、被坐标轴旁不交区域支撑的元素在放大后吸收，得 `@@M@@1_B-b_1-b_2\precsim(b_1-1/2)_+@@`。这恰是 Rørdam–Winter 判据的输入：文中给出其无需稳定秩一（stable rank one）的完整证明，核心是以 Gram 构造造出交换且 `@@M@@\alpha(1_3)+\beta(1_2)=1@@` 的序零映射（order-zero map）`@@M@@\alpha:M_3@@`、`@@M@@\beta:M_2@@`，并用加权翻转恒等式处理二者重叠处，从而得到单同态 `@@M@@I(2,3)\to P^{\otimes m}@@`。

最后接回应用：可分归约取 `@@M@@F_\omega(A)@@` 中同单位的可分无特征标子代数 `@@M@@D@@`，用 Kirchberg–Rørdam 的交换拷贝引理得单同态 `@@M@@D^{\otimes_{\max}m}\to F_\omega(A)@@`，与有限构造复合得 `@@M@@I(2,3)\to F_\omega(A)@@`，其像满足 KR 判据的全部条件，故 `@@M@@A\cong A\otimes_{\min}\mathcal Z@@`；反向由 KR 判据与特征标的限制性质直接得出。推论则经极大到极小商映射把 `@@M@@I(2,3)@@` 送入无穷张量幂，套用 Dadarlat–Toms 定理 1.1，并由 `@@M@@z\mapsto1_B\otimes z@@` 得 `@@M@@\mathcal Z@@` 的单拷贝。

## 可信度与备注

按任务元信息，本文主结果已获 Lean 形式化证明（结果族 299 附形式化文档）。本结果族仅含本文一篇，但论文引用的姊妹篇（companion）以高斯测度与纯态切除（pure state excision）证明有限极大张量幂含两个满的正交正元，本文改走表示稳定标签的新路线并采用其交换拷贝引理，两条路线互相印证。依 OpenAI 官方声明，"未经形式化的结果可能有问题"，故文中未被形式化覆盖的辅助构造仍应以社区核验为准。

{% endraw %}
