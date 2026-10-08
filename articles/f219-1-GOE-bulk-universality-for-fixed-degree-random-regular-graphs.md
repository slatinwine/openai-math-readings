---
layout: default
title: "GOE bulk universality for fixed-degree random regular graphs"
family: "219"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | GOE bulk universality for fixed-degree random regular graphs

> 结果族 219：GOE bulk universality for regular graphs with weak Anderson disorder　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

一支百万人的队伍，每人只认识固定 `@@M@@d@@` 位朋友（关系网稀疏），却要求整支队伍的"关系谱"排布得像所有人被随机充分混合的稠密网络——听起来荒唐，但本文证明它成立：均匀随机 `@@M@@d@@`-正则图的邻接矩阵在谱带内任一固定能量处的微观统计就是 GOE，连三次图（`@@M@@d=3@@`）也不例外，且结论沿一切容许的顶点数成立，不附加连通性等任何条件。

**关键词卡片**

- 随机正则图（random regular graph）：每个顶点恰有 `@@M@@d@@` 条边、均匀抽取的图。
- Kesten–McKay 分布（Kesten–McKay law）：无穷 `@@M@@d@@`-正则树的谱密度，是展开特征值的天然刻度尺。
- 展开点过程（unfolded point process）：按局部密度重标特征值间距，使平均间距归一。
- GOE 体过程（GOE bulk process）：实对称高斯矩阵谱内部的极限点过程。
- Laplace 泛函（Laplace functional）：用一切非负连续检验函数来检验点过程的方式。

**看个具体例子**

公式卡——密度与数字版定理：

`@@M@@D\rho_d(t)=\frac{d\sqrt{4(d-1)-t^2}}{2\pi(d^2-t^2)},\qquad \sum_i\delta_{\,n\rho_d(E)(\lambda_i-E)}\ \to\ \Xi^{\mathrm{GOE}}@@`

代入 `@@M@@d=3@@`、`@@M@@E=0@@`：`@@M@@\rho_3(0)=3\sqrt{8}/(2\pi\cdot 9)\approx 0.150@@`。若图有 `@@M@@n=10^6@@` 个顶点，`@@M@@0@@` 附近的平均间距约 `@@M@@1/(n\rho)\approx 6.7\times10^{-6}@@`；展开后间距归一，局部排布与 GOE 完全一致。换句话说，特征值既不更挤也不更散，恰好是教科书里的正弦核统计。

**为什么值得关心**

它补上了 Bourgade–Huang 猜想留下的最后缺口：单个固定能量处的完整点过程极限，而不再是能量平均意义下的统计。稀疏与稠密两个世界，在谱的显微镜下合二为一。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明固定度体普适性猜想：对每个固定整数 `@@M@@d\ge3@@`（含三次图），均匀随机 `@@M@@d@@`-正则图邻接矩阵在 Kesten–McKay 谱带内任一固定能量处的展开点过程收敛到 GOE 体过程，沿一切容许规模成立且无需任何附加条件。

## 问题背景

随机正则图即使顶点数趋于无穷仍是稀疏的：邻接矩阵每行恰有 `@@M@@d@@` 个非零元，然而人们预期其体特征值具有实对称高斯矩阵（GOE）的局部统计。这一预言由 Jakobson–Miller–Rivin–Rudnick 提出并有数值支持；在固定度下尤为惊人——局部树几何始终存在，特征值统计却要与稠密高斯矩阵一致。此前进展：Bauerschmidt–Knowles–Yau 对增长的度数建立局部律；BHKY（2017）在多项式增长的度范围内证明体间隙普适性与能量平均相关普适性；Huang–Yau 把局部律、刚性与完全离域推广到一切固定 `@@M@@d\ge3@@`；Huang–McKenzie–Yau 进一步在固定度下证明最优刚性与谱边 GOE 普适性；Bourgade–Huang 用回路方程处理 `@@M@@(\log n)^{24}\ll d\le n^{1/2}@@`，并在其猜想 2.11 中留下固定度情形。本文正是解决这一最后缺口：在单个固定能量处识别完整微观点过程律，而非能量平均统计。

## 主要结果

定理：对每个固定整数 `@@M@@d\ge3@@`、每个固定能量 `@@M@@E\in(-2\sqrt{d-1},\,2\sqrt{d-1})@@`（开 Kesten–McKay 体）以及每个非负紧支撑连续函数 `@@M@@h@@`，有 `@@M@@\bigl|\mathbb E e^{-\int h\,d\Xi_{n,d,E}}-\mathbb E e^{-\int h\,d\Xi_n^{\mathrm{GOE}}}\bigr|\to0@@`。这里 `@@M@@\Xi_{n,d,E}=\sum_i\delta_{\,n\rho_d(E)(\lambda_i-E)}@@` 以 Kesten–McKay 密度 `@@M@@\rho_d(t)=\frac{d\sqrt{4(d-1)-t^2}}{2\pi(d^2-t^2)}@@` 展开特征值，`@@M@@\Xi_n^{\mathrm{GOE}}@@` 是归一化 GOE 特征值按 `@@M@@(n/\pi)@@` 缩放后的单位强度参考过程。收敛沿一切容许规模 `@@M@@n@@` 成立，不附加连通性、二部性等任何图条件；结合 GOE 参考过程的依律收敛，这识别了完整局部点过程极限，即 Bourgade–Huang 猜想 2.11 的固定能量 Laplace 泛函版本。

## 证明思路

证明分四步，灵魂在于把有限图的离散切换对称与特征向量端点值的高斯性结合成极限律上的精确连续对称，再注入 GOE 噪声并用 Dyson Brownian 运动完成识别。

先证定量高斯标记。把特征向量按 `@@M@@\|u_i\|^2=n@@` 规范化，在均匀采样有向边的两端读取坐标，称每个采样边及其两个端点坐标为一个通道（channel）；对靠近 `@@M@@E@@` 的任意有限个特征向量，可证这些采样值的任意固定阶联合矩以多项式精度逼近高斯矩：均值为零、方差为一、各特征向量之间独立、同一条边两端的协方差为 `@@M@@E/d@@`。技术核心是 Backhausz–Szegedy 熵方法的定量强化：染色星计数不等式经高斯平滑变成熵不等式，树对数势算出熵代价，一个严格张量不等式再按 Hermite 阶数归纳，把熵亏乏转化为逐阶矩匹配；其严格性是一个有限维张量事实，依赖体的开性与 `@@M@@d\ge3@@`。

再取微观极限。用双边切换（two-edge switch）与上述矩估计控制大微观高度处的 resolvent，抽取带有高斯端点标记的 subsequential 点过程；极限 resolvent 有对称主值（principal value）表示，点计数与常数密度之间有幂次节约的偏差。

然后是连续切换与高斯插入，最具原创性的一步。有限图的切换只给出置换作用；但极限律的端点标记是高斯的，在正交旋转下不变，于是由反射生成整个正交群 `@@M@@O(k)@@`：极限律在精确的解析变换 `@@M@@\mathcal T_O@@` 下不变。再在极限律内部让通道数 `@@M@@k=2r@@` 增大：取 `@@M@@r@@` 个小角度 `@@M@@\theta@@` 的平面旋转，总方差 `@@M@@T=r\theta^2@@`；经两轮截断——外位置删除靠主值尾对消，内块靠加权 Bernstein 与 Schur 补估计——切换后的迹化为有限对角矩阵被 `@@M@@4r@@` 个小秩一项之和扰动；Lindeberg 型逐项替换把秩一和换成 GOE 噪声，得到 `@@M@@H_r=D_I+s_1\mathrm I+\sqrt{s_2}\mathcal W@@`，其特征值点过程收敛到同一极限律。

最后用固定能量 DBM 识别。验证 Landon–Sosoe–Yau 定理所需的正则性假设；用 Rouché 定理与自由卷积（free convolution）把比较密度精确归一到 `@@M@@1/\pi@@`；GOE 紧区间计数的指数矩经 Forrester–Rains 高斯削减（decimation）化为行列式 Hermite 核的界；Bonferroni 有限包容排斥括号把各阶相关函数比较一致地升级为 Laplace 泛函收敛。取极限的次序很关键：先让 `@@M@@n\to\infty@@`（固定标记数与谱窗），再在极限律内部令 `@@M@@r\to\infty@@`，最后提升括号阶数，因此有限图阶段只需固定维数、固定矩阶的高斯逼近。

## 可信度与备注

主结果暂无形式化证明，请以社区核验为准。本文是本结果族的基石：姊妹篇（弱 Anderson 无序版）明确声明改编本文的组合熵与高斯插入论证，把谱输入换成带环境的无穷树理论后得到无序推广；两文在"熵—插入—DBM"框架上互相印证其稳健性。按 OpenAI 官方声明，未经形式化的结果可能有问题，引用前宜等待社区核验。

{% endraw %}
