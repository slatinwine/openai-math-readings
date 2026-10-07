---
layout: default
title: "The sharp exponential rate of singularity for symmetric Bernoulli matrices"
family: "239"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The sharp exponential rate of singularity for symmetric Bernoulli matrices

> 结果族 239：Sharp singularity rates for symmetric random sign matrices　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了对角线及以上元素独立、均匀取 \(\pm1\) 的对称随机矩阵满足 \(\Pr(\det A_n=0)=(1/2+o(1))^n\)：最朴素的"两行相等"机制就是奇异的全部指数级来源，对称模型悬置的精确奇异率由此确定。

## 问题背景

离散随机矩阵何时奇异（singularity）是自 Komlós 以来的经典难题。独立条目模型已完全理解：Komlós 证明独立均匀 \(0/1\) 矩阵以趋于 1 的概率非奇异，Tikhomirov 进一步证明独立均匀符号矩阵的奇异概率恰为 \((1/2+o(1))^n\)。但对称（symmetric）模型中揭示一行等于同时揭示所有后续行的一列，行与行不再独立，基于独立行的利特尔伍德–奥福德（Littlewood–Offord）反集中论证全部失效。Costello–Tao–Vu 发展二次利特尔伍德–奥福德理论，首次证明对称伯努利矩阵渐近非奇异，界为 \(O(n^{-1/8+\delta})\)；此后 Nguyen 改进到任意多项式衰减，Vershynin 与一系列后续工作（最优达 \(\exp(-c\sqrt{n\log n})\)）逐步推进，Campos–Jenssen–Michelen–Sahasrabudhe 终于得到指数界 \(\exp(-cn)\)。但指数常数是否最优——即奇异率是否恰为 \((1/2)^n\)——此前未知，本文给出肯定回答。

## 主要结果

**定理 1.1**　设 \(A_n\) 为对称 \(n\times n\) 随机矩阵，其对角线及以上元素独立且均匀分布于 \(\{-1,1\}\)，则
\[\Pr(\det A_n=0)=\left(\frac12+o(1)\right)^n=2^{-n+o(n)}.\]

下界显而易见：指定两行相等的概率恰为 \(2^{-n}\)——两行交点之外有 \(n-2\) 个坐标相等比较，加上两个对角位置条件，它们相互独立。定理的实质是上界：整数核向量、近似核向量等所有其他奇异机制合起来，在指数尺度上也不超过"两行相等"。

## 证明思路

全文沿"归约—位势—静态计数—动态控制"展开。

先做两次精确归约。将 \(A_n\) 乘以 \((A_n)_{11}\) 并作对角合同变换，可使第一行全为 1，其 Schur 补（Schur complement）等于 \(-2\) 乘一个比特对称矩阵，故 \(\Pr(\det A_n=0)=\Pr(\det\mathbf B_{n-1}=0)\)，而比特模型的上三角元素独立均匀。再翻转 \(k-1\) 个对角比特（\(k\le N^{3/5}\)）可把余秩（corank）\(k\) 化为 1，每个像至多 \(2^{o(N)}\) 个原像；更高余秩的概率不超过 \(2^{-\Omega(N^{6/5})}\)，可以忽略。余秩一又化为加列问题：删去核向量绝对值最大的坐标得非奇异主子式（principal minor）\(B\)，被删列 \(z\) 必属于容许列集 \(\mathcal S(B)=\{z\in\{0,1\}^m:z^{\mathsf T}B^{-1}z\in\{0,1\},\ \|B^{-1}z\|_\infty\le1\}\)，且 \(\Pr(\mathrm{corank}=1)\le N2^{-N}\E|\mathcal S(\mathbf B_{N-1})|\)。于是全部问题化为证明 \(\E|\mathcal S(\mathbf B_{N-1})|\le2^{o(N)}\)。

再在判别群（discriminant group）\(G_B=\Z^m/B\Z^m\) 上定义算术位势（potential）\(\Psi\)：以 \(k_B(p,e)\) 记各素数幂层的层高、\(\nu_p=\log_Np/N\) 记权，令 \(\Psi(B)=\sum\nu_p\,\phi(k_B(p,e))\)（\(\phi(1)=0\)，\(\phi(2)=7/5\)，\(\phi(k)=2k\)）。两个支柱命题：典型地（即除概率 \(2^{-Nf(N)}\)、\(f\to\infty\) 的例外集外）\(|\mathcal S(B)|\le2^{N(\Psi+\ell^{-A})}\)；以及 \(\E\,2^{N\Psi(\mathbf B_{N-1})}\le2^{o(N)}\)。前者把容许列数押在 \(B\) 的算术结构上，后者说明这种结构典型地便宜，相乘即得目标。

静态一半（第六节）用判别配对 \(\lambda_B(\bar x,\bar y)=x^{\mathsf T}B^{-1}y\pmod{\Z}\)：它是完美（perfect）配对，且容许列的类必迷向（isotropic）。对迷向元作正交块分解并染色，使同色元素之差的配对值阶可控；大色块经鲁棒子集构造出 \(B^{-1}\) 图像上协体积（covolume）可控的格。由低高度有理子空间覆盖（low-height cover）使秩估计对所有子空间同时成立，从而让配对给出的行列式下界与典型秩及谱性质的上界相矛盾——后者由半圆律矩估计加 Talagrand 凸集中不等式推出，说明近零特征值稀少；格部分对删去极小子格后的正交商调用 Regev–Stephens-Davidowitz 的逆向 Minkowski 定理（Reverse Minkowski）。

动态一半（第七至十一节）沿主子式路径推进：门控删除引理保证任何非奇异矩阵都可经宽度 1 或 2 的非奇异主子式步到达，宽度二步满足"两新列均容许"的门、其概率由静态列估计直接支付；宽度一步的位势增长由"证书定价"在条件指数矩中结清。高层尾部由"对所有素数的余秩一致不超过 \(N^{3/5}\)"与尾递归排除。最后在短终端窗口上二选一：某节点位势已小则局部估计直接收官；否则一个有界辅助统计量持续下降，迫使出现大量条件概率极小的步骤，总概率可以忽略。

## 可信度与备注

主结果尚无 Lean 形式化证明。姊妹篇（偏置对称情形）直接沿用本文的主子式路径、判别群配对与格工具，并将其立方交估计加强为同时版本，两文互相支撑、共同构成族 239。按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。

{% endraw %}
