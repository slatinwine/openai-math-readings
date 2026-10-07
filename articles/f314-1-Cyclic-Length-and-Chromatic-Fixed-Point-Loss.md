---
layout: default
title: "Cyclic length and chromatic fixed-point loss"
family: "314"
discipline: "Topology"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Cyclic length and chromatic fixed-point loss

> 结果族 314：Cyclic length and chromatic fixed-point loss　·　学科：Topology　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对任意有限 \(p\)-群 \(G\) 与子群 \(H\)，本文证明"色度不动点损失"\(r_n(G,H)\) 恰好等于从 \(H\) 到 \(G\)、以循环群为商的最短次正规链长度 \(\ell(G,H)\)，对一切素数 \(p\) 与高度 \(n\ge0\) 成立，正面解决 Kuhn–Lloyd 提出的等式猜想。

## 问题背景

经典 Smith 理论 (Smith theory) 断言：带有限 \(p\)-群作用的模 \(p\) 零调有限复形，其不动点也模 \(p\) 零调。色度 Smith 理论 (chromatic Smith theory) 追问：把模 \(p\) 同调换成各个 Morava \(K\)-理论后，零调蕴含关系还能保留多少、要付出几个"色度高度"的代价。Balmer–Sanders 对真等变谱范畴素理想的分类把问题精确化；Barthel–Hausmann–Naumann–Nikolaus–Noel–Stapleton 解决了有限交换 \(p\)-群情形：损失恰为 \(G/H\) 的最小生成元个数。非交换情形此前只有"最大初等交换商的秩"这个下界，一般达不到真值——如 Kuhn–Lloyd 所证，\(D_8\) 中非中心二阶子群的损失是 2，而下界只给 1。他们把零调蕴含等价地译成 Morava 同调维数不等式，对中心扩张 \(C_2\to G\to E\)（\(E\) 初等交换）内的子群对证得等式，随后以"谨慎的希望"措辞提出一般等式 \(r_n(G,H)=\ell(G,H)\)，并另问损失是否与高度无关。本文对所有有限 \(p\)-群同时肯定回答这两问。

## 主要结果

固定素数 \(p\)，记 \(K(i)\) 为 Morava \(K\)-理论（\(K(0)=H\Q\)），\(\Phi^H X\) 为几何不动点 (geometric fixed points)。\(r_n(G,H)\) 定义为使蕴含
\[K(n+r)_*(\Phi^H X)=0\ \Longrightarrow\ K(n)_*(\Phi^G X)=0\]
对一切有限 \(p\)-局部真 \(G\)-谱 (genuine \(G\)-spectrum) \(X\) 成立的最小整数 \(r\ge0\)；\(\ell(G,H)\) 是最短次正规链 \(H=G_0\trianglelefteq\cdots\trianglelefteq G_s=G\) 的长度 \(s\)，相邻商群须循环——\(C_{p^2}\) 这样的商只计一步。主定理：对一切 \(p\)、\(G\)、\(H\)、\(n\ge0\)（含 \(n=0\) 的有理检测），
\[r_n(G,H)=\ell(G,H).\]
损失与高度无关；且对每个 \(0\le r<\ell(G,H)\) 都有有限 \(G\)-谱见证：\(\Phi^H X\) 为 \(K(n+r)\)-零调而 \(K(n)_*(\Phi^G X)\ne0\)。子群的嵌入方式举足轻重：在 \(G=C_{p^2}\times C_p\) 中，同构于 \(C_p\) 的子群 \(H_1=pC_{p^2}\times0\) 与 \(H_2=0\times C_p\) 的损失分别是 2 与 1，因为商群分别为 \(C_p\times C_p\) 与 \(C_{p^2}\)。结合 Balmer–Sanders 的共轭与 \(p\)-次正规约化，文末推论还对任意有限群给出素理想包含 \(\mathcal P_m^G(K)\subseteq\mathcal P_n^G(H)\) 的完整数值判据。

## 证明思路

上界 \(r_n\le\ell\) 是旧的：沿链逐段套用循环群的色度 Smith 定理即可。新意全在下界，分四步推进。

第一步把问题译入上自由谱 (cofree spectrum) 的语言：设 \(\mathrm{Bor}_P(D)=F(EP_+,\inf_PD)\)，\(U_P(D)=\Phi^P\mathrm{Bor}_P(D)\)，先证有理估计 \((U_P(L_{T(l)}S))_{\Q}\ne0\Rightarrow\ell(P,1)\le l\)（\(T(l)\) 为望远镜）。做法是在 \(T(l)\)-局部可对偶对象的张量范畴中有理化态射群、拆分 Burnside 幂等元 (Burnside idempotent)：称有限群 \(L\) "出现" (occurring)，若满标记幂等元切出的代数分量 \(D_L=e_L^L\,\one^{BL}\) 非零；出现的群必是 \(p\)-群、对子群与商群封闭，且由 Arone–Dwyer–Lesh–Mahowald 的初等交换锐性定理与 Frattini 论证，其一切截段 (section) 至多 \(l\) 个生成元。再构造极大化塔，逐项最大化"到每个有限群的同态类数"，取极限得到映满 \(P\) 的预 \(p\)-群 (pro-\(p\) group) \(\Gamma\)；其连续同态给出广义特征分裂——这绕开了 Hopkins–Kuhn–Ravenel 特征只看得见交换像的障碍。

第二步（第 4 节）用有限广群上的相对积分导出算术约束：对 \(\Gamma\) 的每个开子群 \(U\) 与有限连续 \(U\)-集 \(X\)，有同余式 \(\sum_{[U:V]=p^h}(|X^V|-|X|)\in p^{h+1}\Z_{(p)}\)，以及同态计数整性 \(|\Hom_{\cts}(\Gamma,F)|/|F|\in\Z_{(p)}\)。

第三步（第 5 节）是纯群论定理：这些条件迫使 \(\Gamma\) 带有长度 \(\le l\)、诸因子同构于 \(\Z_p\) 的闭次正规列。核心是"收缩作用"引理——借助共同置换商，把 \(N\rtimes\Z_p\) 在 \(p\)-进极限下换成 \(N\times\Z_p\)，同时保住同余式与生成元界；再用 Tamanoi 式子群计数生成函数的 \(p\)-进极限证明剩余核的交换化必无限：否则投射满子群计数将收敛到非零极限，与同余式强制的趋于零矛盾。迭代由 \(d+1\le l\) 强制终止。

第四步（第 6 节）升高度：Hopkins–Smith 环幂零性定理与 HKR 广义特征把有理估计升级为 \(T(k)\wedge U_P(L_{T(l)}S)\ne0\Rightarrow k+\ell(P,1)\le l\)。其中用 Lubin–Tate 理论算出满射特征投影子的迹 \(N_{k,r}=p^{k^2(r-1)}\prod_{i=0}^{k-1}(p^k-p^i)>0\)，保证满标记分量非零；再用与 \((C_{p^r})^k\)（\(r\) 任意大）的乘积和逆极限"扣秩"引理分离出 \(k\)，最后望远镜 fracture 方块经归纳粘合成有限高度消没估计。

收官（第 7 节）沿用 Balmer–Sanders 的支集分裂策略：几何 \(J\)-不动点函子有全忠实右伴随，其单位对象 \(\mathcal A_J\) 的各层几何不动点恰由诸 \(U_{K/J'}(E)\) 组成。取最小违反高度，上述消没估计把违规子群层正交隔离出来，把紧对象的支集——一点的闭包，故不可约——拆成两个非空不交闭集，矛盾。由此得特殊化界 \((H,m)\in\overline{\{(G,n)\}}\Rightarrow m\ge n+\ell(G,H)\)，译成素理想包含即 \(r_n\ge\ell\)，与上界合并即得主定理。

## 可信度与备注

本文是 OpenAI 发布的数学预印本，主结果暂无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。论文结构自足：外部输入（Hopkins–Smith 厚子范畴定理与环幂零性、CSY 的色度 ambidexterity、HKR 广义特征、Balmer–Sanders 素理想分类、ADLM 锐性例子）均为已发表结果并逐条引用，新引理均附证明，锐性见证谱由素理想分离构造产生。结果族 314 目前仅此一篇；它把交换情形的"生成元计数"等式（BHNNNS）与 Kuhn–Lloyd 的中心扩张等式统一为非交换的循环链长 \(\ell\)，补上了色度 Smith 理论的最后一块拼图。

{% endraw %}
