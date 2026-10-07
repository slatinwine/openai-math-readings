---
layout: default
title: "A counterexample to the Monge ansatz for the three-marginal Coulomb cost"
family: "373"
discipline: "Partial differential equations"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A counterexample to the Monge ansatz for the three-marginal Coulomb cost

> 结果族 373：Nonattainment of the three-marginal Coulomb Monge problem　·　学科：Partial differential equations　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文构造了一个光滑紧支撑、平方根同样光滑的三维概率密度，使三体库仑最优传输不存在确定性映射解：任何保测度映射对都取不到最优值，但映射下确界与松弛下确界相等，从而推翻了光滑密度下 Monge ansatz（Monge 拟设）的一般可行性。

## 问题背景

多重边际最优传输（multi-marginal optimal transport）研究在给定各边际分布时如何最小化总相互作用代价。当代价为库仑代价（Coulomb cost）\(c=\sum_{i<j}1/|x_i-x_j|\)、三个边际相同时，问题源自密度泛函理论（density functional theory）的强关联极限：强相互作用下电子的基态排布正是库仑型多体传输问题的解。物理文献中的 co-motion ansatz 断言最优构型可写成第一个粒子位置的确定性函数，即映射对 \((\Id,T_2,T_3)\) 的图像。此前两粒子情形最优映射的存在唯一性已证（Cotar–Friesecke–Klüppelberg 2013），一维任意粒子数也有循环最优映射（Colombo–De Pascale–Di Marino 2015）；Colombo–Di Marino（2015）证明 Kantorovich 最优值等于循环保测度映射的下确界，但只给出逼近而非存在性。最接近的反例是 Bindini–De Pascale–Kausamo（2022）针对平面约化径向代价的结果，而非完整库仑代价。三维三粒子的映射取等问题直到 2026 年 1 月仍被 Friesecke 列为公开问题，本文给出否定回答。

## 主要结果

主定理：存在密度 \(\rho\in C_c^\infty(\mathbb{R}^3)\)，\(\int\rho\,dx=1\) 且 \(\sqrt\rho\in C_c^\infty(\mathbb{R}^3)\)，使得对 \(\mu=\rho\,dx\)：Kantorovich 下确界 \(E_*(\mu)\) 有限且被某个耦合取到，但任何满足 \((T_2)_\#\mu=(T_3)_\#\mu=\mu\) 的 Borel 映射对都满足 \(\int c(x,T_2(x),T_3(x))\,d\mu(x)>E_*(\mu)\)（左边允许为 \(+\infty\)）。同时 Monge 下确界（对一切保测度映射对取下确界）仍等于 \(E_*(\mu)\)：逼近可达，取等永不可达。推广定理：对每个维数 \(d\ge 2\) 与每个指数 \(s>0\)，逆幂 Riesz 代价 \(c_s=\sum_{i<j}|x_i-x_j|^{-s}\) 在 \(\mathbb{R}^d\) 上同样存在具备上述全部性质的光滑密度。所造密度落在物理密度类 \(D_3\) 中（取 \(n=3\rho\) 则 \(\sqrt n\in H^1\)），不过文中不涉及外势与基态诠释。

## 证明思路

证明是"几何约束＋质量失衡"的组合，分四步走。

先在五个两两不交的小球（以 \(0,\pm e_1,\pm e_2\) 为心）上建立对偶型的支撑不等式（supporting inequality）：构造有界连续位势 \(u\)，使 \(c\ge u(x_1)+u(x_2)+u(x_3)\)，等号恰在两族三元组 \((x,Y_k(x),W_k(x))\)（\(k=1,2\)）及其坐标置换上成立。局部上固定正向外点、对其余两坐标取条件极小，隐函数定理给出微分同胚（diffeomorphism），换参数后得到分支映射 \(Y_k,W_k\)；关键的巧合是两个中心三元组 \((0,e_k,-e_k)\) 的库仑代价同为 \(5/2\) 且中心梯度相同，故两族能共享同一个中心位势。其余组合被严格代价间隙排除（含零却非对心的组合代价 \(2+1/\sqrt2>5/2\)），重复分量被库仑奇性排除：同球两点代价至少 \(1/(2r)\)，把球半径 \(r\) 取得足够小即可压过位势上界。

再构造边际与最优耦合：取中心球上的光滑概率 \(\nu=g^2dx\)，定义 \(\mu=\frac13\nu+\frac16\sum_H H_\#\nu\)，其中 \(H\) 遍历四个分支映射。随机等概率选一个分支，再对 \((x,Y_k(x),W_k(x))\) 做独立均匀随机置换，所得耦合 \(\pi_0\) 的三个边际恰为 \(\mu\) 且逐点取等，故最优；由换元公式与五个支撑互不相交，\(\rho=\frac13g^2+\frac16\sum_H g_H^2\) 连平方根都光滑。任何最优耦合都被支撑不等式逼到等号集上。

然后是排除映射的测度论核心，即分裂引理（splitting lemma）：若保测度映射对最优，则中心球上 \(\nu\)-几乎处处 \(T_2(x)\in\{Y_1,W_1,Y_2,W_2\}(x)\)。设 \(T\) 在 Borel 集 \(S_j\) 上选了分支 \(H_j\)，则 \(S_j\) 的 \(\mu\)-质量为 \(\frac13\nu(S_j)\)，而其像 \(H_j(S_j)\) 只有 \(\frac16\nu(S_j)\)，保测度性立刻给出矛盾。这里用的是精确的像测度关系而非分量总质量，所以分支选择无论多么不规则都逃不掉。

最后证明两个下确界相等：把五个分量切成直径至多 \(\delta\) 的格子，令图方案在每格积上的质量等于 \(\pi_0\) 的质量，用切片引理与 Rosenblatt 变换（Rosenblatt transform）构造 Borel 传输映射实现重新分配；分量间距 \(\eta>0\) 保证代价振荡至多 \(6\delta/\eta^2\)，令 \(\delta\to0\) 即得，全程无需让奇异代价通过弱极限。Riesz 推广只需验证 \(D^2h_s\) 可逆（径向特征值 \(s(s+1)|b|^{-s-2}\)，切向 \(-s|b|^{-s-2}\)）与新间隙 \(2+2^{-s/2}>2+2^{-s}\)，整套论证照搬。

## 可信度与备注

本文是结果族 373 的奠基篇：质量分裂引理、五分量对偶证书、光滑边际构造、下确界比较与 Riesz 推广在文内自成完整证明链，且明确否定的是任意 Borel 保测度映射对，包括对称化与循环方案。主结果暂无形式化证明，依 OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准；本批次该族仅此一篇，Riesz 推广内嵌于本文而非姊妹篇，其内部各节互相支撑。

{% endraw %}
