---
layout: default
title: "Projection moments, positive cap domination, and Riesz estimates on the sphere"
family: "140"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Projection moments, positive cap domination, and Riesz estimates on the sphere

> 结果族 140：Memory–sample lower bounds for noiseless Gaussian regression　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

考试只许带一张小抄：小抄越小，你就得做越多的题才能过关。这篇论文给"小抄大小"与"做题数量"之间的兑换率开出了定量账单，而且用三条互不相干的路（投影矩、正支配、Riesz 估计）各推导一遍——像三个互不通气的审计员算出了同一个数。

**关键词卡片**

- 内存–样本权衡（memory–sample tradeoff）：记得越少，看得越多，本文给出精确汇率
- 无噪高斯观测（noiseless Gaussian observation）：一条精确成立的线性方程，毫无测量误差
- 球冠（spherical cap）：球面上一顶"小帽子"邻域；估计准就是猜进信号所在的小帽子
- 局部质量条件（ball mass growth）：概率质量在任何小球上都不超过 `@@M@@Kt^\beta@@`——"不许聚堆"
- 随机正交投影（random orthogonal projection）：把高维对象随机压到低维，看它的影子

**看个具体例子**

学习器要猜 `@@M@@d=1000@@` 维球面上的均匀随机单位向量，角精度 `@@M@@\epsilon=10^{-6}@@`、成功率 `@@M@@2/3@@`。定理的兑换率长这样：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><line x1="70" y1="230" x2="500" y2="230" stroke="#333" stroke-width="2"/><line x1="70" y1="230" x2="70" y2="45" stroke="#333" stroke-width="2"/><text x="498" y="252" font-size="14" fill="#333" text-anchor="end">记忆 M（比特）</text><text x="14" y="40" font-size="14" fill="#333">样本数 T</text><path d="M 92 62 Q 170 66 235 95 T 400 170 485 200" fill="none" stroke="#c0392b" stroke-width="3"/><line x1="70" y1="62" x2="92" y2="62" stroke="#c0392b" stroke-dasharray="4 3"/><text x="100" y="52" font-size="13" fill="#c0392b">T ≥ c·d·log(1/ε) / (1 + M/d²)</text><text x="6" y="58" font-size="12" fill="#c0392b">13800·c</text><circle cx="92" cy="62" r="4" fill="#c0392b"/><text x="150" y="88" font-size="13" fill="#333">M≈0：也要 13800·c 条观测</text><text x="250" y="145" font-size="13" fill="#333">记忆越多越省</text><text x="320" y="205" font-size="13" fill="#333">但 M 远小于 d² 时省不了多少</text></svg>

</div>

代入数字：`@@M@@\log(1/\epsilon)=\log(10^6)\approx 13.8@@`，故 `@@M@@T\ge c\cdot 1000\cdot 13.8\approx 13800\,c@@` 条；只要内存 `@@M@@M=o(d^2)@@`（远小于 `@@M@@d^2@@`），这个量级纹丝不动。三条证明各有分工：投影矩路线盯着低维影子的密度，正支配路线把概率质量拆成一顶顶球冠帽子，Riesz 路线则借逆距离位势兜底——三条路殊途同归，都落在同一条兑换率曲线上。

**为什么值得关心**

这是首个对"精确无噪声数据"成立的完整记忆–样本下界，三条独立证明互相兜底，显著降低了单一路径出错的风险。

> 已 Lean 形式化

## 一句话结论

本文证明：只有 `@@M@@o(d^2)@@` 比特持久记忆的单遍学习器，要从无噪高斯线性观测中以角精度 `@@M@@0<\epsilon\le1/10@@`、成功概率 `@@M@@2/3@@` 恢复均匀随机单位向量，必需 `@@M@@\Omega(d\log(1/\epsilon))@@` 个样本；支撑它的随机正交投影矩估计、球冠正支配与 Riesz 位势三套工具给出三个独立证明。

## 问题背景

"记忆—样本"权衡问的是：限制算法能记住多少，会迫使它多看多少数据？Steinhardt、Valiant 与 Wager（2016）把这一问题与通信复杂度和统计查询模型相连，Raz（2016）对 parity 学习证明了二次记忆对指数样本的定性分离。在连续回归方向，Sharan、Sidford 与 Valiant（2019）证明：`@@M@@d^2/4@@` 比特记忆、欧氏精度 `@@M@@d^{-r}@@`、加性噪声模型需要 `@@M@@\Omega(d\log r)@@` 个样本。但他们的论证依赖噪声尺度与全局 `@@M@@L^2@@` 密度条件；无噪（exact label）模型中每条方程携带任意精度的实信息，旧下界无法直接搬用。本文回到位势论（potential theory）的古典源头——Mattila（1975）的投影能量平均与 Drury（1984）的单纯体积雅可比——为精确标签建立局部质量条件下的投影矩理论。

## 主要结果

三条分析主线。其一（投影矩，projection moment）：设 `@@M@@\nu@@` 为 `@@M@@\R^d@@` 上有限正测度，在每个半径 `@@M@@t@@` 的球上质量至多 `@@M@@Kt^\beta@@`（Frostman 型局部质量条件），`@@M@@P@@` 为 `@@M@@k@@` 行随机正交矩阵（Haar 框架），`@@M@@g_P@@` 为推前测度 `@@M@@P_\#\nu@@` 的密度，则密度矩的框架平均 `@@M@@\E_P\int g_P^q@@` 有关于维度、支撑半径与指数 `@@M@@\beta@@` 显式的界。其二（正支配，positive domination）：对球冠（spherical cap）`@@M@@B@@` 上的条件测度 `@@M@@\mu_B@@` 经路由规则加权后的测度 `@@M@@f_w\mu_B@@`，存在可数个规范化球冠测度之和将其正支配，细半径的代价受一个参考路由概率的幂控制。其三（Riesz 估计）：受环境 Riesz 泛函 `@@M@@V(h)=\sup_z\int h\|s-z\|^{-d/2}\,d\sigma@@` 控制的测试函数，其高斯投影密度在每个固定仿射偏移（affine offset）处有同一密度版本的一致矩界。

回归推论：记忆 `@@M@@M(d)=o(d^2)@@`、均匀球面平均成功概率至少 `@@M@@2/3@@`、角精度 `@@M@@0<\epsilon(d)\le1/10@@` 的学习器必须 `@@M@@T\ge c\,d\log(1/\epsilon)@@`；且显式权衡 `@@M@@T\ge \frac{c\,d\log(1/\epsilon)}{1+M/d^2}@@` 对一切非负整数 `@@M@@M@@` 成立，故 `@@M@@M\le Ad^2@@` 时得 `@@M@@\Omega_A(d\log(1/\epsilon))@@`。

## 证明思路

综合矩估计的骨架是：把 `@@M@@q@@` 阶密度矩展开为测度中 `@@M@@q@@` 个点的标签碰撞概率，碰撞由 `@@M@@q-1@@` 个差向量的投影控制。逐列观察 Haar 框架：正交框架的相继坐标有椭球密度，其行列式幂在连乘中逐项相消，只剩一个非负行列式幂与显式的 `@@M@@\sqrt d@@` 尺度；再用 Gram–Schmidt 把剩余变量换成逆仿射高度（successive affine heights），其乘积恰是 Drury 式单纯体积（simplex volume）。对每个先前点的仿射张成作管状邻域（tube）并用球覆盖，局部质量假设便"从后往前"把这些高度积分掉。

回归应用中，先把高斯矩阵分解为正径向因子与独立的正交框架；路由规则可以用整个径向因子，对其取平均即产生框架与投影标签上的权重。投影支撑是一个 `@@M@@k@@` 维球，其体积恰好抵消密度范数中的维度尺度，使输出的半径指数与进入的局部质量指数一致——因此"向后传播"穿过每个数据块都保持环境维度，停止指标（stopping index）在块内计数，最后用对径引理（antipodal bound：`@@M@@T\le d/8@@` 时即使白送全部数据，成功也不超过 `@@M@@5/8@@`）去掉多余的加性 `@@M@@d@@`。

正支配路线方向相反：先由可数球冠字典上的有界测试推出重尺度测试测度的球质量界，再用归一化的矩定理控制 `@@M@@f_w\mu_B@@`；为把一列不等式变成真正的正支配测度，取加权的球冠密度族——每个尺度只留有限个球冠、加权成本使细尺度 `@@M@@L^1@@` 尾趋于零，由此获得范数紧性；对闭的下调凸集（downward convex set）作严格分离，即产生恰好已被控制的正测度和。用它向前传播信号—状态联合律，停止指标只在最后求和一次。

Riesz 路线改用锚定在 `@@M@@z@@` 处的 `@@M@@q@@` 个向量（而非锚定在采样点的 `@@M@@q-1@@` 个差向量），它们在高斯行下的像协方差为锚定 Gram 矩阵，所得球平均估计对一切固定偏移一致；取下极限密度版本并在每个偏移图上用 Fatou 引理保住估计，再用算子范数分箱与径向壳层控制此前延拓的位势。该路线保留 `@@M@@1+\log(1/\epsilon)@@` 的壳层因子与全局终止时钟，两者由其自身的短程论证处理。

## 可信度与备注

主结果已 Lean 形式化（结果族 140 附 Lean 证明文档）。三个证明相互独立、代价结构各有取舍，同一下界的多重推导显著降低了单一路径出错的风险；族内姊妹篇《Subsphere methods…》与《Replacing Gaussian observations…》分别以子球面条件化与信息论比较得到同阶下界，三面互证。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本文的回归下界与显式记忆权衡已形式化，个别显式常数以论文文本为准。

{% endraw %}
