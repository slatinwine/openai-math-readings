---
layout: default
title: "Randomized quasipolynomial-time mean-payoff games"
family: "104"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Randomized quasipolynomial-time mean-payoff games

> 结果族 104：Quasipolynomial algorithms for mean-payoff, stochastic and parity games　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

同一道"长期平均输赢"的博弈题，这次给算法发一枚硬币。它像一位边答边开收据的会计师：先猜出答案，再附上一张任何人都能快速核验的证明；验不过就把账撕掉重来，绝不把错账交出去。整个流程仍是拟多项式时间，一次就猜对的概率至少 7/8。

**关键词卡片**

- 随机算法（randomized algorithm）：内部掷硬币做决定的算法，允许小概率失手
- 零阈值取胜集（zero-threshold winning set）：Max 能保证长期平均收益 `@@M@@\ge 0@@` 的全部出发点
- 证书（certificate）：随答案附带的证据，多项式时间即可机器验真
- Las Vegas 算法：反复重跑直到证书通过——永远正确，期望时间不涨价
- 位置策略（positional strategy）：只看脚下、不用记事本的走法；双方的最优走法都可以是这种

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<rect x="30" y="50" width="140" height="50" rx="8" fill="#e8eef8" stroke="#345" stroke-width="2"/>
<text x="100" y="70" text-anchor="middle" font-size="14">输入博弈</text>
<text x="100" y="90" text-anchor="middle" font-size="12" fill="#567">L 个比特</text>
<line x1="172" y1="75" x2="212" y2="75" stroke="#345" stroke-width="2"/>
<polygon points="216,75 204,69 204,81" fill="#345"/>
<rect x="218" y="50" width="140" height="50" rx="8" fill="#efe8f8" stroke="#53c" stroke-width="2"/>
<text x="288" y="70" text-anchor="middle" font-size="14">随机算法</text>
<text x="288" y="90" text-anchor="middle" font-size="12" fill="#567">内部掷硬币</text>
<line x1="360" y1="75" x2="400" y2="75" stroke="#345" stroke-width="2"/>
<polygon points="404,75 392,69 392,81" fill="#345"/>
<rect x="406" y="50" width="140" height="50" rx="8" fill="#e8f8e8" stroke="#383" stroke-width="2"/>
<text x="476" y="70" text-anchor="middle" font-size="14">取胜集</text>
<text x="476" y="90" text-anchor="middle" font-size="12" fill="#567">附双方策略证书</text>
<line x1="476" y1="102" x2="476" y2="140" stroke="#383" stroke-width="2"/>
<polygon points="476,144 470,132 482,132" fill="#383"/>
<rect x="406" y="146" width="140" height="50" rx="8" fill="#f8f8d8" stroke="#a83" stroke-width="2"/>
<text x="476" y="166" text-anchor="middle" font-size="14">多项式时间检验</text>
<text x="476" y="186" text-anchor="middle" font-size="12" fill="#567">绝不放过错误答案</text>
<line x1="404" y1="171" x2="360" y2="171" stroke="#383" stroke-width="2"/>
<polygon points="356,171 368,165 368,177" fill="#383"/>
<text x="350" y="176" text-anchor="end" font-size="13" fill="#383">✓ 通过 → 采纳</text>
<line x1="476" y1="198" x2="476" y2="228" stroke="#a83" stroke-width="2"/>
<polygon points="476,232 470,220 482,220" fill="#a83"/>
<text x="476" y="252" text-anchor="middle" font-size="13" fill="#a83">✗ 失败 → 重跑一次</text>
<text x="200" y="252" text-anchor="middle" font-size="13">正确概率 ≥ 7/8，时间恒有 2^((log L)²) 级上界</text>
</svg>

</div>

一次运行全错的概率 `@@M@@\le 1/8@@`，独立重跑三次仍全军覆没的概率 `@@M@@\le(1/8)^3=1/512@@`；每次通过检验的输出还附带双方的位置策略，检票口在多项式时间内放行。

**为什么值得关心**

它与同族的确定性结果从两条独立路线登上同一高度、互相印证，而且自带证书，错了能被当场抓住。对悬置四十余年的多项式可解性问题而言，这是又一个坚实的里程碑。

> 已 Lean 形式化

## 一句话结论

为权重按二进制编码的平均支付博弈（mean-payoff game）给出随机拟多项式算法：在每条随机带上只用 `@@M@@2^{O((\log(L+2))^2)}@@` 次位运算（`@@M@@L@@` 为显式输入总长），就以至少 `@@M@@7/8@@` 的概率输出完整零阈值获胜集，并附多项式时间可验证的证书。

## 问题背景

平均支付博弈在有限有向图上进行：顶点分属 Max 与 Min，边带整数权重，双方交替沿边推动 token；Max 要让长期平均收益的 `@@M@@\liminf@@` 非负，Min 要使其为负。Ehrenfeucht 与 Mycielski 在 1979 年证明了这类博弈的位置确定性（positionality）：双方都有最优的位置策略（positional strategy），两个获胜区域因此有有限证书。但多项式时间算法四十余年悬而未决：经典的 Zwick–Paterson 算法（1996）是伪多项式（pseudopolynomial）的，代价正比于权重数值上界，而后者相对其二进制长度是指数级的；此后能量博弈的进度度量（progress measure）、策略改进（strategy improvement）、通用图（universal graph）等路线，都未能同时摆脱对权重数值的依赖。本文所属的结果族 104 宣布了按位长计的拟多项式突破，本文给出其中方法独立、自带证书的随机版本。

## 主要结果

主定理（thm:main，01-introduction.tex:36）：存在一致的随机算法，对输入长度为 `@@M@@L@@` 的任意有限平均支付博弈（允许自环、平行边与任意符号的二进制编码整数权重），以至少 `@@M@@7/8@@` 的概率正确返回整个零阈值获胜集
`@@M@@DU=\{v\in V:\exists\ \text{Max 策略}\ \sigma,\ \forall\ \text{Min 策略}\ \tau,\ \operatorname{MP}_w(\pi_{v,\sigma,\tau})\ge 0\},@@`
其中 `@@M@@\operatorname{MP}_w@@` 是沿途权重均值的 `@@M@@\liminf@@`。对绝对常数 `@@M@@C@@`，即使在被抽到会输出错误的随机带上，总位操作数也不超过 `@@M@@2^{C(\log_2(L+2))^2}@@`，费用涵盖预处理、递归调用、中间算术与随机位生成。配套的证书版结论（cor:certified-output）：一次运行要么输出经多项式时间检验的获胜区域及双方位置策略——Max 在 `@@M@@U@@` 内保证非负平均支付，Min 在 `@@M@@U@@` 外保证上极限平均至多 `@@M@@-1/n@@`——要么报告失败，绝不接受错误输出；重复至检验通过即得恒正确的 Las Vegas 算法，期望位代价仍具同一拟多项式界。

## 证明思路

整个求解被压缩为"精确恢复一个整数势能向量"。先做权重变换 `@@M@@t(e)=(n+1)w(e)+1@@`，使每个简单圈的 `@@M@@t@@`-和恒非零且符号恰与原 `@@M@@w@@`-和一致；再在整数盒 `@@M@@[a,b]@@` 上定义单调算子 `@@M@@F@@`（Max 顶点对出边取 `@@M@@\max@@`、Min 顶点取 `@@M@@\min@@` 的 `@@M@@t(e)+p_j@@`），并引入只在支撑集上要求不等式的次解（subsolution）`@@M@@y_i\le F_i(y)@@` 与超解（supersolution）`@@M@@z_i\ge F_i(z)@@`。比较原理保证任一次解整向量不超过任一超解——否则沿两个比较同取等的"紧边"前进，有限性迫使绕出一个零 `@@M@@t@@`-和的简单圈，与第一步矛盾——于是截断映射 `@@M@@\clip_{[a,b]}F@@` 在盒中有唯一不动点。在宽 `@@M@@B_*=8nW@@` 的盒子 `@@M@@[0,B_*]@@` 中，不动点坐标必然落入低带 `@@M@@[0,nW]@@` 或高带 `@@M@@[7nW,8nW]@@`，中点 `@@M@@B_*/2@@` 作阈值即得完整获胜集：高带给出 Max 保证非负支付的位置策略，低带给出 Min 强迫支付至多 `@@M@@-1/n@@` 的策略。但直接迭代约需 `@@M@@nB_*@@` 步，对位长呈指数。

绕过的办法是放弃迭代、对"比较的支撑集"递归。盒子两侧各配正有理权重 `@@M@@\alpha,\beta@@` 与预算 `@@M@@k,m@@`，秩参数 `@@M@@R=km\sum_i 1/(\alpha_i\beta_i)@@`：把一侧预算乘 `@@M@@\eta=4/5@@`，或在 `@@M@@\mu@@`-测度不超过 `@@M@@1/2@@` 的集合上把该侧权重减半并取预算 `@@M@@3/5@@`，重加权引理都保证相交足够重的可容许（admissible）比较保持可容许，且 `@@M@@R@@` 至少缩至原来的 `@@M@@9/10@@`，秩严格下降；秩或盒宽足够小时直接给基例。求解器先用 `@@M@@J@@` 次独立子调用的逐坐标中位数"收紧"盒界；再由定向程序选择截断哪一侧边界——其单次试验沿中心序列 `@@M@@q_{j+1}=\clip\lfloor(r_1+r_2)/2\rfloor@@` 前进（`@@M@@r_1,r_2@@` 为两次分别降预算的调用之答），位移集测度过半即直接裁决，否则用新鲜随机位均匀采样一个中心、进入半径约 `@@M@@B/8@@` 的中心子盒递归；最后对定向返回的例外集逐个重加权调用，并执行唯一一次不放大、参数不变的主延续把盒宽缩去 `@@M@@\delta@@`。正确性是点态的：对每个事先固定的可容许次解（或超解），输出以至少 `@@M@@15/16@@` 的概率整向量支配它；由于比较向量总在子调用抽取新随机位之前被既往历史确定，可沿至多 `@@M@@K=8s(g+1)+1@@` 个节点的主链做"首错"并集界，总失败率 `@@M@@<1/16@@`。顶盒的真实解 `@@M@@x@@` 兼具次解与超解身份，对同一输出取两个事件之交即得 `@@M@@\Pr(p=x)\ge 1-1/16-1/16=7/8@@`，无需对顶点做并界。复杂度方面：初始秩 `@@M@@d(n^3)=O(\log(L+2))@@`，每节点分支数与主链长均为输入长度的多项式，递推 `@@M@@N_d\le K+KA_0N_{d-1}@@` 解出 `@@M@@2^{O((\log(L+2))^2)}@@` 次调用；所有调用计数是确定性的，故每条随机带都守界；中心子盒可向父盒外伸展，但外伸半径几何收敛，一切中间整数仅 `@@M@@O(L)@@` 位。

## 可信度与备注

据官方标注，本篇主结果已通过 Lean 形式化，且算法自带多项式时间证书、绝不接受错误输出，可信度较高。同族姊妹篇《Deterministic quasipolynomial-time mean-payoff games》用不同方法得到同量级的确定性算法，其第 7 节还把精确值与全局最优位置策略归约为多次获胜集查询，可与本文叠加使用；两者证明相互独立，互为印证。需注意概率保证是点态的：对每个固定比较向量成立，而非一次运行同时覆盖全部可容许比较。另按 OpenAI 官方声明，未经形式化的结果可能存在问题；本文主结果已形式化，其余细节仍以社区核验为准。

{% endraw %}
