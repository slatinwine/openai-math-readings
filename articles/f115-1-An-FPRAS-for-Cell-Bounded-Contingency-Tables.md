---
layout: default
title: "An FPRAS for Cell-Bounded Contingency Tables"
family: "115"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | An FPRAS for Cell-Bounded Contingency Tables

> 结果族 115：Sampling and counting contingency tables with arbitrary margins　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
本文证明：行和、列和与逐格上界（允许取零，即结构性禁区）都以二进制编码、两个维数任意变化的列联表计数，存在完全多项式随机近似方案（FPRAS），且每次运行的比特开销都有一致多项式上界。

## 问题背景
在列联表（contingency table）上再给每个格子一个上界 \(b_{ij}\)，其中 \(b_{ij}=0\) 表示该格被禁止放置（结构性零），要数的是同时满足行和 \(r\)、列和 \(c\) 与所有格界的非负整数矩阵个数 \(Z(r,c,b)\)。精确计数是 #P 难的，目标是完全多项式随机近似方案（FPRAS，fully polynomial randomized approximation scheme）：以 \(1-\delta\) 的概率给出 \((1\pm\epsilon)\) 相对误差内的估计。困难仍在二进制编码：一个格子的容量可以远大于其描述长度，不能被展开成那么多独立选择；此前已知的列联表计数与采样结果都需要固定行数、正容量下界或密度/平衡之类的假设，而逐格上界还让可行集不再是完整的运输多面体（transportation polytope）整点集，组合结构更复杂。

## 主要结果
主定理：存在一个随机算法，输入 \((r,c,b)\) 与有理数 \(\epsilon,\delta\in(0,1)\)，输出非负有理数 \(\widehat Z\)，满足
\[\P\bigl((1-\epsilon)Z(r,c,b)\le\widehat Z\le(1+\epsilon)Z(r,c,b)\bigr)\ge 1-\delta.\]
若可行集为空，则每次执行都输出零。算法只使用独立无偏比特，且存在关于总输入长度 \(L\)、\(\epsilon^{-1}\) 与 \(\log(\delta^{-1})\) 的一个固定多项式，在每一次执行（包括失败事件中）都界定其总比特操作数；不需要任何计数或采样预言机。

## 证明思路
证明把"数值大小"与"组合复杂度"拆开处理。先用网络流（Edmonds–Karp 最短增广路）做可行性判定，并用二分搜索把每格收紧到其可达区间，平移后每格的 \(0\) 与 \(b_s\) 两端都各自被某张可行表取到；再按多项式阈值 \(W\) 把格子分成小格与大格。大格构成一张二部图，取最大容量生成森林：林外的大格作为自由坐标，树上格子的值由非根行/列方程经叶子消去唯一确定，根处的偏差记入罚项。小格则引入双视角：行贡献 \(x_s\) 与列贡献 \(b_s-y_s\)，二者相等当且仅当 \(x_s+y_s=b_s\)。对自由取值定义罚项 \(D\) 度量其对根边际与树格界的违反，软化权重 \(h_j=\sum_z 2^{-jD/H}\) 只在平衡轮廓上求和得到配分函数 \(C(j)\)；\(C(0)\) 显式可算，"污染界" \(Z\le C(H)\le(1+\epsilon/32)Z\) 则把近似计数与原问题挂钩。

接下来做二进制化编码：把界为 \(b_s\) 的小格替换成 \(b_s\) 个带标号的"行–列"元素对，横截面（transversal）从每对中恰选一个元素；配上阶乘归一化后横截面的总质量恰为 \(C(j)\)。作者构造了两个不同的提升权重 \(f_j\) 与 \(\widetilde f_j\)：它们在横截面上相等，分别满足"删二"与"添二"二次型性质——相关矩阵至多有一个正特征值，即 Brändén–Huh 的 Lorentzian 准则在此的离散版本。算法运行在扩充链上：状态空间为横截面加上"一对空、一对满"的缺陷类（defect），Metropolis 交换链配上每类一个乘子 \(w_{il}\)；乘子从观测到的类频率在线学习，这是 Jerrum–Sinclair–Vigoda 求积算法的经典手法。传输（transport）与可观测量方差分析改编自该团队关于两个拟阵公共基计数的工作，同时控制相邻比值 \(C(j+1)/C(j)\) 与缺陷类概率的估计精度，以及横截面迹（trace）的混合与回返成本；退火乘积 \(C(H)=C(0)\prod_j C(j{+}1)/C(j)\) 给出计数。权重 \(h_j\) 本身无法枚举：把自由坐标范围分成每坐标 \(B\) 个箱，在 dyadic 箱权重上做 Metropolis 游走、估计相邻比值、再做人口修正，得到有界的权重求值子程序。最后，单次运行成功概率超过 \(3/4\)，取中位数放大到 \(1-\delta\)；所有有限选择都用固定数量的公平比特实现，并用耦合控制实现误差。

## 可信度与备注
本结果暂无 Lean 形式化证明，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。姊妹篇《Exact Uniform Sampling of Contingency Tables with Arbitrary Margins》解决同族的无界采样侧，两文共享二次签名与传输骨架、互为支撑；本文末节还把结论推及有界整值网络流（network flow）的计数与总变差采样。作者也自陈文中多项式指数非常宽大，是统一的理论保证而非实用运行时间估计。

{% endraw %}
