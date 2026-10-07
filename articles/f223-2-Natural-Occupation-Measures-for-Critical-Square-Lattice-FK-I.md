---
layout: default
title: "Natural Occupation Measures for Critical Square-Lattice FK Interfaces"
family: "223"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Natural Occupation Measures for Critical Square-Lattice FK Interfaces

> 结果族 223：Random-cluster interfaces: critical, disordered, thermal, and natural-time scaling　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
本文证明：单位方格上临界 FK 随机簇 Dobrushin 界面的步数计数测度经 `@@M@@c(q)n^{-d}@@` 归一后收敛到其 `@@M@@\mathrm{SLE}_\kappa@@` 极限曲线的 Minkowski 内容测度（`@@M@@1\le q<4@@`），单一确定性常数给出归一化，且收敛与曲线联合、含总质量——即界面总步数有了标度极限。

## 问题背景
界面标度极限只描述形状，不回答"走完这条形状要多少格点步"。后者需要极限曲线上的一个测度。对 Schramm–Loewner 演化（SLE），恰当的对象是其维数 `@@M@@d=1+\kappa/8@@` 的 Minkowski 内容测度（Minkowski content）：`@@M@@r@@` 邻域面积乘 `@@M@@r^{-(2-d)}@@` 的极限。Beffara 的维数定理只预测指数；Lawler–Sheffield 的自然参数化（natural parametrization）及 Lawler–Rezaei 的内容测度定理提供了连续侧理论。格点侧先例稀少：三角格点渗流（GPS 构造、HLS 收敛、DGLZ 精细臂渐近）与擦除随机游走到 `@@M@@\mathrm{SLE}_2@@`（Lawler–Viklund）。方形格点 FK 界面的占据结果此前完全缺失，卡点在于：臂指数（arm exponent）级别的信息无法排除缓变或振荡的非收敛因子，必须精确到常数。

## 主要结果
取簇权 `@@M@@q\in[1,4)@@`，参数 `@@M@@p_q=\sqrt q/(1+\sqrt q)@@`、`@@M@@\kappa=4\pi/\arccos(-\sqrt q/2)\in(4,6]@@`、`@@M@@d=1+\kappa/8@@`、`@@M@@x=2-d\in[1/4,1/2)@@`。在单位方格 `@@M@@D=(0,1)^2@@` 上布置 Dobrushin 边界条件：左、上边界接线（wired）成一个块，下、右边界边保持随机。`@@M@@\eta_n@@` 为中点图（medial graph）上从 `@@M@@a=(0,0)@@` 到 `@@M@@b=(1,1)@@` 的有序界面，`@@M@@N_n@@` 为其全程中点边通过次数，计数测度 `@@M@@\nu_{n,c}=c\,n^{-d}\sum_j\delta_{\Pi(z_{n,j})}@@`（按通过次数计，而非欧氏长度）。主定理：存在确定性常数 `@@M@@c(q)\in(0,\infty)@@`，使 `@@M@@([\eta_n],\nu_{n,c(q)})@@` 沿全部 `@@M@@n@@` 联合收敛到 `@@M@@([\eta],\mu_\eta)@@`——有序曲线拓扑加 `@@M@@\overline D@@` 上有限测度弱拓扑，其中 `@@M@@\eta@@` 为 `@@M@@(D;a,b)@@` 上的弦 `@@M@@\mathrm{SLE}_\kappa@@`，`@@M@@\mu_\eta@@` 为其 `@@M@@d@@` 维 Minkowski 内容测度（边界赋零质量）；特别地 `@@M@@c(q)n^{-d}N_n\Rightarrow\mu_\eta(\overline D)@@`，给出总步数的标度极限。

## 证明思路
证明分四大步，核心是"从指数精确到常数"。先做全局准备：给环绕指定格点的回路定向并插入依赖绕数（winding）的相位，得到小电荷下取正的标量回路权；围绕开回路的再生（regeneration）给出对外部环境依赖的定量损失与配分函数的无零点复邻域。再解电荷高度势：小电荷的高度势近似调和，误差为可和幂；用两个方向的行切分——未扭曲电流控制插入线以外的势，扭曲行控制其附近的差——经二步格点势论得到带幂余项的库仑（Coulomb）相关公式，复延拓推广到施加臂事件的电荷，反射对称消除局部归一化的线性歧义。第三步到达单条格点边：条件化两条异色臂到达大半径，构造耦合使外部构型以幂精度相同；成功时分离带中恰有两条中点贯穿线，外部延拓与微观起始构型无关——这比"两臂分离"更强，正是可用来计数指定界面的性质。第四步校准（calibration）：把中观间隔的两个电荷与相邻格点上的电荷比较，非零中观振幅控制相对误差，`@@M@@n@@` 与 `@@M@@N\in[n,2n]@@` 尺度间的可和比较产生真正的微观振幅；再用圆盘探针得到"格点访问换邻域面积"的确定性常数。最后组装：在 `@@M@@L^2@@` 中把微观段的计数指示换成半径 `@@M@@\epsilon@@` 的圆盘进入指示（二阶矩替换命题）；固定 `@@M@@\epsilon@@` 时由姊妹篇的有序迹收敛识别圆盘泛函的极限；令 `@@M@@\epsilon\downarrow0@@`，用 Lawler–Rezaei 的 SLE 内容测度定理识别小半径极限；边界条带估计（格点侧 `@@M@@\E X_n(U_\delta)\le Cn^{x-1}+C\delta^{1-x}@@`，连续侧 `@@M@@\E\mu_\eta(U_\delta)\le C\delta^{1-x}@@`）把收敛推进到闭方格并涵盖总质量。

## 可信度与备注
主结果暂无形式化证明，请以社区核验为准（OpenAI 声明未经形式化的结果可能有问题）。本文把曲线收敛本身作为输入，取自同族姊妹篇"Conformal Limits of Critical Square-Lattice Random-Cluster Interfaces"，并依赖 Duminil-Copin–Manolescu–Tassion 的穿越与臂分离输入及六顶点模型高度协方差定电学归一化；作者还特别核查了所引用谱结果在 FK 参数区间的适用性。三篇互相咬合：姊妹篇给形状极限，本文给自然时间（占据）极限，热质量篇给非临界形变，合成族 223 的完整图景。

{% endraw %}
