---
layout: default
title: "Cutoff throughout the high-temperature Sherrington–Kirkpatrick phase"
family: "227"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Cutoff throughout the high-temperature Sherrington–Kirkpatrick phase

> 结果族 227：Critical SK autocorrelation processes and dynamics across the temperature transition　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
论文证明：零场高斯 SK 自旋玻璃的热浴动力学在整个高温区间 `@@M@@0\le\beta<1@@` 都存在最坏起点的总变差 cutoff（锐利切断），位置为 `@@M@@\log n/(2\lambda(\beta))@@`，速率 `@@M@@\lambda(\beta)>0@@` 由平衡态谱构造确定。这在零场高斯设定下回答了 SK 动力学高温相的 cutoff 问题。

## 问题背景
SK 模型（Sherrington–Kirkpatrick model）是自旋玻璃的平均场原型：`@@M@@n@@` 个 `@@M@@\pm1@@` 自旋，耦合 `@@M@@J_{ij}\sim N(0,\beta^2/n)@@` 正负号混杂，吉布斯测度 `@@M@@\mu_J(x)\propto\exp(\frac12x^{\mathsf T}Jx)@@`，高温相边界在 `@@M@@\beta=1@@`。热浴（heat-bath，即 Glauber）动力学让每个自阵以速率 1 按条件分布重新取样，最基本的定量问题是混合时间（mixing time）：链要走多久才贴近平衡？cutoff 现象指总变差距离在混合时刻附近从接近 1 骤降到接近 0，转移窗口相对混合时间可忽略。此前对 SK 动力学的高温结果——`@@M@@\beta<1/4@@` 的对数 Sobolev 不等式（Bauerschmidt–Bodineau）、`@@M@@O(n\log n)@@` 混合（Anari 等、Wang 等逐步推向 `@@M@@\beta<1/2@@`）、直到 `@@M@@\beta<1/2+\varepsilon_0@@` 的正谱隙——都只给出量级，不能定位 cutoff。困难在于：谱隙只控制平衡态附近的涨落，而 cutoff 定理必须管住任意初始组态在 `@@M@@\log n@@` 长的时间里的记忆。

## 主要结果
主定理：对每个固定 `@@M@@0\le\beta<1@@`，存在确定性速率 `@@M@@\lambda(\beta)>0@@`，令 `@@M@@t_n=\log n/(2\lambda(\beta))@@`，则最坏起点总变差距离 `@@M@@d_n((1-\epsilon)t_n)\to1@@`、`@@M@@d_n((1+\epsilon)t_n)\to0@@`，收敛为依无序（disorder）概率收敛；离散时钟（每次均匀挑一个自旋尝试更新）的 cutoff 位置恰为连续时间的 `@@M@@n@@` 倍。独立自旋情形 `@@M@@\lambda(0)=1@@`；一般地
`@@M@@D\lambda(\beta)=\min\{\lambda_{\rm sp},\ \inf{\rm spec}(\mathcal A_v)\}\le(1-\beta)^2,@@`
其中 `@@M@@\lambda_{\rm sp}@@` 是平衡自旋自相关函数极限 `@@M@@C(t)=\int e^{-ut}\,\rho(du)@@` 的谱测度 `@@M@@\rho@@` 的支集下沿，`@@M@@\mathcal A_v@@` 是"可见"精确梯度空间 `@@M@@\mathcal X_v@@`（以条件自旋方差 `@@M@@v_i=1-\tanh^2((Jx)_i)@@` 加权）上极限半群生成元的负部。论文不处理随 `@@M@@n@@` 趋于 1 的温度、外场以及 cutoff 窗口宽度。

## 证明思路
证明的骨架是"先把任意起点拉回可比较范围，再做一个可迭代的一致压缩块"。第一步处理任意初始组态：作者把姊妹篇谱隙定理里的稳定场残差论证加强到任意更换律之下，均值变化被平方根密度的 Dirichlet 能量 `@@M@@D@@` 控制；再经两阶段高斯观测传输得到热核估计 `@@M@@\frac1n\log\|S_d(x,\cdot)/\mu\|_\infty\le Ce^{-cd^{2/3}}@@`，即取一段足够长的固定"预热"，密度代价便可小到让指数可靠的平衡比较在换律后仍然存活。第二步是核心的隐／显分解。对自旋半差分 `@@M@@d_i f@@` 有向量半群关系 `@@M@@dS_tf=K_tdf@@`，其路径展开是矩阵 `@@M@@J@@` 与依赖观测自旋态的对角标签的乘积串。把每个标签与它由起点或终点给出的条件预测相比较，条件协方差消去论证表明：同时含"起点中心化标签"和"之后终点中心化标签"的串，被隐藏初始向量与精确终端梯度检验时为零；剩下的串可由两端预测，中间至多夹一个真实路径标签。配合投影行似然的亚指数矩与自旋谱测度在 `@@M@@\lambda_{\rm sp}@@` 以下速率处的可和权重，隐藏梯度部分得以衰减。第三步回收"可见"部分：把非平稳梯度投影到可见计算上得到随机标量系数，但投影不自动保持刻画梯度的恒等式；逆向熵估计与加权的旋度（curl）强控制把这些恒等式修复回来，使可见投影落入 `@@M@@\mathcal X_v@@`，并显示低于 `@@M@@\lambda_{\rm sp}@@` 的可见谱只由孤立有限重模式组成。最后，把隐、显两部分估计组装成一个固定长度的严格压缩块，一致化后迭代到 `@@M@@\log n@@` 时间尺度而不需固定时极限的定量速率；上界由晚时鞅能量估计收尾。下界分两种情形：若 `@@M@@\lambda=\lambda_{\rm sp}@@`，用自旋自相关作区分观测；若有更慢的可见模式，则用附加块估计对齐其随机系数的均值与涨落，对初始律做小扰动制造可检测的慢偏置，再用凸性选出至少同样远离平衡的确定性起始组态。附录对 `@@M@@\beta<1/2@@` 给出一条独立路线：逐点梯度耗散在一个指数小吉布斯质量的例外集之外以固定正速率成立，熵衰减先让例外集罕见，再在对数长度的正滞后上磨光得到 cutoff 比值，并附完整标量变分证书 `@@M@@0.9969@@`。

## 可信度与备注
本文主结果暂无形式化证明，请以社区核验为准。它以姊妹篇"零场高斯模型对一切 `@@M@@\beta<1@@` 有正的非缩放热浴谱隙"为输入，而同族的临界端论文（`@@M@@\beta=1@@` 处混合时间 `@@M@@n^{2/3+o(1)}@@`）已由 Lean 形式化，族内三篇分别覆盖 `@@M@@\beta<1@@`、`@@M@@\beta=1@@`、`@@M@@\beta>1@@`，恰在无序概率收敛意义下拼出整个温度轴的完整混合图像。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
