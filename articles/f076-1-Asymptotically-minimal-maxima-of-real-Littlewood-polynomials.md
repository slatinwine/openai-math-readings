---
layout: default
title: "Asymptotically minimal maxima of real Littlewood polynomials"
family: "076"
discipline: "Real and complex analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Asymptotically minimal maxima of real Littlewood polynomials

> 结果族 076：Real ultraflat Littlewood polynomials and unbounded binary merit factors　·　学科：Real and complex analysis　·　验证状态：主结果已 Lean 形式化

## 一句话结论
证明了长度为 `@@M@@N@@`、系数全为 `@@M@@\pm1@@` 的实 Littlewood 多项式在单位圆上的最大模最小值是 `@@M@@(1+o(1))\sqrt N@@`，恰好取到 Parseval 下界的渐近值，推翻了 Erdős 固定相对间隙猜想的实符号版本；由此二元字的最大 merit factor（优值因子）随长度趋于无穷，推翻了 Turyn 猜想。

## 问题背景
对 Littlewood 多项式 `@@M@@P(z)=\sum_{k=0}^{N-1}\varepsilon_kz^k@@`（`@@M@@\varepsilon_k\in\{-1,1\}@@`），Parseval 恒等式给出归一化最大模 `@@M@@m_N\ge1@@`。Erdős 1957 年问题集中的固定间隙问题问：`@@M@@m_N@@` 是否最终被 `@@M@@1+c@@`（`@@M@@c>0@@` 为绝对常数）一致压在上方？复单位模系数情形已被 Kahane（1980）的超平坦构造否定，但实符号限制下问题长期悬置：Shapiro–Rudin 构造只给出 `@@M@@\sqrt{2N}@@`（二进长度），Balister 等人 2020 年的双侧平坦结果也只控制数量级而不让常数趋于 1。本文证得 `@@M@@\lim_{N\to\infty}m_N=1@@`，且极限穿越所有整数长度而非子序列，这正是难点所在。注意与 Erdélyi 的下界 `@@M@@\|P\|_\infty^2\ge N+(N-1)^{1/3}/38@@` 相容——加性间隙仍可增长，只是相对量趋于零。

## 主要结果
**定理**：`@@M@@\lim_{N\to\infty}m_N=1@@`。等价地，对每个 `@@M@@\eta>0@@` 存在 `@@M@@N_0@@`，使每个 `@@M@@N\ge N_0@@` 都有符号使 `@@M@@\max_{|z|=1}|\sum_{k=0}^{N-1}\varepsilon_kz^k|\le(1+\eta)\sqrt N@@`。定理只给上界，不断言 `@@M@@|P(z)|@@` 有正下界，也不给出收敛速度或有效算法。**推论一（merit factor）**：二元字 `@@M@@A@@` 的优值因子 `@@M@@F(A)=N^2/(2\sum_{u}C_u(A)^2)@@`（`@@M@@C_u@@` 为非周期自相关）的最大值 `@@M@@\mathcal F_N\to\infty@@`，即 Turyn 猜想（等价于 Erdős 的 `@@M@@L^4@@` 范数猜想）不成立，且对所有整数长度成立。**推论二（符号动力系统）**：借助 Downarowicz–Lacroix 的构造，存在唯一遍历、具有简单谱（simple spectrum）的二进 Morse 移位，其零坐标谱测度绝对连续且密度属 `@@M@@L^2(\mathbb T)@@`。另有：归一化模在每个固定的 `@@M@@L^p(0<p<\infty)@@` 范数中趋于 1。

## 证明思路
证明采用"松弛—取整"两步框架。先允许系数 `@@M@@X_{N,k}\in[-1,1]@@`，把与符号的偏差集中为缺陷 `@@M@@\mu(X)=\frac12\sum(1-|X_k|)@@`；核心逼近命题造出能量 `@@M@@\frac1N\sum X_k^2\ge1-7\delta@@`、Fourier 最大模 `@@M@@\le K_\delta\sqrt N@@`（`@@M@@K_\delta=\sqrt{(1+\delta)^3/(1-\delta)}@@`）的松弛向量，于是 `@@M@@\mu/N\le4\delta@@`；缺陷敏感的取整引理随后把它换成真符号，圆周误差仅 `@@M@@C\sqrt{\mu\log(80N/\mu)}@@`，最终 `@@M@@m_N\le K_\delta+2C\sqrt{\delta\log(20/\delta)}@@`，令 `@@M@@\delta\downarrow0@@` 即得 1。松弛系数的构造分三步。先在高维环面上递推 `@@M@@p_j=p_{j-1}+\frac{1-p_{j-1}^2}{2}\cos(2\pi y_j)@@` 造出 `@@M@@|p|\le1@@`、平方平均趋近 1 的实三角多项式，再用二次相位把各 Fourier 系数摊到频率盒上，使每个频率 `@@M@@a@@` 分得宽度 `@@M@@w_a=|a\cdot v|@@`、系数约 `@@M@@\sqrt{w_a}@@` 大小，且总宽度严格小于 1。接着是组合心脏：带符号区间装填引理——要在圆周上为 `@@M@@2rH@@` 个驻相区间安排两两不交的位置，作者在有限域 `@@M@@\mathbb F_q@@` 上随机构造 `@@M@@r@@` 均匀超图（顶点是半圆内随机开槽、随机定向的中心，边是线性方程组 `@@M@@a_i\cdot y=s_i@@` 可解的相容元组），验证它几乎正则且余度很小，再用 Pippenger–Spencer 边染色定理取出大匹配，其生成向量给出装填中心。最后沿二次相位采样 `@@M@@F@@`：每个角度至多一个驻相贡献幸存，大小 `@@M@@|c_a|/\sqrt{|\lambda_a|}@@`，Poisson 求和与一致驻相公式保证逼近对所有角度一致，正交性回收近乎全部能量。所有维数、素数、块与光滑截断都在 `@@M@@N\to\infty@@` 之前固定，这正是"所有长度"成立的原因。merit factor 推论由 `@@M@@\|P_A\|_4^4=N^2+2\sum C_u^2@@` 与 `@@M@@m_N\to1@@` 直接推出。

## 可信度与备注
本篇是结果族 076 中唯一主结果已有 Lean 形式化的（见合集 lean/docs/076.md 指向的 AsymptoticallyMinimalLittlewood.lean），可信度最高；两篇姊妹篇复用其铺开、装填、采样与取整框架，分别补上正下界 `@@M@@\frac1{16}\sqrt N@@` 与完整超平坦 `@@M@@(1\pm\varepsilon)\sqrt N@@`。文中附录还逐条检查了 el Abdalaoui 非平坦性预印本的具体问题。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇主定理已形式化，推论的符号动力系统部分建议以社区核验为准。

{% endraw %}
