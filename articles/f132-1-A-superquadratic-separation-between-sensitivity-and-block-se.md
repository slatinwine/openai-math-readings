---
layout: default
title: "A superquadratic separation between sensitivity and block sensitivity"
family: "132"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A superquadratic separation between sensitivity and block sensitivity

> 结果族 132：A superquadratic separation of sensitivity and block sensitivity　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

把布尔函数想成一排开关控制的一盏灯。敏感度问：在最不利的位置，有多少个开关"单独一拨就能让灯变"？块敏感度放宽为：把互不相交的几组开关整组一起拨，最多有几组能各自让灯变？人们猜组数顶多是单拨数的平方；本文造出反例：组数能超过平方任意多倍。

**关键词卡片**

- 敏感度（sensitivity, `@@M@@s(f)@@`）：固定一个输入，单独翻转某一位就改变函数值，这样的位数的最大值。
- 块敏感度（block sensitivity, `@@M@@\mathrm{bs}(f)@@`）：同上，但允许互不相交的位组整组翻转。
- 全布尔函数（total Boolean function）：在每个输入上都有定义的函数，不许"部分输入不算数"的取巧。
- 复合（composition）：`@@M@@f\circ g@@` 把 `@@M@@g@@` 的输出当作 `@@M@@f@@` 的输入，用来把一次分离反复放大。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="280" y="24" text-anchor="middle" font-size="15" fill="#333">一排开关控制一盏灯：单拨 vs 整组拨</text><text x="30" y="74" font-size="14" fill="#555">单拨：</text><rect x="90" y="56" width="42" height="28" fill="#fff" stroke="#345"/><text x="111" y="75" text-anchor="middle" font-size="13" fill="#123">1</text><rect x="134" y="56" width="42" height="28" fill="#fff" stroke="#345"/><text x="155" y="75" text-anchor="middle" font-size="13" fill="#123">0</text><rect x="178" y="56" width="42" height="28" fill="#fff" stroke="#345"/><text x="199" y="75" text-anchor="middle" font-size="13" fill="#123">1</text><rect x="222" y="56" width="42" height="28" fill="#fff" stroke="#345"/><text x="243" y="75" text-anchor="middle" font-size="13" fill="#123">1</text><rect x="266" y="56" width="42" height="28" fill="#fff" stroke="#345"/><text x="287" y="75" text-anchor="middle" font-size="13" fill="#123">0</text><rect x="310" y="56" width="42" height="28" fill="#fff" stroke="#345"/><text x="331" y="75" text-anchor="middle" font-size="13" fill="#123">0</text><rect x="354" y="56" width="42" height="28" fill="#fff" stroke="#d62728" stroke-width="3"/><text x="375" y="75" text-anchor="middle" font-size="13" fill="#123">1</text><rect x="398" y="56" width="42" height="28" fill="#fff" stroke="#345"/><text x="419" y="75" text-anchor="middle" font-size="13" fill="#123">0</text><rect x="442" y="56" width="42" height="28" fill="#fff" stroke="#345"/><text x="463" y="75" text-anchor="middle" font-size="13" fill="#123">1</text><rect x="486" y="56" width="42" height="28" fill="#fff" stroke="#345"/><text x="507" y="75" text-anchor="middle" font-size="13" fill="#123">1</text><text x="375" y="46" text-anchor="middle" font-size="12" fill="#d62728">翻转此位 ⇒ 灯变</text><text x="30" y="190" font-size="14" fill="#555">整组拨：</text><rect x="86" y="166" width="94" height="42" fill="none" stroke="#2a7" stroke-width="2" stroke-dasharray="5,4"/><rect x="174" y="166" width="94" height="42" fill="none" stroke="#99a"/><rect x="262" y="166" width="94" height="42" fill="none" stroke="#2a7" stroke-width="2" stroke-dasharray="5,4"/><rect x="350" y="166" width="94" height="42" fill="none" stroke="#99a"/><rect x="438" y="166" width="94" height="42" fill="none" stroke="#2a7" stroke-width="2" stroke-dasharray="5,4"/><rect x="90" y="172" width="42" height="28" fill="#fff" stroke="#345"/><text x="111" y="191" text-anchor="middle" font-size="13" fill="#123">1</text><rect x="134" y="172" width="42" height="28" fill="#fff" stroke="#345"/><text x="155" y="191" text-anchor="middle" font-size="13" fill="#123">0</text><rect x="178" y="172" width="42" height="28" fill="#fff" stroke="#345"/><text x="199" y="191" text-anchor="middle" font-size="13" fill="#123">1</text><rect x="222" y="172" width="42" height="28" fill="#fff" stroke="#345"/><text x="243" y="191" text-anchor="middle" font-size="13" fill="#123">1</text><rect x="266" y="172" width="42" height="28" fill="#fff" stroke="#345"/><text x="287" y="191" text-anchor="middle" font-size="13" fill="#123">0</text><rect x="310" y="172" width="42" height="28" fill="#fff" stroke="#345"/><text x="331" y="191" text-anchor="middle" font-size="13" fill="#123">0</text><rect x="354" y="172" width="42" height="28" fill="#fff" stroke="#345"/><text x="375" y="191" text-anchor="middle" font-size="13" fill="#123">1</text><rect x="398" y="172" width="42" height="28" fill="#fff" stroke="#345"/><text x="419" y="191" text-anchor="middle" font-size="13" fill="#123">0</text><rect x="442" y="172" width="42" height="28" fill="#fff" stroke="#345"/><text x="463" y="191" text-anchor="middle" font-size="13" fill="#123">1</text><rect x="486" y="172" width="42" height="28" fill="#fff" stroke="#345"/><text x="507" y="191" text-anchor="middle" font-size="13" fill="#123">1</text><text x="280" y="234" text-anchor="middle" font-size="12" fill="#2a7">绿框三组：各自整组一起翻转都能让灯变 ⇒ 此处块敏感度 ≥ 3</text><text x="280" y="262" text-anchor="middle" font-size="13" fill="#666">s(f) 取最坏输入下的单拨位数；bs(f) 取同一输入下互不相交组的组数。</text></svg>

</div>

定量地说，构造给出 `@@M@@\mathrm{bs}(f)/s(f)^2\ge 2^d/\big(4(d+2)^2\big)@@`：取 `@@M@@d=20@@`，右端 `@@M@@\approx 541@@`，即存在函数满足 `@@M@@\mathrm{bs}(f)\ge 541\,s(f)^2@@`。再用 `@@M@@d=9@@` 的构造当种子反复复合（复合使敏感度相乘、块敏感度也相乘），得到固定 `@@M@@\alpha>2@@` 使 `@@M@@\mathrm{bs}(F)\ge s(F)^\alpha@@` 且两者都趋于无穷。

**为什么值得关心**

Nisan 与 Szegedy 1994 年提出的"`@@M@@\mathrm{bs}\le s^2@@`"是敏感度猜想（2019 年黄皓证得四次方版本）留下的最自然残部，本文以反例将其终结。

> 已 Lean 形式化

## 一句话结论

本文构造出全布尔函数（total Boolean function）族，使块敏感度（block sensitivity）与敏感度（sensitivity）平方之比任意大，且存在固定 `@@M@@\alpha>2@@` 使 `@@M@@\mathrm{bs}(F)\ge s(F)^\alpha@@`——这推翻了敏感度猜想的二次强化版本，也说明已知四次方上界远非紧致。

## 问题背景

敏感度 `@@M@@s(f)@@` 指单独翻转一个输入位就能改变函数值的位数最大值；块敏感度 `@@M@@\mathrm{bs}(f)@@` 则允许若干互不相交的位组一齐翻转。这对刻画布尔函数复杂度的基本度量源自 Nisan 1989 年关于并行计算时间下界的工作，Nisan 与 Szegedy 在 1994 年进一步明确提出二次猜测 `@@M@@\mathrm{bs}(f)\le s(f)^2@@`。此后 Rubinstein 的经典构造已把分离做到二次量级，Virza（2011）改进为 `@@M@@\frac12s^2+\frac12s@@`，Ambainis 与 Sun（2011）做到 `@@M@@\frac23s^2-\frac13s@@`——步步逼近二次却始终未能逾越；另一边，谁也未能证明任何普适的二次上界。2019 年 Huang 结合 Tal 的精细比较证明了 `@@M@@\mathrm{bs}(f)\le s(f)^4@@`，Wellens 又把常数改进为 `@@M@@\sqrt{2/3}\,s^4+1@@`。多项式问题虽已解决，"二次"这一最自然的猜想却悬置三十余年——本文以否定回答将其终结。

## 主要结果

**主定理**：对任意实数 `@@M@@C>0@@`，存在正整数 `@@M@@n@@` 与非常数全布尔函数 `@@M@@f:\{0,1\}^n\to\{0,1\}@@`，使 `@@M@@\mathrm{bs}(f)>C\,s(f)^2@@`。定量版本：对每个整数 `@@M@@d\ge1@@`，构造给出的 `@@M@@f@@` 满足

`@@M@@D\frac{\mathrm{bs}(f)}{s(f)^2}\ge\frac{2^d}{4(d+2)^2},@@`

右端随 `@@M@@d\to\infty@@` 发散，故任何普适二次常数都不存在。

**幂分离推论**：取 `@@M@@d=9@@`、`@@M@@M\ge9^{10}@@` 的构造为种子，记 `@@M@@A=22M^{10}@@`、`@@M@@B=M^2k^9@@`，则 `@@M@@B/A^2\ge128/121>1@@`，固定 `@@M@@\alpha=\log B/\log A>2@@`；以 `@@M@@F_{m+1}=f\circ F_m@@` 反复复合，得 `@@M@@\mathrm{bs}(F_m,0)\ge s(F_m)^\alpha@@` 对一切 `@@M@@m@@` 成立且 `@@M@@\mathrm{bs}(F_m,0)\to\infty@@`。这正是 Ambainis 与 Prūsis 2014 年指出过、却从未有人实现的超二次幂分离。

## 证明思路

证明是"递归构造＋耦合递推"的组合。

先搭底层。取参数 `@@M@@L=d+2@@`、`@@M@@k=2M^2+1@@`、`@@M@@r=\lceil\sqrt M\rceil@@`。第 0 层把 `@@M@@LM@@` 个比特分成 `@@M@@M@@` 个长为 `@@M@@L@@` 的块，以各块的指示向量为中心，令 `@@M@@P_{0,q}@@` 为"到最近中心的汉明距离（Hamming distance）不超过 `@@M@@H_0-q@@`"的指示函数——半径是逐个递减的整数，于是得到一族天然嵌套（nested）的谓词 `@@M@@P_{\ell,1}\ge P_{\ell,2}\ge\cdots@@`。关键观察：相邻输入的最近中心距离 `@@M@@D@@` 至多变化 1，一个比特不可能同时跨过两个整数半径，故初始的联合敏感度（joint profile）`@@M@@J_{0,b}@@`——同一比特使两个不同谓词同时反转的最大位数——恒为零。

再递归堆叠。第 `@@M@@\ell@@` 层把输入切成 `@@M@@k@@` 行、每行 `@@M@@r@@` 个子输入，行间连一个每点出度恰为 `@@M@@M^2@@` 的循环锦标赛（tournament），每条边 `@@M@@i\to j@@` 带随机标签 `@@M@@a(i,j)\in[r]@@`。子句 `@@M@@i@@` 断言：第 `@@M@@i@@` 行全部子输入满足最强子谓词（目标条件），且每条出边按标签选中的子输入满足较弱子谓词 `@@M@@=0@@`（门条件）；`@@M@@P_{\ell,q}=1@@` 当且仅当某子句成立。由于单个子句的 `@@M@@r+M^2@@` 个条件落在互不相同的子输入上，一个比特至多改动固定子句的一个条件——这是敏感度可控的根源。

接着对任意输入建立四条耦合递推。从 1 变 0 的方向直接：破坏一个已满足子句必须翻转某门位或目标位，得 `@@M@@S_{\ell,1}\le M^2S'_0+rS'_1@@`。难点在 0 变 1：能被一比特修复的子句必恰有一个失败条件。恰失败目标者的集合 `@@M@@\mathcal T@@` 受标签引理制约——随机标签加联合界（违规概率 `@@M@@\le k^{16}r^{-104}\le3^{16}M^{-20}<1@@`）保证不存在 16 个顶点使内部边标签全部对准失败位置，故 `@@M@@|\mathcal T|<16@@`；恰失败门者的集合 `@@M@@\mathcal G@@` 在诱导锦标赛中每点出度至多 1，数边得 `@@M@@|\mathcal G|\le3@@`，且至多一个点没有内部出边——修复带内部出边的门要求两个不同子谓词同时从 1 变 0，恰好落入 `@@M@@J'_1@@` 的管辖。合并得 `@@M@@S_{\ell,0}\le tS'_0+S'_1+3J'_1@@` 与 `@@M@@J_{\ell,0}\le tS'_0+3J'_1@@`。

最后归一化收割。取 `@@M@@M\ge9^{d+1}@@` 使 `@@M@@\epsilon=\max(r,t)/M\le2/3^{d+1}@@`，递推除以 `@@M@@M^{\ell+b}@@` 后用比较序列同步归纳，得 `@@M@@S_{\ell,b}\le2LM^{\ell+b}@@`：敏感度每层只涨约 `@@M@@M@@` 倍，而零点处的互不相交敏感块每层乘 `@@M@@k>2M^2@@`。取 `@@M@@f@@` 为 `@@M@@M@@` 个 `@@M@@P_{d,1}@@` 副本的 OR（沿用 Ambainis–Sun 的平衡原理），则 `@@M@@s(f)\le2LM^{d+1}@@` 而 `@@M@@\mathrm{bs}(f,0)\ge M^2k^d@@`，两式相除即得主定理。固定 `@@M@@d=9@@` 得到 `@@M@@B>A^2@@` 的种子，由复合引理 `@@M@@s(f\circ g)\le s(f)s(g)@@` 与 `@@M@@\mathrm{bs}(f\circ g,0)\ge\mathrm{bs}(f,0)\mathrm{bs}(g,0)@@` 反复自复合，幂分离随之而来。

## 可信度与备注

任务元信息标注主结果已有 Lean 形式化证明，核心构造与定量估计均经机器核验。论文坦承架构改编自 Meiburg 的谱敏感度（spectral sensitivity）构造，并特别指出 `@@M@@\lambda(f)\le s(f)@@`，谱版本的 `@@M@@\mathrm{bs}/\lambda^2@@` 下界不能自动给出普通敏感度分离——本文的贡献正是补全了所需的直接估计。本结果族目前仅此一篇手稿，无姊妹篇互证；脚注还注明 Meiburg 将门控锦标赛思想归功于 GPT-5.6-Sol，其本人负责表述、参数优化与形式化核验。按 OpenAI 官方声明，未经形式化的结果可能有问题，而本文主结果已形式化，可信度较高。

{% endraw %}
