---
layout: default
title: "Critical slowing down in the Sherrington–Kirkpatrick model"
family: "227"
discipline: "Probability and statistical mechanics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Critical slowing down in the Sherrington–Kirkpatrick model

> 结果族 227：Critical SK autocorrelation processes and dynamics across the temperature transition　·　学科：Probability and statistical mechanics　·　验证状态：主结果已 Lean 形式化

## 一句话结论
论文在 SK 模型临界点 `@@M@@\beta=1@@` 证明了临界慢化（critical slowing down）的严格总变差下界：把典型的平衡组态固定为初始状态，热浴动力学在 `@@M@@o(n^{2/3})@@` 时间内（离散更新尝试 `@@M@@o(n^{5/3})@@` 步内）几乎必然仍未混合。配合独立比较得到的次指数上界，临界混合时间被夹在 `@@M@@n^{2/3-\epsilon}@@` 与 `@@M@@e^{\epsilon n}@@` 之间。

## 问题背景
SK 模型在 `@@M@@\beta=1@@` 发生自旋玻璃转变：Du 与 Huang 证明两独立副本的重叠（overlap）`@@M@@n^{-1}x^Ty@@` 在临界处的尺度是 `@@M@@n^{-1/3}@@`，而非高温侧的高斯尺度 `@@M@@n^{-1/2}@@`。物理上"临界慢化"指弛豫在转变点附近急剧变慢：Kirkpatrick–Sherrington 1978 年的线性化平均场、Sompolinsky–Zippelius 的响应方程、Billoire–Campbell 的数值（恰好在每自旋 `@@M@@n^{2/3}@@` 更新的尺度上观察自相关）都支持这一图像。但这些都是关联函数层面的结果；此前没有任何定理说明从总变差（total variation）角度看混合真的慢——尤其没有结果针对"已实现取值被固定的平衡组态"这类最自然的初始状态（对其平均反而恒等于平稳律，必须逐点检验）。临界处谱隙塌缩，高温端的谱隙工具全部失效，这是长期的技术卡点。

## 主要结果
三款定理。第一（实现平衡起点）：对任何确定性序列 `@@M@@t_n=o(n^{2/3})@@`，在依无序（disorder）概率收敛意义下，`@@M@@\mu_W\{x:d_{t_n}^{\rm ct}(W,x)>1/4\}\to1@@`；离散时钟下任何 `@@M@@k_n=o(n^{5/3})@@` 同理。即绝大多数平衡组态作为固定起点时都是慢的。第二（协方差与线性检验尺度）：协方差矩阵范数 `@@M@@\|\Sigma\|@@` 与线性函数的最大逆 Rayleigh 商 `@@M@@\mathcal R_{\rm lin}(\mu_W)@@` 都落在 `@@M@@n^{2/3\pm o(1)}@@`，其中 Dirichlet 形式 `@@M@@\mathcal D_{\mu_W}(f)=\sum_i\mu_W[\Var(f\mid x_{-i})]@@` 是速率一时钟对应的能量。第三（混合时间夹逼）：以高概率 `@@M@@n^{2/3-\epsilon}\le t_{\rm mix}\le e^{\epsilon n}@@`，离散为 `@@M@@n^{5/3-\epsilon}\le k_{\rm mix}\le e^{\epsilon n}@@`。配套姊妹篇进一步把指数配平到 `@@M@@n^{2/3+o(1)}@@`。

## 证明思路
证明的关键一招是"对角增广"：给耦合矩阵加上独立高斯对角元，其对能量在超立方体 `@@M@@\{-1,1\}^n@@` 上是常数，故吉布斯律与两条马氏链完全不变，而矩阵变成 GOE。设 `@@M@@v@@` 为其单位顶部特征向量。静态主输入是投影稀有性：对任何 `@@M@@b_n\to0@@`，`@@M@@\mu_W\{|v^Tx|\le b_n n^{1/3}\}\to0@@`——平衡组态在顶部特征方向上的投影几乎不小于 `@@M@@n^{1/3}@@`。而该线性泛函的 Dirichlet 能量不超过 `@@M@@1@@`；可逆性给出沿平稳轨迹投影的均方变化在连续时间不超过 `@@M@@2t@@`、`@@M@@k@@` 次尝试后不超过 `@@M@@2k/n@@`。于是在 `@@M@@o(n^{2/3})@@`（或 `@@M@@o(n^{5/3})@@` 次尝试）时刻，轨迹两端的投影以高概率同号非零；对每个固定起点，这个符号张出一个平衡质量至多一半的半空间，直接给出总变差大于 `@@M@@1/4@@` 的检验。投影稀有性的建立分三阶段：先在 GOE 边缘上方 `@@M@@s_0=L_nn^{-2/3}@@` 处（`@@M@@L_n@@` 可任意慢发散）控制头部特征值与两条预解式迹；再把倾斜球面模型（球面上按 `@@M@@\exp(u^T\Lambda u/2)@@` 加权的均匀律）表示为独立高斯坐标 conditioning 于平方和，边缘估计使头号坐标标准差至少 `@@M@@cn^{1/3}/\sqrt{L_n}@@`，径向密度上下界控制 conditioning 效应；最后用 Comets 的 Haar 平均恒等式（伊辛配分和的一阶矩等于球面积分）加上配分和集中，把小投影与平方重叠估计从球面搬到立方体，二阶矩中"三次方亏损"压制大重叠，外向单调格子比较则免除对二重积分的求导。协方差两侧由此分别得出：顶部投影给下界，平方重叠控制 `@@M@@\Tr\Sigma^2@@` 给上界；线性 Rayleigh 商还差一步——用自旋删除（cavity）论证说明倒数权重大的格点只贡献较小的协方差块。上界则来自与某个固定 `@@M@@\beta<1@@` 高温模型的独立比较（调用姊妹篇的 Poincaré 定理）。附录给出澄清更新规则、时钟与无序量词角色的初等例子。

## 可信度与备注
本文主结果已由 Lean 形式化证明，是本族中验证最强的一篇。族内互相支撑：高温端 cutoff 论文与本文共享"速率一每自旋"时钟约定，本文上界调用 `@@M@@\beta<1@@` 谱隙姊妹篇，而下界与静态输入又被配套的"Critical mixing"一文用于配平 `@@M@@n^{2/3+o(1)}@@` 指数。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文虽已形式化，其余姊妹篇仍建议以社区核验为准。

{% endraw %}
