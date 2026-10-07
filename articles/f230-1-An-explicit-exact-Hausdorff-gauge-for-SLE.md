---
layout: default
title: "An explicit exact Hausdorff gauge for SLE"
family: "230"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | An explicit exact Hausdorff gauge for SLE

> 结果族 230：Exact Hausdorff gauges for SLE　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文给出 Schramm 问题的显式解答：当 `@@M@@0<\kappa<8@@`、`@@M@@d=1+\kappa/8@@` 时，规范 `@@M@@h(r)=r^d(\log\log(1/r))^{(2-d)/2}@@` 使 `@@M@@\mathrm{SLE}_\kappa@@` 每段轨迹的豪斯多夫测度几乎必然正且有限；同时证明 Schramm 建议的 `@@M@@r^d\log\log(1/r)@@` 并非 `@@M@@\sigma@@`-有限。

## 问题背景

对 `@@M@@0<\kappa<8@@` 的弦 `@@M@@\mathrm{SLE}_\kappa@@`（chordal Schramm–Loewner evolution），Beffara 求得轨迹维数 `@@M@@d=1+\kappa/8@@`，Rezaei 证明临界幂 `@@M@@r^d@@` 的豪斯多夫测度（Hausdorff measure）为零，于是问题聚焦在"对数修正取什么形状"。Schramm 建议 `@@M@@r^d\log\log(1/r)@@`，但长期无人能证。前一日的姊妹篇用矩积分构造出存在性规范，却既未给出规则公式，也未判定 Schramm 猜想的真伪。另需注意 Holden–Yuan 的规范 `@@M@@r^d(\log\log(1/r))^{-(d-1)}@@` 作用于有序时间分割，与本文任意空间覆盖下的豪斯多夫测度是不同的长度概念。

## 主要结果

记 `@@M@@p=2-d=1-\kappa/8\in(0,1)@@`，在足够小的半径上取
`@@M@@Dh(r)=r^d\bigl(\log\log(1/r)\bigr)^{p/2}@@`
（大半径处连续单调延拓）。定理 1.1：在一个概率为一的事件上，对所有实数 `@@M@@0<s<t<\infty@@` 同时有 `@@M@@0<\mathcal H^h(\gamma([s,t]))<\infty@@`；且对每个 `@@M@@0<R<\infty@@`，`@@M@@\mathbb E\,\mathcal H^h(\Gamma\cap\overline B(0,R))\le C_{\kappa,R}@@`，其中 `@@M@@\Gamma=\gamma([0,\infty))@@` 含实轴点，即整条轨迹在每个有界圆盘内期望测度有限。推论 1.2：对 `@@M@@g(r)=r^d\log\log(1/r)@@`，`@@M@@\mathcal H^g@@` 限制在任一 `@@M@@\gamma([s,t])@@` 上都不是 `@@M@@\sigma@@`-有限——因 `@@M@@h/g\to0@@`，任何 `@@M@@\mathcal H^g@@`-有限测度之集的 `@@M@@\mathcal H^h@@`-测度为零，与该段 `@@M@@\mathcal H^h@@`-测度为正矛盾。故正确的对数修正指数是 `@@M@@(2-d)/2@@` 而非 1。

## 证明思路

上、下界需要相反类型的局部事件：下界要把轨迹上的质量控制在小球内不超过 `@@M@@h(r)@@`，上界要找到偶尔"异常富有"的圆盘。

下界从定量尾估计出发。在活点 `@@M@@z@@` 处取格林密度 `@@M@@R^{-p}\sin^{8/\kappa-1}\theta@@`，在其首次活逼近至距离 `@@M@@e@@` 时停住，得停权 `@@M@@W_e(z)@@`；核心估计是 `@@M@@\mathbb P\{\int_AW_e\,dA>u\}\le C\exp(-cu^{2/p})@@`，且关于允许的过去与最终网格一致。其机制是先在中间距离 `@@M@@\delta@@` 处测试大质量：确定性密度界给出 `@@M@@\delta^{-p}@@`，而更细网格的后续增量只在概率 `@@M@@\le Ce^{-c\delta^{-2}}@@` 的例外事件上抬高此界，取 `@@M@@\delta\sim u^{-1/p}@@` 即得指数 `@@M@@2/p@@`；实现时 `@@M@@\kappa\le4@@` 用格林核递减，`@@M@@\kappa>4@@` 用空间分离窗口加吞噬估计。随后删除边长 `@@M@@r=2^{-k}@@`、质量超过 `@@M@@Dr^d(\log k)^{p/2}@@` 的二进方格：命中一个方格代价 `@@M@@O(r^p)@@`、方格共 `@@M@@O(r^{-2})@@` 个、质量尺度为 `@@M@@r^d@@`，恰因 `@@M@@p+d=2@@` 而平衡；指数尾使删除损失可和，正的一阶矩加有界的二阶矩留下正的剩余质量，其弱极限在每个小球上质量 `@@M@@\lesssim h(r)@@`，再在确定性容量时槽上重启即得每段为正。

上界用蛇形带（serpentine ribbon）制造"稠密到访"。对曲线段 `@@M@@\eta@@`，其在网格 `@@M@@v@@` 的归一化香肠面积（sausage area）为 `@@M@@v^{-p}\mathrm{Area}\{\mathrm{dist}(z,\eta)<v\}@@`；`@@M@@m@@` 条并行通道在尺度 `@@M@@m^{-1}@@` 上提供约 `@@M@@m^2@@` 次互不相交的局部测试。"单步引理"给出一致于整个粗糙过去与网格截断的条件成功概率 `@@M@@\ge q@@`（通过共形映射沿内部导轨的紧性与一致局部分解，把光滑模板的点态支撑变成一致界），于是整次到访以概率 `@@M@@\ge c\,e^{-Cm^2}@@` 产生归一化面积 `@@M@@\sim m^p@@`。最终取 `@@M@@m\asymp\sqrt{\log n}@@`，在 `@@M@@j\in[n/3,2n/3]@@` 的几何间隔半径 `@@M@@r_j@@` 上做约 `@@M@@n@@` 次测试：条件成功界（无需独立性）使总失败很小，而 `@@M@@\log n\asymp\log\log(1/r_j)@@`，产生的质量恰与 `@@M@@h@@` 中 `@@M@@(\log\log)^{p/2}@@` 的修正匹配。贪心选出的不相交圆盘统一记在单一网格香肠测度 `@@M@@\mu^v@@` 的账上，其期望在每个有界圆盘一致有界（`@@M@@p<1@@` 保证边界积分收敛），漏检格子的代价趋于零，让时间与高度截断同时增大即得全时结论。

## 可信度与备注

本文主结果暂无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。本文的停时换律、质量与覆盖论证均自含，不引用姊妹篇的证明结果；姊妹篇证明存在性，本文给出显式公式并否定 Schramm 的指数一猜想，两篇互相印证，但两个精确规范之间的渐近关系仍开放。

{% endraw %}
