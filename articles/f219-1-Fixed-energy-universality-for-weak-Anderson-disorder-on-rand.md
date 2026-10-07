---
layout: default
title: "Fixed-energy universality for weak Anderson disorder on random regular graphs"
family: "219"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Fixed-energy universality for weak Anderson disorder on random regular graphs

> 结果族 219：GOE bulk universality for regular graphs with weak Anderson disorder　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明：对固定度 \(d\ge 3\) 的均匀随机 \(d\)-正则图，加上强度足够小且固定的独立对角无序后，干净谱带内任一固定能量处的特征值点过程经无穷树态密度展开后收敛到 GOE 体过程，把固定度普适性推广到弱 Anderson 无序情形。

## 问题背景

Anderson（1958）提出用无序（disorder）解释随机介质对电子输运的抑制；在无穷正则树（Bethe 格子）上，砍断一条边即分离出独立分支，Green 函数因此满足递归分布方程，成为 Abou-Chacra–Thouless–Anderson 自洽理论的基础。Klein（1994、1998）证明了小无序时干净谱带的紧子区间上谱纯绝对连续。有限随机正则图局部像树，但有限谱引出新问题：长度约 \(1/n\) 的窗口内，特征值是否具有实对称高斯矩阵的统计？此前无序侧只有 Anantharaman–Sabri 的量子遍历性（平均意义的空间均衡分布），单个固定能量处的联合特征值统计在固定度加无序的情形完全未知。

## 主要结果

模型为 \(H_{n,d,w}=A_{n,d}+w\,\mathrm{diag}(\omega_1,\dots,\omega_n)\)：\(A_{n,d}\) 是均匀简单 \(d\)-正则图的邻接矩阵，\((\omega_v)\) 独立均匀分布于 \([-1,1]\) 且与图独立，\(w>0\) 固定。定理（固定能量普适性）：对每个 \(d\ge3\) 与 \(0<\kappa<2\sqrt{d-1}\)，存在 \(w_0(d,\kappa)>0\)，使得对每个固定的 \(0<w<w_0\)，无穷树算子 \(A_{\mathbb T_d}+w\,\mathrm{diag}(\omega_v)\) 的态密度（density of states）测度 \(\nu_{d,w}\) 在区间 \(I_{d,\kappa}=[-2\sqrt{d-1}+\kappa,\ 2\sqrt{d-1}-\kappa]\) 的邻域上有连续密度 \(\rho_{d,w}\)，且在 \(I_{d,\kappa}\) 上严格为正；进而对每个固定能量 \(E\in I_{d,\kappa}\)，微观点过程 \(\Xi_{n,E}=\sum_i\delta_{\,n\rho_{d,w}(E)(\lambda_i-E)}\) 的 Laplace 泛函收敛到 GOE 体参考过程 \(\Xi_n^{\mathrm{GOE}}\)，收敛沿一切容许图规模 \(n\) 成立。允许的无序强度随度数及与干净谱边的距离而变化。

## 证明思路

证明分四大步，骨架承自干净模型的姊妹篇，而全部难点在于随机环境必须被显式保留到最后一步。

先建立分布型局部律（distributional local law）。分支 Green 函数满足一个标量递归；第 2 节证明该递归在干净体解附近的稳定性，包括上半平面边界值的控制——这是 Klein 型绝对连续结论的定量强化。第 3 节再对有限图腔 resolvent（cavity resolvent）的经验分布导出近似递归，工具是有限条边的切换、对势的谱平均（spectral averaging）与 Ward 恒等式。与通常局部律不同，所得极限中随机环境仍然可见。

再识别采样顶点处的特征向量标记（marks）。取范数平方为 \(n\) 的特征向量与距 \(E\) 不超过 \(O(n^{-1})\) 的有限特征值列表；subsequential 极限下根点坐标满足树特征方程，微观一致可积性保住精确二阶矩。消除条件均值的小技巧是让全部势同时做微小的保序形变并配合谱平均。第 4 节对整棵树的环境取条件建立星–边熵不等式，其中势分箱带来的 \(-\log Q\) 项在极限中精确抵消。

然后是比较场的刚性论证。以树 Green 函数虚部为协方差的高斯场同样满足树特征方程，其精度（precision）按入射边分解，同一条边两端的贡献相加恰为边精度。第 5 节结合换根不变性做 Fisher 信息比较，迫使熵不等式取等；等号情形给出：在环境条件下根点各坐标为独立高斯，方差是 \(\Im m_o(E+i0)/(\pi\rho_{d,w}(E))\)——这一条件化陈述保留了取平均后会抹去的信息。

最后确定微观谱过程。第 6 节把采样 resolvent 表示为点过程上的高斯标记；重抽单个势给出精确的秩一恒等式，配合高斯集中把初步的慢估计提升为极限 Stieltjes 变换的一致正则性。再利用势分布上保测度的短区间交换制造大量微小扰动，切换恒等式把其效应表示成高斯标记构成的小符号秩一矩阵之和；第 7 节以 Lindeberg 型替换把中心化和换成 GOE 噪声，于是每个 subsequential 点过程律都可被"有限对角矩阵＋标量平移＋GOE 噪声"的特征值逼近。第 8 节验证正则性与密度归一化后，套用 Landon–Sosoe–Yau 的固定能量 Dyson Brownian 运动（DBM）定理，所得展开恰为定理中的 \(\rho_{d,w}\)；最后用 Bonferroni 有限包容排斥括号把相关函数层面的比较升级为 Laplace 泛函收敛。

## 可信度与备注

本文主结果暂无形式化证明，请以社区核验为准。它与同族的姊妹篇（干净固定度模型）关系密切：后者提供"熵—高斯插入—DBM"骨架，本文明确声明改编其组合熵与高斯插入论证，并新增树递归稳定性、分布型局部律与势重抽样三项纯无序侧的构造；干净模型结论形式上对应本文 \(w\to0\) 的极限。按 OpenAI 官方声明，未经形式化的结果可能有问题，引用前宜等待社区核验。

{% endraw %}
