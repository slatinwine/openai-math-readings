---
layout: default
title: "Random Walks on Critical FK–Ising Maps and Liouville Brownian Motion"
family: "211"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Random Walks on Critical FK–Ising Maps and Liouville Brownian Motion

> 结果族 211：The geometric phase diagram, diffusion, and spectra of random planar maps　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
证明了临界球面 FK–Ising 地图上的平稳简单随机游走，在时间恰好加速 \(n\)（边数）倍后，连同随机曲面一起收敛到 \(\sqrt3\)-量子球上的刘维尔布朗运动——首次在该模型得到常数恒为 1 的精确线性时钟。

## 问题背景
随机平面地图（random planar map）是统计力学与二维量子引力的离散随机曲面。Sheffield 的存货累积编码（inventory accumulation）把临界 Fortuin–Kasteleyn（FK）装饰地图与相关布朗路径联系起来，Gwynne–Sun 证得其有限体积等值线编码的极限，mating-of-trees 理论（Duplantier–Miller–Sheffield 及 Miller–Sheffield 的有限球面形式）进一步把极限曲面识别为 \(\gamma=\sqrt3\) 的刘维尔量子引力（LQG）球面。但曲面的极限并不自动决定曲面上粒子的运动极限：带时间参数的游走还依赖图的电网络能量与顶点质量分布。此前 Berestycki–Gwynne 在 mated-CRT 地图上证明了游走收敛到刘维尔布朗运动（Liouville Brownian motion），但其时钟由中位出口时间归一化定义，渐近常数未被识别（其文 Remark 1.3 明确遗留此问题）。本文在普通有限 FK–Ising 球面上解决这一问题，并给出精确时钟。

## 主要结果
模型为临界球面 FK–Ising 地图 \((M_n,A_n)\)：\(n\) 条边的有根平面多重图配上边子集 \(A\)，概率正比于 \(2^{\ell(M,A)/2}\)，其中 \(\ell=k(A)+k(A^*)-1\) 由 \(A\) 与对偶 \(A^*\) 的连通分支数定义。游走在每个顶点等概率选取一条关联半边（half-edge）并走到其对端，保留环与重边；其平稳分布恰为角测度（corner measure）\(\mu_n(v)=\deg(v)/(2n)\)。主定理：设确定性尺度 \(a_n\to0\) 使度量-测度空间 \((V_n,a_nd_n,\mu_n)\) 在 Gromov–Hausdorff–Prokhorov 意义下收敛到单位面积 \(\sqrt3\)-量子球 \((S,D_h,\mu_h)\)，则把时间加速恰好 \(n\) 倍后，电缆实现（cable realization）上的插值游走与曲面联合收敛：给定地图出发的 \(r\) 条条件独立平稳游走，收敛到给定 \(h\) 的 \(r\) 条独立刘维尔布朗运动，极限扩散由狄利克雷型（Dirichlet form）\(\E_h(f,f)=\frac12\int_S\abs{\nabla_g f}^2\dd\mathrm{vol}_g\) 的闭包生成，收敛在曲线装饰的 Gromov–Hausdorff–Prokhorov 拓扑中成立，且保留条件路径律而非仅平均后的轨道分布。

## 证明思路
文章把证明明确拆为"引进输入"与"本地新贡献"。先从谱姊妹篇引进四项输入：同一保角坐标下的几何收敛（把地图一致化到坐标球面后，顶点间距离无畸变、嵌入网格趋于零）；通过角巡回（corner tour）把 \(L^2(\mu_n)\) 与 \(L^2(\mu_h)\) 等距嵌入同一希尔伯特空间 \(L^2([0,1])\)；中心化逆算子（centered inverse）的 Hilbert–Schmidt 收敛；以及单位电导率下的局部能量恢复——图上截断函数一致逼近光滑函数且能量无多余消耗。由逆算子收敛得正时间半群收敛，配以探索巡回的一致跟踪，在公共坐标中识别有限维分布。真正的新困难是保留时间参数的紧性（tightness）：特征值收敛乃至有限维分布收敛，都不能排除空间直径可观的快速远足。绕过办法是：先对光滑空间截断用局部能量恢复构造全图一致的图截断；再用预解式（resolvent）磨光，得到生成子一致有界、仍在整条路径上准确的逼近函数；关键一步是证明一个有限状态马尔可夫链版本的 Lyons–Zheng 前向–后向鞅极大不等式（本文直接对跳链证明），把两个逼近之间的形式范数误差转化为沿平稳轨迹一致的路径误差；最后对磨光截断做可选停止（optional sampling），得到停止时间增量估计，满足 Aldous 紧性判据。极限路径必连续（最大跳跃随嵌入网格消失）、有限维分布唯一，收敛由此得证；末节再转移到电缆路径、消除指数时钟，并组装出随机环境中的联合收敛。全程无需额外混合假设或热核估计，但平稳性在论证中必不可少——作者明言不主张任意起始顶点的收敛。

## 可信度与备注
本文主结果暂无形式化证明；依 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。几何与电网络输入全部来自同族谱姊妹篇（Spectral convergence for critical FK–Ising planar maps）的命题 2.4、定理 5.2 等，两篇互为支撑：姊妹篇证单位电导率与逆算子收敛，本文补上"从算子到路径"的最后一环；姊妹篇另证得特征值与热迹收敛，与本文共享同一极限曲面，形成闭环。

{% endraw %}
