---
layout: default
title: "Donovan's Conjecture over Algebraically Closed Fields"
family: "203"
discipline: "Algebra"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Donovan's Conjecture over Algebraically Closed Fields

> 结果族 203：Donovan's conjecture over fields and complete mixed-characteristic DVRs　·　学科：Algebra　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明了特征 `@@M@@p>0@@` 的每个代数闭域上的 Donovan 猜想：固定域 `@@M@@K@@` 与亏群阶的上界 `@@M@@M@@` 后，所有有限群的块只代表有限多个 `@@M@@K@@`-线性 Morita 等价类。亏群不必交换，素数 `@@M@@p=2@@` 也包括在内——这是该猜想自 1980 年提出以来在完全一般性下的首次证明。

## 问题背景

有限群代数 `@@M@@KG@@` 的块（block）是由本原中心幂等元（primitive central idempotent）定义的直和分量 `@@M@@KGb@@`，其亏群（defect group）是衡量该块偏离半单性的 `@@M@@p@@`-子群。Donovan 猜想（以 Peter Donovan 命名，1980 年出现在 Alperin 的问题清单中，编号 Conjecture M）断言：一个固定有限 `@@M@@p@@`-群只能作为有限多个互不 Morita 等价（Morita equivalence）的块的亏群出现。它用纯局部群数据约束整个表示范畴——群本身的阶、单模维数都不受限制。此前结果局限于特殊亏群（对称群块的 Scopes 定理、Kessar 的二重覆盖、Jost 与 Hiss–Kessar 的 Lie 型群归约、Eaton–Livesey 的交换 `@@M@@2@@`-群等），一般情形——非交换亏群、`@@M@@p=2@@`、任意有限群——始终悬而未决。难点有二：既要对 Cartan 矩阵（Cartan matrix）元素给出一致界，又要控制定义域（有理性与 Morita–Frobenius 数），而 Lie 型群的秩与有限环面的 `@@M@@p@@`-部分在固定亏群阶时仍可无界增长。

## 主要结果

主定理（Donovan 猜想）：固定素数 `@@M@@p@@`、特征 `@@M@@p@@` 的代数闭域 `@@M@@K@@` 与正整数 `@@M@@M@@`。当 `@@M@@G@@` 取遍有限群、`@@M@@b@@` 取遍 `@@M@@KG@@` 中亏群阶至多 `@@M@@M@@` 的块幂等元时，块代数 `@@M@@KGb@@` 只有有限多个 `@@M@@K@@`-线性 Morita 等价类。由有界阶群只有有限多个同构型，这等价于"固定单个亏群"的原始表述，因此猜想对每个有限 `@@M@@p@@`-群（包括非交换群）成立。附带地，这份有限列表还一致界住 Cartan 矩阵元素、基代数（basic algebra）的 Loewy 长度，以及每个固定次数的单模之间扩张群（Ext）的维数。

## 证明思路

证明先在 `@@M@@k=\overline{\mathbb F}_p@@` 上完成，最后经系数比较转移到任意代数闭域 `@@M@@K@@`：嵌入 `@@M@@k\hookrightarrow K@@` 后块幂等元双射且亏群不变，Morita 双模作纯量扩张即可搬运有限列表。主体分两大里程碑。

第一个里程碑是拟单群（quasisimple）块的一致 Cartan 界。对固定根数据的 Lie 型群，作者在双旗空间上沿用 Eteve 的构造，从 tilting 层得到投射表示，核心估计是"非凡茎中投射重数之和"：借助 Kummer 层上同调计算与覆盖环面的消没，把对有限环面 `@@M@@p@@`-部分的依赖彻底去掉；再仅取所给块内普通特征标坐标上的投影，用 Deligne–Lusztig 正交性与 Brauer–Feit 界压出范数界，最后由 Cauchy–Schwarz 得 Cartan 界。对无界秩的经典群，则采用承袭 Scopes 算盘法的"runner 归约"：先以单循环 Jordan 标签计算提供所需的归纳矩阵，再让 Harish–Chandra 移动作用在投射特征标锥上——多数移动归一化后是精确置换，其余误差可求和；行列式与锥体积估计把控制转成投射不可分解模（PIM）列的界。归约的终点可能是无界秩的"cuspidal 三角形"标签，作者直接用模 Harish–Chandra 诱导处理：构造 intertwiner、消除扩张障碍、清点 Hecke 代数的 simple types，其界只依赖三角形上方的 Harish–Chandra 权重而非三角形本身的秩。

第二个里程碑是从拟单群到任意有限群。先经广义 Fitting 子群（generalized Fitting subgroup）归约得到"受控交叉扩张（crossed extension）"，其恒等分量 `@@M@@F^*(H)=PZE(H)@@` 的亏群与 Cartan 元有界；关键在于保留外作用的**实际乘法因子** `@@M@@n_{xy}@@`。新工具是 Sylow 等变的 Frobenius 比较（Sylow comparison）：构造一个有界 Frobenius 周期 `@@M@@m@@` 的整 Morita 双模，其模 `@@M@@p@@` 约化带有可逆映射 `@@M@@J_x@@`，同时相容于 Sylow `@@M@@p@@`-作用与这些因子。构造上，先把域自同构换成多副本代数群上的真实置换自同构，再取对偶中心化子的不动环面与对偶 Levi，套用 Bonnafé–Rouquier 整 Morita 等价得等变 Levi 等价；特征标计算（正则嵌入后行轨道有界、symbol 标签的 Fourier 分离）表明 `@@M@@m@@` 次 Frobenius 后 Levi 块回归，只差一个中心线性特征扭转。乘法误差只剩标量，而 `@@M@@p@@`-群满足 `@@M@@H^2(S,k^\times)=0@@`，重新标度即可消去——这正是误差必须为标量、不能是任意中心单位的原因。最后组装：Eaton–Eisele–Livesey 判据给出有限多个整基序，Eisele 的 Picard 有限性给出有限外作用像，Lang 定理把交叉系统下降到有限域，大 `@@M@@p'@@`-核经扭曲 Maschke 与 Skolem–Noether 剥除矩阵因子，综合得 `@@M@@k@@` 上有限性。

## 可信度与备注

本文是 OpenAI 于 2026 年 9 月发布的预印本，主结果尚无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。姊妹篇（同族 203 的第二篇）把本文的 `@@M@@k@@` 上有限列表提升为 Witt 向量环 `@@M@@W(\overline{\mathbb F}_p)@@` 上的整有限性，并显式复用本文产出的整恒依分量序与相容 Morita 双模；两文互相印证，但本文的域上证明不依赖姊妹篇。

{% endraw %}
