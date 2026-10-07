---
layout: default
title: "Exponential PSD rank of positively shifted matching matrices"
family: "126"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Exponential PSD rank of positively shifted matching matrices

> 结果族 126：Exponential semidefinite complexity of perfect matching　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对任意固定的 \(0<\rho<1\)，奇割—完美匹配矩阵 \(|M\cap\delta(U)|-1+\rho\) 的实半定秩（PSD rank）至少为 \(2^{cn}\)；因此完全图完美匹配多面体的任何精确半定提升（semidefinite lift）规模必为指数级，负面回答了 Rothvoss 的"多项式规模半定提升"问题。

## 问题背景

扩展表述（extended formulation）用高维凸集的投影紧凑描述复杂多面体。Yannakakis 的非负分解框架与 Rothvoß 2014 年的工作证明完美匹配多面体（perfect matching polytope）\(P_n\) 的任何线性表述都有指数规模，但换成正半定锥仿射切片的投影（半定提升）可能更省，线性下界不自动排除它。Gouveia–Parrilo–Thomas 的锥分解定理把最小半定提升规模等同于松弛矩阵（slack matrix）的 PSD 秩，"匹配是否有多项式规模半定提升"由此悬而未决。此前仅有对称情形（Braun 等）与非负秩（Braun–Pokutta）的指数下界；Kaniewski–Lee–de Wolf 还给出容许误差 \(2^{-\sqrt{n/2}}\) 的亚指数近似分解，可见精确性必须严苛对待。本文的分离泛函承袭 Grigoriev 针对 Tseitin 矛盾的低度泛函。

## 主要结果

主定理：存在 \(c>0\)，对每个固定 \(0<\rho<1\) 有 \(n_0(\rho)\)，偶数 \(n\ge n_0\) 时 \(\rank_{psd} A_n(\rho)\ge 2^{cn}\)。行标为 \(K_n\) 的奇数大小顶点集 \(U\)（奇割，odd cut），列标为完美匹配 \(M\)，元素 \(|M\cap\delta(U)|-1+\rho\)（\(\delta(U)\) 为割集）；完美匹配穿过奇集的次数为正奇数，矩阵非负。PSD 秩是最小的 \(r\)，使存在实对称半正定因子 \(F_U,G_M\in\R^{r\times r}\) 满足 \(A_{U,M}=\tr(F_UG_M)\)。端点 \(\rho=1\) 有 \(\binom n2\) 规模对角分解，指数下界到不了它。推论：\(A_n(0)\) 与 Edmonds 描述（度等式+非负性+奇割不等式）的松弛矩阵 \(T_n(0)\) 的 PSD 秩均为 \(2^{c_0n}\)，故 \(P_n\) 的每个精确半定提升规模至少 \(2^{c_0n}\)。给 \(A_n(0)\) 因子追加标量块即得 \(A_n(\rho)\) 分解，故 \(\rank_{psd} A_n(\rho)\le\rank_{psd} A_n(0)+1\)，平移版蕴含未平移版。

## 证明思路

反证法，循 Lee–Raghavendra–Steurer 路线以低度分离泛函对付平方和，难点是把匹配问题传输到奇偶系统并处理正平移。

先造分离泛函。以 \(d=100\) 个随机完美匹配的并构造 \(t\) 点 \(d\)-正则二部扩展图（expander）\(H\)，割满足 \(|\delta_H(W)|\ge\beta d\min\{|W|,t-|W|\}\)。给各顶点指定总和为奇的奇偶位 \(b_i\)，则满足各处奇偶约束的位指派 \(y\) 必有某边两端不同，故 \(f_\epsilon(y)=\sum_e\mathbf 1_{\{y_{u,e}\ne y_{v,e}\}}-\epsilon\) 严格正。但论文在块 Fourier 特征（Fourier character）上定义线性泛函 \(\mathcal D\)：若 \(p\) 的关联像是割且块度（block degree）\(\le 2D\)（\(D=\lfloor t/1000\rfloor\)），就用扩展性选唯一小侧 \(S(p)\) 并给 \(\chi_p\) 赋值 \((-1)^{\sum_{i\in S(p)}b_i}\)，否则为零。各割陪集上 \(\mathcal D(\chi_p\chi_{p'})\) 是秩一半正定块，故对块度 \(\le D\) 的 \(g\) 有 \(\mathcal D(g^2)\ge0\)，而 \(\mathcal D(f_\epsilon)=-\epsilon<0\)。

再把奇偶系统嵌入匹配：把 \(H\) 每个顶点换成 \(k\) 个顶点的胞（\(k\) 为先固定的常数），奇割行取每胞中规定奇偶的子集，列匹配每胞留 \(d\) 个端子、其余顶点胞内配对，辅助边连接对应端子；局部限制使胞内对割位相等，于是 \(|M\cap\delta(U)|-1+\rho=f(y)\) 精确成立。若存在规模 \(r\le 2^t\) 的分解，先以 \(\log\det\) 势归一化迹，再对行因子作限制平均，得 \(\tr(\overline F_m(y)G_{M(m)})=f(y)\)。

最后证明小分解迫使 \(f\) 接近低块度平方和（sum of squares），靠三个组件：局部平均引理借置换对称性（非常特征空间维数 \(\ge k/2\)）与迹估计得方差压缩 \(O(k^{-1/4}\sqrt{\log k})\)；正交分裂引理以 Helstrom 型谱投影把 \(L\) 个 PSD 矩阵分入正交子空间；乘积平滑定理逐坐标归纳，以直和堆叠实现新平均、控制新频率重叠并分配分支，势每步至多翻倍。于是可选 \(m\) 使 \(\overline F_m=\sum_q H_q^{\mathsf T}H_q\) 且加权 Fourier 质量极小；把每分支截断到中心邻域 \(\mathrm{dist}\le D\)，弃量被指数权重压至 \(n(4L)^{-2t}\)，故 \(f_*\) 一致逼近 \(f\)。乘以 \(\chi_q\) 把保留频率平移到块度 \(\le D\) 而平方不变（支撑平移原理），故 \(\mathcal D(f_*)\ge0\)；但范数界给出 \(|\mathcal D(f-f_*)|\to0\)，与 \(\mathcal D(f)=-\epsilon\) 矛盾。故 \(r>2^t\ge 2^{n/(2k)}\)。

## 可信度与备注

本文是结果族 126 的主定理载体，本批次该族仅此一篇。局部平均、正交分裂、乘积平滑三个组件独立成节，可单独核验与复用，增强可信度。按任务元信息，主结果暂无 Lean 形式化证明；OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。

{% endraw %}
