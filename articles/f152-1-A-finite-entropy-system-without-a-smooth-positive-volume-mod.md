---
layout: default
title: "A zero-entropy system without a smooth positive-volume model"
family: "152"
discipline: "Dynamical systems and ergodic theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A zero-entropy system without a smooth positive-volume model

> 结果族 152：Zero entropy does not guarantee a smooth positive-volume model　·　学科：Dynamical systems and ergodic theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文构造了一个零 Kolmogorov–Sinai 熵、遍历、可逆的测度保持变换，并证明它不与任何紧有限维流形上保持严格正光滑概率密度的 `@@M@@C^\infty@@` 微分同胚可测共轭——单个反例同时排除一切有限维数，说明"零熵"之下光滑正体积实现仍可整体失败。

## 问题背景

光滑实现问题 (smooth realization problem) 问：哪些抽象测度保持系统 `@@M@@(X,\mu,T)@@` 能用紧流形上的光滑动力系统表示？Lind 与 Thouvenot（1977）证明任意有限熵遍历变换可实现为二维环面上保 Lebesgue 测度的同胚；Quas 与 Soo 又用无单位根特征值的环面自同构实现一切有限熵系统，但其不变测度只是满支撑的 Borel 概率，允许奇异。若要求不变测度本身是严格正的光滑密度 (smooth positive volume)，此前既无普适实现定理也无反例：Katok–Thouvenot（1997）的慢熵 (slow entropy) 障碍针对须同时实现两个交换生成元的 `@@M@@\mathbb{Z}^2@@` 作用，不回答单个变换的问题；Foreman–Weiss 等的反分类 (anti-classification) 定理刻画的是光滑模型族内部等价关系的复杂性，并不指认某个具体抽象系统缺少光滑模型。Ruelle 的可微熵不等式说明有限熵是必要限制，本文证明即使在零熵也不充分。

## 主要结果

主定理 (thm:main)：存在标准无原子概率空间 (standard nonatomic probability space) 上的遍历可逆测度保持变换 `@@M@@(X,\mu,T)@@`，其 Kolmogorov–Sinai 熵 `@@M@@h_\mu(T)=0@@`，且在任何不变全测集上都不与如下系统可测共轭 (measurably conjugate)：紧有限维光滑流形 `@@M@@M@@`、形如 `@@M@@d\nu=f(x)|dx_1\cdots dx_d|@@`（`@@M@@f>0@@` 且光滑到边界）的概率体积 `@@M@@\nu@@`、以及保 `@@M@@\nu@@` 的 `@@M@@C^\infty@@` 微分同胚 `@@M@@S@@`。流形可以带光滑边界、也可以不可定向；共轭映射只要求可测，不要求连续。作者同时言明：结论不触及仅与体积等价但密度不光滑、或奇异的模型。

## 证明思路

证明分光滑侧、符号侧与最终对撞三步，先固定符号系统、后假设光滑模型，次序本身是论证的一部分。

光滑侧核心是"切换定理" (smooth switching, thm:switching)。任取保光滑正体积的系统 `@@M@@(M,\nu,S)@@`，在二进时刻 `@@M@@n=2^k@@` 把 `@@M@@M@@` 剖成至多 `@@M@@\exp(CB_k n)@@` 个胞腔，其中 `@@M@@\sum_k B_k^{16}<\infty@@`；先按体积选一个胞腔，再在其中独立取两点 `@@M@@x,y@@`。对质量 `@@M@@\ge 1-\eta@@` 的点对，存在切换点 `@@M@@z@@`：其未来 `@@M@@[0,n]@@` 一致影子化 (shadowing) `@@M@@x@@` 的未来、过去 `@@M@@[-n,0]@@` 一致影子化 `@@M@@y@@` 的过去，且 `@@M@@z@@` 的未归一化分布被 `@@M@@2\nu@@` 控制。构造分三层：先在正交标架丛上对导数作正对角 QR 分解，得平稳三角上循环 (stationary triangular cocycle)，对对数对角项证明二进弦估计 (dyadic chord estimate)——把块平均按二分层级逐层平方差求和即得平方可和偏差，从而完全绕开对遍历定理收敛速率的依赖；再用有限区间上的快/慢分裂把两段轨道的拼接化为线性差分方程的边值问题，以加权传播子与 Neumann 级数求逆、经非线性压缩收敛为一条真轨道；最精巧的是测度控制——互补的两个切换 `@@M@@(z,w)@@` 的端点坐标恰好互换，用外幂 (exterior power) 的相对子式估计转移巨大因子，行列式恒等式给出雅可比 `@@M@@1+o(1)@@`，全局单射性保证换元无重数，最终得 `@@M@@(z_k)_*(\rho_k|_{G_k})\le 2\nu@@`。

符号侧构造对立面：递归词族 `@@M@@\mathcal W_i@@`（每级 `@@M@@L_i=2^{2s_i}-1@@` 个词，长度 `@@M@@m_i@@` 为二的幂），词标签等同于 `@@M@@\mathbb{F}_2^{2s_i}@@` 的非零向量并赋辛形式 `@@M@@[\cdot,\cdot]_i@@`；同一 `@@M@@H_i@@`-组内相隔 `@@M@@2^k@@` 个块位的标签对被强制正交，同时短标签列表熵高、词与其错位拼接保持正的符号距离 `@@M@@d_*@@`（即 comma-free index）。在同时记录符号序列与全部相容相位的紧空间上取遍历测度：因每符号信息率 `@@M@@R_i\to 0@@`，熵为零；但对齐的标签列表熵 `@@M@@\ge .996(D-1)\ell_i@@`，且合法点的过去、未来对应标签几乎必然通过正交测试。

最后对撞：设某光滑模型存在并固定，其 `@@M@@(B_k)@@` 随之固定，而 `@@M@@\sum_i K_iR_i^{16}=\infty@@` 与 `@@M@@\sum_k B_k^{16}<\infty@@` 不相容，故可选出测试时刻 `@@M@@n=m_iD@@`，使条件在胞腔上仅损失 `@@M@@o((D-1)\ell_i)@@` 比特。统计量 `@@M@@Z@@` 为两列表中通过 `@@M@@[U_j,V_j]_i=0@@` 的比例：条件独立性加高熵，用二进辛图 (binary symplectic graph) 的谱界 `@@M@@\sqrt{L+1}@@` 与轻重分解得 `@@M@@\E_\rho Z\le .62@@`；而切换点的影子化经符号距离识别迫使 `@@M@@z@@` 与合法点同相位、标签几乎全同，得 `@@M@@\E_\rho Z\ge .912@@`。矛盾。尺度论证吸收所有依赖模型的常数，故一个例子排除一切有限维数。

## 可信度与备注

本篇是结果族 152 的核心手稿，切换定理、词族构造与对撞论证在同一文内闭环、互相咬合。任务元数据标注 formalized=false，即主结果暂无 Lean 形式化证明；OpenAI 官方声明未经形式化的结果可能有问题。证明涉及大量数值常数（`@@M@@0.62@@` 与 `@@M@@0.912@@` 的对撞、`@@M@@10^{-4}@@` 容差等）与跨层次组合估计，个别步骤技术性较强，此处从略，整体宜以社区核验为准。

{% endraw %}
