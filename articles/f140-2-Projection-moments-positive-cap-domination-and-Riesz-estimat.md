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

## 一句话结论

本文证明：只有 \(o(d^2)\) 比特持久记忆的单遍学习器，要从无噪高斯线性观测中以角精度 \(0<\epsilon\le1/10\)、成功概率 \(2/3\) 恢复均匀随机单位向量，必需 \(\Omega(d\log(1/\epsilon))\) 个样本；支撑它的随机正交投影矩估计、球冠正支配与 Riesz 位势三套工具给出三个独立证明。

## 问题背景

"记忆—样本"权衡问的是：限制算法能记住多少，会迫使它多看多少数据？Steinhardt、Valiant 与 Wager（2016）把这一问题与通信复杂度和统计查询模型相连，Raz（2016）对 parity 学习证明了二次记忆对指数样本的定性分离。在连续回归方向，Sharan、Sidford 与 Valiant（2019）证明：\(d^2/4\) 比特记忆、欧氏精度 \(d^{-r}\)、加性噪声模型需要 \(\Omega(d\log r)\) 个样本。但他们的论证依赖噪声尺度与全局 \(L^2\) 密度条件；无噪（exact label）模型中每条方程携带任意精度的实信息，旧下界无法直接搬用。本文回到位势论（potential theory）的古典源头——Mattila（1975）的投影能量平均与 Drury（1984）的单纯体积雅可比——为精确标签建立局部质量条件下的投影矩理论。

## 主要结果

三条分析主线。其一（投影矩，projection moment）：设 \(\nu\) 为 \(\R^d\) 上有限正测度，在每个半径 \(t\) 的球上质量至多 \(Kt^\beta\)（Frostman 型局部质量条件），\(P\) 为 \(k\) 行随机正交矩阵（Haar 框架），\(g_P\) 为推前测度 \(P_\#\nu\) 的密度，则密度矩的框架平均 \(\E_P\int g_P^q\) 有关于维度、支撑半径与指数 \(\beta\) 显式的界。其二（正支配，positive domination）：对球冠（spherical cap）\(B\) 上的条件测度 \(\mu_B\) 经路由规则加权后的测度 \(f_w\mu_B\)，存在可数个规范化球冠测度之和将其正支配，细半径的代价受一个参考路由概率的幂控制。其三（Riesz 估计）：受环境 Riesz 泛函 \(V(h)=\sup_z\int h\|s-z\|^{-d/2}\,d\sigma\) 控制的测试函数，其高斯投影密度在每个固定仿射偏移（affine offset）处有同一密度版本的一致矩界。

回归推论：记忆 \(M(d)=o(d^2)\)、均匀球面平均成功概率至少 \(2/3\)、角精度 \(0<\epsilon(d)\le1/10\) 的学习器必须 \(T\ge c\,d\log(1/\epsilon)\)；且显式权衡 \(T\ge \frac{c\,d\log(1/\epsilon)}{1+M/d^2}\) 对一切非负整数 \(M\) 成立，故 \(M\le Ad^2\) 时得 \(\Omega_A(d\log(1/\epsilon))\)。

## 证明思路

综合矩估计的骨架是：把 \(q\) 阶密度矩展开为测度中 \(q\) 个点的标签碰撞概率，碰撞由 \(q-1\) 个差向量的投影控制。逐列观察 Haar 框架：正交框架的相继坐标有椭球密度，其行列式幂在连乘中逐项相消，只剩一个非负行列式幂与显式的 \(\sqrt d\) 尺度；再用 Gram–Schmidt 把剩余变量换成逆仿射高度（successive affine heights），其乘积恰是 Drury 式单纯体积（simplex volume）。对每个先前点的仿射张成作管状邻域（tube）并用球覆盖，局部质量假设便"从后往前"把这些高度积分掉。

回归应用中，先把高斯矩阵分解为正径向因子与独立的正交框架；路由规则可以用整个径向因子，对其取平均即产生框架与投影标签上的权重。投影支撑是一个 \(k\) 维球，其体积恰好抵消密度范数中的维度尺度，使输出的半径指数与进入的局部质量指数一致——因此"向后传播"穿过每个数据块都保持环境维度，停止指标（stopping index）在块内计数，最后用对径引理（antipodal bound：\(T\le d/8\) 时即使白送全部数据，成功也不超过 \(5/8\)）去掉多余的加性 \(d\)。

正支配路线方向相反：先由可数球冠字典上的有界测试推出重尺度测试测度的球质量界，再用归一化的矩定理控制 \(f_w\mu_B\)；为把一列不等式变成真正的正支配测度，取加权的球冠密度族——每个尺度只留有限个球冠、加权成本使细尺度 \(L^1\) 尾趋于零，由此获得范数紧性；对闭的下调凸集（downward convex set）作严格分离，即产生恰好已被控制的正测度和。用它向前传播信号—状态联合律，停止指标只在最后求和一次。

Riesz 路线改用锚定在 \(z\) 处的 \(q\) 个向量（而非锚定在采样点的 \(q-1\) 个差向量），它们在高斯行下的像协方差为锚定 Gram 矩阵，所得球平均估计对一切固定偏移一致；取下极限密度版本并在每个偏移图上用 Fatou 引理保住估计，再用算子范数分箱与径向壳层控制此前延拓的位势。该路线保留 \(1+\log(1/\epsilon)\) 的壳层因子与全局终止时钟，两者由其自身的短程论证处理。

## 可信度与备注

主结果已 Lean 形式化（结果族 140 附 Lean 证明文档）。三个证明相互独立、代价结构各有取舍，同一下界的多重推导显著降低了单一路径出错的风险；族内姊妹篇《Subsphere methods…》与《Replacing Gaussian observations…》分别以子球面条件化与信息论比较得到同阶下界，三面互证。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本文的回归下界与显式记忆权衡已形式化，个别显式常数以论文文本为准。

{% endraw %}
