---
layout: default
title: "Uniform exclusion of Landau–Siegel zeros"
family: "003"
discipline: "Number theory"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Uniform exclusion of Landau–Siegel zeros

> 结果族 003：The quasi-Riemann hypothesis　·　学科：Number theory　·　验证状态：主结果已 Lean 形式化

## 一句话结论

论文证明存在绝对常数 `@@M@@c>0@@`，使得任何导子 (conductor) `@@M@@q\ge 3@@` 的本原非主实 Dirichlet `@@M@@L@@`-函数的实零点 `@@M@@\beta\in(0,1)@@` 都满足 `@@M@@(1-\beta)\log q\ge c@@`，从而一致地排除了悬置近百年的 Landau–Siegel 零点。

## 问题背景

对模 `@@M@@q@@` 的本原 Dirichlet 特征 (primitive Dirichlet character) `@@M@@\chi@@`，`@@M@@L(s,\chi)=\sum_{n\ge1}\chi(n)n^{-s}@@` 是研究算术级数中素数分布的核心工具。经典理论给出无零点区域 (zero-free region)：`@@M@@\Re s\ge 1-c_1/\log(q(|\Im s|+2))@@` 内 `@@M@@L(s,\chi)@@` 没有零点，唯一可能的例外是实特征 (real character) 附带的一个贴近 `@@M@@s=1@@` 的实单零点——即 Landau–Siegel 零点。它一旦存在，会破坏素数在算术级数中的一致估计，并通过 Dirichlet 类数公式 (class number formula) 中的 `@@M@@L(1,\chi)@@` 影响二次域类数。1935 年 Siegel 证明 `@@M@@L(1,\chi)\gg_\varepsilon q^{-\varepsilon}@@`，但常数无效 (ineffective)，无法排除 `@@M@@(1-\beta)\log q\to 0@@` 的零点序列；Page 定理只保证导子不超过 `@@M@@Q@@` 的本原实特征中至多一个在窗口 `@@M@@(1-c_2/\log Q,1)@@` 内有实零点，且窗口依赖 `@@M@@Q@@` 而非各特征自身的导子；Linnik 与 Heath-Brown 定量化发展的 Deuring–Heilbronn 现象则只能把"其余"零点推离 `@@M@@1@@`。一致排除这一例外零点，就是著名的 Landau–Siegel 零点问题，本文解决其对数形式。

## 主要结果

**定理（主定理）.** 存在绝对常数 `@@M@@c>0@@`，使得对每个导子 `@@M@@q\ge 3@@` 的本原 (primitive)、非主 (nonprincipal) 实 Dirichlet 特征 `@@M@@\chi@@`，`@@M@@L(s,\chi)@@` 的每个实零点 `@@M@@\beta\in(0,1)@@` 满足

`@@M@@D(1-\beta)\log q\ge c .@@`

换言之，实零点到 `@@M@@1@@` 的距离被 `@@M@@1/\log q@@` 的绝对常数倍一致隔开：无论导子 `@@M@@q@@` 多大，都不会出现紧贴 `@@M@@s=1@@` 的实零点。这正是 Landau–Siegel 零点问题的对数形式 (logarithmic formulation)；常数 `@@M@@c@@` 不依赖 `@@M@@\chi@@` 与 `@@M@@q@@`，论文未给出显式数值。

## 证明思路

证明分"解析输入"与"代数主体"两段。先证素数偏差引理：记 `@@M@@\ell=\log q@@`、`@@M@@\delta=(1-\beta)\ell@@`。对 `@@M@@s=1+1/\log X@@`，用 `@@M@@\zeta@@` 与 `@@M@@L(s,\chi)@@` 对数导数的 Hadamard 乘积恒等式及 Euler 乘积的非负性，可得 `@@M@@\sum_{p\le X,\,\chi(p)=1}\frac{\log p}{p}\ll\ell+\frac{\delta(\log X)^2}{\ell}@@`；再结合 Mertens 定理便知：满足 `@@M@@\chi(p)=-1@@` 的素数携带至少 `@@M@@\log X-C\ell-C\delta(\log X)^2/\ell@@` 的对数质量。零点越贴近 `@@M@@1@@`，`@@M@@\chi(p)=1@@` 的素数越稀缺，这一偏差是后续比较的引擎。

代数主体是插值行列式法 (interpolation-determinant method)。把 `@@M@@\chi@@` 对应的二次域 `@@M@@\Q(\sqrt d)@@`（`@@M@@d@@` 无平方因子，奇素数 `@@M@@p\nmid q@@` 时 `@@M@@\chi(p)=(d/p)@@`）添上 `@@M@@\sqrt 2@@`，得双二次域 (biquadratic field) `@@M@@K=\Q(a,b)@@`，其中 `@@M@@a^2=d@@`、`@@M@@b^2=2@@`（`@@M@@d=2@@` 这一固定例外被排除，大导子时自动绕开）。令 `@@M@@\theta_n=n_1+n_2a+n_3b+n_4ab@@`，`@@M@@\sigma@@` 变 `@@M@@a@@` 的符号、`@@M@@\tau@@` 变 `@@M@@b@@` 的符号，以 `@@M@@\theta_n^{\alpha_1}\sigma(\theta_n)^{\alpha_2}\sigma\tau(\theta_n)^{\alpha_3}@@` 为行、`@@M@@n\in\{0,\dots,N-1\}^4@@` 为列。可复用的代数输入是一条新插值引理：只要线性投影 `@@M@@A:\C^4\to\C^3@@` 的核由一个坐标在 `@@M@@\Q@@` 上线性无关的向量生成，分开次数 (separate degrees) 乘积超过 `@@M@@(4N)^4@@` 量级的多项式空间便能满秩插值这 `@@M@@N^4@@` 个点；其证明综合维数计数、整点凸体的最近点论证与支撑面 (supporting face) 上的 Lagrange 插值。于是在自然刻度 `@@M@@U=N^{4/3}@@`（`@@M@@U^3=N^4@@`）下，按权 `@@M@@w=\alpha_1+H(\alpha_2+\alpha_3)@@` 贪心保留 `@@M@@M=U^3@@` 行，并保证后两个坐标的次数占比 `@@M@@S_2/S_1\le C/H@@`——大权重 `@@M@@H@@` 把总次数几乎全部压进第一个坐标。

最后为非零行列式 `@@M@@\Delta@@` 建立两个界。上界：每个复嵌入下 `@@M@@|\theta_n|\le 8N\sqrt q@@`，Hadamard 不等式给出 `@@M@@\tfrac14\log|\Nm(\Delta)|\le\tfrac M2\log M+(S_1+S_2)(\log N+\tfrac\ell2+\log 8)@@`，其中 `@@M@@\log N=\tfrac34\log U@@`。下界来自整除性：对每个"可容"素数（`@@M@@p>H@@`、`@@M@@p\nmid 2q@@`、`@@M@@\chi(p)=-1@@`），环 `@@M@@\Z[a,b]/p@@` 中的 Frobenius 关系 `@@M@@\theta^p\equiv g_p(\theta)@@`（`@@M@@g_p@@` 为 `@@M@@\sigma@@` 或 `@@M@@\sigma\tau@@`）允许把每行的一块 `@@M@@p@@` 个第一因子换成共轭：严格降权因而不改变行列式，却使新行每个条目被 `@@M@@p@@` 整除，故 `@@M@@p^{E_p}\mid\Nm(\Delta)@@`，`@@M@@E_p=\sum_\alpha\lfloor\alpha_1/p\rfloor@@`。结合素数偏差引理与 Chebyshev 界，下界主项为 `@@M@@S_1\log U@@`；两界相除后，上界主项是 `@@M@@\tfrac34(1+S_2/S_1)@@`，下界是 `@@M@@1@@`——正是 `@@M@@3/4<1@@` 这一严格差驱动矛盾。反证收尾：若存在 `@@M@@q\to\infty@@`、`@@M@@\delta\to 0@@` 的零点序列，先取 `@@M@@H@@` 足够大使首项 `@@M@@\le 13/16@@`，再取 `@@M@@N=\lceil q^\gamma\rceil@@` 压低 `@@M@@\ell/\log U@@` 项至 `@@M@@1/16@@` 以下，令 `@@M@@q\to\infty@@`，得 `@@M@@1\le 13/16+1/16=7/8@@`，矛盾。

## 可信度与备注

本篇 formalized 标记为 true，主结果已有 Lean 形式化证明，是本族中验证状态最强的成果之一。同族姊妹篇分别证明所有 Dirichlet `@@M@@L@@`-函数（含 `@@M@@\zeta@@`）在半平面 `@@M@@\Re s>7/8@@` 内无零点（已形式化），以及 `@@M@@\Re s>11/12@@` 的另一条证明路线（未形式化）；其中 `@@M@@7/8@@` 半平面结论在逻辑上蕴含本文定理——实零点必满足 `@@M@@\beta\le 7/8@@`，从而 `@@M@@(1-\beta)\log q\ge\frac18\log 3@@`——而本文给出完全独立的证明，两条路线互为印证。按 OpenAI 官方声明，未经形式化的结果可能有问题，已形式化部分以 Lean 证明库为准，其余请以社区核验为准。

{% endraw %}
