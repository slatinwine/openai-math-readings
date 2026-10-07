---
layout: default
title: "A Power Saving for Polynomial Differences at Prime Arguments"
family: "182"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Power Saving for Polynomial Differences at Prime Arguments

> 结果族 182：Power savings for intersective polynomial differences and prime arguments　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明：若 \(h\) 模每个正整数都有单位根，则避开全部非零 \(h(p)\)（\(p\) 取素数）之差的集合满足 \(|A|\le C_hN^{1-c_h}\)。这把多项式差集的幂节省首次推广到素数自变量，关键解析输入是 Dirichlet \(L\)-函数在 \(\Re s>7/8\) 的一致无零点半平面。

## 问题背景

把 Sárközy 型定理中多项式的自变量限制为素数，回避条件更弱、问题更难，且出现新的局部障碍：模 \(q\) 的根须落在与 \(q\) 互素的剩余类（单位根，unit root）。Wierdl 给出这一条件的定性刻画，Rice（2013）据此对素数交集多项式证明了对数型界 \(N(\log N)^{-c}\)。素数变量的历史：Sárközy 处理 \(p\pm1\) 型位移，Green（2024）对 \(p-1\) 得到幂节省，Thorner–Zaman 给出显式指数，Li–Pan 处理 \(h(1)=0\) 的特例；但非线性多项式此前没有幂节省。卡点在于：核方法需要"一致于模数的素数分布"与"素数上的多项式指数和相消"，而经典零点自由区域不够强，素数权也远比整数权难于差分。

## 主要结果

定理（Theorem 1.1）：设 \(h\in\Z[x]\) 素数交集（prime-intersective，即对每个 \(q\ge1\) 存在 \(r\) 使 \((r,q)=1\) 且 \(h(r)\equiv0\pmod q\)）、次数至少二、首项系数为正，则存在 \(c_h>0\) 与 \(C_h\ge1\)：凡 \(A\subseteq[N]\) 满足 \((A-A)\cap\{h(p):p\in\mathbb P\}\subseteq\{0\}\)，必有 \(|A|\le C_hN^{1-c_h}\)。\(h(p)=0\) 不限制 \(A\)（允许 \(h\) 有素数根）。一个例子：\(h(x)=(x-1)^2\) 只禁 \((p-1)^2\) 型差已得幂节省，从而也重新蕴含平方差情形的幂节省。

## 证明思路

框架整体移植自族内交集多项式篇：反射正 tuple 律、Fourier 提升、符号核、收缩递归一应俱全；新困难有二。其一，tuple 律须与单位剩余类相容——指定圈的增量要能实现为素数自变量可取的局部多项式值；其二，核须支在素数自变量的真实多项式取值上，需要新的素数分布估计。

素数分布侧是本篇独有内容：从配套的无零点定理（一切 Dirichlet \(L\)-函数，含非本原特征，在 \(\Re s>7/8\) 无零点，允许主特征在 \(s=1\) 的极点）出发，先用 Borel–Carathéodory 得对数导数界 \(L'/L\ll\log(2b(2+|t|))\)，再用 Mellin 反演做光滑和、把积分轮廓移到 \(\Re s=15/16\)，最后对非负的等差素数和做锐利差分（取 \(H=x^{31/32}\)），得到一致素数定理 \(\sum_{n\le x,\,n\equiv c\,(b)}\Lambda'(n)=x/\varphi(b)+O(Y^{31/32}\log^2)\)。小弧则用 Vaughan 恒等式（Vaughan's identity）拆分素权，配合单变量与混合 Weyl 差分（文中说明乘积截断不破坏差分），对素数多项式指数和给出 \(Y^{1-c_m}\) 型相消。

辅助族带伴随自变量映射 \(T_l\)（\(T_1(m)=m\)，\(T_l(Dm-i)=T_{lD}(m)\)，结构出自 Rice）："在 \(l\) 处回避"指差避开一切使 \(T_l(m)\) 为素数的非零 \(h_l(m)\)，这使素数自变量条件沿等差数列精确传递。

收敛归纳与前身同构：定义 \(\mathcal Y_l(N)\) 为 Fourier 提升的对角积分，先立密度不等式 \((|A|/N)^d\le\mathcal Y_l(N)\) 与普适上界 \(\mathcal Y_l(N)\ll N^{o(1)}\)（对一切 \(l\) 成立，无 \(l\le N^\zeta\) 限制）；对固定正比例 \(\rho_l\ge\rho_*\) 的好指派，用素数核沿指定圈边得 \(N^{-\sigma}\) 相消，坏指派与例外质量经更短尺度比较控制；容斥展开后得严格收缩递归，对一切 \(l\) 同时强归纳给出 \(\mathcal Y_l(N)\le C_0l^{b_0}N^{-a_0}\)。取 \(l=1\)（此时 \(h_1=h\)、\(T_1(m)=m\)，正是定理的回避条件）得 \(|A|\le C_0^{1/d}N^{1-a_0/d}\)，即 \(c_h=a_0/d\)。只有严格有序对（正差）参与相消，故 \(h(p)=0\) 始终无害。

## 可信度与备注

本篇暂无形式化证明。其反射正 tuple 律与 Fourier 提升矩估计直接复用或重证族内交集多项式篇的内容；素数分布所依赖的无零点半平面定理则引用同批配套论文作为定理输入。方法链（平方 → 一般交集多项式 → 素数自变量）三篇分别覆盖三类禁差集合，结论与技巧互相支撑；素数篇成立时取 \(h=(x-1)^2\) 即回到平方情形，逻辑上闭合。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
