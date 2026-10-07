---
layout: default
title: "Essential Singularity of the Correlation Length in the Planar XY Model"
family: "216"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Essential Singularity of the Correlation Length in the Planar XY Model

> 结果族 216：Critical and near-critical XY scaling and BKT universality　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文严格证明了方格最近邻 XY 模型的 BKT 本质奇性（essential singularity）：从低温侧逼近临界点时 \(\sqrt{b_c-b}\,\log\xi(b)\to A_{\mathrm{XY}}\in(0,\infty)\)，即相关长度（correlation length）按 \(\exp(A_{\mathrm{XY}}/\sqrt{b_c-b})\) 型速度发散，首次对原始余弦相互作用证实了 Kosterlitz 1974 年的重整化预言。

## 问题背景

平面 XY 模型在每个格点放一个单位向量（角度 \(\theta_x\in\R/(2\pi\Z)\)），相邻自旋以 \(\exp\{b\cos(\theta_u-\theta_v)\}\) 耦合。Berezinskii（1970）与 Kosterlitz–Thouless（1973）提出：低温下涡旋（vortex）成对束缚、自旋波（spin wave）主导，相关呈幂律衰减；升温后涡旋解绑，相关变为指数衰减。Kosterlitz（1974）的重整化群（renormalization group）递推进一步预言：转变点处相关长度的发散不是普通幂律，而是 \(\exp(\mathrm{const}/\sqrt{b_c-b})\) 型本质奇性。严格数学方面，Fröhlich–Spencer（1981）证明了相变与低温慢衰减，van Engelenburg–Lis 给出了指数–多项式二分法，但"精确奇性"对原始余弦模型始终悬而未决。难点在于：临界点附近温度偏移 \(\varepsilon=b_c-b\) 与涨落尺度同时发散，必须在一个尺度不断增长的区间里全程控制重整化流，再把流给出的尺度翻译回无穷体积的相关长度。

## 主要结果

定义两点相关函数 \(C_b(r)\)：先取自由边界方盒的热力学极限（thermodynamic limit），再让沿坐标轴的间距 \(r\to\infty\)；质量 \(m(b)=\lim_{r\to\infty}-\frac1r\log C_b(r)\)，轴相关长度 \(\xi(b)=m(b)^{-1}\)，临界逆温度 \(b_c=\inf\{b>0:m(b)=0\}\)。主定理：存在有限正常数 \(A_{\mathrm{XY}}\)，使得 \(b\uparrow b_c\) 时 \(\sqrt{b_c-b}\,\log\xi(b)\to A_{\mathrm{XY}}\)。常数依赖模型归一化，文中未给出闭式；论文还给出表达式 \(A_{\mathrm{XY}}=(\log L)\pi/\sqrt{3\mathcal P}\)，其中 \(L\) 是分块比率、\(\mathcal P\) 是临界轨迹的温度响应常数。

## 证明思路

证明把"确定一个尺度"与"把这个尺度解释为相关长度"分成两个独立任务，使解析活动映射（analytic activity map）只在坐标小时使用。第一步先让温度成为映射的受控变量：把高度按边长 \(s\) 的胞平均后，证明在 \(b_c\) 附近半径正比于 \(s^{-2}\) 的复圆盘上可以解析初始化。尺度 \(L^j\) 上两个标量坐标 \((x_j,y_j)\) 分别度量二次梯度扰动与粗糙高度权重的第一傅里叶谐波，其主导递推为 \((x,y)\mapsto(x-y^2,\,y-xy)\)，临界轨迹是 \((1,1)/j+O(\log j/j^2)\)。论文的核心新估计是非零温度响应：\(\frac1j\partial_b(x_j,y_j)|_{b=b_c}\to\mathcal P(1,-\tfrac12)\) 且 \(\mathcal P>0\)；其正值来自高度方差导数的有限体积下界，而线性化矩阵的特征方向分析（增长方向 \((1,-\tfrac12)\)、衰减方向 \((1,1)\)）配合物理读出比较排除了纯衰减解。随后令 \(\delta=\sqrt{b_c-b}\)、重标定 \(w=\delta j\)，坐标 \(X=x/\delta,Y=y/\delta\) 收敛到流 \(X'=-Y^2,\ Y'=-XY\)；守恒量 \(X^2-Y^2=-3\mathcal P\) 给出显式解 \(k\cot(kw),\,k\csc(kw)\)（\(k=\sqrt{3\mathcal P}\)），流在时刻 \(T=\pi/k\) 到达出射极点。离散轨迹恰在指标 \(j_e\)（\(\delta j_e\to T\)）处越出小活动区，故特征空间尺度为 \(L^{T/\delta}\)。第二步识别 \(\xi(b)\)：沿 \(b\uparrow b_c\) 的序列提取子列，得到对数尺度 \(w=\delta\log_L m\) 上非增的高度廓线 \(\mathcal A(w)=8\pi\)（\(0<w<T\)）、\(\mathcal A(w)=0\)（\(w>T\)）。下界方向：\(T\) 以下钉扎高度协方差为正，它要求存在水平直径宏观的电流环，而 van Engelenburg–Lis 随机环表示中访问远点的概率被 \(e^{-m(b)\cdot\mathrm{dist}}\) 控制，若 \(m(b)\) 过大协方差将趋于零，导出矛盾。上界方向：\(T\) 以上高度系数为零使固定环量倾斜几乎无代价，在围绕源点的指数多个不相交环面上叠加倾斜，得任意强多项式衰减，再用 Lieb–Rivasseau 有限尺寸判据转化为 \(m(b)\ge(\log 2)/r\)。两界匹配得 \(\delta\log_L(1/m)\to T\)，换底即得主定理；子列抽取通过反证去掉。

## 可信度与备注

本篇主结果暂无形式化证明，按 OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。家族内姊妹篇互相支撑：本批中"临界相关指数"一文证明了对偶高度场的临界系数恰为 \(8\pi\)（即上文廓线的左值），"高度与自旋场 BKT 普适性"一文提供了本族共用的有限高斯比较、环面几何与解析映射工具；本篇还引用了家族中关于临界对数修正的另一篇伴侣工作。三篇合成一条完整的 BKT 图景：临界指数、对数修正与近临界奇性。

{% endraw %}
