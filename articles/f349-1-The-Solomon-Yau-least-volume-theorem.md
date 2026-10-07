---
layout: default
title: "The Solomon–Yau least-volume theorem"
family: "349"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Solomon–Yau least-volume theorem

> 结果族 349：The Solomon–Yau least-volume conjecture　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了 Solomon–Yau 最小体积猜想：单位球面 `@@M@@S^{m+1}@@`（`@@M@@m\ge2@@`）中任何非全测地（non-totally-geodesic）的闭连通极小浸入超曲面，其体积（按定义域计数、含覆盖重数）不小于最小极小 Clifford 积的体积 `@@M@@a_m@@`——Clifford 积确是赤道之上的第一个体积能级。

## 问题背景

单位球面中体积最小的闭极小超曲面（minimal hypersurface）是全测地（totally geodesic）的赤道，那么赤道之上的下一个体积能级由谁占据？天然候选是极小 Clifford 积 `@@M@@\mathcal C_{k,m-k}=S^k(\sqrt{k/m})\times S^{m-k}(\sqrt{(m-k)/m})\subset S^{m+1}@@`：两因子的主曲率符号相反、绝对值成比例，加权平均恰好抵消，因而极小。这一"第二体积能级"问题列于丘成桐 1994 年问题集（Problem 31），现代表述即 Ge–Li 2021 年所称的 Solomon–Yau 猜想。二维情形 `@@M@@a_2=2\pi^2@@`（Clifford 环面）已由 Marques–Neves 2014 年的 Willmore 定理解决；高维却长期受阻：极小性本身不控制拓扑、曲率与奇异极限，普通紧性会产生带奇点的 varifold 极限，而 Cheng–Li–Yau 的热核比较与 Ge–Li 的最新嵌入界都未达到 Clifford 阈值。

## 主要结果

**定理（Theorem 1.1）**：设 `@@M@@m\ge2@@`，`@@M@@M^m@@` 为闭连通光滑流形，`@@M@@F:M\to S^{m+1}@@` 是到单位球面的光滑极小浸入。若 `@@M@@F(M)@@` 不全测地，则 `@@M@@\Vol(M,F^*g_{\rm round})\ge a_m:=\min_{1\le k<m}\Vol_m(\mathcal C_{k,m-k})@@`。体积在定义域上度量，有限覆盖的层数被计入。下界由取到最小值的 Clifford 积实现，故 `@@M@@a_m@@` 是赤道（体积 `@@M@@\sigma_m=|S^m|@@`）之上确切的下一能级。证明途中还独立得到两项副产品：其一是 Perdomo 平均曲率猜想的不等式部分 `@@M@@\int_\Sigma|A|^2\,dV\ge m\,\Vol_m(\Sigma)@@`，其中 `@@M@@A@@` 为形状算子（shape operator）；其二是指标刚性：此类超曲面的 Morse 指数（index）`@@M@@\ind\ge m+3@@`，且等号成立当且仅当像为 Clifford 积。于是体积小于 `@@M@@a_m@@` 的反例必有指标 `@@M@@>m+3@@`，多出一个使面积下降的方向——这正是后续极小极大（min–max）论证的引擎。

## 证明思路

全文按"归约—先验估计—变分族—紧性归纳"四步推进。

先归约到嵌入情形。把极小浸入锥化为欧氏空间中的平稳整 varifold，单调性公式给出：若某像点有 `@@M@@q@@` 个原像，则体积 `@@M@@\ge q\sigma_m@@`；又因比值 `@@M@@\vartheta_m=a_m/\sigma_m@@` 随 `@@M@@m@@` 严格递减，有 `@@M@@a_m<2\sigma_m@@`，故任何反例必是嵌入超曲面 `@@M@@\Sigma@@`。嵌入性继而给出两侧性、解析性与"满性"（位置向量张满 `@@M@@\mathbb R^{m+2}@@`）。

再建立两件先验事实。其一，对两点商 `@@M@@\mu(x)=\sup_{y\ne x}|\langle N(x),y\rangle|/(1-\langle x,y\rangle)@@` 的光滑上试验函数证明微分不等式 `@@M@@\Delta\log\phi\ge m-P@@`（`@@M@@P=|A|^2@@`），其中基于反射的计算须同时处理对角接触与重合主曲率；若 `@@M@@\int P<m\Vol@@`，用 Poisson 方程构造上试验函数即得矛盾，此即 Perdomo 不等式。其二，`@@M@@m+2@@` 个法向坐标函数是 Jacobi 算子 `@@M@@L=\Delta+m+P@@` 的独立特征函数，故 `@@M@@\ind\ge m+3@@`；等号情形经 Li–Yau 共形重心平衡与逐点谱等式逼出 `@@M@@P\equiv m@@`、`@@M@@\nabla A=0@@`，Gauss 方程随即把像分类为 Clifford 积。

然后构造洛伦兹距离族。取 `@@M@@\Sigma@@` 的欧氏锥的带号距离函数，视其图像为带一个时间坐标的空间中的图；用保持 `@@M@@|z|^2-h^2@@` 的 Lorentz boost 作用后与单位球面相交，得到水平集族。最近点接触处的面积雅可比为 `@@M@@|\det(rI-hA)|\le r^m@@`（由 `@@M@@\tr A=0@@` 与算术–几何均值不等式），最近点不唯一亦无妨。参数经紧化成为 `@@M@@\mathbb{RP}^{m+3}@@` 上的检测族（detecting family）：拉回的上同调类满足 `@@M@@(\Phi^*\lambda)^{m+3}\ne0@@`，中心参数对应 `@@M@@\Sigma@@` 本身且是唯一面积最大点。指标 `@@M@@>m+3@@` 提供的额外负方向把族在中心邻域内整体压低，得 `@@M@@\sup\mathbf M<|\Sigma|@@`，同时保持检测性与质量不集中。

最后是极小极大与锥归纳。检测性迫使族中出现体积为半球、质心为零的区域边界；球面等周不等式（半球因质心非零取不到等号）给出一致下阈 `@@M@@\gamma_m>\sigma_m@@`，Almgren–Pitts 理论（Marques–Neves 表述）随之产出质量落在 `@@M@@[\gamma_m,\sup\mathbf M]@@` 的平稳整 varifold。奇点靠对 `@@M@@m@@` 的归纳消除：密度低于 `@@M@@\vartheta_m@@` 的平稳整锥在锥维数 `@@M@@\le m@@` 时是重数一超平面，在锥维数 `@@M@@m+1@@` 时除顶点外光滑、其链是光滑连通极小超曲面——机制是切锥的"径向分裂"（radial splitting）：非零点的切锥分裂出一条直线，把分类归约到更低锥维数，而无须对链动用未知的 `@@M@@m@@` 维体积定理。于是反例类面积的下确界 `@@M@@H\in[\gamma_m,a_m)@@` 被光滑连通、重数一的 `@@M@@\Sigma_*@@` 实现；其族被压低后再经极小极大给出质量 `@@M@@\in[\gamma_m,H)@@` 的光滑极小超曲面——比 `@@M@@\Sigma_*@@` 更小的反例，矛盾。归纳从 `@@M@@m=2@@` 起步，无需低维体积假设。

## 可信度与备注

本文是结果族 349 的核心论文，本批族内仅此一篇：它把 Perdomo 平均曲率不等式、指标刚性、洛伦兹检测族的极小极大理论与低密度锥正则性四条线索整合为自洽证明，其中前两条也与 Nifa 2026 年预印本的结果相互独立印证。按任务信息，主结果暂无 Lean 形式化证明；依 OpenAI 官方声明，未经形式化的结果可能有问题，本文结论请以社区核验为准。

{% endraw %}
