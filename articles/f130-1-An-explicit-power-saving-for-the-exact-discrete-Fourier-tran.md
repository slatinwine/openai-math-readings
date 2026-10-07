---
layout: default
title: "An explicit power saving for the exact discrete Fourier transform"
family: "130"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | An explicit power saving for the exact discrete Fourier transform

> 结果族 130：Exact Fourier transforms below \(n\log n\)　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
本文给出单一确定性算法，对每个长度 \(n\) 都用 \(O(n(\log n)^{1-10^{-13}})\) 次精确复数运算完成离散傅里叶变换（discrete Fourier transform），且标量准备与寻址开销全部计费，首次在一切长度上严格突破 \(n\log n\) 界线。

## 问题背景
长度 \(n\) 的傅里叶矩阵 \(F_n=(\zeta_n^{jk})\) 的快速计算是算法理论的试金石：1965 年 Cooley–Tukey 的 FFT 在高复合长度达到 \(O(n\log n)\)，Bluestein 的啁啾卷积（chirp convolution）又把任意长度化归到同一量级，\(n\log n\) 从此被视作天然界线。下界方面，Morgenstern 的行列式论证只适用于系数有界的模型，Ailon 的熵型下界依赖酉两坐标门等限制，都无法约束系数不受限的精确计算；上界方面，Alman–Rao 借矩阵非刚性只改进了 2 的幂长度的领先常数。能否在所有长度上把对数因子本身的指数压低，此前没有任何先例。

## 主要结果
定理 1.1：存在单一确定性算法，对每个正整数 \(n\) 与每个 \(x\in\mathbb C^n\) 精确计算 \(F_nx\)，耗时 \(O(n(\log n)^\theta(\log\log n)^{4-\theta})\)，其中指数 \(\theta=\log_m\lambda\) 由显式常数 \(m=10^6\)、\(W_*=2^{71}\)、\(\Delta=6871402692000000\)、\(\lambda=m-\Delta/W_*\) 给出，数值上 \(\theta=0.99999999999978\ldots<1\)；推论 1.2 即为 \(O(n(\log n)^{1-10^{-13}})=o(n\log n)\)。计算模型的计费相当苛刻：精确复数算术，数据上只允许加减及乘预选标量，系数幅度不受限；由外部提供一个指定单位根（root of unity）\(\zeta_{D_*}\)，\(D_*<1024n^3\)；标量准备、调度构造与对数字长的寻址操作全部计入。推论 1.3 把同样的界推广到精确卷积与多项式乘法。

## 证明思路
证明由三个部件拼装而成。

先造固定网络，攻克一个二元矩阵的张量幂（tensor power）。取 \(C=\frac12\begin{pmatrix}1+i&1-i\\1-i&1+i\end{pmatrix}\)：逐轴计算 \(C^{\otimes k}\) 需 \(O(k2^k)\)，而文中显式构造的标量网络（寄存器由 100 元集合的三元组编址，三阶段、每段八行更新，恒等式 \(RG+JV=I\) 保证一切辅助线复原）能把两排寄存器整体轮换。关键一招是换标架：给每个门贴上 \(\mathbb F_2^m\) 的子空间标签 \(U\)，令 \(\Phi_U=J_m\diag(i^{\wt(P_Ux)\bmod4})J_m\)，则 \(\Phi_0=I\)、\(\Phi_{\mathbb F_2^m}=C^{\otimes m}\)；由正交向量的 Hamming 重量模 4 可加，嵌套标签之间的换架恰化为若干方向核 \(C_z=aI+bR_z\)，个数等于残差维数。清点全部残差得 \(s=Wm-\Delta\)，绝对盈余 \(\Delta=2v^2(v-3h(h+1))>0\)；把角色数补齐到 \(W_*=2^{71}\) 后，递归式 \(t(k)\le A+\lambda t(\lfloor k/m\rfloor)\) 解出 \(C^{\otimes k}\) 只需 \(O(2^k(k+1)^\theta)\)。注意网络必须连暂存角色一起变换，递归批处理在任意初值下才严格成立——这是全文反复强调的设计约束。

再造局部编译器，把任意 \(F_r\) 压回恰好 \(r\) 个坐标。Newton 插值给出分解 \(F_r(u)=ND_N^{-1}N^{\mathsf T}\)，其中 \(N\) 是两个对角阵夹一个可逆下三角 Toeplitz 阵；后者用位移秩（displacement rank）方法拆成至多三个秩一外积与平移的卷积和，经 Bennett 式"计算—读取—逆算"重放，可在原有坐标上借用携带任意数据的"脏"坐标执行并复原，深度 \(O(\log^4 r)\)；块大小由打印出的电路门数这一纯整数判据选定。任意剪切运算再用固定的六拷贝 \(C\) 词实现，\(\kappa=1+|\mu|^2\) 的非零拆分避开了复数零判别。

最后同步并覆盖全部长度。Good 互素分解把 \(F_L\) 写成各素因子傅里叶阵的张量积，扇区打包公式让同时的两坐标层在线性数组工作量内变成 \(C^{\otimes k}\) 调用；取 \(L\) 为前 \(\ell\) 个奇素数之积再乘一个 2 的幂（\(2n\le L<4n\)），初等组合估计（不用素数定理）给出 \(\ell=\Theta(\log n/\log\log n)\)；Bluestein 啁啾恒等式 \(\zeta_n^{jk}=\eta^{k^2}\eta^{-(k-j)^2}\eta^{j^2}\) 把任意 \(n\) 化为长度 \(L\) 的循环卷积，且全部所需单位根都是单个 \(\zeta_{D_*}\) 的幂。合并即得 \(O(n\ell^\theta(\log\ell)^4)\)，也就是定理的界。

## 可信度与备注
本文主结果暂无形式化证明，请以社区核验为准。姊妹篇《Finite tensor savings and exact Fourier circuits》用矩阵价格方法独立证明"有限盈余必然存在"，为本文的证书接口提供第二条来源；两坐标核 \(C\) 的网络则出自同项目的整数乘法论文。按 OpenAI 官方声明，未经形式化的结果可能有问题。另外文中常数极大，作者明言这是渐近存在性与显式性结果，没有实用的交叉点估计，也不涉及数值稳定性或比特复杂度。

{% endraw %}
