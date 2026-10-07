---
layout: default
title: "Regular trajectories, pruning and quantum parity"
family: "274"
discipline: "Mathematical physics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Regular trajectories, pruning and quantum parity

> 结果族 274：Parity is not in QAC<sup>0</sup>　·　学科：Mathematical physics　·　验证状态：主结果已 Lean 形式化

## 一句话结论
本文用"正则轨迹＋剪枝"的新框架独立证明：常数深度、多项式总比特的 QAC⁰ 电路无法以任何固定优势计算奇偶性，从而排除 Moore 猜想中的无界扇出，并连带给出态制备与对称函数的一批下界。

## 问题背景
\(\QAC\) 允许任意单比特酉门和任意元数的广义 Toffoli 门，但每层门的支撑两两不交——于是"一条导线能否同时驱动任意多个门"，即无界扇出 (fanout)，成为实质问题。Moore 1999 年猜想该模型实现不了扇出；由于 Hadamard 共轭交换 CNOT 的控制与目标，扇出 \(F_n\) 与相干奇偶变换 \(\ket{y,b}\mapsto\ket{y,b\oplus\Parity_n(y)}\) 互相等价，猜想亦称奇偶性猜想。此前的下界或限制辅助比特数（Anshu–Dong–Ou–Yao 2025 等的 \(\widetilde O(n^{1+3^{-d}})\) 量级），或固定纠缠深度（Joshi–Tal–Vasconcelos–Wright、Kintali），没有一个能同时覆盖所有固定深度与所有固定多项式资源。本文在最宽松的测量输出 (measured-output) 模型——输入可被破坏、非输出寄存器可留任意垃圾、只测一个输出比特——下补齐这一缺口。

## 主要结果
**定理**：固定正整数 \(d,k,C\) 与 \(0<\varepsilon\le1/2\)，存在 \(n_0=n_0(d,k,C,\varepsilon)\)，使得 \(n\ge n_0\) 时，任何深度 \(\le d\)、总比特数 \(\le C(n+1)^k\) 的电路必有某个输入 \(x\)，在其上答对 \(\Parity_n(x)\) 的概率严格小于 \(1/2+\varepsilon\)。由此，常数深度多项式资源无法实现扇出 \(F_n\)：给它配两层单比特门和一个零目标比特即得奇偶计算，与定理矛盾；这同时否定 Moore 原始的"辅助比特须归零"表述。态制备方面，定义保留态的 felinity \(2\sum_y p_y p_{\bar y}\)（\(\bar y\) 为按位取反，\(p_y\) 为对角概率），则每个固定深度与多项式比特界下最终 felinity \(<n^{-A}\)；且对 \(n^\delta\le k\le n/2\)，Dicke 态 \(|D_k^n\rangle=\binom nk^{-1/2}\sum_{|y|=k}|y\rangle\) 的制备必有迹距离误差 \(>1/(80k)\)。结合 Xu–Li 的归约，严格多数及更广的对称函数同样没有 \(1/(\log n)^\gamma\) 的最坏情形优势。

## 证明思路
方法整体是状态依赖的轨迹分析。先把广义 Toffoli 视为关于乘积投影的反射 \(R_g=I-2P_g\)；对每个"乘积测试"定义激发计数 (excitation count) \(H_A\)，它统计有多少位点偏离指定单比特态。核心概念是正则轨迹 (regular trajectory)：逐层演化时，任取一层中至多 \(m^b\) 个反射，它们测试位点的合计失配在进入该层的状态上有指数衰减的尾部 \(\|\one_{H_S\ge m^h}\xi_{j-1}\|\le e^{-m^p}\)。先构造两类 Chebyshev 滤波多项式：零滤波 \(Q\) 在整数谱点上逼近零投影（\(Q(0)=1\)、精度 \(e^{-m^q}\)、度与全局范数 \(\le e^{m^r}\)）；尾探测器 \(T\) 处处非负、在 \([m^h,m^u]\) 上 \(\ge1/4\) 而在低段 \(\le e^{-m^s}\)——非负性保证二次型中不会出现外部抵消。在此基础上证三个结构命题：其一，低度算子沿正则轨迹传播，度数指数只损失任意小的固定量，依据是"度数 \(\ell\) 的算子至多改变激发数 \(\ell\)"这一局部性原理；其二，尾部传输引理比较两条正则轨迹，把两个多项式分别放在内积的两侧，使其巨大的全局范数各自被对方的尾界吸收；其三，投影插入命题说明在输出端插入任意乘积投影再反向演化仍保持正则，由此得到关键推论：从乘积初态出发，\(\|\one_{H_0\ge m^h}W^\dagger P_BW\psi_0\|\le e^{-m^p}\)。但一般电路未必正则，于是引入剪枝 (pruning)：逐层用"剪后前缀"的真实状态作判断，保留投影概率 \(\|P_g\psi\|^2\ge m^{-6}\) 的反射；被保留的层自动正则，被删的门对状态的扰动每层 \(\le 2m^{-2}\)，故剪后电路 \(W\) 与原电路在初态上只差 \(2tm^{-2}\)。最后是奇偶收官：附加 \(n\) 比特参考寄存器，用一排 CNOT 把输入拷贝进去（其投影概率为 \(1/4\)，必被保留），初态取均匀相干叠加 \(\psi_0=\ket{+}^{\otimes n}\ket0^{\otimes a}\ket0_R^{\otimes n}\)。逐点正确性把带符号期望 \(\ip{\Phi}{Z_RP_B\Phi}=2^{-n}\sum_x(-1)^{|x|}p_x\) 压到 \(\le-\varepsilon\)，剪枝几乎不改变它。再把 \(Z_R\) 穿过被保留的拷贝层得 \(Z_IZ_R\)，其作用于 \(\psi_0\) 恰把每个输入因子 \(\ket+\) 翻成 \(\ket-\)，新向量相对 \(\psi_0\) 的失配数恰为 \(n\)。由于总比特数 \(m\) 多项式依赖于 \(n\)，可选 \(m^h=o(n)\)，使该向量落入高失配谱段，前述尾推论把配对 \(|\ip{\Omega}{Z_RP_B\Omega}|\le e^{-m^p}\) 逼到零，与 \(\le-\varepsilon\) 矛盾。

## 可信度与备注
主定理已完成 Lean 形式化（结果族 274），滤波、传输、剪枝等结构引理均自含于本文，不依赖姊妹篇。姊妹篇《Product-projection localization and the QAC0 parity lower bound》以一致的算子范数局部化定理给出另一条独立证明，两条路线各自完成全部环节、互不引用，显著降低单一路线出错的风险。多数与态制备推论引用 Xu–Li、Gretta–Gupta–Joshi 及 Grier–Morris–Wu 的归约。按 OpenAI 官方声明，未经形式化的结果可能有问题，形式化范围之外的细节请以社区核验为准。

{% endraw %}
