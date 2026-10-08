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

## 入门导读 🐣

判断一排开关里"按下的个数是奇是偶"（奇偶性），你必须看清每一个开关，任何偷懒的速算都会露馅。这篇论文证明：即使借助量子魔法——常数深度、多项式个量子比特、能一次摸遍所有输入的巨型门——也没有固定优势能算对奇偶性。Moore 1999 年的猜想被正面解决。

**关键词卡片**

- 奇偶函数（parity）：x₁⊕x₂⊕…⊕xₙ，输出"1 的个数是奇还是偶"。
- QAC⁰（constant-depth quantum circuits）：常数深度量子电路，允许任意单比特门和无界元 Toffoli 门。
- Toffoli 门（Toffoli gate）：多控制位的受控翻转门，可一次触碰任意多个输入。
- 辅助比特（ancilla）：电路自备的工作比特，允许纠缠、允许留下任意垃圾。
- 局部化（localization）：本文核心定理——乘积态经电路演化后仍"记不住"大量失配。

**看个具体例子**

画出一个这样的电路：所有输入汇入一个巨型 Toffoli 门，最后只测一个输出比特。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="60" y="49" font-size="14" fill="#333">x₁</text><line x1="85" y1="45" x2="225" y2="45" stroke="#333" stroke-width="2"/><text x="60" y="84" font-size="14" fill="#333">x₂</text><line x1="85" y1="80" x2="225" y2="80" stroke="#333" stroke-width="2"/><text x="60" y="119" font-size="14" fill="#333">⋯</text><line x1="85" y1="115" x2="225" y2="115" stroke="#333" stroke-width="2" stroke-dasharray="5 3"/><text x="60" y="154" font-size="14" fill="#333">xₙ</text><line x1="85" y1="150" x2="225" y2="150" stroke="#333" stroke-width="2"/><circle cx="235" cy="45" r="5" fill="#333"/><circle cx="235" cy="80" r="5" fill="#333"/><circle cx="235" cy="115" r="5" fill="#333"/><circle cx="235" cy="150" r="5" fill="#333"/><line x1="235" y1="45" x2="235" y2="190" stroke="#333" stroke-width="2"/><circle cx="235" cy="200" r="10" fill="none" stroke="#333" stroke-width="2"/><line x1="228" y1="200" x2="242" y2="200" stroke="#333" stroke-width="2"/><line x1="235" y1="193" x2="235" y2="207" stroke="#333" stroke-width="2"/><line x1="245" y1="200" x2="322" y2="200" stroke="#333" stroke-width="2"/><path d="M 327 209 A 11 11 0 0 1 349 209" fill="none" stroke="#333" stroke-width="2"/><line x1="338" y1="200" x2="346" y2="209" stroke="#333" stroke-width="1.5"/><text x="356" y="205" font-size="14" fill="#333">只测这一个输出比特</text><text x="262" y="178" font-size="13" fill="#666">无界元 Toffoli 门</text><text x="340" y="35" font-size="15" fill="#333">深度 d、总比特 ≤ nᶜ</text><text x="60" y="240" font-size="14" fill="#999">|0⟩</text><line x1="85" y1="236" x2="225" y2="236" stroke="#999" stroke-width="1.5" stroke-dasharray="5 3"/><line x1="225" y1="236" x2="235" y2="211" stroke="#999" stroke-width="1.5" stroke-dasharray="5 3"/><text x="100" y="264" font-size="14" fill="#999">辅助比特（初始 |0⟩，可纠缠、可留垃圾）</text></svg>

</div>

数字版定理：对任何深度 ≤ d、总比特 ≤ nᶜ 的此类电路，必存在输入 x，使其答对 parity(x) 的概率 `@@M@@<\tfrac12+\varepsilon@@`。取 ε=1/6：成功率连常见的 2/3 门槛都够不着。此前最好的结果都要限制辅助比特数量或固定纠缠深度，本文一举覆盖任意固定多项式资源下的全部固定深度。

**为什么值得关心**

奇偶性是浅电路的试金石：它一倒，严格多数判决、Dicke 态制备等一串对称任务连带倒下，量子浅电路的真实能力边界由此划定。

> 已 Lean 形式化

## 一句话结论
本文证明 QAC⁰——常数深度、多项式总比特、由任意单比特门与无界元数 Toffoli 门组成的量子电路——无法以任何固定正优势算出奇偶性，正面解决 Moore 1999 年的奇偶性猜想（测量输出模型），并连带排除严格多数判决等对称任务。

## 问题背景
奇偶函数 `@@M@@\parity(x)=x_1\oplus\cdots\oplus x_n@@` 是检验浅电路能否整合全局信息的试金石：答对它就必须让每个输入都影响到输出。经典电路复杂度理论的起点正是 `@@M@@\mathrm{AC}^0@@` 上的奇偶下界（Furst–Saxe–Sipser 与 Ajtai，1983–1984；Håstad 1986 的切换引理给出近最优指数界）。1999 年 Moore 提出量子类比 `@@M@@\QAC@@`：允许任意单比特酉门和任意元数的 Toffoli 门，但每层门的支撑两两不交，并猜想它无法实现相干奇偶／无界扇出 (fanout)。困难有二：一个 Toffoli 门可一次触碰全部输入，逆向光锥论证完全失效；量子辅助 (ancilla) 比特可以纠缠、可以留下任意垃圾。此前最好的结果（Anshu–Dong–Ou–Yao 2025、Dong–Ou–Yao 2025）仍把辅助比特数限制在 `@@M@@\widetilde O(n^{1+2^{-d}})@@`，Joshi–Tal–Vasconcelos–Wright 等则固定纠缠深度，均未覆盖任意固定多项式资源下的全部固定深度。

## 主要结果
**奇偶下界定理**：固定深度 `@@M@@d\ge0@@`、指数 `@@M@@c\ge1@@` 与优势 `@@M@@0<\varepsilon\le1/2@@`。当 `@@M@@n@@` 充分大时，任何深度 `@@M@@\le d@@`、输入 `@@M@@n@@` 比特、总比特数 `@@M@@\le n^c@@`、由任意单比特酉与无界元 Toffoli 门构成的电路，必存在输入 `@@M@@x@@` 使其答对 `@@M@@\parity(x)@@` 的概率低于 `@@M@@1/2+\varepsilon@@`。辅助比特初始为 `@@M@@\ket0@@`、只测量一个输出比特、其余寄存器任意丢弃——这是最宽松的测量输出 (measured-output) 模型。取 `@@M@@\varepsilon=1/6@@` 即常见的成功阈 `@@M@@2/3@@`，故 `@@M@@\mathrm{PARITY}\notin\QAC@@`。核心结构定理是乘积投影的局部化 (localization)：对失配计数 (mismatch count) `@@M@@M=\sum_{i\in S}(I-\proj{v_i})_i@@` 与任意 `@@M@@U\in\cU_d(N)@@`，有 `@@M@@\|[M\ge N^t]\,U[D=0]U^\dagger[M=0]\|\le e^{-N^s}@@`（任意固定 `@@M@@0\le s<t@@`），且对所有电路与计数一致成立。推论包括：严格多数 `@@M@@\operatorname{MAJ}_n@@` 无 `@@M@@1/(\log n)^\gamma@@` 的最坏情形优势（结合 Xu–Li 归约）；固定汉明重量均匀叠加态 `@@M@@|D_k^n\rangle@@`（Dicke 态）与字符串及其按位取反不可被高精度制备；输出期望符号的傅里叶系数在大小 `@@M@@\ge n^\delta@@` 的输入子集上总平方权重超快速衰减——一个量子版 LMN 定理。

## 证明思路
整个证明绕开光锥，转而控制"从一个乘积条件出发、跳到大量失配状态"的转移范数，且保留投影造成的振幅损失、绝不重新归一化。先把每个 Toffoli 门改写为关于乘积投影 (product projection) `@@M@@A@@` 的反射 `@@M@@I-2A@@`（控制位全为 1、目标位取 `@@M@@\ket-@@`），电路呈 `@@M@@U=(L_dR_d)\cdots(L_1R_1)L_0@@` 的规范形，且取逆后深度不变。第一步证深度 0：共轭一个乘积投影仍是乘积投影，失配数变成独立伯努利变量之和，用关于 `@@M@@2^K@@` 的 Markov 不等式得 `@@M@@2^{-r}@@` 型尾界。第二步剥层归纳：设投影只固定 `@@M@@k@@` 个比特，一层内至多 `@@M@@k@@` 个反射与它相遇，在投影两侧展开每个反射，得系数和 `@@M@@\le 9^k@@` 的"三投影乘积"项，再用深度 `@@M@@d-1@@` 的归纳假设，在三个因子之间插入两档中间失配截断，把每段跳变逐一压住。第三步克服展开代价随支撑指数增长的困难：把任意乘积投影写成第二个计数 `@@M@@D@@` 的 `@@M@@[D=0]@@`，用 Chebyshev 型多项式 `@@M@@p@@`（`@@M@@p(0)=1@@`、在正整数谱点上误差 `@@M@@\le e^{-N^a}@@`、度与加权系数和 `@@M@@\le e^{N^u}@@`）把 `@@M@@D@@` 的幂展开成至多 `@@M@@N^k@@` 个小支撑单项式。最巧妙的是算子次序：平方目标范数得 `@@M@@\|HQP\|^2=\|HQPQH\|@@`，只把最左的 `@@M@@Q@@` 替换为 `@@M@@p(C)@@`，残余误差落在 `@@M@@PQ@@` 上，经逆电路共轭后恰好变成"两个计数互换、阈值更高"的同一命题——于是先在更大阈值证 `@@M@@\cB_d(t,b)@@`，再倒推 `@@M@@\cB_d(s,t)@@`。尺度链 `@@M@@t_{i+1}=2t_i-s_i-3\eta@@` 经 `@@M@@O(1/(t-s))@@` 步把阈值推过 1（此时尾投影消失、命题平凡），自后向前逐级归约完成归纳。收官时令 `@@M@@B=W^\dagger OW@@`，输出零概率 `@@M@@p_0(x)@@` 的奇偶傅里叶系数恰是互补 Hadamard 乘积态 `@@M@@\ket{\xi_h},\ket{\xi_{\bar h}}@@` 间矩阵元的平均；这两态在全部 `@@M@@n@@` 个输入比特上失配，局部化迫使每个矩阵元 `@@M@@\le e^{-N^s}@@`（取 `@@M@@0<s<t<1/c@@` 使 `@@M@@N^t<n@@`），平均趋于零；而逐点正确率 `@@M@@\ge1/2+\varepsilon@@` 强迫该平均 `@@M@@\ge\varepsilon@@`，矛盾。

## 可信度与备注
主定理已通过 Lean 形式化验证（结果族 274）。姊妹篇《Regular trajectories, pruning and quantum parity》给出第二条独立证明：其走"正则轨迹＋剪枝"的状态依赖路线，本文则证一致的算子范数定理、不以任何轨迹假设为前提；两文各自完成多项式估计与奇偶转化，互不引用对方结构定理，构成交叉核验。多数函数、态制备等推论依赖 Xu–Li 与 Gretta–Gupta–Joshi 的归约。仍需留意 OpenAI 官方声明：未经形式化的结果可能存在问题，形式化覆盖之外的具体表述请以社区核验为准。

{% endraw %}
