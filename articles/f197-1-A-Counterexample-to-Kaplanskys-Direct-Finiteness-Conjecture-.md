---
layout: default
title: "A Counterexample to Kaplansky's Direct-Finiteness Conjecture in Characteristic Two"
family: "197"
discipline: "Algebra"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Counterexample to Kaplansky's Direct-Finiteness Conjecture in Characteristic Two

> 结果族 197：A torsion-free group algebra that is not directly finite　·　学科：Algebra　·　验证状态：主结果已 Lean 形式化

## 一句话结论

在特征二有限域上构造有限展示群 \(G\) 与 \(a,b\in K[G]\)，使 \(ab=1\) 而 \(ba\ne1\)，否定 Kaplansky 直接有限性猜想；同组元素又给出单而不满的元胞自动机，连带否定 Gottschalk 满射性猜想。

## 问题背景

Kaplansky 猜想问：群代数 \(K[G]\) 中 \(ab=1\) 是否必蕴含 \(ba=1\)？sofic 群上答案肯定（Elek–Szabó 的稳定有限性定理），故反例群必非 sofic——而"是否每个群都 sofic"本身是著名未决问题。另一条线是 Gottschalk 1973 年的 surjunctivity 猜想：群上每个单射元胞自动机（cellular automaton）必满射；已知 surjunctive 群的群代数稳定有限（Phung 等），两个猜想在有限域上相通。技术难点在于：先造出矩阵反例 \(AB=I\ne BA\) 并不自动给出标量反例；Dykema–Juschenko 证明可用与有限群的直积实现传递，本文首次给出完整而显式的实现。

## 主要结果

定理：存在特征二有限域 \(K\)、含奇素数阶元的有限展示群 \(G\)，以及由可终止的有限处方（terminating prescription）显式指定的 \(a_{\mathrm{out}},b_{\mathrm{out}}\in K[G]\)，使得

\[a_{\mathrm{out}}b_{\mathrm{out}}=1,\qquad b_{\mathrm{out}}a_{\mathrm{out}}\ne1 .\]

两个乘积断言均有不依赖群字问题判定程序的代数证书。推论：该群非 sofic；以 \(b_{\mathrm{out}}\) 的支集为记忆集、其系数为局部规则的元胞自动机 \(T_{b_{\mathrm{out}}}:K^G\to K^G\) 单而不满，其像恰为 \(T_{b_{\mathrm{out}}a_{\mathrm{out}}}\) 的不动点集——某个点指示构形 \(\delta_h\) 不在像中，故 Gottschalk 猜想被否定。借同族嵌入定理，反例还可迁移到 \(F_\infty\) 型群。

## 证明思路

证明沿"组合数据→群→代数元素"三层铸造。第一层是组合判据：取有限点集 \(V\)（\(|V|=t\)）与线族 \(\mathcal F\)，使每点恰属 \(D=\ell+1\) 条线（\(\ell\) 为奇素数）、点线关联图围长（girth）\(\ge12\)；再取向量 \(x_v\in K^m\) 满足 \(\sum_{v\in V}x_vx_v^{\mathsf T}=-I_m\)、每条线上 \(\sum_{v\in f}x_vx_v^{\mathsf T}=0\)、以及 \(m<t\le m\ell^2\)。满足这些有限数据即可铸出反例。

第二层由数据建群与元素。在每个点放加法群 \(\mathbb F_\ell^2\) 的拷贝 \(K_v\)、每条线放一维子群 \(L_f\)，按长度至多三的零和关系生成群；平面平衡论证（欧拉公式配围长条件）保证子群真正嵌入。代数上取子群平均 \(P_v=\ell^{-2}\sum_{u\in K_v}u\)（幂等元），用分解式 \(1+\sum_{f\ni v}\bigl(\sum_{u\in L_f}u-1\bigr)\) 与向量配对式相乘，得矩形恒等式 \(UT=I_m\)。为把 \(t\) 个中间坐标压入 \(m\) 个槽位，作 HNN 扩张（HNN extension）加入稳定字母 \(\tau_v\) 实现特征扭转 \(\tau_v eP_v\tau_v^{-1}=eQ_{\alpha_v}\)：中心特征幂等 \(e\) 与两两正交的特征幂等 \(Q_\alpha\) 使共享槽位的坐标互不串扰，从而得到方阵 \(a_{\rm mat}b_{\rm mat}=I_m\)。检测反向缺陷最见功力：三明治计算 \(J_0(b_{\rm mat}a_{\rm mat}-I_m)C=e(TU-P)\) 把问题拉回子群代数，再用特殊化同态 \(\varepsilon(nz^r)=\zeta^r\) 化为 \(X^{\mathsf T}X-I_t\)；因 \(t>m\) 而秩亏，此矩阵非零。最后在有限群 \(F=(\mathbb Z/\ell)^m\rtimes S_m\) 中构造矩阵单位 \(p_{ij}\)，把矩阵代数单射嵌入群代数，补上正交补 \(1-\sum_i p_{ii}\)，即得标量元素。

第三层供给组合数据。在 \(Q^n\)（\(|Q|=q=2^h\)）中删去洞集 \(O\)；取 \(\ell\) 为模 \(q^{100}\) 同余 \(-1\) 的最小素数（Linnik 定理保证其存在且不太大）。洞上的 Newton 插值多项式给出向量 \(x_v\)：次数 \(\le q-2\) 的多项式在整条仿射线上求和为零，而洞处的值为坐标单位向量，相减恰得 \(\sum_{v\in V}x_vx_v^{\mathsf T}=-I_m\)。线系先按方向分块，再做局部交换——把过洞的 \(q\) 条线换成 \(q-1\) 条避开洞的平行线，保持每点度数不变；随机选取二维子空间并配合 Lovász 局部引理（文中自证）排除三角形、矩形、五边形等短关联圈。收尾用从 \(h=2\) 起的字典序有限搜索确定全部选择，处方可终止。

## 可信度与备注

本文主结果已 Lean 形式化。它是本结果族的枢纽：行列式姊妹篇直接引用其定理作存在性输入，无挠姊妹篇再以独立构造去掉挠。注意构造显式使用奇阶挠与特征二（正则度 \(D=\ell+1\) 在特征二为零，使线恒等式与总恒等式相容），系数域是有限域但未断言为 \(\mathbb F_2\)；处方只证明了终止性而未实际执行。按 OpenAI 官方声明，未经形式化的结果可能有问题——本文主结果不在此列。

{% endraw %}
