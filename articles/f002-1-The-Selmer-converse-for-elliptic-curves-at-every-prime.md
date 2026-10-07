---
layout: default
title: "The Selmer converse for elliptic curves at every prime"
family: "002"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Selmer converse for elliptic curves at every prime

> 结果族 002：The full BSD formula from low Selmer corank　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对 `@@M@@\Q@@` 上任意椭圆曲线与任意素数 `@@M@@p@@`：只要全 `@@M@@p@@` 幂 Selmer 群的 `@@M@@\Z_p@@`-余秩为 `@@M@@0@@` 或 `@@M@@1@@`，则 `@@M@@L@@`-函数的解析秩与 Mordell–Weil 秩都恰等于它，且整个 Tate–Shafarevich 群有限；由此统一推出每个素数 `@@M@@\ell\equiv4,7,8\pmod9@@` 都是两个有理立方数之和。

## 问题背景

Birch 与 Swinnerton-Dyer 的猜想（BSD）断言：椭圆曲线 `@@M@@L@@`-函数在中心点 `@@M@@s=1@@` 的消没阶等于有理点群（Mordell–Weil 群）的秩。经典成果都是从解析侧推向算术侧：Coates–Wiles 处理复乘（CM）情形，Gross–Zagier 公式与 Kolyvagin 的 Euler 系统证明解析秩至多为一时秩相等且 `@@M@@\Sha@@` 有限。反方向的"Selmer 逆命题"（Selmer converse，又称 `@@M@@p@@`-converse）则问：若某素数 `@@M@@p@@` 处的全 `@@M@@p@@` 幂 Selmer 群 `@@M@@\Sel_{p^\infty}@@` 余秩为 `@@M@@0@@` 或 `@@M@@1@@`，能否反推解析秩与代数秩恰好等于它？此前最强的结果——Skinner–Urban、Skinner、张伟以及 Burungale–Castella–Skinner、Keller–Yin、Castella–Wan、Burungale–Tian 等的系列推进——总要附加条件：`@@M@@p@@` 是好普通（ordinary）素数、剩余表示（residual representation）不可约、附加分歧假设、半稳定或 CM 等。本文把这些限制一次性全部去掉。

## 主要结果

**主定理（无限制低余秩 Selmer 逆命题）**：对每条椭圆曲线 `@@M@@A_0/\Q@@`、每个素数 `@@M@@p@@` 与每个 `@@M@@r\in\{0,1\}@@`，若全 `@@M@@p@@` 幂 Selmer 群的 `@@M@@\Z_p@@`-余秩 `@@M@@s_p(A_0)=r@@`，则解析秩 `@@M@@a(A_0)=\ord_{s=1}L(A_0,s)@@` 与 Mordell–Weil 秩都等于 `@@M@@r@@`，且整个 Tate–Shafarevich 群 `@@M@@\#\Sha(A_0/\Q)<\infty@@`。对约化类型、复乘、剩余 Galois 表示、有理挠与有理同源（isogeny）一概不作假设。由 Kummer 正合列

`@@M@@D0\to A_0(\Q)\otimes\Q_p/\Z_p\to\Sel_{p^\infty}(A_0/\Q)\to\Sha(A_0/\Q)[p^\infty]\to0@@`

余秩同时探测 Mordell–Weil 秩与 `@@M@@\Sha@@` 的可除部分，故这里的有限性覆盖全部素数部分；但定理不给出精细 BSD 公式的首项系数——那是同族姊妹篇的任务。

**应用（Sylvester 立方和问题）**：对每个素数 `@@M@@\ell\equiv4,7,8\pmod9@@`，三次曲线 `@@M@@E_\ell:X^3+Y^3=\ell Z^3@@` 的解析秩与 Mordell–Weil 秩均为 `@@M@@1@@`，且 `@@M@@\Sha(E_\ell/\Q)@@` 有限；特别地存在有理数 `@@M@@x,y@@` 使 `@@M@@x^3+y^3=\ell@@`。关键在于结论在 `@@M@@p=3@@`——这些曲线的加性约化（additive reduction）素数——上使用定理，而这正是带普通性假设的旧方法覆盖不了之处。

## 证明思路

固定奇素数 `@@M@@p@@`（`@@M@@p=2@@` 直接引用配套论文已确立的逆命题）并设 `@@M@@s_p(A_0)\in\{0,1\}@@`。先做算术归约：用配套的解析扭密度定理选取互素的基本判别式 `@@M@@D,D'@@`，使虚二次域 `@@M@@K=\Q(\sqrt D)@@` 与双二次 CM 场 `@@M@@L=\Q(\sqrt D,\sqrt{D'})@@` 满足 Heegner 假设，且三条二次扭的解析秩都取根数（root number）允许的最小值；于是 `@@M@@A_0@@` 及其辅助扭在 `@@M@@K@@` 上的紧 Selmer 空间都是一维，后者由非挠点生成。问题化为：只要导子 `@@M@@1@@` 的 Heegner 迹 `@@M@@y\in A_0(K)@@` 非挠，Gross–Zagier 加 Kolyvagin 立即完成。反设 `@@M@@y@@` 挠，去制造 Selmer 假设容不下的多余 Galois 扩张。

再证上界。取一列在 `@@M@@L@@` 中完全分裂的辅助素数 `@@M@@q_i@@` 与环类群（ring class group）的循环 `@@M@@p@@` 商，经 `@@M@@p@@` 进超滤极限得到取值于截断幂级数环 `@@M@@R_b=k[t]/(t^b)@@`、模 `@@M@@t@@` 余 `@@M@@1@@` 的驯特征 `@@M@@\psi@@`，并以"可容许上链"（admissible cochains）定义上同调。在 `@@M@@p@@` 的一个赋值处取全局部条件、其共轭处取零条件，得单侧 Greenberg 群 `@@M@@\mathcal H_b@@`：若 Selmer 线在 `@@M@@p@@` 处局部化非零则 `@@M@@\mathcal H_b=0@@`；否则为"严格情形"，用 Heisenberg 交换子构造非零的一阶提升障碍，配合系数正合列把一切类压进最高 `@@M@@t@@`-层，得 `@@M@@\length_{R_b}\mathcal H_b\le2@@`。两种情形都严格小于 `@@M@@b_*@@`（分别取 `@@M@@1,3@@`）。同时 `@@M@@y@@` 挠的假设迫使加权 Heegner 对数（环类 Heegner 点局部对数的驯特征加权和）的前 `@@M@@b_*@@` 个系数 `@@M@@p@@` 进赋值趋于零。

然后是自守部分。在 `@@M@@L@@` 的极大实子域的两个实赋值处、签名 `@@M@@(3,1)@@` 的酉群上，用 Weil 振子表示与 Kudla–Rallis 的 theta 框架构造全纯 theta 族；代数平方恒等式把常项与环面周期（toric periods）挂钩，其中一个特例正是上述 Heegner 对数（循 Bertolini–Darmon–Prasanna 的逆微分算子方法）；一致积分矩估计使常项很小，一个正 Fourier–Jacobi 系数除性有界，防整个级数消失。几何输入是目标 PEL 模空间的普通轨迹（ordinary locus），而非 `@@M@@A_0@@` 自身的好约化：借 Lan 与 Katz 的紧致化与普通形变框架，把 theta 提升为模 `@@M@@p@@` 各次幂的真尖点形式，且积分系数格与 Hecke 迹保持整个截断驯环——只在单个特征处取同余，会丢掉测量长度的幂零参数 `@@M@@t@@`。

最后提下界。承 Ribet–Wiles 与 Castella–Liu–Wan 的 `@@M@@\mathrm{GU}(3,1)@@` 构造，从尖点同余得四维特征零 Galois 表示，极限迹分离为 `@@M@@V=T_pA_0\otimes\Q_p@@` 的二维扭曲与两个特征；用极限矩阵代数的角模（corner modules，承 Bellaïche–Chenevier 广义矩阵代数思想）记录成分间的扩张。两个关键：利用 `@@M@@L@@` 单位秩为一排除多余分圆扩张商；在整个 Artin 环上验证严格局部条件。Fitting 理想计算给出 `@@M@@\length_{R_{b_*}}\mathcal H_{b_*}\ge b_*@@`，与上界矛盾，故 `@@M@@y@@` 非挠。

Sylvester 应用的推导很短：Satg\'e 的一对三次同源下降保留 `@@M@@\Sha@@` 项，把 `@@M@@E_\ell@@` 的全 `@@M@@3@@` 幂 Selmer 余秩压到至多 `@@M@@1@@`；根数 `@@M@@-1@@` 排除解析秩零，定理即给出秩 `@@M@@1@@` 与 `@@M@@\Sha@@` 有限，而非挠点 `@@M@@Z@@` 坐标非零，除以 `@@M@@Z^3@@` 便得立方和表示。

## 可信度与备注

本文是 OpenAI 于 2026 年 9 月发布的预印本，主结果暂无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。证明以同项目配套论文（Goldfeld 密度方向）的两个定理为输入（`@@M@@p=2@@` 的逆命题与解析扭密度），环环相扣；同族姊妹篇《Exact Birch–Swinnerton-Dyer Formula from Low Selmer Corank》在本文的秩相等与 `@@M@@\Sha@@` 有限之上补全含全部素因子的 BSD 首项公式，《The two-primary Birch–Swinnerton-Dyer formula in Selmer corank at most one》专攻 `@@M@@2@@` 部分主公式，三篇互相支撑构成结果族 002。另外，Sylvester 立方和的这些情形此前已由 Yin 与 Burungale–Tian 以直接 Heegner 点方法独立证得，与本文结论互为交叉印证。

{% endraw %}
