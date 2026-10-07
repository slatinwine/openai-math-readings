---
layout: default
title: "Memory and precision in noiseless Gaussian regression"
family: "140"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Memory and precision in noiseless Gaussian regression

> 结果族 140：Memory–sample lower bounds for noiseless Gaussian regression　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 一句话结论

本文证明：持有至多 \(Ad^2\) 比特状态的单遍学习者即便读的是无噪高斯线性方程，要把随机单位向量估计到角度误差（angular error）\(\epsilon\) 仍需 \(\Omega_A(d\log(1/\epsilon))\) 个样本，与 Kaczmarz 算法演示的天然尺度吻合。

## 问题背景

一条精确观测 \(\langle x_t,s\rangle\) 是携带任意精度的实数：若全部样本可保留，\(d\) 条高斯方程几乎必然唯一确定未知向量。但单遍流式学习者只能把每次观测压缩进 \(2^M\) 个状态之一，这种压缩是否要多付样本？经典的随机化 Kaczmarz 算法迭代 \(t\) 步后期望误差为 \((1-1/d)^t\)，恰好解释了 \(d\log(1/\epsilon)\) 这个天然尺度，但它存储实数寄存器，不提供有限比特保证。理论方面，Steinhardt–Duchi 与 Raz 等人针对带噪或离散情形建立了内存–样本权衡；最接近的 Sharan–Sidford–Valiant（SSV）结果在带半宽 \(2^{-d/5}\) 微噪的高斯回归中，对 \(d^2/4\) 比特、精度 \(\epsilon=d^{-r}\) 证明了 \(\Omega(d\log r)\) 下界。然而带噪下界推不出精确观测的对应结论——持精确标签的学习者可自行加噪——因此无噪情形的精度代价是否仍为 \(\Theta(d\log(1/\epsilon))\) 一直是悬案，本文正面解决。

## 主要结果

主定理（Theorem 1.2）说：对任意固定 \(A>0\) 存在常数 \(c_A,d_A>0\)，只要 \(d\ge d_A\)，任何持久状态至多 \(M\le Ad^2\) 比特的学习者逐条读取新高斯行 \(x_t\) 与精确标签 \(y_t=\langle x_t,S\rangle\)，若在球面均匀先验（uniform prior on the sphere）\(S\sim\sigma_d\) 下以至少 \(2/3\) 概率做到 \(\arccos\langle\widehat s,S\rangle\le\epsilon\)（\(0<\epsilon\le1/10\)），则其样本时限必然满足 \(T\ge c_A\,d\log(1/\epsilon)\)。模型极为宽松：块内计算与随机化完全不受限，输出只能依赖终态、停止下标与新随机数。两条推论：其一，当 \(M=o(d^2)\) 时常数 \(c\) 是绝对的；其二，把"平均成功"换成"对每个固定信号都成功"，同样的下界依然成立。论文还由此导出 SSV 带噪实验中的 \(\Omega_A(dr\log d)\) 推论。

## 证明思路

证明采用沿时间"倒推"的归纳，最大障碍是后验奇异性：球面均匀先验被一条精确观测条件化后，信号被限制在超平面截面上，相对球面测度没有密度。作者的绕法是不动先验，转而研究从某个指定状态出发、只用未来样本的成功概率 \(h(s)\)，维持不变量：对一切球 \(B(z,r)\) 有 \(\int_{B(z,r)}h\,d\sigma_d\le(Rr)^{(d-1)/2}\)，其中尺度参数 \(R\) 度量成功信号集合的集中程度，终端输出规则天然给出 \(R=\epsilon\)。倒推跨过含 \(m\le q\)（\(q\asymp d\)）条观测的块时，先由一般投影估计给出高斯矩阵及其精确标签联合 law 的 \(L^q\) 密度，其范数损失一个半径幂次；再注意到公共投影椭球体积至多 \(e^{Cd}r^m\)，其 \(1-1/q\) 次幂在 H\"older 不等式中恰好补回密度损失的幂次，半径指数完全相消；最后对 \(N\) 个可能的目的状态再用一次 H\"older，选择代价只有 \(N^{1/q}\)。由于把质量增长换算成尺度增长的是指数 \(a\asymp d\)，最终得 \(\log(R'/R)\le C(1+M/d^2)\)——二次内存正是在此处进入：\(q\asymp d\) 摊薄了 \(\log N\)。于是每倒推一块 \(R\) 至多乘常数倍，而平均成功 \(2/3\) 迫使 \(R\) 有下界，故从 \(\epsilon\) 出发需要 \(\Omega(\log(1/\epsilon))\) 块、每块 \(\asymp d\) 条观测。大尺度端点由反射论证给出：把信号关于全部行的张空间作镜面对称，两个对称信号产生相同数据却相距超过 \(2\epsilon\)，故即便保留全部数据，\(T\le d/4\) 时成功率也不超过 \(1/2+T/(2d(1-\epsilon^2))<2/3\)。随机化规则与可测性（逐 seed 的 Borel 版本）在流式一节统一处理。

## 可信度与备注

据任务文件，本文主结果已有 Lean 形式化证明。同族姊妹篇《Posterior replicas…》（副本耦合与条件信息）与《Localization costs…》（二进制定位）用独立技术路线得到同一 \(\Omega(d\log(1/\epsilon))\) 流式下界，三篇互相印证。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文主定理已形式化，可信度较高。

{% endraw %}
