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

## 入门导读 🐣

一张巨型社交网，每人恰好有 `@@M@@d@@` 位朋友（网络稀疏得可怜），再给每人随机塞一点"个人偏好"（无序）。这张网的"关系矩阵"振动起来，特征值在数轴上的局部排布会像谁？本文证明：像实对称高斯矩阵 GOE——尽管网络每行只有 `@@M@@d@@` 个非零元、局部像棵树，谱的微观统计却与稠密随机矩阵无异。

**关键词卡片**

- d-正则图（d-regular graph）：每个顶点恰好有 `@@M@@d@@` 条边；均匀随机抽取一张。
- 邻接矩阵（adjacency matrix）：图的账本，第 `@@M@@i@@` 行第 `@@M@@j@@` 列记 1 表示有边。
- Anderson 无序（Anderson disorder）：每个顶点上独立随机的对角偏移 `@@M@@w\omega_v@@`，模拟杂质。
- 态密度（density of states）：单位谱长里特征值的平均个数，是展开谱的新刻度尺。
- GOE 体过程（GOE bulk process）：实对称高斯矩阵谱内部的极限点过程，局部统计的"参照仪"。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <circle cx="90" cy="60" r="7" fill="#333"/>
  <circle cx="50" cy="120" r="7" fill="#333"/>
  <circle cx="130" cy="120" r="7" fill="#333"/>
  <circle cx="30" cy="180" r="7" fill="#333"/>
  <circle cx="70" cy="180" r="7" fill="#333"/>
  <circle cx="110" cy="180" r="7" fill="#333"/>
  <circle cx="150" cy="180" r="7" fill="#333"/>
  <line x1="90" y1="60" x2="50" y2="120" stroke="#333" stroke-width="2"/>
  <line x1="90" y1="60" x2="130" y2="120" stroke="#333" stroke-width="2"/>
  <line x1="50" y1="120" x2="30" y2="180" stroke="#333" stroke-width="2"/>
  <line x1="50" y1="120" x2="70" y2="180" stroke="#333" stroke-width="2"/>
  <line x1="130" y1="120" x2="110" y2="180" stroke="#333" stroke-width="2"/>
  <line x1="130" y1="120" x2="150" y2="180" stroke="#333" stroke-width="2"/>
  <text x="95" y="45" font-size="13" fill="#e67e22">ω=+0.3</text>
  <text x="8" y="110" font-size="13" fill="#e67e22">ω=−0.7</text>
  <text x="142" y="112" font-size="13" fill="#e67e22">ω=+0.9</text>
  <text x="25" y="215" font-size="14" fill="#333">图局部像 3-正则树（带无序 ω）</text>
  <line x1="250" y1="90" x2="530" y2="90" stroke="#333" stroke-width="2"/>
  <text x="252" y="70" font-size="13" fill="#333">−2√2</text>
  <text x="498" y="70" font-size="13" fill="#333">+2√2</text>
  <circle cx="290" cy="90" r="3" fill="#333"/>
  <circle cx="322" cy="90" r="3" fill="#333"/>
  <circle cx="341" cy="90" r="3" fill="#333"/>
  <circle cx="368" cy="90" r="3" fill="#333"/>
  <circle cx="384" cy="90" r="3" fill="#333"/>
  <circle cx="412" cy="90" r="3" fill="#333"/>
  <circle cx="439" cy="90" r="3" fill="#333"/>
  <circle cx="460" cy="90" r="3" fill="#333"/>
  <circle cx="483" cy="90" r="3" fill="#333"/>
  <circle cx="502" cy="90" r="3" fill="#333"/>
  <circle cx="390" cy="90" r="11" fill="none" stroke="#c0392b" stroke-width="2"/>
  <text x="300" y="130" font-size="14" fill="#c0392b">放大固定能量 E 处：按树态密度 ρ(E) 展开</text>
  <text x="360" y="152" font-size="14" fill="#c0392b">后点过程 ≈ GOE</text>
  <text x="255" y="215" font-size="14" fill="#333">d=3 的干净谱带 [−2√2, 2√2]</text>
</svg>

</div>

红圈内取固定能量 `@@M@@E@@`，把特征值按无穷树算子的态密度 `@@M@@n\rho_{d,w}(E)@@` 重标展开后，其微观点过程收敛到 GOE 体过程——无序强度 `@@M@@w@@` 固定且足够小即可，结论沿一切图规模成立。

**为什么值得关心**

Anderson 1958 年的无序思想与稀疏图的 GOE 普适性在此汇合：单个固定能量处的完整统计，首次在固定度加无序的情形被完全识别。证明里最讲究的一步，是把随机环境显式保留到最后一刻才平均，避免过早抹去关键信息。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明：对固定度 `@@M@@d\ge 3@@` 的均匀随机 `@@M@@d@@`-正则图，加上强度足够小且固定的独立对角无序后，干净谱带内任一固定能量处的特征值点过程经无穷树态密度展开后收敛到 GOE 体过程，把固定度普适性推广到弱 Anderson 无序情形。

## 问题背景

Anderson（1958）提出用无序（disorder）解释随机介质对电子输运的抑制；在无穷正则树（Bethe 格子）上，砍断一条边即分离出独立分支，Green 函数因此满足递归分布方程，成为 Abou-Chacra–Thouless–Anderson 自洽理论的基础。Klein（1994、1998）证明了小无序时干净谱带的紧子区间上谱纯绝对连续。有限随机正则图局部像树，但有限谱引出新问题：长度约 `@@M@@1/n@@` 的窗口内，特征值是否具有实对称高斯矩阵的统计？此前无序侧只有 Anantharaman–Sabri 的量子遍历性（平均意义的空间均衡分布），单个固定能量处的联合特征值统计在固定度加无序的情形完全未知。

## 主要结果

模型为 `@@M@@H_{n,d,w}=A_{n,d}+w\,\mathrm{diag}(\omega_1,\dots,\omega_n)@@`：`@@M@@A_{n,d}@@` 是均匀简单 `@@M@@d@@`-正则图的邻接矩阵，`@@M@@(\omega_v)@@` 独立均匀分布于 `@@M@@[-1,1]@@` 且与图独立，`@@M@@w>0@@` 固定。定理（固定能量普适性）：对每个 `@@M@@d\ge3@@` 与 `@@M@@0<\kappa<2\sqrt{d-1}@@`，存在 `@@M@@w_0(d,\kappa)>0@@`，使得对每个固定的 `@@M@@0<w<w_0@@`，无穷树算子 `@@M@@A_{\mathbb T_d}+w\,\mathrm{diag}(\omega_v)@@` 的态密度（density of states）测度 `@@M@@\nu_{d,w}@@` 在区间 `@@M@@I_{d,\kappa}=[-2\sqrt{d-1}+\kappa,\ 2\sqrt{d-1}-\kappa]@@` 的邻域上有连续密度 `@@M@@\rho_{d,w}@@`，且在 `@@M@@I_{d,\kappa}@@` 上严格为正；进而对每个固定能量 `@@M@@E\in I_{d,\kappa}@@`，微观点过程 `@@M@@\Xi_{n,E}=\sum_i\delta_{\,n\rho_{d,w}(E)(\lambda_i-E)}@@` 的 Laplace 泛函收敛到 GOE 体参考过程 `@@M@@\Xi_n^{\mathrm{GOE}}@@`，收敛沿一切容许图规模 `@@M@@n@@` 成立。允许的无序强度随度数及与干净谱边的距离而变化。

## 证明思路

证明分四大步，骨架承自干净模型的姊妹篇，而全部难点在于随机环境必须被显式保留到最后一步。

先建立分布型局部律（distributional local law）。分支 Green 函数满足一个标量递归；第 2 节证明该递归在干净体解附近的稳定性，包括上半平面边界值的控制——这是 Klein 型绝对连续结论的定量强化。第 3 节再对有限图腔 resolvent（cavity resolvent）的经验分布导出近似递归，工具是有限条边的切换、对势的谱平均（spectral averaging）与 Ward 恒等式。与通常局部律不同，所得极限中随机环境仍然可见。

再识别采样顶点处的特征向量标记（marks）。取范数平方为 `@@M@@n@@` 的特征向量与距 `@@M@@E@@` 不超过 `@@M@@O(n^{-1})@@` 的有限特征值列表；subsequential 极限下根点坐标满足树特征方程，微观一致可积性保住精确二阶矩。消除条件均值的小技巧是让全部势同时做微小的保序形变并配合谱平均。第 4 节对整棵树的环境取条件建立星–边熵不等式，其中势分箱带来的 `@@M@@-\log Q@@` 项在极限中精确抵消。

然后是比较场的刚性论证。以树 Green 函数虚部为协方差的高斯场同样满足树特征方程，其精度（precision）按入射边分解，同一条边两端的贡献相加恰为边精度。第 5 节结合换根不变性做 Fisher 信息比较，迫使熵不等式取等；等号情形给出：在环境条件下根点各坐标为独立高斯，方差是 `@@M@@\Im m_o(E+i0)/(\pi\rho_{d,w}(E))@@`——这一条件化陈述保留了取平均后会抹去的信息。

最后确定微观谱过程。第 6 节把采样 resolvent 表示为点过程上的高斯标记；重抽单个势给出精确的秩一恒等式，配合高斯集中把初步的慢估计提升为极限 Stieltjes 变换的一致正则性。再利用势分布上保测度的短区间交换制造大量微小扰动，切换恒等式把其效应表示成高斯标记构成的小符号秩一矩阵之和；第 7 节以 Lindeberg 型替换把中心化和换成 GOE 噪声，于是每个 subsequential 点过程律都可被"有限对角矩阵＋标量平移＋GOE 噪声"的特征值逼近。第 8 节验证正则性与密度归一化后，套用 Landon–Sosoe–Yau 的固定能量 Dyson Brownian 运动（DBM）定理，所得展开恰为定理中的 `@@M@@\rho_{d,w}@@`；最后用 Bonferroni 有限包容排斥括号把相关函数层面的比较升级为 Laplace 泛函收敛。

## 可信度与备注

本文主结果暂无形式化证明，请以社区核验为准。它与同族的姊妹篇（干净固定度模型）关系密切：后者提供"熵—高斯插入—DBM"骨架，本文明确声明改编其组合熵与高斯插入论证，并新增树递归稳定性、分布型局部律与势重抽样三项纯无序侧的构造；干净模型结论形式上对应本文 `@@M@@w\to0@@` 的极限。按 OpenAI 官方声明，未经形式化的结果可能有问题，引用前宜等待社区核验。

{% endraw %}
