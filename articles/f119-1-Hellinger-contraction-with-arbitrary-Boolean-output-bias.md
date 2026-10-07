---
layout: default
title: "Hellinger contraction with arbitrary Boolean output bias"
family: "119"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Hellinger contraction with arbitrary Boolean output bias

> 结果族 119：The Courtade–Kumar and Hellinger conjectures　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文对任意输出偏置的布尔函数证明了 Hellinger 猜想：平方根轮廓损失 \(\sqrt{1-m^2}-\mathbb E\sqrt{1-(T_\rho f)^2}\) 不超过单个坐标的损失 \(1-\sqrt{1-\rho^2}\)，等号由带符号坐标取得，并由此推出 Courtade–Kumar 互信息界。

## 问题背景

2017 年，Anantharam、Bogdanov、Chakrabarti、Jayram 与 Nair（ABCJN）提出 Hellinger 猜想：把 Courtade–Kumar"最信息布尔函数"问题中的二元熵换成 Hellinger 亲和（Hellinger affinity）后，单个坐标是否仍在乘积噪声下最大化损失？该表述保留了函数均值 \(m\)，偏置函数因此也在问题之内；ABCJN 证明此猜想蕴含 Courtade–Kumar 猜想，使其意义超出平方根轮廓本身。此前最好的结果是 Chen–Nair 由高斯等周（Gaussian isoperimetric）轮廓给出的均值依赖下界，但在平衡情形 \(m=0\) 只给出 \(\sqrt{2/\pi}\,s\)，低于锐利值 \(s\)；Durcik–Ivanisvili–Roos–Xie 证明了平衡情形的锐利平方根敏感度不等式。任意偏置下的完整猜想一直悬而未决。

## 主要结果

设 \(X\) 均匀分布于 \(\{-1,1\}^n\)，噪声观测 \(Y_i=X_iZ_i\)，各 \(Z_i\) 独立且 \(\Pr(Z_i=1)=(1+\rho)/2\)；记 \(H(t)=\sqrt{1-t^2}\)（注意：此处 \(H\) 是平方根轮廓，不是熵）。

定理（Hellinger 猜想，完整非平衡形式）：对一切 \(n\ge1\)、布尔 \(f:\{-1,1\}^n\to\{-1,1\}\)、\(\rho\in[-1,1]\)，记 \(m=\mathbb E f\)，有
\[H(m)-\mathbb E\,H(T_\rho f)\le 1-H(\rho),\]
带符号坐标（独裁函数）\(f=\pm x_i\) 对每个 \(\rho\) 取等。

其 Hellinger 含义：设 \(P_\pm\) 为给定 \(f(X)=\pm1\) 时 \(Y\) 的条件分布，贝叶斯公式给出亲和 \(A(P_+,P_-)=\mathbb E H(T_\rho f)/H(m)\)，故定理即加权亲和损失界 \(H(m)(1-A)\le1-H(\rho)\)。再经 ABCJN 的蕴含论证（凸函数 \(\varphi(t)=h_2(\frac{1-\sqrt{1-t^2}}{2})\) 与 Jensen 不等式）得到 Courtade–Kumar 结论（比特单位）：\(I(f(X);Y)\le1-h_2(\varepsilon)\)，带符号坐标取等。

## 证明思路

证明由互补的两段组成；计算机辅助仅限与维度 \(n\) 无关的固定标量不等式，文中每个小数都表示精确有理数。

低噪声段 \(s=\sqrt{1-\rho^2}\le0.84\) 用非对称维数归纳。先用压缩（compression）引理把 \(f\) 换成逐坐标单调的增函数且不增大 \(\mathbb E H(T_\rho f)\)：对每条坐标边把两截面排序为逐点最小/最大，利用 \(u\mapsto H(a+u)+H(a-u)\) 的偶凹性。再选一个一阶傅里叶系数 \(0<x\le b(m)\) 的活跃坐标——用四个活跃坐标平均值的重排上界控制 \(\mathbb E[fZ]\) 保证其存在。要传播的是非对称加强估计 \(\mathbb E\,G((1+T_\rho f)/2)\ge sB(m)\)，其中 \(G\) 满足反射恒等式 \(G(p)+G(1-p)=2H(2p-1)\)，\(B\) 是显式多项式轮廓；把它对 \(f\) 与其对偶 \(f^*(x)=-f(-x)\) 各用一次再平均，即还原 \(H\) 轮廓。归纳步骤：对两截面混合的增益，先用带间隙的两点标量不等式（由有限精确算术证书认证）控制，再用 Cauchy–Schwarz 平均化，得到只含两截面平均及其均值间隙的关系式；其单调的二次求根形式允许直接代入归纳假设。至多三个活跃坐标的基例由计算机穷举验证。

高噪声段 \(s\ge0.84\) 用延续（continuation）论证。半群能量恒等式 \(\frac{d}{d\tau}\mathbb E H(d)=\mathcal E(d)\)（即 Chen–Gohari–Nair 的 Hellinger 边导数）给出交叉判据：若目标不等式首次失效，则存在参数同时满足 \(b=h-1+s\) 与能量 \(\mathcal E(d)\le K=r/s\)；排除它（除非 \(f\) 是带符号坐标）即完成证明。换元 \(F'(x)=(1-x^2)^{-3/4}\) 把能量下方控制为 \(F(d)\) 的 Dirichlet 能量。中心带 \(m\le r^2/2\)：用满足 \(H(x_0)=b\) 的对称比较对 \(\pm x_0\) 校准边比较，恰好保住带符号坐标的精确边代价；方差增益与一阶傅里叶层的集中合起来逼出高于一层的傅里叶权重全部为零，从而 \(f\) 必为带符号坐标。中间带用奇偶傅里叶分解归约到带显式偏置裕度的逐点界（该段技术性较强，此处从略）。大偏置带 \(m\ge0.74\) 则是直接证明：由立方体对数索博列夫不等式（Gross 半群方法；正向界属 Bonami–Beckner 超收缩理论，反向界属 Borell）夹逼各阶矩，对 \(\sqrt{1-z}\) 的正系数二项级数逐项控制，在四个噪声区间上以精确有理算术收尾，所有常数严格小于 1。

## 可信度与备注

本篇暂无形式化证明，请以社区核验为准；其算术部分附有可执行证书（verification/central_band.py、verification/large_bias.py），且计算机辅助只涉及与 \(n\) 无关的标量不等式。同族姊妹篇《Sharp binary-information contraction on the discrete cube》主结果已 Lean 形式化，直接证明了 Courtade–Kumar 猜想，与本篇的推论互相印证。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
