---
layout: default
title: "Primitive roots for every admissible integer base"
family: "029"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Primitive roots for every admissible integer base

> 结果族 029：Primitive roots for every admissible integer base　·　学科：数论（Number theory）　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

把钟面换成 p 个刻度，乘法就像指针转动：从 a 出发不断自乘，看能否把所有非零刻度转个遍——能转遍的 a 叫原根，是这个钟面最称职的"发令员"。Artin 在 1927 年猜想：只要 a 不是 −1 也不是平方数，就有无穷多张钟面请 a 当发令员。这篇论文不需要任何未证假设，证明了这一点。

**关键词卡片**

- 原根（primitive root）：模 p 乘法世界的生成元，幂次跑遍全部非零剩余。
- 乘法阶（multiplicative order）：a 自乘多少次第一次回到 1。
- Artin 猜想（Artin's conjecture）：每个可容许整数都是无穷多个素数的原根。
- 可容许（admissible）：a ≠ −1 且不是完全平方数。
- 无条件（unconditional）：不依赖广义黎曼假设等未经证明的猜想。

**看个具体例子**

p = 7、a = 3：幂次依次是 3、2、6、4、5、1，六个非零刻度各到一次，3 是原根；换 a = 2：2、4、1，转三格就回家，不是原根。主定理说：对每个可容许的 a，区间 (x, 2x) 内至少有 c_a·x/(ln x)² 个素数让 a 当原根——虽比猜想预测少一个对数因子，足以确立无穷多。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><rect x="40" y="84" width="54" height="48" fill="#fff" stroke="#333" stroke-width="2"/><rect x="130" y="84" width="54" height="48" fill="#fff" stroke="#333" stroke-width="2"/><rect x="220" y="84" width="54" height="48" fill="#fff" stroke="#333" stroke-width="2"/><rect x="310" y="84" width="54" height="48" fill="#fff" stroke="#333" stroke-width="2"/><rect x="400" y="84" width="54" height="48" fill="#fff" stroke="#333" stroke-width="2"/><rect x="490" y="84" width="54" height="48" fill="#fff" stroke="#333" stroke-width="2"/><text x="67" y="104" font-size="16" text-anchor="middle" fill="#333">1</text><text x="67" y="124" font-size="11" text-anchor="middle" fill="#777">3⁰=1</text><text x="157" y="104" font-size="16" text-anchor="middle" fill="#333">3</text><text x="157" y="124" font-size="11" text-anchor="middle" fill="#777">3¹=3</text><text x="247" y="104" font-size="16" text-anchor="middle" fill="#333">2</text><text x="247" y="124" font-size="11" text-anchor="middle" fill="#777">3²=2</text><text x="337" y="104" font-size="16" text-anchor="middle" fill="#333">6</text><text x="337" y="124" font-size="11" text-anchor="middle" fill="#777">3³=6</text><text x="427" y="104" font-size="16" text-anchor="middle" fill="#333">4</text><text x="427" y="124" font-size="11" text-anchor="middle" fill="#777">3⁴=4</text><text x="517" y="104" font-size="16" text-anchor="middle" fill="#333">5</text><text x="517" y="124" font-size="11" text-anchor="middle" fill="#777">3⁵=5</text><line x1="98" y1="108" x2="118" y2="108" stroke="#333" stroke-width="2"/><polygon points="126,108 116,103 116,113" fill="#333"/><line x1="188" y1="108" x2="208" y2="108" stroke="#333" stroke-width="2"/><polygon points="216,108 206,103 206,113" fill="#333"/><line x1="278" y1="108" x2="298" y2="108" stroke="#333" stroke-width="2"/><polygon points="306,108 296,103 296,113" fill="#333"/><line x1="368" y1="108" x2="388" y2="108" stroke="#333" stroke-width="2"/><polygon points="396,108 386,103 386,113" fill="#333"/><line x1="458" y1="108" x2="478" y2="108" stroke="#333" stroke-width="2"/><polygon points="486,108 476,103 476,113" fill="#333"/><text x="292" y="44" font-size="15" text-anchor="middle" fill="#333">3 的幂（mod 7）走遍 1 到 6 的每个刻度</text><path d="M 544 100 C 544 196 40 196 40 100" fill="none" stroke="#1e8449" stroke-width="2.5"/><polygon points="40,100 34,113 46,113" fill="#1e8449"/><text x="292" y="222" font-size="13" text-anchor="middle" fill="#1e8449">再乘一次 3：3⁶≡1，回到起点</text><text x="292" y="250" font-size="13" text-anchor="middle" fill="#555">每个刻度恰好经过一次 → 3 是模 7 的原根（而 2 只走到 2、4、1）</text></svg>

</div>

**为什么值得关心**

从前的无条件结果只能说"任取若干个基数总有一个成立"，无法指认；本文让 2、3、10 这类任何指定基数全部落实。核心突破是一致零点自由区域：对相关 L 函数的无零点区域宽度对所有数域统一，不再随域变化。这是走向 Artin 猜想完全证明的关键一跃。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
论文无条件证明了 Artin 原根猜想的无穷性断言：对每个既非 `@@M@@-1@@` 也非平方数的整数 `@@M@@a@@`（包括 `@@M@@a=2@@`），一切充分大的区间 `@@M@@(x,2x)@@` 内至少有 `@@M@@c_a x/(\log x)^2@@` 个素数以 `@@M@@a@@` 为原根，可容许基数全部"洗白"。

## 问题背景
设素数 `@@M@@p\nmid a@@`，`@@M@@a@@` 模 `@@M@@p@@` 的乘法阶 `@@M@@\ord_p(a)@@` 是使 `@@M@@a^k\equiv1\pmod p@@` 的最小正整数；若 `@@M@@\ord_p(a)=p-1@@`，称 `@@M@@a@@` 为模 `@@M@@p@@` 的原根（primitive root）。Artin 于 1927 年猜想：每个既非 `@@M@@-1@@` 也非平方数的"可容许"整数都是无穷多个素数的原根，并给出渐近计数。Hooley 在 1967 年于 Kummer 扩域 `@@M@@\mathbb{Q}(\mu_n,a^{1/n})@@` 的 Dedekind zeta 函数满足 GRH 的假设下证明了该渐近式。无条件的结果一直很弱：Gupta–Murty 造出 13 个整数保证其中至少一个成立；Heath-Brown 证明至多两个素基数失效（即 `@@M@@2,3,5@@` 至少一个成立）；而 Klurman–Shparlinski–Teräväinen 的平均结果虽然对几乎处处的 `@@M@@a@@` 给出期望渐近，但例外集随 `@@M@@x@@` 变动，处理不了指定基数。固定基数要迈过两道坎：一是分裂域随可能的指数因子变化，经典零点自由区域宽度依赖域、导子与高度，无法一致使用；二是必须构造出大量"指数因子落入可控范围"的素数。

## 主要结果
论文给出两个定理。主定理：对每个可容许整数 `@@M@@a@@`，存在常数 `@@M@@c_a>0@@` 与 `@@M@@x_a\ge2@@`，使对每 个实数 `@@M@@x\ge x_a@@`，`@@M@@\#\{p\text{ 素}：x<p<2x,\ p\nmid a,\ \ord_p(a)=p-1\}\ge c_a\,x/(\log x)^2@@`。猜想预测的量级是 `@@M@@x/\log x@@`，这里低一个对数因子，但足以确立无穷性，且在每个二进区间一致成立。解析定理：设 `@@M@@F@@` 是含 `@@M@@\mu_{12}@@` 的分圆域（cyclotomic field），则对 `@@M@@F@@` 上任何有限阶 Hecke 特征（finite-order Hecke character）`@@M@@\eta@@`，`@@M@@L_F(s,\eta)@@` 的亚纯延拓在 `@@M@@\re s>1-10^{-6}@@` 内无零点（主特征在 `@@M@@s=1@@` 的极点除外）；关键在于区域宽度 `@@M@@10^{-6}@@` 对所有域与特征一致，没有导子或高度截断。由此导出一致分裂估计：固定 `@@M@@|a|>1@@`，对所有素数 `@@M@@q\le\exp((\log x)^{0.3})@@`，在 Kummer 域 `@@M@@K_q=\mathbb{Q}(\mu_q,a^{1/q})@@` 中完全分裂的素数个数 `@@M@@\ll_a x/(q(q-1)\log x)+x^{1-10^{-6}}@@`，常数与 `@@M@@q@@` 无关。此外还有素数构造命题：在固定同余类里能找到 `@@M@@\gg x/(\log x)^2@@` 个形如 `@@M@@p-1=crQ@@`（`@@M@@c\in\{2,4\}@@`，`@@M@@Q>x^{0.9}@@` 素数，`@@M@@r@@` 的素因子全落在 `@@M@@(\exp(L^{0.1}),\exp(L^{0.3}))@@`，`@@M@@L=\log x@@`）的素数。

## 证明思路
整体是"先造素数、再拆指数、最后清点损失"的组装。先看指数约化：`@@M@@a@@` 不是模 `@@M@@p@@` 的原根，当且仅当某素数 `@@M@@q@@` 整除指数 `@@M@@i_p(a)=(p-1)/\ord_p(a)@@`。取 `@@M@@M=8\prod_{\ell\mid a}\ell@@`，用二次互反律（含 `@@M@@d_0\in\{-1,\pm2,\pm3,\pm6\}@@` 的补充定律表）选一个同余类 `@@M@@u\bmod M@@`，使该类中素数满足 `@@M@@(a/p)=-1@@`；由 Euler 判据 `@@M@@a^{(p-1)/2}\equiv-1\pmod p@@`，指数必为奇数，先排除 `@@M@@q=2@@`。构造命题再供给 `@@M@@\gg_a x/L^2@@` 个 `@@M@@p\equiv u\pmod M@@`、`@@M@@p-1=crQ@@` 的素数，于是剩余的指数素因子只能落在 `@@M@@rQ@@` 里，分两段排除：若 `@@M@@q=Q@@`，则 `@@M@@p@@` 整除某个 `@@M@@a^j-1@@`（`@@M@@j\le2x^{0.1}@@`），这些整数的乘积之对数仅 `@@M@@\ll_a x^{0.2}@@`，损失 `@@M@@O_a(x^{0.2}/L)=o(x/L^2)@@` 个；若 `@@M@@q\mid r@@`，分裂判据说 `@@M@@p\equiv1\pmod q@@` 且 `@@M@@a^{(p-1)/q}\equiv1\pmod p@@` 等价于 `@@M@@p@@` 在 `@@M@@K_q@@` 中完全分裂，逐个套用一致分裂估计再求和，`@@M@@\sum_{m>\exp(L^{0.1})}1/(m(m-1))@@` 的尾部与 `@@M@@x\exp(-\delta_0L+L^{0.3})@@` 均为 `@@M@@o(x/L^2)@@`。两项损失扣除后仍剩 `@@M@@\gg_a x/L^2@@` 个指数为 `@@M@@1@@` 的素数。一致分裂估计的来历是：`@@M@@K_q@@` 未必分圆，故取 `@@M@@F_q=\mathbb{Q}(\mu_{12q})@@`、复合 `@@M@@\widetilde K_q=K_qF_q@@`，用 Abel 扩张的 Artin 分解把 `@@M@@\zeta_{\widetilde K_q}@@` 拆成 `@@M@@F_q@@` 上 Hecke `@@M@@L@@`-函数之积，每个因子都被一致零自由定理覆盖，零点自由性随之"下降"到 `@@M@@\zeta_{K_q}@@`；再用一条误差仅线性依赖 `@@M@@\log D+n@@` 的光滑显式公式，把宽度 `@@M@@\delta_0@@` 的无零点区域转成与 `@@M@@q@@` 无关的素理想计数上界。解析核心即 Hecke 零点自由定理：在 `@@M@@F@@` 上取 Kazhdan–Patterson 三次 theta 系数做六次 Kummer 挠，用反射与 Poisson 求和两种方式估计同一个加性平均。反射一侧，挠中赋值为一的素与无平方系数素相互作用时六次指数为 `@@M@@1@@` 与 `@@M@@-4@@`，模 `@@M@@6@@` 之和为 `@@M@@3@@`，交互退化为二次型，由数域形式的 Heath-Brown 二次大筛法控制；Poisson 一侧，相对范数公式把三次 Gauss 相位的立方等同于 Hecke 特征值，主频首项恰是目标 `@@M@@L@@`-函数倒数的局部因子，其余局部项组成全纯不消失的修正因子；导体大筛法与零点检测压住非主频。两估计相减所得的幂节省使主逆 Mellin 积分越过 `@@M@@\re s=1@@` 延拓，从而排除零点；全程用理想范数让数值指数与 `@@M@@F@@` 的次数无关——这正是"一致宽度"的来源。素数构造则靠 Bombieri–Vinogradov 分布、Brun–Hooley 分块筛与 Buchstab 最小素因子恒等式保住正筛余量，同余条件经 Dirichlet 特征展开后融入双线性估计。

## 可信度与备注
本族主结果暂无 Lean 形式化证明，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。论文多处倚重同批姊妹稿：标记双线性估计取自《The Poisson–Dirichlet law for the prime factors of `@@M@@p-1@@`》，反射与 Poisson 探针机制承接《The Quasi-Riemann Hypothesis》。姊妹篇《Simultaneous primitive roots》把本文的四个解析与筛法输入列为显式假设并推出联立原根下界，族内结果环环相扣，但也意味着整体可信度需随这批手稿一并通过审查。

{% endraw %}
