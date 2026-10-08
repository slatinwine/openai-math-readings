---
layout: default
title: "Conformal Limits of Critical Square-Lattice Random-Cluster Interfaces"
family: "223"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Conformal Limits of Critical Square-Lattice Random-Cluster Interfaces

> 结果族 223：Random-cluster interfaces: critical, disordered, thermal, and natural-time scaling　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

把一张用乐高积木拼出的海岸线照片不断放大：积木越换越小，轮廓越来越像一条连续曲线。这篇论文证明，方形格点上一整族随机折线——"随机簇模型"的相变边界——在格点无限加细后，确实收敛到一种标准随机曲线 SLE，连刻画它"性格"的参数都能精确写出。

**关键词卡片**

- 随机簇模型（random-cluster model）：在格点每条小边上独立决定"开/关"，参数 q 控制扎堆倾向；渗流（q=1）和伊辛模型（q=2）都是它的成员。
- Dobrushin 界面（Dobrushin interface）：把边界一段设为"接线"、一段设为"自由"后，开簇与闭簇之间那条随机分界折线。
- SLE（stochastic Loewner evolution）：由布朗运动驱动的随机曲线，二维临界模型的通用极限形状。
- CLE（conformal loop ensemble）：SLE 的全套家族版——一整族互相嵌套的随机回路。
- Cardy 公式（Cardy's formula）：临界渗流中区域被黑色"横穿"概率的显式公式。

**看个具体例子**

主定理给出参数公式 `@@M@@\kappa(q)=4\pi/\arccos(-\sqrt q/2)@@`，代进具体数字：`@@M@@q=1@@`（渗流，临界概率 `@@M@@p_1=1/2@@`）时 `@@M@@\arccos(-1/2)=2\pi/3@@`，得 `@@M@@\kappa=6@@`；`@@M@@q=4@@` 时 `@@M@@\arccos(-1)=\pi@@`，得 `@@M@@\kappa=4@@`。也就是说：普通方格键渗流的界面极限是 SLE`@@M@@_6@@`，`@@M@@q=4@@` 端点是 SLE`@@M@@_4@@`。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><rect x="90" y="40" width="370" height="200" fill="none" stroke="#bbb" stroke-width="2"/><polyline points="130,240 90,240 90,40 420,40" fill="none" stroke="#333" stroke-width="7"/><polyline points="420,40 460,40 460,240 130,240" fill="none" stroke="#333" stroke-width="2" stroke-dasharray="6 5"/><polyline points="130,240 165,215 150,178 208,188 238,148 218,108 288,118 318,78 378,88 420,40" fill="none" stroke="#c0392b" stroke-width="3"/><circle cx="130" cy="240" r="5" fill="#111"/><circle cx="420" cy="40" r="5" fill="#111"/><text x="112" y="262" font-size="16">a</text><text x="428" y="30" font-size="16">b</text><text x="16" y="150" font-size="14">接线弧</text><text x="200" y="264" font-size="14">自由弧(虚线)</text><text x="442" y="150" font-size="14">界面 η</text><text x="330" y="264" font-size="14">格距 δ→0：折线→SLE</text></svg>

</div>

图中粗实线是"接线"边界、虚线是"自由"边界，红色折线就是 Dobrushin 界面：格距趋于零后它不再逐格拐折，而是收敛为一条光滑却依旧随机的 SLE 曲线。

**为什么值得关心**

它补上了共形不变性纲领在普通方格上整个 `@@M@@1\le q\le4@@` 区间的缺口，还第一次证明了方格键渗流的 Cardy 公式。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
本文证明：对方形格点上簇权 `@@M@@1\le q\le4@@` 的临界随机簇模型，Dobrushin 界面收敛到弦 `@@M@@\mathrm{SLE}_{\kappa(q)}@@`（`@@M@@\kappa(q)=4\pi/\arccos(-\sqrt q/2)@@`），完整的嵌套平面回路族收敛到全平面 `@@M@@\mathrm{CLE}_{\kappa(q)}@@`，并在 `@@M@@q=1@@` 得到方形格点键渗流（含自由边界边）的 Cardy 公式——补上了共形不变性预言在普通方形格点上整个 `@@M@@q@@` 区间的缺口。

## 问题背景
平面临界模型的共形不变标度极限是统计力学核心纲领。Schramm 用共形不变性刻画导出 SLE；Cardy 的渗流穿越公式由 Smirnov 在三角格点座渗流证明；FK–Ising（`@@M@@q=2@@`）界面收敛由 Chelkak–Duminil-Copin–Hongler–Kemppainen–Smirnov 用离散全纯观测量建立；完整回路族的极限律 CLE 由 Sheffield–Werner 构造。但方形格点、原始随机簇概率律、整个区间 `@@M@@1\le q\le4@@` 的界面与回路收敛此前没有证明——除 `@@M@@q=2@@` 外既无适用的离散全纯结构，也无 Cardy 公式的方形格点键渗流版本。难点有三：单条界面的极限不自动给出与其他界面的耦合；紧集上的迹收敛不保留回路重数、嵌套与完整遍历次序；探索后的随机区域上四点公式是否仍可用。

## 主要结果
主定理：固定 `@@M@@1\le q\le4@@`，`@@M@@p_q=\sqrt q/(1+\sqrt q)@@`。在标记 Jordan 域 `@@M@@(D;a,b)@@` 上，`@@M@@W@@` 弧接线（wired）、`@@M@@F@@` 弧自由，中点图（medial graph）Dobrushin 线 `@@M@@\eta_n@@` 在一致标记边界逼近下收敛到 `@@M@@(D;a,b)@@` 中的弦 `@@M@@\mathrm{SLE}_{\kappa(q)}@@`，收敛保持有序遍历（保序曲线拓扑）；自由无边无穷体积律的完整嵌套回路族 `@@M@@\Gamma_\delta@@` 收敛到嵌套全平面 `@@M@@\mathrm{CLE}_{\kappa(q)}@@`（球面 `@@M@@\epsilon@@`-匹配拓扑，保留重数与遍历），极限 Möbius 不变。两结论沿任何网格序列成立，`@@M@@q=4@@` 时为 `@@M@@\mathrm{SLE}_4@@` 与标准简单嵌套 `@@M@@\mathrm{CLE}_4@@`。附带定理：方形格点键渗流（所有边含边界边独立以 `@@M@@1/2@@` 开启、不接线）的穿越概率收敛到 Cardy 公式 `@@M@@\int_0^x[t(1-t)]^{-2/3}\dd t\big/\int_0^1[t(1-t)]^{-2/3}\dd t@@`。

## 证明思路
对 `@@M@@1\le q<4@@`，证明从"四换边"计算出发：上半平面边界换点 `@@M@@0,\chi,1,\infty@@` 处，开帽归一化下的连接概率为 `@@M@@f(\chi)=I_C/(I_B+I_C)@@`（`@@M@@I_B,I_C@@` 为带指数 `@@M@@\rho-1@@`、`@@M@@1-3\rho@@` 的显式积分，`@@M@@\sqrt q=2\cos\lambda@@`、`@@M@@\rho=\lambda/\pi@@`）；两条指定区间分别接线后变为 `@@M@@g=f/(f+d(1-f))@@`，`@@M@@d=\sqrt q@@`——`@@M@@d\ne1@@` 时两种归一化必须严格区分。先做正向比较：瓦片律与随机簇律精确等同、领圈与通道数比较、指数不等式，随后一切复电流估计都落在这些正律中。再经角向转移算子与反射范数、标量谱分解压制妨碍全纯性的角向模式，用远探针比较与折叠混合格式估计解除全纯性假设，得到四换边公式而不假设任何格点共形不变性定理。接着把固定形状公式搬到随机探索后的区域：有限图逼近加上原开关律下的平均六臂估计（`@@M@@\P(A_6(r,R))\le C(r/R)^{2+c_0}@@`），配合"定向障碍物"构造与长度—面积论证完成搬移。然后识别驱动：在自由侧插入小区间，条件配对概率是精确有界鞅，四换边试验识别其值为 `@@M@@f(\chi_t)@@`，导出鞅测试 `@@M@@M_t(x)=(xg_t'(x)/(g_t(x)-W_t))^h@@`；双测试凸性论证给出二次变差界，Itô 公式加 Lévy 刻定识别 `@@M@@W_t=\sqrt\kappa B_t@@`。曲线层面用领土臂计数、六臂估计排除三点三次访问、"小闸门"论证排除被吞没区域内的多余游走，从而识别完整有序迹。回路部分用均匀壁剥离构造目标树、匹配分支 SLE 描述与离散回路，绕数定标签、逃逸界升级到球面匹配拓扑。`@@M@@q=4@@` 端点单独处理：借助 FK 同伦耦合的旋转双射与全平面六顶点场定理控制双接触，最终以双值局部集（two-valued local sets）唯一性识别 `@@M@@\mathrm{CLE}_4@@`；严格角向与六臂估计未通过极限论证延拓到 `@@M@@q=4@@`。

## 可信度与备注
主结果暂无形式化证明，请以社区核验为准；OpenAI 官方声明未经形式化的结果可能有问题。本文是结果族的基石：它为占据测度姊妹篇提供有序迹收敛输入（其 Input trace 即本文 Theorem chordal:trace），也与热质量篇共享穿越估计框架。作者强调只用公开结果于其陈述假设内，不借助随机平面地图或随机嵌入的度规极限；所有定理均对固定 `@@M@@q@@` 成立，不宣称 `@@M@@q\uparrow4@@` 的一致性。

{% endraw %}
