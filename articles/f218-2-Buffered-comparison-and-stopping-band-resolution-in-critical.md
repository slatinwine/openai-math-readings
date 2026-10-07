---
layout: default
title: "Buffered comparison and stopping-band resolution in critical Ising"
family: "218"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Buffered comparison and stopping-band resolution in critical Ising

> 结果族 218：Conformal universality for weakly interacting and random-bond Ising models　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

为临界方格伊辛模型证明两条基础工具定理：允许任意公共钉扎自旋的点态似然比较（由零场 FK 连接概率控制），以及界面探索穿越固定宽度条带时用有限个正则带号势垒逼近目标条件律——它们是同族两篇普适性论文的关键引擎。

## 问题背景

探索伊辛界面会沿一条随机路径逐步固定自旋，而后续估计必须在这种条件化之下仍然有效。困难有二：被固定的符号可以任意交替，暴露出的边界可能含有大量窄峡湾。经典工具——FKG/Holley 的正关联、Edwards–Sokal 的自旋-簇对应、Duminil-Copin–Hongler–Nolin 的 FK 交叉去相关——控制的是事件概率；本文需要的是对整个条件自旋律的点态比较，以及把探索后可见的不规则边界替换为有限多个正则带号势垒（regular signed barrier）的逼近定理，且要对包括随网格变化的有界可观测量一致。这两类估计正是族内体关联篇与 \(\mathrm{SLE}_3\) 界面篇反复调用的输入。

## 主要结果

定理一（有限图比较）：任意有限铁磁伊辛图、非负耦合与任意场；设 \(I,J\) 为不相交非空端集，\(F\) 为公共钉扎集。删去 \(F\)、把 \(I,J\) 各收缩成一个端点、场归零，取簇权 \(2\)、参数 \(p_e=1-e^{-2K_e}\) 的随机簇（random-cluster）模型，设两端点连接概率为 \(q_0\)。则对 \(J\) 上任意两组条件构型与 \(I\) 上任意构型 \(a\)，条件概率之比介于 \(e^{\pm4\operatorname{arctanh}q_0}\)。临界方格上进一步得到带缓冲（buffered）版本：\(I,J\) 被正宽度环域隔开时有一致常数界；\(I\subset z+B_w\)、\(J\) 在 \(z+B_R\) 之外且 \(R\ge8w\) 时，对数似然比至多 \(C(w/R)^\alpha\)（绝对常数 \(\alpha>0\)）。公共钉扎可在端集之外任意分布。

定理二（有限条件分解）：在宽度固定的条带 \(Q_v\setminus Q_u\) 中按面内三角剖分上自旋插值的零集做界面向内或向外探索。对任意 \(\epsilon,\eta>0\)，可在分离子窗口内选定轮廓水平、有限描述子 \(Z^\delta\in\{0,1,\dots,m\}\) 与有限个正则带号势垒 \(\Gamma_1,\dots,\Gamma_m\)，使得对所有充分细的网格：例外态概率至多 \(\epsilon\)；在好态 \(i\) 上，按"先加号钉扎、后减号钉扎"插入 \(\Gamma_i\)，目标律的总变差（total variation）改变之和至多 \(\eta\)，且最终目标侧律 \(Q_{i,\delta}\) 对该态中每个探索记录都相同——因此结论同时对一切有界目标观测量（包括随网格变化的）成立；若另一律的带密度至多是参考密度的 \(K\) 倍，其例外概率至多 \(K\epsilon\)。

## 证明思路

比较定理的证明是纯有限图代数：铁磁伊辛权重满足格条件（log-supermodular，即对数超模），且在边缘化下保持——文中给出二元消元证明，呼应 Karlin–Rinott 的多变量全正性理论；随后证明任意四个构型形成的对数几率矩形都被"两端集各自取全同号"的极端矩形控制，于是似然比问题约化为两自旋问题；把两端的有效场配平后引用 Ding–Song–Sun 的任意场协方差不等式，两自旋有效耦合恰为极端对数交叉项的四分之一，再经 \(\operatorname{arctanh}\) 与删除图上零场 FK 连接概率 \(q_0\) 挂钩；最后用 FK 交叉与单臂估计把 \(q_0\) 换成临界格点上的几何衰减。逼近定理的机制是：先在加倍自旋模型中构造有序耦合——抵达某补丁的分歧会在尺度 \(w\) 的计数线段上携带约 \(w^{7/8}\) 的磁质量，点态比较控制"修改该补丁"对距离 \(s\) 处目标的影响，对容许割求和即得有序传输（ordered transmission）及其带号源、总变差形式；作为 Chelkak–Hongler–Izyurov 自旋关联极限的定量推论，还得到邻近轮廓归一化磁化间的 \(L^2\) 界 \((w/s)^{3/8}\) 与预测界。再借助 Benoist–Hongler 的嵌套 \(\mathrm{CLE}_3\) 同时逼近，覆盖、定向与重数在任何不交叉完整分解下得以保持；在一般停止水平，目标可见的边界是带有限裂缝的若尔当基底，可用有限图嵌入与平面延拓定理作拓扑图纸，窄缎带保住裂缝两侧及尖端的变号；自旋关联极限控制固定正则比较域中的磁均值，有序传输再把小的均值差转化为目标总变差；最后把每个可实现探索记录邻域的可数覆盖，归约为有限个承载任意高概率的连续性集，得到有限分解定理。

## 可信度与备注

本篇处理的是可积的最近邻临界模型，主要输入（Ding–Song–Sun 协方差不等式、DHN 的 FK 估计、CHI 关联极限、Benoist–Hongler 的 \(\mathrm{CLE}_3\) 逼近）均为已发表结果；本文自身无 Lean 形式化证明，请以社区核验为准，OpenAI 亦声明"未经形式化的结果可能有问题"。作为族内体关联篇与 \(\mathrm{SLE}_3\) 界面篇共同引用的比较与传输引擎，它把两篇普适性论证中最关键的"条件化之后仍可用"的估计落到了实处。

{% endraw %}
