---
layout: default
title: "Product-projection localization and the QAC0 parity lower bound"
family: "274"
discipline: "Mathematical physics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Product-projection localization and the QAC0 parity lower bound

> 结果族 274：Parity is not in QAC<sup>0</sup>　·　学科：Mathematical physics　·　验证状态：主结果已 Lean 形式化

## 一句话结论
本文证明 QAC⁰——常数深度、多项式总比特、由任意单比特门与无界元数 Toffoli 门组成的量子电路——无法以任何固定正优势算出奇偶性，正面解决 Moore 1999 年的奇偶性猜想（测量输出模型），并连带排除严格多数判决等对称任务。

## 问题背景
奇偶函数 \(\parity(x)=x_1\oplus\cdots\oplus x_n\) 是检验浅电路能否整合全局信息的试金石：答对它就必须让每个输入都影响到输出。经典电路复杂度理论的起点正是 \(\mathrm{AC}^0\) 上的奇偶下界（Furst–Saxe–Sipser 与 Ajtai，1983–1984；Håstad 1986 的切换引理给出近最优指数界）。1999 年 Moore 提出量子类比 \(\QAC\)：允许任意单比特酉门和任意元数的 Toffoli 门，但每层门的支撑两两不交，并猜想它无法实现相干奇偶／无界扇出 (fanout)。困难有二：一个 Toffoli 门可一次触碰全部输入，逆向光锥论证完全失效；量子辅助 (ancilla) 比特可以纠缠、可以留下任意垃圾。此前最好的结果（Anshu–Dong–Ou–Yao 2025、Dong–Ou–Yao 2025）仍把辅助比特数限制在 \(\widetilde O(n^{1+2^{-d}})\)，Joshi–Tal–Vasconcelos–Wright 等则固定纠缠深度，均未覆盖任意固定多项式资源下的全部固定深度。

## 主要结果
**奇偶下界定理**：固定深度 \(d\ge0\)、指数 \(c\ge1\) 与优势 \(0<\varepsilon\le1/2\)。当 \(n\) 充分大时，任何深度 \(\le d\)、输入 \(n\) 比特、总比特数 \(\le n^c\)、由任意单比特酉与无界元 Toffoli 门构成的电路，必存在输入 \(x\) 使其答对 \(\parity(x)\) 的概率低于 \(1/2+\varepsilon\)。辅助比特初始为 \(\ket0\)、只测量一个输出比特、其余寄存器任意丢弃——这是最宽松的测量输出 (measured-output) 模型。取 \(\varepsilon=1/6\) 即常见的成功阈 \(2/3\)，故 \(\mathrm{PARITY}\notin\QAC\)。核心结构定理是乘积投影的局部化 (localization)：对失配计数 (mismatch count) \(M=\sum_{i\in S}(I-\proj{v_i})_i\) 与任意 \(U\in\cU_d(N)\)，有 \(\|[M\ge N^t]\,U[D=0]U^\dagger[M=0]\|\le e^{-N^s}\)（任意固定 \(0\le s<t\)），且对所有电路与计数一致成立。推论包括：严格多数 \(\operatorname{MAJ}_n\) 无 \(1/(\log n)^\gamma\) 的最坏情形优势（结合 Xu–Li 归约）；固定汉明重量均匀叠加态 \(|D_k^n\rangle\)（Dicke 态）与字符串及其按位取反不可被高精度制备；输出期望符号的傅里叶系数在大小 \(\ge n^\delta\) 的输入子集上总平方权重超快速衰减——一个量子版 LMN 定理。

## 证明思路
整个证明绕开光锥，转而控制"从一个乘积条件出发、跳到大量失配状态"的转移范数，且保留投影造成的振幅损失、绝不重新归一化。先把每个 Toffoli 门改写为关于乘积投影 (product projection) \(A\) 的反射 \(I-2A\)（控制位全为 1、目标位取 \(\ket-\)），电路呈 \(U=(L_dR_d)\cdots(L_1R_1)L_0\) 的规范形，且取逆后深度不变。第一步证深度 0：共轭一个乘积投影仍是乘积投影，失配数变成独立伯努利变量之和，用关于 \(2^K\) 的 Markov 不等式得 \(2^{-r}\) 型尾界。第二步剥层归纳：设投影只固定 \(k\) 个比特，一层内至多 \(k\) 个反射与它相遇，在投影两侧展开每个反射，得系数和 \(\le 9^k\) 的"三投影乘积"项，再用深度 \(d-1\) 的归纳假设，在三个因子之间插入两档中间失配截断，把每段跳变逐一压住。第三步克服展开代价随支撑指数增长的困难：把任意乘积投影写成第二个计数 \(D\) 的 \([D=0]\)，用 Chebyshev 型多项式 \(p\)（\(p(0)=1\)、在正整数谱点上误差 \(\le e^{-N^a}\)、度与加权系数和 \(\le e^{N^u}\)）把 \(D\) 的幂展开成至多 \(N^k\) 个小支撑单项式。最巧妙的是算子次序：平方目标范数得 \(\|HQP\|^2=\|HQPQH\|\)，只把最左的 \(Q\) 替换为 \(p(C)\)，残余误差落在 \(PQ\) 上，经逆电路共轭后恰好变成"两个计数互换、阈值更高"的同一命题——于是先在更大阈值证 \(\cB_d(t,b)\)，再倒推 \(\cB_d(s,t)\)。尺度链 \(t_{i+1}=2t_i-s_i-3\eta\) 经 \(O(1/(t-s))\) 步把阈值推过 1（此时尾投影消失、命题平凡），自后向前逐级归约完成归纳。收官时令 \(B=W^\dagger OW\)，输出零概率 \(p_0(x)\) 的奇偶傅里叶系数恰是互补 Hadamard 乘积态 \(\ket{\xi_h},\ket{\xi_{\bar h}}\) 间矩阵元的平均；这两态在全部 \(n\) 个输入比特上失配，局部化迫使每个矩阵元 \(\le e^{-N^s}\)（取 \(0<s<t<1/c\) 使 \(N^t<n\)），平均趋于零；而逐点正确率 \(\ge1/2+\varepsilon\) 强迫该平均 \(\ge\varepsilon\)，矛盾。

## 可信度与备注
主定理已通过 Lean 形式化验证（结果族 274）。姊妹篇《Regular trajectories, pruning and quantum parity》给出第二条独立证明：其走"正则轨迹＋剪枝"的状态依赖路线，本文则证一致的算子范数定理、不以任何轨迹假设为前提；两文各自完成多项式估计与奇偶转化，互不引用对方结构定理，构成交叉核验。多数函数、态制备等推论依赖 Xu–Li 与 Gretta–Gupta–Joshi 的归约。仍需留意 OpenAI 官方声明：未经形式化的结果可能存在问题，形式化覆盖之外的具体表述请以社区核验为准。

{% endraw %}
