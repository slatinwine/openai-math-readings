---
layout: default
title: "Uniform real Lipschitz surfaces on the triangular lattice"
family: "232"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Uniform real Lipschitz surfaces on the triangular lattice

> 结果族 232：Gaussian fields and interfaces for triangular-lattice Lipschitz heights　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

把随机地形的高度从整数"台阶"放宽成任意实数"斜坡"：每个格点的高度是实数，唯一约束仍是相邻差不超过 1，再按约束区域内的体积均匀随机取。结论双响：这片随机曲面收敛到高斯自由场的倍数，而曲面上的"零海拔等高线"收敛到著名的随机曲线 SLE`@@M@@_4@@`——Schramm 问题 2.3 就此解决。

**关键词卡片**

- 实值 Lipschitz 曲面（real Lipschitz surface）：高度为实数、只约束 `@@M@@|h(x)-h(y)|\le 1@@`、按体积均匀分布的随机曲面。
- 零高度界面（zero-height interface）：高度在三角形上仿射延拓后，高度为 0 的线段连成的一条连接两标记点的弦曲线。
- SLE`@@M@@_4@@`（chordal SLE`@@M@@_4@@`）：`@@M@@\kappa=4@@` 的 SLE 曲线；高斯自由场等高线的普适极限。
- 调和测度（harmonic measure）：从区域内一点出发的布朗运动首次击中边界某段弧的概率。
- 切向通量系数（tangent-flux coefficient）A：由元胞问题构造性定义的有效刚度参数，决定涨落大小，暂无闭式。

**看个具体例子**

数字版定理：三角格顶点密度 `@@M@@v=\dfrac{2}{\sqrt{3}}\approx 1.155@@`；场方差 `@@M@@\sigma^2=\dfrac{1}{vA}@@`，而让界面恰好变成 SLE`@@M@@_4@@` 的"调准"边界幅值 `@@M@@\lambda@@` 满足 `@@M@@\lambda^2=\dfrac{\pi}{8vA}@@`。两式联立消去 `@@M@@vA@@`，得到干净的关系 `@@M@@\lambda=\sigma\sqrt{\dfrac{\pi}{8}}\approx 0.6267\,\sigma@@`。读法：恰好当两弧边界抬升为涨落 `@@M@@\sigma@@` 的 0.6267 倍时，零等高线收敛到 SLE`@@M@@_4@@`；抬得更高或更低，极限界面就不再是它。

**为什么值得关心**

首次对"硬约束"实值随机曲面同时给出场极限与界面极限，补齐 Schramm 问题 2.3；系数 A 的数值刻画则成为天然的后续课题。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
证明了三角格点上均匀实值 Lipschitz 曲面的高度场收敛到 Dirichlet 高斯自由场的倍数，且在一个调准的两弧边界幅值处零高等界收敛到 chordal SLE`@@M@@_4@@`，解决 Schramm 问题 2.3；场方差与边界高度经一个隐式切向通量系数相联系。

## 问题背景
Schramm 问题 2.3 考虑实值最近邻 Lipschitz 约束下的随机曲面：自由顶点高度服从约束多面体上的规范化 Lebesgue 测度，问高度场与零界面的标度极限。Schramm–Sheffield 曾对离散 GFF 建立等值线与 SLE`@@M@@_4@@` 的对应，Miller 把围线普适性推广到光滑、对称、一致凸的梯度势；但本模型的"硬势"在 `@@M@@[-1,1]@@` 上取常数、在外为无穷，不满足凸性假设，因此用光滑势逼近本身并不构成解。另一方面，梯度场同质化传统（Naddaf–Spencer、Giacomin–Olla–Spohn）与硬核离域化结果（Miłoś–Peled、Cohen-Alloro–Peled 的受控梯度估计）都只给出无穷体积或去局域化信息，不产出有界域的场极限或围线极限，问题长期悬置。

## 主要结果
模型：区域 `@@M@@D@@` 光滑单连通，标记边界点 `@@M@@a,b@@` 分出开弧 `@@M@@A_\pm@@`，边界高度在两弧上分别为 `@@M@@\pm\lambda@@`（`@@M@@0<\lambda\le1/2@@`），自由顶点高度满足 `@@M@@|h(x)-h(y)|\le1@@`；高度在三角形上仿射延拓，几乎必然每个三角形至多含一条零高度线段，这些线段组成回路与一条连接标记点的弦界面 `@@M@@\gamma_\delta@@`。主定理：存在与 `@@M@@D,a,b@@` 无关的常数 `@@M@@A>0@@`、`@@M@@\sigma>0@@` 与调准幅值 `@@M@@\lambda\in(0,1/2]@@`，使得 `@@M@@\gamma_\delta\Rightarrow\mathrm{SLE}_4(D;a,b)@@`（在一致曲线距离下）且 `@@M@@\frac{h_\delta-\E h_\delta}{\sigma}\Rightarrow\mathrm{GFF}_D@@`（在随机分布意义下）。具体地，`@@M@@v=2/\sqrt3@@` 为格点顶点密度，`@@M@@\sigma^2=(vA)^{-1}@@`，调准幅值满足 `@@M@@\lambda^2=\pi/(8vA)@@`，极限均值为 `@@M@@m_D(z)=\lambda[\omega_D(z,A_+)-\omega_D(z,A_-)]@@`，其中 `@@M@@\omega_D@@` 是调和测度（harmonic measure）。`@@M@@A@@` 是元胞构造中定义的切向通量系数（tangent-flux coefficient），有效刚度 `@@M@@vA@@` 无初等闭式；界面结论恰在一个调准幅值处成立，该幅值等于高度间隙 `@@M@@\sigma\sqrt{\pi/8}@@`。高度场极限不需要对数重标度。

## 证明思路
证明分四部分。先打体积基础：利用 Prékopa 对数凹性得到局部体积曲率，配合稀疏缺陷估计与三角暴露、平均锚定等有限体积论证，推出宏观平均的无标度矩；Cohen-Alloro–Peled 的受控梯度估计提供零钉扎起点，并被推广到有界数据与符号观测——这步不可省，因为界面探索会不断改变所条件的高度多面体。第二步构造同步反射耦合（synchronous reflected coupling）：给自由坐标驱动相同的 Brown 噪声，公共噪声相消，只剩强制相对漂移与凸多面体边界接触的平均作用；借助 Słomiński 的固定域 Skorokhod 逼近、Bass–Hsu 的反射 Brown 运动半鞅结构与 Lyons–Zheng 前向—反向鞅分解，把接触事件按发生次序保留到平稳体极限，再用相对高度的平均输运识别宏观方程。第三步解平稳元胞问题（cell problem）：体采样下的梯度过程连同其驱动 Brown 增量有唯一的局部极限，它平稳且空间遍历；切向更新识别出一个标量通量律，其正系数即 `@@M@@A@@`，而对小平滑指数倾斜（tilt）的线性响应给出高斯场极限与 `@@M@@\sigma^2=(vA)^{-1}@@`；随后在变化的观测集合上建立解析迹估计，得到条件 Dirichlet 协方差。第四步做界面：可行移动（feasible shift）以受控的体积代价把交叉估计转化为障碍；障碍与条件场估计联合给出采样界面的分离性、高度间隙与在停止时刻一致的调和观测量；在对偶符号链滤流下 `@@M@@M_T(f)=\E[X(f)\mid\mathcal F_T]@@` 是精确鞅，格点游走的调和测度落点可与相应区域的 Brownian 出口耦合，前向与反向驱动函数收敛经 Sheffield–Sun 强路径判据升格为一致曲线收敛，即 `@@M@@\mathrm{SLE}_4@@`；装配论证最后把每个提取的高度间隙识别为 `@@M@@\sigma\sqrt{\pi/8}@@`，反推出调准的 `@@M@@\lambda@@` 并去除子列依赖。

## 可信度与备注
本结果暂无形式化证明；按 OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。族内三篇共同支撑 Schramm 的实场/界面纲领：两篇整数模型姊妹篇分别解决两弧边界与加权零边界的 GFF 极限，本篇补上实值模型的场与界面，但其技术路线（凸几何加反射 Brown 运动，而非谱方法）相对独立。切向通量系数 `@@M@@A@@` 只以构造方式定义，其数值刻画与闭式是自然的后续课题。

{% endraw %}
