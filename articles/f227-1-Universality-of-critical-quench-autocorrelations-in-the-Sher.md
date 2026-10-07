---
layout: default
title: "Universality of critical quench autocorrelations in the Sherrington--Kirkpatrick model"
family: "227"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Universality of critical quench autocorrelations in the Sherrington--Kirkpatrick model

> 结果族 227：Critical SK autocorrelation processes and dynamics across the temperature transition　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了 SK 自旋玻璃在临界温度 \(\beta=1\) 处，从独立均匀自旋"淬火"（quench）出发的两点自相关函数与平稳自相关函数联合收敛到同一个随机泛函极限，且该极限对高斯与拉德马赫（Rademacher）两类耦合普适；淬火极限随等待时间增长弛豫回平稳极限。

## 问题背景

Sherrington 与 Kirkpatrick 在 1975 年提出这个全连接自旋玻璃模型，它是理解无序系统慢弛豫的标杆。"淬火"指让系统从简单的非平衡初态（如独立公平自旋）出发，再在给定温度下演化。在临界温度 \(\beta=1\) 处，弛豫时间随系统尺寸发散，\(n^{2/3}\) 尺度的临界窗口成为正确的观测尺度：Billoire–Campbell 的数值实验早已猜测平稳自相关形如 \(n^{-1/3}F(t/n^{2/3})\)，而 Sompolinsky–Zippelius、Cugliandolo–Kurchan 的动力学平均场理论只处理软自旋且取极限次序不同。此前姊妹篇（平稳情形的临界定理）只解决了平衡态起点；非平衡淬火起点的极限是否存在、由什么选定，一直没有严格结果。难点在于：临界处谱边缘本身是随机的（GOE 边缘过程），而淬火初态在窗口内到达的"入口律"可能依赖边缘之外的额外随机性。

## 主要结果

模型为零场 SK 的 Gibbs 测度 \(\pi_{n,J}(\sigma)\propto\exp\{n^{-1/2}\sum_{i<j}J_{ij}\sigma_i\sigma_j\}\)，每个格点配速率为一的热浴（heat-bath）时钟。记 \(T_n=n^{2/3}\)，定义平稳自相关 \(A_{n,J}(t)=n^{-2/3}\sum_i\langle\sigma_i,P^J_{tT_n}\sigma_i\rangle_{\pi_{n,J}}\) 与淬火自相关 \(B_{n,J}(s,t)=n^{-2/3}\sum_i\mathbb E_{\nu_n}^J[\sigma_i(sT_n)\sigma_i((s+t)T_n)]\)，其中 \(\nu_n\) 是均匀初态，\(s\) 为等待时间、\(t\) 为滞后。定理证明：无论耦合 \(J_{ij}\) 取高斯还是 \(\{\pm1\}\) 上的拉德马赫律，\((A_{n,J},B_{n,J})\) 在紧集上一致依律收敛到同一对随机函数 \((A_g,B_g)\)。这里 \(g\) 是 GOE 上边缘过程（edge process，即 \(n^{2/3}(2-\lambda_a)\) 的联合极限），\(\Pi_g\) 是由它构造的条件边缘测度（conditioned edge measure），\(S_t^g=e^{-tc_*H_g}\) 是对应 Dirichlet 形式生成的马尔可夫半群，\(c_*\) 是确定的微观系数。淬火极限由密度族 \(h_s^g\)（满足 \(h_{s+t}^g=S_t^g h_s^g\)）给出，\(B_g(s,t)=\sum_a\int h_s^g x_a (S_t^g x_a)\,d\Pi_g\)；当 \(s\downarrow0\) 时 \(h_s^g\Pi_g\) 在乘积拓扑下弱收敛到 \(\delta_0\)，当 \(s\to\infty\) 时 \(B_g(s,\cdot)\) 一致趋近平稳极限 \(A_g\)。

## 证明思路

证明先做一个谱分离：高斯情形下给相互作用矩阵补一条 GOE 对角线不改变 Gibbs 测度，于是在特征向量坐标系 \(x_a=n^{-1/3}\langle u_a,\sigma\rangle\) 下有恒等式 \(n^{-2/3}\sigma\cdot\sigma'=\sum_a x_a(\sigma)x_a(\sigma')\)，从而 \(B_{n,J}(s,t)=\sum_a\mu[w_s x_a P^J_{tT_n}x_a]\)，其中 \(w_s\) 是时刻 \(sT_n\) 的相对密度——这把"淬火到达的律"与"之后的弛豫"拆开。第一步做预热（warming）估计：用尺度 \(p\) 的嵌套高斯观测把特征值截断在 \(2-p^2\)，配合熵的反证论证，在紧阈值 \(k_p=np^3\) 之上得到对一切初态一致的密度与核控制。第二步用有限马尔可夫预解式压缩界住平稳松弛能量定理中的优化子，得到子序列上的强半群收敛，产出由 \(S_t^g\) 演化的正时间密度族——但它可能仍含 \(g\) 之外的随机性。第三步是关键的入口律选定（entrance selection）：证明权重 \(p_i(x)=x_i^2/(2r_iM_g(x))\) 沿某序列逃离每个固定有限集这一条件唯一确定密度族；技术上通过角坐标 SDE 消去公共投影与漂移，将平方约束化为一个标量 Volterra 方程，再用带停时的耦合论证压缩映射式地证明固定 \(g\) 的唯一性与 \(\delta_0\) 边界，最后可测地从 \(g\) 构造出该族。最后用 Chatterjee 的元素替换（entry replacement）做无序比较：两类耦合对归一化相互作用的前三阶导数匹配，四阶导数必须带消失因子，配合静态重叠尾估计与转移区间二叉树上的正反条件估计，把联合迹律迁移到拉德马赫情形。

## 可信度与备注

本文主结果尚无 Lean 形式化证明，属于 OpenAI 以"论文级证明"标准发布的预印本，官方声明未经形式化的结果可能存在问题，请以社区核验为准。它的平稳输入（条件边缘测度、闭形式与系数 \(c_*\)）直接取自同族姊妹篇《Functional universality of critical SK autocorrelations》，两文互相咬合：姊妹篇给出平衡态极限，本文在其上叠加淬火入口律的选定与弛豫，构成结果族 227 在临界点的完整动力学图景。

{% endraw %}
