---
layout: default
title: "Conformal universality of bulk Ising correlations under weak interactions"
family: "218"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Conformal universality of bulk Ising correlations under weak interactions

> 结果族 218：Conformal universality for weakly interacting and random-bond Ising models　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了：方格伊辛模型（Ising model）加上充分弱的平方对称、可正可负的有限程偶多自旋扰动后，存在一条临界温度分支，使体自旋与能量场的混合关联连续极限与最近邻模型只差两个域无关振幅，共形协变原样保留，实现了 BPZ 普适性预言。

## 问题背景

1944 年 Onsager 精确解出方格最近邻伊辛模型的自由能，1952 年 Yang 得到自发磁化；1984 年 Belavin–Polyakov–Zamolodchikov 的共形场论把临界自旋场与能量场按标度维数（scaling dimension）`@@M@@1/8@@` 与 `@@M@@1@@` 编排。普适性（universality）问题问：当微观相互作用破坏可积结构后，同样的连续关联是否仍然成立？对可积的最近邻模型，Chelkak–Smirnov 的离散复分析路线已给出严格证明（CHI 2015/2022 的混合初级场极限等）。超出可积，Giuliani–Greenblatt–Mastropietro（2012）与 Antinucci–Giuliani–Greenblatt（2023）用构造性重整化处理了能量关联，Cava–Giuliani–Greenblatt（2025）处理了半平面边界自旋（维数 `@@M@@1/2@@`），但体自旋（维数 `@@M@@1/8@@`）的混合极限一直空缺，Giuliani 2022 年国际数学家大会报告将其列为公开问题。卡点有二：体自旋插入对费米子方法是非局域缺陷；尺度变换会不断生成涉及任意多个自旋的局域函数，任何固定数量场插入的收敛定理都覆盖不了它们。

## 主要结果

定理（共形普适性）：设位势 `@@M@@V@@` 只作用于偶数大小、直径 `@@M@@\le R_V@@` 的集合，在平移、反射与旋转 `@@M@@\pi/2@@` 下不变，系数可正可负。则存在 `@@M@@\lambda_0>0@@` 及在零点连续的实函数 `@@M@@\beta_c@@`、`@@M@@Z_\sigma@@`、`@@M@@Z_\epsilon@@`，满足 `@@M@@\beta_c(0)=\beta_0=\frac{1}{2J}\log(1+\sqrt2)@@`、`@@M@@Z_\sigma(0)=Z_\epsilon(0)=1@@`，使得对每个 `@@M@@|\lambda|<\lambda_0@@`、每个有界单连通 `@@M@@C^2@@` 若尔当域（Jordan domain）`@@M@@D@@`、自由/加/减边界条件 `@@M@@b@@`、任意互异内点上的混合插入，有

`@@M@@D\lim_{a\downarrow0}\Big\langle\prod_{i=1}^n S_a(x_i)\prod_{k=1}^m E_{a,j_k}(y_k)\Big\rangle_{a,D}^{\lambda,b}=Z_\sigma(\lambda)^n\,Z_\epsilon(\lambda)^m\,\mathcal C_D^b(\boldsymbol x;\boldsymbol y),@@`

其中自旋场 `@@M@@S_a(x)=a^{-1/8}\sigma_{[x]_a}@@`，能量场 `@@M@@E_{a,j}(x)=a^{-1}\big(\sigma\sigma-\langle\sigma\sigma\rangle_{a,D}^{\lambda,b}\big)@@` 在真实相互作用态中中心化，`@@M@@\mathcal C_D^b@@` 是最近邻临界模型的对应极限。极限共形协变（conformal covariance）：共形映射 `@@M@@\phi@@` 带来因子 `@@M@@\prod_i|\phi'(x_i)|^{1/8}\prod_k|\phi'(y_k)|@@`。先取周期方盒热力学极限、再取 `@@M@@a\downarrow0@@`，得全平面版本，特别地两自旋关联是非零常数乘 `@@M@@|x-y|^{-1/4}@@`。同一组函数与耦合区间适用于所有几何。

## 证明思路

证明分五步。第一步，在临界最近邻参考测度 `@@M@@\E_0@@` 中建立一致的条件平均估计：把半径 `@@M@@s@@` 方块内的有界函数 `@@M@@F@@` 条件在半径 `@@M@@R\gg s@@` 的方块回路上，扣除参考均值后，剩余部分在奇宇称扇区只剩自旋分量、在偶宇称扇区只剩能量分量。这里调用姊妹篇《Buffered comparison and stopping-band resolution in critical Ising》的比较与停止估计，把 `@@M@@F@@` 对一切远处有界测试的作用替换为有限个带确定钉扎（pin）回路的参考律的带号组合，系数绝对值总和不超过 `@@M@@\|F\|_\infty@@`；再借助 Camia–Jiang–Newman 的簇项链与鬼附着论证及磁化矩估计，把硬钉扎换成细管内自旋的归一化软权重 `@@M@@e^X/\E_0 e^X@@`。第二步，反射正性（reflection positivity）把软权重放入径向希尔伯特空间：低谱恰含维数 `@@M@@1/8@@` 的自旋线与维数 `@@M@@1@@` 的能量线；在偶的旋转不变扇区，一个有限荷恒等式消去了维数 `@@M@@2@@` 的可能贡献，剩余为 `@@M@@(s/R)^3@@` 阶——这多出的一次幂是决定性的，因为在二维块上求和要消耗两次标度比，于是其余方向全部收缩。第三步，把条件平均变成相互作用的精确替换：按"出现列表"展开相互作用的指数，孤立出现被条件平均吸收，重叠出现被一并保留，得到恒等式 `@@M@@\E_0 e^H=e^c\,\E_0 e^{H'}@@`；连通对数与树图估计（硬核 Mayer、tree-graph 方法）给出具指数局域性的解析映射。第四步，重整化群（renormalization group）流：线性化后恰有一个扩张方向，即温度方向；把温度坐标沿轨迹倒向求解、收缩坐标正向求解，温度坐标便成为收缩坐标的解析函数，形成与温度线横截的衰减轨迹图；微观温度方向横截穿越此图，从而选出临界分支 `@@M@@\beta_c(\lambda)@@`。边界收缩与指数局域性把同一条分支带到各种几何与周期方盒。最后，把有限个标记源插入同一精确配分恒等式，在商代数 `@@M@@\mathbb C[t_1,\dots,t_q]/(t_\ell^2)@@` 中作有限源 jet；从对数生成函数中删去能量单点系数恰好实现真实态中心化；单源极限给出振幅 `@@M@@Z_\sigma@@` 与 `@@M@@Z_\epsilon@@`；在固定的物理半径处停止后，互不相交切割方块中的条件独立性恢复参考模型的全部混合关联，从而完成定理。

## 可信度与备注

本文结果未形式化，属长程构造性论证，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。族内三篇互为支撑：工具篇提供钉扎比较与停止带引理，`@@M@@\mathrm{SLE}_3@@` 界面篇在相近的尺度流框架下处理临界界面，两篇共用的"精确换相互作用 + 温度分支"机制相互印证。定理不涉及重合插入点、边界插入与界面问题，文中均已明示。

{% endraw %}
