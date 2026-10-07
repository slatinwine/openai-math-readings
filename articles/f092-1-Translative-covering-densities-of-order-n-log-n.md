---
layout: default
title: "Translative covering densities of order n log n"
family: "092"
discipline: "Convex and metric geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Translative covering densities of order n log n

> 结果族 092：The optimal order of convex-body covering density　·　学科：Convex and metric geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

在充分大的每个维度构造出中心对称凸体，其任意平移覆盖的密度都超过 `@@M@@cn\log n@@`，否定了一致线性上界猜想；与 Rogers 上界相配，最坏平移覆盖密度的阶被钉在 `@@M@@\Theta(n\log n)@@`。

## 问题背景

平移覆盖密度 (translative covering density) `@@M@@\theta_T(K)@@` 度量用凸体 `@@M@@K@@` 的副本铺满 `@@M@@\R^n@@` 所需的最小平均重叠，覆盖中心集合只要求局部有限 (locally finite)，甚至不需要存在渐近密度。Rogers 1957 年证明每个凸体都有密度至多 `@@M@@n\log n+n\log\log n+5n@@` 的周期平移覆盖，Fejes Tóth 后来用 `@@M@@O(\log n)@@` 个陪集达到同阶。下界一侧，Coxeter–Few–Rogers 对等球覆盖给出 `@@M@@\Omega(n)@@` 的障碍，球的精确阶至今悬而未决。Naszódi 记录的问题问：是否存在绝对常数 `@@M@@C@@`，使一切维度、一切凸体都有 `@@M@@\theta_T(K)\le Cn@@`？本文给出否定回答，而且是在"最坏的体可任选"这一最强意义下。

## 主要结果

主定理：存在绝对常数 `@@M@@c>0@@` 与 `@@M@@n_0@@`，对每个整数 `@@M@@n\ge n_0@@`，存在中心对称凸体 `@@M@@K_n\subset\R^n@@` 使

`@@M@@D\theta_T(K_n)>c\,n\log n.@@`

体还可以取为具有有理顶点的中心对称多胞形 (polytope)。结合 Rogers 的经典上界与姊妹篇的单格上界定理，四个量——一般或中心对称凸体、平移或格点覆盖——的密度上确界阶均为 `@@M@@n\log n@@`。

## 证明思路

随机构造：取半径 `@@M@@b=a(1+1/n)@@` 的球与一族对称平板 (slab) 之交

`@@M@@DK=bB\cap\bigcap_{u\in\Pi}\{x:|u\cdot x|\le1\},@@`

法向 `@@M@@u@@` 由球面 `@@M@@S^{n-1}@@` 上强度 `@@M@@\mu=M\sigma@@` 的泊松过程 (Poisson process) `@@M@@\Pi@@` 采样。先证以正概率 `@@M@@|K|>2v\omega_na^n@@`：球 `@@M@@aB@@` 内任一点被切掉的法向测度至多为 1，故期望保留体积至少 `@@M@@e^{-1}@@` 倍，再用上下界夹出严格体积事件。

反证设存在中心强度 `@@M@@\le\rho_0=R/(2v\omega_na^n)@@` 的周期覆盖。关键新机制是决定性局部化：对带重复指标的中心多重集用周期平均恒等式（Tonelli 论证），找到一个平移窗口，其中保留中心数不超过 `@@M@@N_n@@`，且至少一半的点满足"没有中心过近、相关残差个数与径向权重都有预算"；把中心舍入到固定网格，得到覆盖小窗 `@@M@@B_D@@` 的有限列表 `@@M@@P@@`。所有可能列表构成在体采样之前就固定的有限类 `@@M@@\mathcal F_n@@`，其熵不超过 `@@M@@\exp(\lambda_0n+O(\log n))@@`。这样，即使格与陪集是在体选定之后才挑的，也逃不出这个类。

固定 `@@M@@P@@`，证它极难覆盖 `@@M@@B_D@@`：目标 `@@M@@y@@` 处只有距离 `@@M@@\le b+3\eta@@` 的中心相关，残差 `@@M@@x_i=y-p_i@@` 决定球面切割帽 `@@M@@C_i=\{u:|u\cdot x_i|>1+3\eta\}@@`——只要泊松过程在每个相关帽内各落一点，`@@M@@y@@` 就是洞。为处理近重合切割事件的强相依，仿 Li–Liu 把帽分块、每块取一个公共法向子集，把"每个帽被命中"化为"每个槽位分到互异泊松点"的注入计数 `@@M@@Z_y@@`。核心工具是连续版 Janson 下尾不等式：先证允许重复指标的有限 Bernoulli 版本（Harris 相关不等式加私有 Bernoulli 技巧），再用胞腔剖分逼近可测槽位，得 `@@M@@\Prob\{Z_y=0\ \forall y\}\le\exp[-(\sum\nu_y)^2/(2\sum D_{yz})]@@`，协方差项 `@@M@@D_{yz}@@` 由部分匹配图 (partial matching diagram) 控制。目标选取用圆柱体积估计在两个角度尺度上分离：任意目标对的残差方向都分开 `@@M@@H\sqrt{\log n/n}@@`（保证交叉图 `@@M@@\le n^{-3}\nu_y\nu_z@@`），除 `@@M@@\exp(-\gamma n)@@` 比例外都分开 `@@M@@4\sqrt\varepsilon@@`（交叉图为零）；把 `@@M@@e^{n\log n/16}@@` 个目标按活跃度 `@@M@@\nu_y@@` 分箱，同箱目标让分子的平方压倒自重叠 `@@M@@e^{C_*R}@@`，得到双指数小的覆盖概率。最后对所有 `@@M@@P\in\mathcal F_n@@` 取并：因 `@@M@@\gamma>\lambda_0@@`，总失败概率 `@@M@@o(1)@@`，故存在实现同时满足体积下界且无任何保留模式覆盖 `@@M@@B_D@@`，于是 `@@M@@\theta_T=\theta_{\mathrm{per}}\ge\rho_0|K|>R@@`，其中周期化等价 `@@M@@\theta_T=\theta_{\mathrm{per}}@@` 在附录证明。

## 可信度与备注

本文暂无形式化证明。证明建立在 Li–Liu 格点下界的随机平板与泊松见证方法之上，新增的局部化论证专门排除任意有限个格陪集的中心构型；姊妹篇的单格上界与本文下界共同把四个密度量的阶定为 `@@M@@n\log n@@`。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
